# 🛠️ Projeto de Teste de API - Postman

Este projeto contém testes automatizados para a API **X** utilizando **Postman** e **Newman**. O objetivo é validar os endpoints da API e garantir seu correto funcionamento.

## 📌 Tecnologias Utilizadas
- [Postman](https://www.postman.com/) - Plataforma para testes de API
- [Newman](https://www.npmjs.com/package/newman) - Executor de testes do Postman via linha de comando
- [JSON Schema Validation](https://json-schema.org/) - Para validação das respostas da API

---

## 🚀 Como Executar os Testes

### 1️⃣ Clonar o repositório:
```sh
git clone https://github.com/BeatrizCamposPortifolio/PostmanAPI
cd PostmanAPI
```

### 2️⃣ Instalar o Newman (caso ainda não tenha):
```sh
npm install -g newman
```

### 3️⃣ Executar os testes:
```sh
newman run collections/minha-colecao.json -e environments/meu-ambiente.json
```

### 4️⃣ Gerar um relatório HTML dos testes (opcional):
```sh
newman run collections/minha-colecao.json -e environments/meu-ambiente.json -r html --reporter-html-export reports/relatorio.html
```

---

## 📂 Estrutura do Projeto

```
projeto-teste-api/
│── 📂 collections       # Coleções de testes do Postman
│── 📂 reports           # Relatórios gerados pelo Newman
│── 📜 README.md         # Documentação do projeto
```

---

## 📖 Testes no Postman

Foram realizadas **4 requisições**, todas concluídas com sucesso. Utilizamos **JavaScript** no Collection Runner para automatizar o processo de teste da API.

### 🖥️ Endpoints Testados
- **GET**: Obtenção de informações
- **POST**: Criação de novos registros
- **PUT**: Atualização de registros existentes
- **DELETE**: Remoção de registros

### 📝 Exemplos de Testes

#### ✅ GET
https://reqres.in/api/users?page=2%0A
```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response contains user data", function () {
    pm.expect(pm.response.json().data).to.be.an('array');
});
```

#### ✅ POST
https://reqres.in/api/users
Realizamos uma inserção no corpo dessa requisição, e fizemos um teste em javascript.

```json
{
    "name": "João QA",
    "job": "Testador"
}
```


```javascript
pm.test("Status code is 201", function () {
    pm.response.to.have.status(201);
});

pm.test("Response has ID", function () {
    pm.expect(pm.response.json()).to.have.property("id");
});
```


#### ✅ PUT
https://reqres.in/api/users
Realizamos uma inserção no corpo dessa requisição, e fizemos um teste em javascript.
```json
{
    "name": "João QA",
    "job": "QA Senior"
}
```


```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response contains updated job title", function () {
    pm.expect(pm.response.json().job).to.eql("QA Senior");
});
```

#### ✅ DELETE
https://reqres.in/api/users/2%0A
```javascript
pm.test("Status code is 204", function () {
    pm.response.to.have.status(204);
});
```

---

## 📄 Licença
Este projeto é de código aberto e está disponível sob a licença MIT.

---

📌 **Dicas adicionais**:
- Utilize variáveis de ambiente no Postman para tornar os testes mais dinâmicos.
- Automatize a execução dos testes via CI/CD para garantir a qualidade contínua da API.









