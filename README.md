# API de Games
Esta API é utilizada como projecto de estudo de um curso de fullstack node js.
## Endpoints
### GET /games
Esse endpoint é responsável de retornar a listagem de todos os dados cadastrados no banco de dados.
#### Parâmetros
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta acontece você vai receber a listagem de todos os games.

Exemplo de resposta
```
[
    {
        "id": 13,
        "title": "Sea of Thieves",
        "year": 2021,
        "price": 40,
        "createdAt": "2024-02-06",
        "updatedAt": "2024-02-06"
    },
    {
        "id": 11,
        "title": "Minecraft",
        "year": 2019,
        "price": 92,
        "createdAt": "2024-01-02",
        "updatedAt": "2024-02-06"
    }
]
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição, Motivos: Token Inválido, Token Expirado.

Exemplo de resposta

```
{
    "err": "Token Invalido!"
}
```

### POST /auth
Esse endpoint é responsável de fazer o processo de login.
#### Parâmetros
email: E-mail do usuário cadastrado no sistema.

password: Senha do usuário cadastrado no sistema, com aquele determinado e-mail.

Exemplo: 
```
{
    "email": "victorliaddev@gmail.com",
    "password": "nodejs3"
}
```
#### Respostas
##### OK! 200
Caso essa resposta acontece você vai receber o token JWT para conseguir acessar endpoints protegidos na api.

Exemplo de resposta
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJ2aWN0b3JsaWFkZGV2QGdtYWlsLmNvbSIsImlhdCI6MTcwNzI1MzI4MCwiZXhwIjoxNzA3NDI2MDgwfQ.gWr2ORKfc_-OcLU4H9tyhkW729U2PZMoo3SXdmnMD1M"
}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição, Motivos: senha ou email incorreto.

Exemplo de resposta

```
{"err": "Credenciais Invalidas!"}
```
