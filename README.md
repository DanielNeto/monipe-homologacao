# monipe-homologacao

Criar container:

```shell
docker-compose up -d
```

Após o serviço do apache iniciar corretamente.

Autenticação Web:

Email: admin@rnp.br
Senha: admin

Autenticar na API:

```shell
curl --insecure --location --request POST 'https://localhost:8001/api/v1/auth/login' --form 'email="admin@rnp.br"' --form 'password="admin"'
```

Usar o token obtido na autenticação para criar um teste:

```shell
curl --insecure --location --request POST 'https://localhost:8001/api/v1/testpoint/99/tests' --header "Authorization: Bearer $TOKEN" --header 'Content-Type: application/json' -d @teste.json
```

Obs: Não esquecer de modificar a data do teste no arquivo *teste.json* para um valor válido.

Documentação
