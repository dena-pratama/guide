# General Convention

## Naming

### Singular Form

- Use singular form for variables, functions, table, atau endpoints.

    /user, instead of /users
    db.user, instead of db.users
    user(), instead of users()

- Whenever possible, use a single word for variables, functions, table, atau endpoint.

    /user, instead of /userList
    db.user, instead of db.userList
    user(), instead of userList()

- If more than one word is needed, then use the following pattern:

    [grouping] [parent] [child] [SIzeAgeShapeColorOriginMaterialPurpose]

    i.e.
    URL_API
    URL_BASE
    URL_HOST

### Order

- Use alphabetical order for variables, functions, table, or endpoints.

### Comfort

- Use word that easy to understand and in a language that is more comfortable for you to use.
- if it is decided to use a certain language , then you should pay attention to the language's grammar and syntax.

### Cases

- Use camelCase for variables, function, table, or endpoints.
- Use PascalCase for class names, interface, or enum and for things that are already standarized to use PascalCase. For example: 
    - React Components.
    - Golang Exported functions.
- Use kebab-case for filenames and endpoints.
- Use snake-case for languages that exclusively use snake-case

# API

### Endpoints

- Use kebab-case for endpoints. 

    /user-friend

- use the following pattern for endpoints:
    - GET     /[entity-name]
    - GET     /[entity-name]/:id
    - POST    /[entity-name]
    - PATCH   /[entity-name]/:id
    - PUT     /[entity-name]/:id
    - DELETE  /[entity-name]/:id
- Don't over complicate your endpoints.

    /[entity#1]/:param/[entity#2]/:param/[entity#3]/:param

- Don't add any prefix ('/api') to your api, to avoid redundancy.

### Versionless

- should not have an explicit version written in the function name.

    func GetUserV1() // wrong
    func GetUser() // right

### Separation

Shall there be major version bump, then the API should be seperated into an entirely new service.

core api (v1) - udin
/order
/transaction

core api (v2) - amir
/order
/transaction

/v1/transaction -> udin /transaction
/v2/transaction -> amir /transaction