# self learning rabbit-mq

## install rabbit-mq

### Docker

- docker pull:
```bash
docker pull rabbitmq:3
```

- docker run container

```bash
docker run -d --hostname 0.0.0.0 -p 5672:5672 --name rabbit rabbitmq:3
```

## run project
### hello
1. start send message:
```go
go run send/hello/send.go 
```
2. receive message: 
```go
go run receive/hello/receive.go
```

### work queue
1. Message default:
- start send message:
    ```go
    go run send/workQueue/new_task.go
    ```
- receive message: 
    ```go
    go run receive/workQueue/worker.go
    ```