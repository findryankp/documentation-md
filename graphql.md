# GraphQl, GORM, Viper
**Development by:** 
- Findryankp

```go
go mod init graphql
```

```go
go get -u gorm.io/gorm
go get -u gorm.io/driver/mysql
go get github.com/spf13/viper
go get github.com/99designs/gqlgen
go get github.com/99designs/gqlgen@v0.17.29
```

```go
go run github.com/99designs/gqlgen init
go mod tidy
```

* set your schema
example

```go
type Product {
  id: ID!
  name: String!
  price: Int!
}

type Query {
  products: [Product!]!
  product(id: ID!): Product!
}

input ProductInput {
  name: String!
  price: Int!
}

type Mutation {
  createProduct(input:ProductInput!): Product
}
```


```go
go run github.com/99designs/gqlgen@v0.17.29 generate
```