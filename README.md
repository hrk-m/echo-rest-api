# echo-rest-api

```
# create module
go mod init go-rest-api
# start db
docker compose up -d
# remove db
docker compose rm -s -f -v
# start app
GO_ENV=dev go run .
# run migrate
GO_ENV=dev go run migrate/migrate.go
```

## Architecture of REST API (Go/Echo) application

<img src="https://raw.githubusercontent.com/GomaGoma676/echo-rest-api/main/architecture.png">

## 教材

- https://www.udemy.com/course/echo-go-react-restapi/

## Udemy の教材の github

- バックエンド: https://github.com/GomaGoma676/echo-rest-api
- フロント: https://github.com/GomaGoma676/react-todo?tab=readme-ov-file

## 講座のファイル作成手順のメモ

- <a href='https://github.com/hrk-m/echo-rest-api/created_steps.md'>created_steps.md</a>
