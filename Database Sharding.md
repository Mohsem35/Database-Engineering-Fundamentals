Database sharding is a process of segmenting the data into partitions that are spread on multiple database instanc. This is essentially to speed up query and scale the system


### Database Sharding

As the size of the database table increases, indexing will also increase, causing queries to become slower and utilize more CPU and RAM.

Partition your table. Row based partition on certain field, certain column called Partition

Split 1 million rows table into 5 database instances... Same schema

Which database server is 5FTOJ in? How do you know that? 

Consistent Cashing

But there is just a function and you can always find out it's not really hard or I can build it on function to determine how to consistently hash this input(query) to a server and this case.

<img width="550" alt="Screenshot 2024-04-15 at 12 34 25 AM" src="https://github.com/Mohsem35/Database-Engineering-Fundamentals/assets/58659448/e1a55aa7-e468-41d1-9e2e-18bc8b4b4f7c">

Once you find out which server you want to connect to, you connect to only that server and you send your query to only that server.

You don't want to send your query to all databases. You want to connect to the right database server. 

<img width="550" alt="Screenshot 2024-04-15 at 12 34 49 AM" src="https://github.com/Mohsem35/Database-Engineering-Fundamentals/assets/58659448/efa4c6e5-7ac0-4e38-bc82-f685b4995c2b">


### Consistent Hashing

The idea of consistent hashing, you take input or a string or any user provided piece of data that you want to query on and you want to know which database to query on, essentially that hash going to give you back that instance somehow.

Hash("Input1") -> 5432 database instance 

Hash("Input2") -> 5433 database instance 

Hash("Input3") -> 5434 database instance 

You might get another like I say again, if you submit and "input2" again, you can always get the same output.

How does actually this work?

One implementation would be just, hey, make this input into some sort

```
num("Input2") % 3
```

Convert all these ASCII character codes into binary, then convert them back to decimal, and finally perform a modulo operation. Right, which is the remainder of three because I have three nodes.



That does consistent hashing.

Essentially, they get an input. Give me the port number back so that I can connect to my desired database. 

<img width="505" alt="Screenshot 2024-04-15 at 12 58 18 AM" src="https://github.com/Mohsem35/Database-Engineering-Fundamentals/assets/58659448/7a1e55ad-4801-4a62-8a52-871c603e2ffe">

suppose, input2 value = 10, then the modulus will be 1

calculation: 1 + 5432(1st database instance) = 5433(2nd database instance)

That is called the hash rank as well. So this is like almost like a ring. Cassandra, use this all the time with the shards that they have.


So every time you have an input, I know which which database to hit.

