## Running the sample code

1. Start a first node:

    ```
    mvn compile exec:exec -DAPP_CONFIG=local1.conf
    ```

2. (Optional) Start another node with different ports:

    ```
    mvn compile exec:exec -DAPP_CONFIG=local2.conf
    ```

3. Check for service readiness

    ```
    curl http://localhost:9101/ready
    ```

## Start containers

```shell
❯ cd shopping-cart-service

❯ docker-compose up -d
Building with native build. Learn about native build in Compose here: https://docs.docker.com/go/compose-native-build/
Creating network "shopping-cart-service_default" with the default driver
Creating shopping-cart-service_kafka_1            ... done
Creating shopping-cart-service_postgres-db_1      ... done
Creating shopping-cart-service_zookeeper_1        ... done
Creating shopping-cart-service_postgres-db-test_1 ... done

❯ docker-compose exec -T postgres-db psql -U shopping-cart -t < ddl-scripts/create_tables.sql
CREATE TABLE
CREATE INDEX
CREATE TABLE
CREATE TABLE
CREATE TABLE
CREATE INDEX
```