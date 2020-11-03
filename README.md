# logspout-kafka
logspout kafka. use container.name as kafka.message.key

# usage

```
docker run --name="logspout-kafka" -d --restart=always -p 8080:80 -v /etc/localtime:/etc/localtime --volume=/var/run/docker.sock:/var/run/docker.sock -e KAFKA_TEMPLATE="{\"time\":\"{{.Time}}\",\"containername\":\"{{.Container.Name}}\",\"source\":\"{{.Source}}\",\"data\":\"{{.Data}}\"}"  registry.cn-hangzhou.aliyuncs.com/leapmotor_docker/iov:logspout-kafka kafka://IP:PORT?topic=docker_log_es_channel&brokers=IP2:PORT,IP3:PORT
```
