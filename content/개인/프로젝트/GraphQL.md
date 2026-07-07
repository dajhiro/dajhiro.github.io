# GraphQL
A GraphQL is
- a **query language** for your API
- a **server-side runtime** for executing quries 

Properties
- A type system
- GraphQL specification
- it is backed by existing code and data

## Describe API with a type system
A GraphQL service is created by
- defining types and their fields
- writing a function for each field

### Definition
types
```ts
type Query {
  me: User
}

type User {
  name: string
}
```

functions
```ts
function resolveQueryMe(_parent, _args, context, _info) {
  return context.request.auth.user;
}

function resolveUserName(user, _args, context, _info {
  return context.db.getUserFullName(user.id);
}
```

## Query 
Query
```
{
  me {
    name
  }
}
```

⇒ JSON
```json
{
  "data": {
    "me": {
	  "name": "Luke Skywalker"
    }
  }
}
```

---
## Keywords
- [[DataLoader]]
- [[Resolver]]

---
## REST API의 한계
Over-fetching
- I want to get `[user]/name` but I need to request `/user/[user]`

Under-fetching
- I want to get
	- `[user]/name`
	- `[user]/post`
	- `[user]/comment`
- but I need to request 3 times

Version Management

...










