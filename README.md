# Commands:

1. **Run portainer**
```
docker volume create portainer_data

docker run -d -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer
```
2. **Run Apache Cassandra**
```
docker-compose up -d
```
3. **Execute query**
```
CREATE KEYSPACE mykeyspace
WITH replication = {
	'class' : 'NetworkTopologyStrategy',
	'datacenter1' : 1,
	'datacenter2' : 1
};

CREATE TABLE mykeyspace.mytable (
	id int primary key,
	name text
);
```
or
```
CREATE KEYSPACE mykeyspace WITH replication = { 'class' : 'NetworkTopologyStrategy', 'datacenter1' : 1, 'datacenter2' : 1 };

CREATE TABLE mykeyspace.mytable (id int primary key, name text);
```