## Requirement

- Go 1.21.xx

## set up

```bash
# int
# - go.modファイルが作成される
go mod init go-rest-api

# docker-compose 作成
- touch docker-compose.yml

# start db
docker compose up -d

# .env 作成
touch .env

# model user/task 作成
mkdir model
touch model/user.go
touch model/task.go

# db 作成
mkdir db
touch db/db.go

# migrate 作成
mkdir migrate
touch migrate/migrate.go

# run migrate
GO_ENV=dev go run migrate/migrate.go

# repository 作成
mkdir repository
touch repository/user_repository.go

# usecase 作成
mkdir usecase
touch usecase/user_usecase.go

# controller 作成
mkdir controller
touch controller/uer_controller.go

# router 作成
mkdir router
touch router/router.go

# サーバ起動
GO_ENV=dev go run main.go
```

## note

```bash
# remove db
docker compose rm -s -f -v

# パッケージインストール
# NOTE
# フォルダ内で「import '../path/...'」とかいた後にコマンド実行する
go mod tidy

```
