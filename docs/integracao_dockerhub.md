# Integração com o Docker Hub

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