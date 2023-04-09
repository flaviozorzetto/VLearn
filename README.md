# Virtual Learn

Projeto para o challenge

Api de controle da plataforma de cursos envolvendo realidade virtual para pessoas com pcd

## Endpoints

- Login
  - [cadastrar](#cadastrar-login)
  - [apagar](#apagar-login)
  - [alterar](#alterar-login)
  - [mostrar detalhes](#detalhes-do-login)
- Professor
  - [cadastrar](#cadastrar-professor)
  - [apagar](#apagar-professor)
  - [alterar](#alterar-professor)
  - [mostrar detalhes](#detalhes-do-professor)
- Aluno
  - [cadastrar](#cadastrar-aluno)
  - [apagar](#apagar-aluno)
  - [alterar](#alterar-aluno)
  - [mostrar detalhes](#detalhes-do-aluno)
- Curso
  - [cadastrar](#cadastrar-curso)
  - [apagar](#apagar-curso)
  - [alterar](#alterar-curso)
  - [mostrar detalhes](#detalhes-do-curso)
  - [listar todas](#detalhes-do-curso-geral)

---

## Endpoints de Login

### Cadastrar Login

`POST` /virtuallearn/api/login

**Campos da Requisição**

| campo    | tipo  | obrigatório | descrição               |
| -------- | ----- | :---------: | ----------------------- |
| email    | texto |     sim     | email do cadastro       |
| senha    | texto |     sim     | senha do cadastro       |
| login_id | int   |     sim     | id de cadastro do login |

**Exemplo de corpo de requisição**

```js
{
    email: "teste@gmail.com",
    senha: "123",
    login_id: '1'
}
```

**Códigos de Respostas**

| código | descrição                    |
| ------ | ---------------------------- |
| 201    | login cadastrada com sucesso |
| 400    | campos inválidos             |

---

### Apagar Login

`DELETE` /virtuallearn/api/login/{id}

**Códigos de Respostas**

| código | descrição            |
| ------ | -------------------- |
| 204    | No content           |
| 404    | Login não encontrado |

---

### Alterar Login

`PUT` /virtuallearn/api/login/{id}

**Campos da Requisição**

| campo    | tipo  | obrigatório | descrição               |
| -------- | ----- | :---------: | ----------------------- |
| email    | texto |     sim     | email do cadastro       |
| senha    | texto |     sim     | senha do cadastro       |
| login_id | int   |     sim     | id de cadastro do login |

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

| código | descrição                  |
| ------ | -------------------------- |
| 201    | login alterado com sucesso |
| 400    | campos inválidos           |
| 404    | Login não encontrado       |

---

### Detalhes do login

`GET` /virtuallearn/api/login/{id}

**Exemplo de corpo de resposta**

```js
{
    email: "teste@gmail.com",
    senha: "12345",
    login_id: '1'
}
```

**Códigos de Respostas**

| código | descrição                 |
| ------ | ------------------------- |
| 200    | dados do login retornados |
| 404    | Login não encontrado      |

---

## Endpoints de Professor

### Cadastrar Professor

`POST` /virtuallearn/api/professor

**Campos da Requisição**

| campo        | tipo   | obrigatório | descrição                                             |
| ------------ | ------ | :---------: | ----------------------------------------------------- |
| professor_id | number |     sim     | identificador unico do professor                      |
| nome         | texto  |     sim     | nome completo do professor                            |
| telefone     | number |     sim     | telefone para contato do professor                    |
| formacao     | texto  |     sim     | graduações do professor                               |
| experiencia  | texto  |     sim     | experiencia profissional do professor                 |
| idiomas      | texto  |     sim     | idiomas do professor                                  |
| status       | texto  |     sim     | status da conta do professor (1 = Ativo, 0 = Inativo) |

**Exemplo de corpo de requisição**

```js
{
    professor_id: '1',
    nome: 'Jorge Rodrigo',
    telefone: '5511974825648',
    formacao: "Tecnólogo...",
    experiencia: "Trabalhei em...",
    idiomas: "Português, Inglês",
    status: '1'
}
```

**Códigos de Respostas**

| código | descrição                        |
| ------ | -------------------------------- |
| 201    | professor cadastrado com sucesso |
| 400    | campos inválidos                 |

---

### Apagar Professor

`DELETE` /virtuallearn/api/professor/{id}

**Códigos de Respostas**

| código | descrição                |
| ------ | ------------------------ |
| 204    | No content               |
| 404    | Professor não encontrado |

---

### Alterar Professor

`PUT` /virtuallearn/api/professor/{id}

**Campos da Requisição**

| campo        | tipo   | obrigatório | descrição                                             |
| ------------ | ------ | :---------: | ----------------------------------------------------- |
| professor_id | number |     sim     | identificador unico do professor                      |
| nome         | texto  |     sim     | nome completo do professor                            |
| telefone     | number |     sim     | telefone para contato do professor                    |
| formacao     | texto  |     sim     | graduações do professor                               |
| experiencia  | texto  |     sim     | experiencia profissional do professor                 |
| idiomas      | texto  |     sim     | idiomas do professor                                  |
| status       | texto  |     sim     | status da conta do professor (1 = Ativo, 0 = Inativo) |

**Exemplo de corpo de requisição**

```js
{
    professor_id: '1',
    nome: 'Jorge Rodrigo',
    telefone: '5511974825648',
    formacao: "Tecnólogo...",
    experiencia: "Trabalhei em...",
    idiomas: "Português, Inglês",
    status: '1'
}
```

**Códigos de Respostas**

| código | descrição                      |
| ------ | ------------------------------ |
| 201    | professor alterado com sucesso |
| 400    | campos inválidos               |
| 404    | Professor não encontrado       |

---

### Detalhes do Professor

`GET` /virtuallearn/api/professor/{id}

**Exemplo de corpo da resposta**

```js
{
    professor_id: '1',
    nome: 'Jorge Rodrigo',
    telefone: '5511974825648',
    formacao: "Tecnólogo...",
    experiencia: "Trabalhei em...",
    idiomas: "Português, Inglês",
    status: '1'
}
```

**Códigos de Respostas**

| código | descrição                                 |
| ------ | ----------------------------------------- |
| 200    | Dados do professor retornados com sucesso |
| 404    | Professor não encontrado                  |

---

## Endpoints de Aluno

### Cadastrar Aluno

`POST` /virtuallearn/api/aluno

**Campos da Requisição**

| campo    | tipo   | obrigatório | descrição                      |
| -------- | ------ | :---------: | ------------------------------ |
| aluno_id | number |     sim     | identificador unico do aluno   |
| nome     | texto  |     sim     | nome completo do aluno         |
| telefone | number |     sim     | telefone para contato do aluno |
| tipo_pcd | texto  |     sim     | tipo de pcf do aluno           |

**Exemplo de corpo de requisição**

```js
{
    professor_id: '1',
    nome: 'Jorge Rodrigo',
    telefone: '5511974825648',
    tipo_pcd: 'Prótese perna direita'
}
```

**Códigos de Respostas**

| código | descrição                    |
| ------ | ---------------------------- |
| 201    | Aluno cadastrado com sucesso |
| 400    | campos inválidos             |

---

### Apagar Aluno

`DELETE` /virtuallearn/api/aluno/{id}

**Códigos de Respostas**

| código | descrição            |
| ------ | -------------------- |
| 204    | No content           |
| 404    | Aluno não encontrado |

---

### Alterar Aluno

`PUT` /virtuallearn/api/aluno/{id}

**Campos da Requisição**

| campo    | tipo   | obrigatório | descrição                      |
| -------- | ------ | :---------: | ------------------------------ |
| aluno_id | number |     sim     | identificador unico do aluno   |
| nome     | texto  |     sim     | nome completo do aluno         |
| telefone | number |     sim     | telefone para contato do aluno |
| tipo_pcd | texto  |     sim     | tipo de pcf do aluno           |

**Exemplo de corpo de requisição**

```js
{
    professor_id: '1',
    nome: 'Jorge Rodrigo',
    telefone: '5511974825648',
    tipo_pcd: 'Baixa visão'
}
```

**Códigos de Respostas**

| código | descrição                    |
| ------ | ---------------------------- |
| 201    | Aluno atualizado com sucesso |
| 400    | Campos inválidos             |
| 404    | Aluno não encontrado         |

---

### Detalhes do Aluno

`GET` /virtuallearn/api/aluno/{id}

**Exemplo de corpo da resposta**

```js
{
    professor_id: '1',
    nome: 'Jorge Rodrigo',
    telefone: '5511974825648',
    tipo_pcd: 'Baixa visão'
}
```

**Códigos de Respostas**

| código | descrição                             |
| ------ | ------------------------------------- |
| 200    | Dados do aluno retornados com sucesso |
| 404    | Aluno não encontrado                  |

---

## Endpoints de Curso

### Cadastrar Curso

`POST` /virtuallearn/api/curso

**Campos da Requisição**

| campo     | tipo   | obrigatório | descrição                    |
| --------- | ------ | :---------: | ---------------------------- |
| curso_id  | number |     sim     | identificador unico do curso |
| nome      | texto  |     sim     | nome do curso                |
| descricao | texto  |     sim     | descricao do curso           |
| preco     | number |     sim     | preço do curso               |
| autor     | texto  |     sim     | autor do curso               |
| duracao   | number |     sim     | duração do curso em minutos  |

**Exemplo de corpo de requisição**

```js
{
    curso_id: '1',
    nome: "Estrutura de computador",
    descricao: "Este curso tem como propósito especializar pessoas em montagens de computadores",
    preco: 98.40,
    autor: "Jorge Rodrigo",
    duracao: 1890
}
```

**Códigos de Respostas**

| código | descrição                    |
| ------ | ---------------------------- |
| 201    | Curso cadastrado com sucesso |
| 400    | campos inválidos             |

---

### Apagar Curso

`DELETE` /virtuallearn/api/curso/{id}

**Códigos de Respostas**

| código | descrição            |
| ------ | -------------------- |
| 204    | No content           |
| 404    | Curso não encontrado |

---

### Alterar Curso

`PUT` /virtuallearn/api/curso/{id}

**Campos da Requisição**

| campo     | tipo   | obrigatório | descrição                    |
| --------- | ------ | :---------: | ---------------------------- |
| curso_id  | number |     sim     | identificador unico do curso |
| nome      | texto  |     sim     | nome do curso                |
| descricao | texto  |     sim     | descricao do curso           |
| preco     | number |     sim     | preço do curso               |
| autor     | texto  |     sim     | autor do curso               |
| duracao   | number |     sim     | duração do curso em minutos  |

**Exemplo de corpo de requisição**

```js
{
    curso_id: '1',
    nome: "Estrutura de computador",
    descricao: "Este curso tem como propósito especializar pessoas em montagens de computadores",
    preco: 98.40,
    autor: "Jorge Rodrigo",
    duracao: 1890
}
```

**Códigos de Respostas**

| código | descrição                    |
| ------ | ---------------------------- |
| 201    | Curso atualizado com sucesso |
| 400    | campos inválidos             |
| 404    | Curso não encontrado         |

---

### Detalhes do Curso

`GET` /virtuallearn/api/curso/{id}

**Exemplo de corpo de resposta**

```js
{
    curso_id: '1',
    nome: "Estrutura de computador",
    descricao: "Este curso tem como propósito especializar pessoas em montagens de computadores",
    preco: 98.40,
    autor: "Jorge Rodrigo",
    duracao: 1890
}
```

**Códigos de Respostas**

| código | descrição                             |
| ------ | ------------------------------------- |
| 200    | Dados do curso retornados com sucesso |
| 404    | Curso não encontrado                  |

---

### Detalhes do Curso Geral

`GET` /virtuallearn/api/curso

**Exemplo de corpo de resposta**

```js
[
	{
		curso_id: '1',
		nome: 'Estrutura de computador',
		descricao:
			'Este curso tem como propósito especializar pessoas em montagens de computadores',
		preco: 98.4,
		autor: 'Jorge Rodrigo',
		duracao: 1890,
	},
];
```

**Códigos de Respostas**

| código | descrição                                      |
| ------ | ---------------------------------------------- |
| 200    | Curso retornados com sucesso em forma de array |
| 404    | Curso não encontrado                           |
