# Comandos do Docker


## Comando `ps`: Listar containers

Listar container que estão executando: 

```
$ docker ps
```

Listar todos os containers que executaram:

```
$ docker ps -a
```

## Comando `run`: Rodar um container

Rodar um container:

```
$ docker run <nome_imagem>
```

Rodar um container no modo iterativo:

```
$ docker run -it <nome_imagem>
```

Rodando container em background (detached):

```
$ docker run -d <nome_imagem>
```

Expondo uma porta do container:

```
$ docker run -d -p <porta_pc>:<porta_container> <nome_imagem>
```

Definindo um nome para um container:

```
$ docker run -d --name <nome_container> <nome_imagem>
```

Remover container após a parada:

```
$ docker run --rm <container>
```

Remover container após a parada:

```
$ docker run --rm <container>
```

## Comando `stop`: Parar containers


Para um container:

```
$ docker stop <id ou nome_container>
```

## Comando `start`: Reiniciar containers

Reiniciar um container:

```
$ docker start <id ou nome_container>
```

Comando start interativo:

```
$ docker start -it <id ou nome_container>
```

## Comando `rm`: Remover um container

Remover um container parado:

```
$ docker rm <id ou nome_container>
```

Remover um container que está rodando:

```
$ docker rm <id ou nome_container> -f
```

## Comando `build`: Criar imagen

Criar uma imagem a partir do Dockerfile:

```
$ docker build <diretório da imagem>
```

Criar imagem com um nome:

```
$ docker build -t <nome> .
```

ou

```
$ docker build -t <nome>:<tag> .
```

## Comando `image`: Lista Imagens

Listar imagens:

```
$ docker image ls
```

## Comando `pull`: Baixar Imagem

Download de imagens:

```
$ docker pull <imagem>
```

Para aprender mais sobre os comandos basta adicionar a flag `--help`.

## Comando `tag`: Alterando o nome da imagem

Alterando o nome da imagem e tag:

```
$ docker tag <nome>
```

ou

```
$ docker tag <id_imagem> <nome>:<tag>
```

## Comando `rmi`: Remover imagens

Removendo imagens:

```
$ docker rmi <imagem>
```

Removendo imagens de um container que está rodando:

```
$ docker rmi <imagem> -f
```

## Comando `prune`: Auto limpeza

Removendo imagens, containers e networks não utilizados:

```
$ docker system prune
```

## Comando `cp` : Copiar arquivo entre containers 

Para copiar arquivo de um diretório para um container ou de um container para um diretório:

```
$ docker cp <container>:<caminho_relativo_arquivo> <caminho_destino>
```

## Comando `top`: Verificar informações de processamento

Para verificar dados de excecução de um container utilizamos o camando:

```
$ docker top <container>
```

## Comando `inspect`: Verificar dados de um container

```
$ docker inspect <container>
```

## Comando `stats`: Verificar processamento

```
$ docker stats
```

## Integração com o Docker Hub

Realizar login:

```
$ docker login
```

Realizar logout

```
$ docker logout
```

Enviando imagem para o Docker Hub

- Criar repositório no Docker Hub;
- Criar imagem usando o nome completo do repositório `<username>/<imagem>`;
- Enviar imagem para o Docker Hub com o comando abaixo:

```
$ docker push <imagem>
```

Atualizar a imagem no Docker Hub:

- Criar uma nova imagem adicionando uma tag
- Enviar imagem para o Docker Hub informando a tag

```
$ docker push <imagem>:<tag>
```