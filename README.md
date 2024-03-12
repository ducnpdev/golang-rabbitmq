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

### pub/sub
1. Message default:
- start send message:
    ```go
    go run send/pubsub/emit_log.go
    ```
    or
    ```go
    go run send/pubsub/emit_log.go 123
    ```
- receive message: 
    ```go
    go run receive/pubsub/receive_logs.go
    ```

### routing
- start send message:
    ```go
    go run send/pubsub/emit_log.go
    ```
    default send message routing key `info`
    or 
    ```go
    go run send/pubsub/emit_log.go error
    ```
    send message routing key `error`
- receive message: 
    ```go
    go run receive/routing/receive_logs_direct.go info // routing info
    go run receive/routing/receive_logs_direct.go error // routing error 
    go run receive/routing/receive_logs_direct.go debug // routing debug 
    go run receive/routing/receive_logs_direct.go 123123 // routing 123123
    ```

### topic

- start send message:
    ```go
    go run send/topic/emit_log_topic.go "kern.critical" "A critical kernel error"
    ```
- receive message: 
    ```go
    go run receive/topic/receive_logs_topic.go "#" // To receive all the logs:
    go run receive/topic/receive_logs_topic.go "kern.*" // To receive all logs from the facility "kern":
    go run receive/topic/receive_logs_topic.go "*.critical" // Or if you want to hear only about "critical" logs:
    go run receive/topic/receive_logs_topic.go "kern.*" "*.critical" // You can create multiple bindings:
    ```

## contacts:
- facebook: https://www.facebook.com/phucducdev/
- zalo: +84335280715
- telegram: @DucNPh
- mail: ducnp09081998@gmail.com