
## Server Caching Strategies
**Cache-Aside**
In this caching strategy, the cache is logically placed at the side and the application directly communicates with the cache and the database to know if the requested information is present or not. The cache is first checked by the application. If the information is found, it is marked as cache hit, and so, it is read and returned to the client. If the information is not present, it is marked as cache miss. The application queries the database for reading the data, returns the read data to the client, and then stores it in cache for future cache hits.

It works best for read-heavy workloads. If the cache server is down, the system still works by directly communicating with the database; though that is never a long-term solution in case of peak load that suddenly hits at times. The cache server requires to be fixed soon. The data model can be different in cache and that of the database.

**Write-Through Cache**

In this method, the information is first written to the cache before the main memory/database. The cache is logically in between the Application, through which the client interacts, and the database. Therefore, if a client requests for anything the application does not have to check in the cache for its availability since it is already there. It directly retrieves from the cache memory and serves the client.

On the downside, it increases the write latency; but if paired with  _**read-through cache**_ we get the guarantee of data consistency.

**3. Read-Through Cache**

In this method, the cache sits inline with the database. Whenever there is a cache miss (meaning, the requested data isn’t in the cache), the missing data is populated from the database and gets returned to the application, so that the client is served.

It works best for  _**read-heavy workloads**_  when the same set of information is requested several times. For instance, a news story that needs to be loaded over and over again by many people on different devices.

Its main disadvantage is, if the data is requested for the first time, it is always a  _**cache miss**_,  thereby loading it way too slowly than normal. The developers deal with it by issuing queries manually or by  _**write-through cache**_.

**Write-Back**

In this server caching strategy, the application writes the information to the cache that immediately acknowledges the changes, and after some delay, it writes back the data to the database. We can also call it  _**write-behind**_.

It is a good strategy for write-heavy workloads that improves the write performance. It can tolerate moderate database downtime and failures that take place at times. It works good with  _**read-through cache**_. If batching is supported, it can reduce the overall writes to the database, thereby decreasing the load and costs.

In most relational database storage engines, such as InnoDB, the write-back cache is enabled by default in which the queries are written to memory at first and then flushed to the main disk later. The major disadvantage is, if there is a cache failure, the data may get permanently lost.

**5. Write-Around**

In this case, the data is directly written in the database and only that data is stored into the cache which is read.

It can be combined with  _**read-through cache**_. It is a good choice in situations in which the data is written once and is read negligibly or never. For instance, when there is a need of real-time logs or chatroom messages. It can also be mixed with  _**cache-aside**_.
