### Steps
* Instalar as dependências
```
npm install
```
* Copiar o arquivo `.env-example` e alterar para `.env`

* Fazer build das imagens com docker-compose
```
docker-compose build
```
* Subindo aplicações com docker-compose
```
docker-compose up -d
```
* Fazer alguns requests na app2 e validar se os logs estão aparecendo no terminal.
```
watch "curl http://localhost:3003/get"
docker-compose logs -f
```
* Criar index no kibana (http://localhost:5601) com pattern "logstash" e analisar os logs da aplicação "app2"
* Remover todos os recursos criados
```
docker-compose down
```

| Nome                | Descrição                                       | Valor                   | Obrigatório      |
|---------------------|-------------------------------------------------|-------------------------|------------------|
|NEW_RELIC_LICENSE_KEY|Licença do New Relic                             |                         |:white_check_mark:|
|APP1_PORT            |Porta da aplicação 1                             |3000                     |:white_check_mark:|
|APP1_HOSTNAME        |Host da aplicação 1                              |localhost                |:white_check_mark:|
|APP1_IS_RETURN_200   |Decide se a app1 responde 200 ou não             |1                        |:white_check_mark:|
|APP2_PORT            |Porta da aplicação 2                             |3001                     |:white_check_mark:|
|APP2_NGINX_URL       |Host do nginx que bate na aplicação 2            |http://localhost:80      |:white_check_mark:|
|APP2_REDIS_HOST      |Host do redis na aplicação 2                     |localhost                |:white_check_mark:|
|APP2_REDIS_PORT      |Porta do redis na aplicação 2                    |6379                     |:white_check_mark:|
|APP2_LOGSTASH_HOST   |Host do Logstash da app 2                        |localhost                |:white_check_mark:|
|APP2_LOGSTASH_PORT   |Porta do Logstash da app 2                       |5000                     |:white_check_mark:|
|ELASTICSEARCH_URL    |Url do elasticsearch                             |http://elasticsearch:9200|:white_check_mark:|

Mantenha o arquivo `.env-example` e a tabela de variáveis sempre atualizada.
![app1-app2-newrelic](https://user-images.githubusercontent.com/49416086/187796232-d6d8194b-4975-49c3-a3b6-38a6fabb99c0.png)

![grafico](https://user-images.githubusercontent.com/49416086/187796263-b10a07ca-3c25-4513-9cee-910febeae0c2.png)
