# Replica-MongoDB 
Assignment 2 Replica MongoDB

mkdir cm_replica_demo<br>
cd cm_replica_demo<br>
mkdir r1<br>
mkdir r2<br>
mkdir r3<br>

mongod --replSet cmpos --logpath ./r1.log --dbpath ./r1 --port 27020 &<br>
mongod --replSet cmpos --logpath ./r2.log --dbpath ./r2 --port 27021 &<br>
mongod --replSet cmpos --logpath ./r3.log --dbpath ./r3 --port 27022 &<br>


mongo --port 27020

config = {_id: "cmpos", members:[
 {_id: 0, host: "localhost:27020
 {_id: 1, host: "localhost:27021,
 {_id: 2, host: "localhost:27021"}]
};

rs.initiate(config);<br>
rs.status();<br>

mongo --host cmpos/localhost:27020,localhost:27021,localhost:27022<br>
use courses<br>
db.getCollection('test').find({})<br>
