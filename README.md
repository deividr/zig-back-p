# Desafio técnico

Temos aqui uma API já pré-configurada usando o [Express](https://expressjs.com/pt-br/) para encapsulamento dos recursos HTTP.
Já temos configurado também o Typescript, Eslint e Prettier.
Existem 3 rotas abertas já configuradas.

## Proposta de implementação:

### 1. Crie um endpoint `POST` chamado `/create-user` que vai receber um objeto JSON com a seguinte estrutura:

```
{
  "name": string,
  "username": string,
  "password": string,
}
```

- Criptografar a informação do password usando uma criptografia simples. Pode usar a lib [bcrypt](https://www.npmjs.com/package/bcrypt) ou qualquer outra da sua preferência;
- Armazenar as informações recebida em um novo item no ARRAY em memória, usando o password já criptografado e criando um ID randômico;
- Retornar esse novo objeto como reposta usando o HTTP correto;

### 2. Crie um endpoint `POST` chamado `/login` que vai receber um objeto JSON com a seguinte estrutura:

```
{
  "username": string,
  "password": string,
}
```

- Efetuar a consulta no banco de dados por esse username e senha. Lembrando que a senha está criptografada no banco/array em memória;
- Retonar um token de acesso usando o [JWT](https://jwt.io/);

### 3. Alterar o endpoint `/create-book` para receber o token no "Header - Authentication - Bearer Token":

- Validar se o token recebido está correto;
- Se não, retornar erro HTTP informando que a requisição não foi autorizada;
- Se sim, retornar como já está hoje implementado;
