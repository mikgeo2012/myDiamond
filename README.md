# myDiamond

##Step 1

###Planing

**Created a software architecture diagram for myDiamond.**
- Will use microservices architecture.
- 3 data stores (2 NOSQL databases and 1 file store).
- ETL layer that runs weekly to load and perform analysis on data.
-   Consisting of several processes which call various internal microservices
-   Utilizes message queues as event triggers for processing in order to avoid bottlenecks
- REST API will serve data to client


![Architecture Diagram](/myDiamond.png?raw=true "Optional Title")
