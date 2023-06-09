# Microsserviços

## RabbitMQ: Dispatcher para os Proxies

Os Microsserviços Produtores(A, B, C, D, E, F, G, H) irão gerar mensagens para o Exchange que será responsável pela entrega das mesmas para o microsserviço Consumidor Log


### Log
```json
{
    "timestamp" : "31.01.2021 21.03:48.357",
    "level" : "INFO",
    "thread" : "main",
    "logger" : "com.alexgutjahr.jasonlog.JsonLogApplicationKt",
    "message" : "Starting JsonLogApplicationKt using Java 15.0.1 on vortex.fritz.box wit",
    "context" : "default"
}
```

### Dispatchers
Utilizando uma fila de prioridade para que logs acionaveis(Logs acionaveis são aqueles que você pode realmente usa-los) saiam primeiro da fila.
Como primeira proposta os logs acionaveis serão logs de erro, e os outros logs terão prioridade menor.

### Executar RabbitMQ
Para executar o container com o RabbitMQ é necessário ter o docker instalado e executar o seguinte comando:

```bash
    docker compose up -d # Inicializa os continers com base no arquivo docker-compose.yml
```

![RabbitMQ first version](/resources/rabbitmq_dispatchers.jpg)
