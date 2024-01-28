---
{"dg-publish":true,"permalink":"/benchmark/"}
---


did a simple benchmark between local postgres, sqlite and mysql using prisma orm in nodejs
- these aren't batch write
- for the non-local, the db location is in NY, 300 ms ping 
- as for the local:
	- postgres was using this [[compose\|compose script]]

```
MySQL with uuid

Seeding 20 users in 20.446s

Read 20 users in 4.964s

Seeding 20 users in 20.659s

Read 20 users in 4.976s

  

POSTGRES with uuid

Seeding 20 users in 5.652s

Read 20 users in 4.451s

Seeding 20 users in 6.348s

Read 20 users in 4.999s

Seeding 20 users in 6.344s

Read 20 users in 4.925s

  

POSTGRES with cuid

Seeding 20 users in 6.103s

Read 20 users in 4.816s

Seeding 20 users in 6.022s

Read 20 users in 4.727s

Seeding 20 users in 6.005s

Read 20 users in 4.705s

  

LOCAL SQLITE

Seeding 20 users in 0.115s

Read 20 users in 0.023s

Seeding 20 users in 0.141s

Read 20 users in 0.024s

Seeding 20 users in 0.131s

Read 20 users in 0.025s

Seeding 20 users in 0.123s

Read 20 users in 0.023s

  

LOCAL POSTGRES

Seeding 10000 users in 22.282s

Read 10000 users in 22.645s

Seeding 10000 users in 19.416s

Read 10000 users in 22.05s

  

LOCAL POSTGRES with INDEX

Seeding 10000 users in 22.143s

Read 10000 users in 14.039s

  

LOCAL SQLITE with INDEX

Seeding 10000 users in 19.085s

Read 10000 users in 14.513s
```

Interestingly enough, postgres is the winner... yes I'm biased

Didn't check mongodb because
- postgres on docker is 140MB
- sqlite (pocketbase) on docker is 75MB
- mongodb on docker is 750MB