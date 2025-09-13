<p align="center">
    <img src="https://img.shields.io/badge/Redis-Study%20Repo-red?style=for-the-badge&logo=redis&logoColor=white" alt="Redis Study Badge" />
</p>
<p align="center">
  <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/redis/redis-original-wordmark.svg" alt="Redis Logo" width="60%" />
</p>
# 📕 Redis Study Repo

Welcome to my **Redis Study Repository**
This repo is dedicated to learning and experimenting with **Redis** — the blazing-fast in-memory data store.  

Here you’ll find:  
-  **Redis Basics** — keys, strings, hashes, lists, sets, sorted sets  
- **Performance Patterns** — caching, rate limiting, session storage  
- **Advanced Features** — pub/sub, streams, queues (BullMQ)  
-  **Integration** — practical examples of using Redis in a Node.js backend  

Redis is widely used for **caching, real-time apps, leaderboards, pub/sub systems, and distributed architecture**.  
This repo will grow with hands-on examples and study notes 

---
# Redis Basics
## Strings
`name - 'marwan'`
`color - 'red'`
`age - '30'`
- to set a key-value pair we use `SET`
- `set name marwan`
- `set name2 marwan mohamed ` - this is not acceptable
- `set name2 'marwan mohamed`
- to get a value with the key
- `get name`
- to delete we use `del`
- `del name2`
- to set multiple keys we use `mset`
- `mset name2 maro age 21 color red`
- to get multiple kesy we use`mget`
- `mget name2 age color`
- to get a range of chars we use `getrange key start end`
- `getrange name 0 3` - first 4 chars
- to set a range of chars we use `setrange offset string`
- `setrange name 2 abc`
- increase a number by 1 we use `incr key`
- `incr rating`
- decrease a number by 1 we use `decr key`
- `decr rating`
- increase a number by x we use `incrby key number`
- decrease a number by x we use `decrby key number`
## Sets
`names -> {'marwan','marwan','peach'}` - members must be unique
- to add a member in the set we use 'sadd key members'
- `SADD names marwan mohamed zein`
- to remove emembers in the set 'SREM'
- `SREM names marwan`
- to union sets uwe use `sunion`
- `SUNION names allnames`
- to check if an element is the set we use `sismember`
- `SISMEMBER names link`

## Lists
`names -> {'marwan','marawan','mohamed'` - members could repeat
- lists are impelemented as linkedlist data structure
- `LPUSH` -> push from left -->
- `RPUSH` -> push from right <---
- `LPOP orders 1` -> pops the first element from the left
- `LPOP orders 2` -> first 2
- `RPOP orders x` pops the first x elements from the right
- `LLEN` -> len of the list
- `LRANGE orders 0 1` -> get the first to2 elements (we can go from end with negative)
- `lpos orders sagat` -> get the position of the sagat member

## Hashes
- multiple types
- `HSET books:1 key:value`
- `HSET books:1 rating:8`
- `HGET books:1 rating` -> gets the rating property of the books hash
- `HGETALL books:1` -> get the property names amd the keys
- `HEXESISTS books:1 title` -> check if books hash has title property
- `HKEYS books:1` -> get all the keys of books:1 hash
- `HVALS books:1` -> get all the values of books:1 hash
- `HDEL books:1 author` -> delete the key author from books:1 hash
- `DEL books:1` -> delete the entire hash
---
# Performance Patterns
