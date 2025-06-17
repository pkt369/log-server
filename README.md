# log-server
Vector + Clickhouse + Granfana Combination with Docker compose


## access Clickhouse
`docker exec -it clickhouse clickhouse-client`

create table in Clickhouse for getting log from Vector.
```sql
CREATE TABLE spring_logs (
    timestamp DateTime,
    level String,
    profile String,
    thread String,
    logger String,
    message String,
    stack_trace String
) ENGINE = MergeTree()
ORDER BY timestamp;
```

## create .env file
You can see ${CLICKHOUSE_PASSWORD} in docker compose file.
It means I'll use this variable from env file.

```env
CLICKHOUSE_PASSWORD=my_pass_word
```