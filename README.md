# Microsserviço Serverless para Validação de CPF

## Sobre o Projeto

Este projeto foi desenvolvido como parte de uma atividade hands-on da **DIO (Digital Innovation One)** no **"Criando um Microsserviço Serverless para Validação de CPF"**.

O objetivo é criar uma Azure Function que valida CPFs brasileiros através de uma API HTTP, utilizando a arquitetura serverless do Microsoft Azure.

## Funcionalidades

- ✅ Validação de CPF segundo o algoritmo oficial brasileiro
- ✅ API HTTP REST que aceita requisições POST
- ✅ Remove automaticamente pontos e hífens do CPF
- ✅ Retorna respostas claras sobre a validade do CPF
- ✅ Logging integrado para monitoramento

## Tecnologias Utilizadas

- **C# .NET 8.0**
- **Azure Functions v4**
- **Microsoft.NET.Sdk.Functions**
- **Newtonsoft.Json**

## Como Usar

### Requisição

Faça uma requisição POST para o endpoint da function com o seguinte formato:

```http
POST https://your-function-app.azurewebsites.net/api/fnvalidacpf
Content-Type: application/json

{
  "cpf": "12345678901"
}
```

### Respostas

**CPF Válido (200 OK):**
```json
"CPF válido."
```

**CPF Inválido (400 Bad Request):**
```json
"CPF inválido."
```

**Requisição sem CPF (400 Bad Request):**
```json
"Por favor, passe um CPF no corpo da requisição."
```