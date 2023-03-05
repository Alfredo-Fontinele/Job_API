<li style='font-size: 30px; list-style: square' align="center">
  Employee_API
</li>

<br/>

<h2 align="center" style='font-family: sans-serif'>
	API REST (Back-end) de serviços de empregabilidade
</h2>

<br/>

## **Endpoints**

<br/>

A url base da API é https://api-person.onrender.com

<br/>

-   ## Nenhuma rota precisa de autenticação no momento

## <br/>

<h2 align ='center'> Listando trabalhadores </h2>

<br/>

`GET /employees - FORMATO DA RESPOSTA - STATUS 200`

```json
[
    {
        "id": "46be8c58-e512-4f47-8b01-bb3775f14650",
        "name": "matheus",
        "email": "matheus1111@gmail.com",
        "jobs": [
            {
                "id": "91db49c6-6ab8-45b9-9d69-fdcd39feee5b",
                "name": "software engineer",
                "level": "pleno"
            }
        ]
    }
]
```

## <br/>

<li style='font-size: 20px'>Podemos acessar um trabalhador específico utilizando o endpoint:</li>

<br/>

`GET /employees/:employee_id - FORMATO DA RESPOSTA - STATUS 200`

```json
[
    {
        "id": "a4dd2b88-d087-4834-bf18-0a8f442765ec",
        "name": "filipe",
        "email": "filipe@gmail.com",
        "jobs": []
    }
]
```

## <br/>

<li style='font-size: 20px'>Criação de usuário:</li>

<br/>

`POST /employees - FORMATO DA REQUISIÇÃO`

```json
{
    "name": "matheus",
    "password": "matheus",
    "email": "matheus1111@gmail.com"
}
```

Caso dê tudo certo, a resposta será assim:

`POST /employees - FORMATO DA RESPOSTA - STATUS 201`

```json
{
    "id": "2a145ef5-cfee-4ecf-8062-c3cf37f81259",
    "name": "matheus",
    "email": "matheus@gmail.com"
}
```

## <br/>

<li style='font-size: 20px'>Atualização de usuário:</li>

<br/>

`PATCH /employees - FORMATO DA REQUISIÇÃO`

```json
{
    "password": "lucas",
    "email": "lucas@gmail.com",
    "name": "lucas"
}
```

Caso dê tudo certo, a resposta será assim:

`PATCH /employees - FORMATO DA RESPOSTA - STATUS 201`

```json
{
    "id": "2a145ef5-cfee-4ecf-8062-c3cf37f81259",
    "name": "lucas",
    "email": "lucas@gmail.com"
}
```

<li style='font-size: 20px'>Podemos deletar um trabalhador específico utilizando o endpoint:</li>

<br/>

`DELETE /employees/:employee_id - FORMATO DA RESPOSTA - STATUS 204`

```json
{}
```

---

## <br/>

<h2 align ='center'> Listando trabalhos </h2>

<br/>

`GET /jobs - FORMATO DA RESPOSTA - STATUS 200`

```json
[
    {
        "id": "91db49c6-6ab8-45b9-9d69-fdcd39feee5b",
        "name": "software engineer",
        "level": "pleno",
        "persons": [
            {
                "id": "46be8c58-e512-4f47-8b01-bb3775f14650",
                "name": "matheus",
                "email": "matheus1111@gmail.com"
            }
        ]
    },
    {
        "id": "c334e3b0-6a5b-4996-8626-a5e93640d51c",
        "name": "software engineer",
        "level": "júnior",
        "persons": []
    }
]
```

## <br/>

<li style='font-size: 20px'>Podemos acessar um trabalho específico utilizando o endpoint:</li>

<br/>

`GET /jobs/:job_id - FORMATO DA RESPOSTA - STATUS 200`

```json
[
    {
        "id": "91db49c6-6ab8-45b9-9d69-fdcd39feee5b",
        "name": "software engineer",
        "level": "pleno",
        "persons": [
            {
                "id": "46be8c58-e512-4f47-8b01-bb3775f14650",
                "name": "matheus",
                "email": "matheus1111@gmail.com"
            }
        ]
    }
]
```

## <br/>

<li style='font-size: 20px'>Criação de um trabalho:</li>

<br/>

`POST /jobs - FORMATO DA REQUISIÇÃO`

```json
{
    "name": "software engineer",
    "level": "pleno"
}
```

Caso dê tudo certo, a resposta será assim:

`POST /jobs - FORMATO DA RESPOSTA - STATUS 201`

```json
{
    "name": "software engineer",
    "level": "pleno",
    "id": "91db49c6-6ab8-45b9-9d69-fdcd39feee5b"
}
```

## <br/>

<li style='font-size: 20px'>Atualização de um trabalho:</li>

<br/>

`PATCH /jobs/:job_id - FORMATO DA REQUISIÇÃO`

```json
{
    "name": "SOFTWARE ENGINEER",
    "level": "Sênior"
}
```

Caso dê tudo certo, a resposta será assim:

`PATCH /jobs/:job_id - FORMATO DA RESPOSTA - STATUS 201`

```json
{
    "id": "028ee457-fb01-44e2-b537-bb257bc9ed22",
    "name": "software engineer",
    "level": "sênior"
}
```

<li style='font-size: 20px'>Podemos deletar um trabalho específico utilizando o endpoint:</li>

<br/>

`DELETE /jobs/:job_id - FORMATO DA RESPOSTA - STATUS 204`

```json
{}
```

By Alfredo Neto
