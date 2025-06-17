# log-server
Vector + Clickhouse + Granfana Combination with Docker compose


## access Clickhouse
`docker exec -it clickhouse clickhouse-client`

create table in Clickhouse for getting log from Vector.
```sql
CREATE TABLE spring_logs (
    timestamp DateTime,
    level String,
    thread String,
    logger String,
    message String,
    stacktrace String
) ENGINE = MergeTree()
ORDER BY timestamp;
```
