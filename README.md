## Getting Started with Hasura Todo API

# todo API

### The GraphQL todo API

All the todo setup (CRUD) you'll ever need in one place, easily accessible through a modern GraphQL API.

## Try it Now!

[https://hasura-todo-api.hasura.app/v1/graphql](https://hasura-todo-api.hasura.app/v1/graphql)

Before any `query` to go through, you need to authenticate. Check [here](https://nigeriancoder.hashnode.dev/) for the proccess, or follow the blog to build something similar. it is being explain step by step with greate details and links where neended.

Hit the following URL with a `query` request like below

```
{
  todos {
    id
    title
    is_public
    is_completed
    user {
      name
    }
  }
}
```

you will receive the following output

```
{
  "data": {
    "todos": [
      {
        "id": "e0b5b675-5c62-4230-9710-ebe924648445",
        "title": "todo two",
        "is_public": false,
        "is_completed": false,
        "user": {
          "name": "user two"
        }
      },
      {
        "id": "4b3957b7-5177-4033-aa66-7ab11f1f9f91",
        "title": "todo three",
        "is_public": true,
        "is_completed": false,
        "user": {
          "name": "user two"
        }
      },
      {
        "id": "93d45a3d-262c-46bb-bc6e-a78e18606395",
        "title": "todo one",
        "is_public": true,
        "is_completed": true,
        "user": {
          "name": "user two"
        }
      },
      {
        "id": "a896db16-bfca-4733-a705-9cb431281948",
        "title": "todo two",
        "is_public": true,
        "is_completed": false,
        "user": null
      }
    ]
  }
}
```

You see **_user two_** because I'm logged in as **_user two,_** if you go through the output very well, you will find out that some users are **_null_** that is bacause the **_todo_** is public. **_Public_** todos are accessible to all the **_users_** not only the owners, but **_private_** is only accessible to the owner only.

As a **_user,_** you can `query,` `mutate` and `subscribe` to your **_data_** and **_todos_** (as shown above).

```
{
	users {
    id
    name
    email
    created_at
    updated_at
  }
}
```

See the result below.

```
{
  "data": {
    "users": [
      {
        "id": "auth0|6236654b647a36006ba3abd3",
        "name": "user two",
        "email": "user@two.com",
        "created_at": "2022-03-20T13:17:56.495124+00:00",
        "updated_at": "2022-03-20T13:17:56.495124+00:00"
      }
    ]
  }
}
```

can `query` with the **\*todo** together

```
{
	users {
    id
    name
    email
    created_at
    updated_at
    todos {
      id
      title
      is_completed
      is_public
      user_id
      created_at
      updated_at
    }
  }
}
```

see the result below.

```
{
  "data": {
    "users": [
      {
        "id": "auth0|6236654b647a36006ba3abd3",
        "name": "user two",
        "email": "user@two.com",
        "created_at": "2022-03-20T13:17:56.495124+00:00",
        "updated_at": "2022-03-20T13:17:56.495124+00:00",
        "todos": [
          {
            "id": "e0b5b675-5c62-4230-9710-ebe924648445",
            "title": "todo two",
            "is_completed": false,
            "is_public": false,
            "user_id": "auth0|6236654b647a36006ba3abd3",
            "created_at": "2022-03-20T13:18:11.743855+00:00",
            "updated_at": "2022-03-20T13:18:11.743855+00:00"
          },
          {
            "id": "4b3957b7-5177-4033-aa66-7ab11f1f9f91",
            "title": "todo three",
            "is_completed": false,
            "is_public": true,
            "user_id": "auth0|6236654b647a36006ba3abd3",
            "created_at": "2022-03-20T13:18:27.338045+00:00",
            "updated_at": "2022-03-20T13:18:27.338045+00:00"
          },
          {
            "id": "93d45a3d-262c-46bb-bc6e-a78e18606395",
            "title": "todo one",
            "is_completed": true,
            "is_public": true,
            "user_id": "auth0|6236654b647a36006ba3abd3",
            "created_at": "2022-03-20T13:18:48.607927+00:00",
            "updated_at": "2022-03-20T13:18:48.607927+00:00"
          }
        ]
      }
    ]
  }
}
```

To start exploring the **_API_** visit the this [blog](https://nigeriancoder.hashnode.dev), see how it started, how it is going and where it is ending :)

### How to USE the API

All you need is the hasura graphql link which is given above, then the Auth0 link for Authentication and authorization, for that, I can't give that here but you can message me on Twitter [@mxhdiqaim](https://twitter.com/mxhdiqaim) or IG [@mxhdiqaim](https://instagram.com/mxhdiqaim) for that.
