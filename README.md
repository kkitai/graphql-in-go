# graphql-in-go

## Run
```
$ go generate ./...
$ go run server.go
```

## The practice of GraphQL in go

* list all types

```
{
  __schema {
    types {
      name
      kind
      description
      fields {
        name
        type {
          name
          kind
          ofType {
            name
            kind
          }
        }
      }
      inputFields {
        name
        description
        defaultValue
      }
    }
  }
}
```

* create todo
```
mutation {
  createTodo(input: { text: "todo", userId: "1" }) {
    user {
      id
    }
    text
    done
  }
}

```

* find todos
```
query {
  todos {
    text
    done
    user {
      name
    }
  }
}
```
