# myDiamond

## Goal

Aggregate and analyze diamond data from various wholesalers and allow users to organize and transform data. Calculate various measurements via known metrics and determine diamond clarity based on GIA clarity diagram. Score and rank diamonds in a group (similar attributes) factoring in price and measurements calculated.

Implement a performant, scalable ETL solution for diamond data.

The entire app will be cloud hosted in order dynamically scale depending on load.

***

## Design & Architecture

### Application Architecture

- *Use microservices architecture to implement each task with the best tools and allow for the app to dynamically scale as needed and reduce bottlenecks while guaranteeing availability for users.*
  - Containerize the application with docker and kubernetes.
  - Host in the cloud.
  - Golang for concurrency and easy deployment and scaling in the cloud.
  - Python for machine learning, data analysis and image processing.
  - Angular to serve a dynamic front-end.
  <br>
- *Employ event-driven architecture for the ETL solution to coordinate between several microservices working with several datastores.*
  - NoSQL key-value store DB for diamond data because of large weekly writes and scaling read requests from web server
  - Cloud file store to temporarily hold documents and images
  - Message queue to trigger events and pass information while keeping the microservices decoupled  

<details>
  <summary><b>Diagram<b></summary>
  <p>
    <img src="/app_architecture.png?raw=true" alt="Mountain View">
    </p>
</details>

    
### ETL Solution

- *Run in weekly in the background to not interrupt user experience while still keeping data relevant.*
  - Scrape diamond wholesalers (e.g. James Allen) for GIA certificate.
  - Update price / remove sold from existing diamonds
  - Extract GIA number from certificate and compile data / store clarity diagram from [GIA](www.gia.edu).
  - Perform image analysis on clarity diagram to give a clarity score
  - Calculate metrics on new diamonds
