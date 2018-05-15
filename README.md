# myDiamond

## Goal

Scrape diamond wholesalers (e.g. James Allen) and collect all diamond data. Run various analysis on the diamonds such as calculating import ratio's and calculating efficient frontier's for diamonds with given attributes. Use image processing to score diamonds based on their clarity diagrams. Also, generate scores based on these numbers to determine which diamonds have the best value. 

In addition, create a web app that allows the user to organize and chart the data as they wish.

## Process

### Step 1

<details>
  <summary><b>Planning</b></summary>
<p>
  <br/>
  <i>Created a software architecture diagram for myDiamond.</i>
  <ul>
    <li>Will use microservices architecture.</li>
    <li>3 data stores (2 NOSQL databases and 1 file store).</li>
    <li>ETL layer that runs weekly to load and perform analysis on data.</li>
    <ul>
      <li>Consisting of several processes which call various internal microservices</li>
      <li>Utilizes message queues as event triggers for processing in order to avoid bottlenecks</li>
    </ul>
    <li>REST API will serve data to client</li>
  </ul>


![Architecture Diagram](/myDiamond.png?raw=true "Optional Title")
</p>
</details>

