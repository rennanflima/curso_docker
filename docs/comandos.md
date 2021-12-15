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

### Volumes

Volumes anônimos

```
$ docker run -v /data
```

Volumes nomeados (named volume)

```
$ docker run -v <nome_volume>:/<caminho_onde_salva_arquivos>
```

Bind mounts (o diretório fica no host).

```
$ docker run -v <diretorio_host>:/<caminho_onde_salva_arquivos>
```

O Bind mounts pode ser utilizado para atualização em tempo real do projeto, durante o processo de desenvolvimento

```
$ docker run -v <diretorio_base_host>:/<workdir>
```

Volume apenas de leitura:
```
$ docker run -v <nome_volume>:/<caminho_onde_salva_arquivos>:ro
```

> Este `:ro` é a abreviação de read only.

Listar todos os volumes (anônimos e nomeados):

```
$ docker volume ls
```

Criar um volume nomeado:

```
$ docker volume create <nome>
```

Checar um volume:

```
$ docker volume inspect <nome>
```

Remover um volume:

```
$ docker volume rm <nome>
```

Removendo volumes não utilizados:

```
$ docker volume prune
```

### Networks

Listar todas as redes do ambiente:

```
$ docker network ls
```

Criar rede (default: bridge):

```
$ docker network create <nome>
```

Criar rede com driver diferente do bridge:

```
$ docker network create -d <driver> <nome>
```

Remover rede:

```
$ docker network rm <nome>
```

Remover redes em massa:

```
$ docker network prume
```

Para especificar a um container a network utilizar a flag `--network`:

```
$ docker run --network <nome_network>
```

> Conectar um container com a um banco que está rodando no host onde o container está rodando, no IP de host utilizamos: `host.docker.internal`.

Conectar um container a uma rede:

```
$ docker network connect <nome_network> <container>
```

Desconectar um container a uma rede:

```
$ docker network disconnect <nome_network> <container>
```

Inspecionar uma rede:

```
$ docker network inspect <nome_network>
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