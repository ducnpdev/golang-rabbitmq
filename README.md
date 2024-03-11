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
