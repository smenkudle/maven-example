# Todo and Hello World Rest APIs Connecting to H2 In memory database running on port 5000

## Hello World Resource

- http://localhost:5000/hello-world

```txt
Hello World
```

- http://localhost:5000/hello-world-bean

```json
{"message":"Hello World - Changed"}
```

- http://localhost:5000/hello-world/path-variable/smenkudle

```json
{"message":"Hello World, smenkudle"}
```


## Todo Resource

- GET - http://localhost:5000/jpa/users/smenkudle/todos

```
[
  {
    "id": 10001,
    "username": "smenkudle",
    "description": "Learn JPA",
    "targetDate": "2019-06-27",
    "done": true
  }
  {
    "id": 10002,
    "username": "smenkudle",
    "description": "Learn to Drive a Plane",
    "targetDate": "2030-01-01",
    "done": false
  }
]
```

#### Retrieve a specific todo

- GET - http://localhost:5000/jpa/users/smenkudle/todos/10001

```
{
    "id": 10001,
    "username": "smenkudle",
    "description": "Learn JPA",
    "targetDate": "2019-06-27",
    "done": true
 }
```

#### Creating a new todo



- POST to http://localhost:5000/jpa/users/smenkudle/todos with BODY of Request given below

```
{
  "username": "smenkudle",
  "description": "Learn to Drive a Car",
  "targetDate": "2023-01-01",
  "done": false
}
```

#### Updating an existing todo

- PUT Request to http://localhost:5000/jpa/users/smenkudle/todos/10001 with BODY of Request given below

```
{
  "id": 10001,
  "username": "smenkudle",
  "description": "Learn to Drive a Car",
  "targetDate": "2045-01-01",
  "done": false
}
```

#### Delete todo

- DELETE to http://localhost:5000/jpa/users/smenkudle/todos/10001


## H2 Console

- http://localhost:5000/h2-console
- Use `jdbc:h2:mem:testdb` as JDBC URL 