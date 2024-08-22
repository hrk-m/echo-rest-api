## Architecture of REST API (Go/Echo) application

<img src="https://raw.githubusercontent.com/GomaGoma676/echo-rest-api/main/architecture.png">

## 教材

- https://www.udemy.com/course/echo-go-react-restapi/

## Udemy の教材の github

- バックエンド: https://github.com/GomaGoma676/echo-rest-api
- フロント: https://github.com/GomaGoma676/react-todo?tab=readme-ov-file

## 講座のファイル作成手順のメモ

- <a href='https://github.com/hrk-m/echo-rest-api/blob/main/created_steps.md'>created_steps.md</a>

# echo-rest-api

## setup

- start db

```
docker compose up -d
```

- run migrate

```
GO_ENV=dev go run migrate/migrate.go
```

- data insert

```
 PGPASSWORD=pass psql -U root -d echo-rest-api-db -h localhost -p 5434 -f users.sql
```

- start app

```
GO_ENV=dev go run .
```

## API

postman で確認したい場合は以下を import してください。
echo-rest-api.postman_collection.json

- sample

```
curl -i -c cookies.txt -X GET http://localhost:8080/csrf \
     -H "Content-Type: application/json"

{"csrf_token":"ug3ZaTsbck9I6t1jPQIS0bOOEPDG1x6Y"}
```

```
curl -i -b cookies.txt -X POST http://localhost:8080/signup \
     -H "Content-Type: application/json" \
     -H "X-CSRF-TOKEN:ug3ZaTsbck9I6t1jPQIS0bOOEPDG1x6Y" \
     -d '{"email": "test.user01@example.com", "password": "password"}'

{"id":1,"email":"test.user@example.com"}
```

```
curl -i -b cookies.txt -X POST http://localhost:8080/login \
    -H "Content-Type: application/json" \
    -H "X-CSRF-TOKEN:ug3ZaTsbck9I6t1jPQIS0bOOEPDG1x6Y" \
    -d '{"email": "test.user01@example.com", "password": "password"}'
```

```
curl -i -b cookies.txt -X POST http://localhost:8080/tasks \
     -H "Content-Type: application/json" \
     -H "X-CSRF-TOKEN:ug3ZaTsbck9I6t1jPQIS0bOOEPDG1x6Y" \
     -d '{"title": "task"}'
```

```
curl -i -b cookies.txt -X GET http://localhost:8080/tasks \
     -H "Content-Type: application/json" \
     -H "X-CSRF-TOKEN:ug3ZaTsbck9I6t1jPQIS0bOOEPDG1x6Y"
```
