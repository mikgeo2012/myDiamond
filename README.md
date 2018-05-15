# myDiamond

## Goal

Aggregate and analyze diamond data from various wholesalers and allow users to organize and transform data. Calculate various measurements via known metrics and determine diamond clarity based on GIA clarity diagram. Score and rank diamonds in a group (similar attributes) factoring in price and measurements calculated.

Implement a performant, scalable ETL solution for diamond data.

The entire app will be cloud hosted in order dynamically scale depending on load.

## Design & Architecture

### Application Architecture

- Use microservices architecture to implement each task with the best tools and allow for the app to dynamically scale as needed and reduce bottlenecks while guaranteeing availability for users.
  - Containerize the application with docker and kubernetes.
  - Host in the cloud.
  - Golang for concurrency and easy deployment and scaling in the cloud.
  - Python for machine learning, data analysis and image processing.
  - Angular to serve a dynamic front-end.
- Employ event-driven architecture for the ETL solution to coordinate between several microservices working with several datastores.
  - NoSQL key-value store DB for diamond data because of large weekly writes and scaling read requests from web server
  - Cloud file store to temporarily hold documents and images
  - Message queue to trigger events and pass information while keeping the microservices decoupled  
<br />

<details>
  <summary>Diagram</summary>
  <p>
    <img src="/application_architecture.png?raw=true" alt="Mountain View">
  </p>
</details>

