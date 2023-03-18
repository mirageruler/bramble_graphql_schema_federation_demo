# Running locally

There is a [docker-compose](./docker-compose.yaml) file that will run bramble and three [example](./examples) services.

```
docker-compose up
```

The gateway will then be hosted on `http://localhost:8082/query`, be sure to point a GraphQL client to this address.

```graphql
{
  randomGizmo {
    email
    id
    name
    rating
  }
}

If you have a look on the source code:
- The `gqlgen-service` service enriches the boundaries type Gizmo with `name` field
- The `graph-gophers-service` service enriches the boundaries type Gizmo with `email` field
- The `nodejs-service` service enriches the boundaries type Gizmo with `rating` field
- All three services provide the same `id` field for the boundaries type Gizmo

When trying the query above, the returned response data is gathered from those three services by the Bramble gateway.
```
