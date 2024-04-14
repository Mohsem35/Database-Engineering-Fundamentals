Database sharding is a process of segmenting the data into partitions that are spread on multiple database instanc. This is essentially to speed up query and scale the system


#### Database Sharding

As the size of the database table increases, indexing will also increase, causing queries to become slower and utilize more CPU and RAM.

Partition your table. Row based partition on certain field, certain column called Partition

Split 1 million rows table into 5 database instances... Same schema

Which database server is 5FTOJ in? How do you know that? 

Consistent Cashing

But there is just a function and you can always find out it's not really hard or I can build it on function to determine how to consistently hash this input(query) to a server and this case.

Once you find out which server you want to connect to, you connect to only that server and you send your query to only that server.

You don't want to send your query to all databases. You want to connect to the right database server. 