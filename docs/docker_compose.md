# Docker Compose

Chaves muito utilizadas:

- version: versão do Compose;
- services: Containers/serviços que vão rodar nessa aplicação;
- volumes: Possível adição de volumes;
- env_file: Arquivo de configuração (variáveis de ambiente)

## Comandos

Rodando o Compose:

```
$ docker compose up
```

ou 

```
$ docker-compose up
```

Rodar Compose em background (utilizar a flag `-d`):

```
$ docker-compose up
```

Parando o Compose:

```
$ docker-compose down
```

Verificando o que tem no compose:

```
$ docker-compose ps
```