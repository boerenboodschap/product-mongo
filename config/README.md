# Sharded mongo cluster instructions

## start a config server

```command
mongod --config ./conf/mongod.conf
```

## initiate the replica set

Go into the mongo shell:

```command
mongosh --port 27019
```

in that shell run this command:

```command
rs.initiate(
  {
    _id: "configserver",
    configsvr: true,
    members: [
      { _id : 0, host : "localhost:27019" }
    ]
  }
)
```

## create a shard

```command
mongod --config ./config/shard/mongod.conf
```

```command
mongosh --port 27018
```

```command
rs.initiate(
  {
    _id : "shardserver2",
    members: [
      { _id : 0, host : "localhost:34000" }
    ]
  }
)
```

## Start a mongos for the Sharded Cluster

```command
mongos --config ./config/mongos/mongos.conf
```

Connect to the sharded cluster

```command
mongosh --host localhost --port 27017
```

## Add Shards to the Cluster

```command
sh.addShard( "shardserver/localhost:27018")
```

## Shard the collection with shard key hashes

```command
sh.shardCollection("Product.Products", { shardKey : "hashed" } )
```
