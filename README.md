# VLearn

Projeto para o challenge

Api de controle da plataforma de cursos envolvendo realidade virtual

## Endpoints

- Login
    - [cadastrar](#cadastrar-login)
    - [apagar](#apagar-login)
    - [alterar](#alterar-login)
    - [mostrar detalhes](#detalhes-do-login)
- Professor
    - cadastrar
    - apagar
    - alterar
    - mostrar detalhes
- Aluno
    - cadastrar
    - apagar
    - alterar
    - mostrar detalhes
- Curso
    - cadastrar
    - apagar
    - alterar
    - mostrar detalhes
    - listar todas
---

### Cadastrar Login

`POST` /vlearn/api/login

**Campos da Requisição**

| campo | tipo | obrigatório | descrição 
|-------|------|:-------------:|---
| email | texto | sim | email do cadastro 
| senha | texto | sim | senha do cadastro
| login_id | int | sim | id de cadastro do login


**Exemplo de corpo de requisição**

```js
{
    email: "teste@gmail.com",
    senha: "123",
    login_id: '1'
}
```

**Códigos de Respostas**

| código | descrição
|-|-
| 201 | login cadastrada com sucesso
| 400 | campos inválidos

----

### Apagar Login

`DELETE` /vlearn/api/login/{id}

**Códigos de Respostas**

| código | descrição
|-|-
| 204 | No content
| 404 | Login não encontrado

----
### Alterar Login

`PUT` /vlearn/api/login/{id}

**Campos da Requisição**

| campo | tipo | obrigatório | descrição 
|-------|------|:-------------:|---
| email | texto | sim | email do cadastro 
| senha | texto | sim | senha do cadastro
| login_id | int | sim | id de cadastro do login

**Exemplo de corpo de requisição**

```js
{
    email: "teste@gmail.com",
    senha: "12345",
    login_id: '1'
}
```

**Exemplo de corpo da resposta**

```js
{
    email: "teste@gmail.com",
    senha: "12345",
    login_id: '1'
}
```

**Códigos de Respostas**

| código | descrição
|-|-
| 201 | login alterado com sucesso
| 400 | campos inválidos
| 404 | Login não encontrado

----

### Detalhes do login

`GET` /vlearn/api/login/{id}

**Exemplo de corpo de resposta**

```js
{
    email: "teste@gmail.com",
    senha: "12345",
    login_id: '1'
}
```

**Códigos de Respostas**

| código | descrição
|-|-
| 200 | dados do login retornados
| 404 | Login não encontrado

