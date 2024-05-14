# Base de Datos NoSQL

En este apartado se encuentran ejemplos de implementacion de distintas Bases de Datos NoSQL, materia dictada en la UTN FRBA.

Los tipos de bases tratados son:
* Key-Value
* Column-Family
* Document
* Graphs

## Modelado de datos
En la primer parte se vio los conceptos, caracteristicas y como **modelar** los datos en cada una de ellas.

En particular, las BDs utilizadas fueron: [Redis](https://redis.io/es/), [Cassandra](https://cassandra.apache.org/_/index.html), [MongoDB](https://www.mongodb.com/es) y [Neo4J](https://neo4j.com/) por ser las mas utilizadas en su tipo (no se tuvo en cuentas las BDs en la nube como DynamoDB, Big Table, etc)

*En este [link](https://db-engines.com/en/ranking) se puede ver el ranking de la bases mas utilizadas*

#### Ejecución de las BDs
Como los ejemplos son a fines prácticos y para evitar tener que instalar cada BD, se opto por utilizar los contenedores de Docker.

A continuación se muestra los comandos de ejecución y conexión a la BD:

* Redis
```bash
docker run --rm --name db-redis -p 6379:6379 redis

docker exec -it db-redis redis-cli
```

* Cassandra
```bash
docker run --rm --name db-cassandra cassandra

docker exec -it db-cassandra cqlsh
```

* MongoDB
```bash
docker run --rm --name db-mongo -p 27017:27017 mongodb/mongodb-community-server # or use mongo image

docker exec -it db-mongo mongosh
```

* Neo4J
```bash
docker run --rm --name db-neo4j -p 7474:7474 -p 7687:7687 neo4j

# Open Neo4J' interface at http://localhost:7474/
```

Los ejemplos prácticos de modelado de datos se encuentran en: [modelado_de_datos](./modelado_de_datos)

## Distribucion de datos
En esta segunda parte se ven caracteristicas cross de las BDs No SQL, como la distribucion de datos en nodos que conforman un cluster. En particular, se utilizan los conceptos **Replicacion** y **Particionamiento (Sharding)** de datos
