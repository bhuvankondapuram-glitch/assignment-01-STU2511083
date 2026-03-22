## Storage Systems

In this architecture, different storage systems are used to meet specific requirements. A relational OLTP database such as PostgreSQL is used to store patient records and hospital transactions, ensuring strong consistency and reliability. A data lake is used to store raw and semi-structured data from multiple sources, including ICU streaming data and historical medical records, providing scalability and flexibility. A data warehouse is used for analytical processing and generating monthly reports such as bed occupancy and department costs, as it supports efficient aggregation queries. A vector database is used to store embeddings of patient records, enabling semantic search for doctor queries. For real-time ICU data, a streaming system is used to ingest high-frequency data efficiently.

## OLTP vs OLAP Boundary

The OLTP system handles real-time transactional data such as patient records, admissions, and updates. It ensures ACID properties and is optimized for fast insert and update operations. The OLAP system begins when data is extracted from the OLTP system and loaded into the data lake and data warehouse. The data warehouse is used for analytical queries, reporting, and business intelligence. Therefore, the boundary between OLTP and OLAP lies at the point where operational data is moved into analytical systems for reporting and analysis.

## Trade-offs

A key trade-off in this architecture is between consistency and scalability. OLTP systems provide strong consistency but are not suitable for large-scale analytics, while data lakes and streaming systems offer high scalability but may sacrifice consistency. To address this, critical patient data is maintained in the OLTP system to ensure accuracy, while large-scale analytical and AI workloads are handled by the data lake and warehouse. Data validation and synchronization processes can be used to ensure consistency across systems.
