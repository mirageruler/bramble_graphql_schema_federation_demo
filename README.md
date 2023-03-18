# Running locally

There is a [docker-compose](./docker-compose.yaml) file that will run bramble and three [example](./examples) services.

```
docker-compose up
```

The gateway will then be hosted on `http://localhost:8082/query`, be sure to point a GraphQL client to this address.

```graphql
{
  randomFoo {
    nodejs
    graphGophers
    gqlgen
  }
}
```