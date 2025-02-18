# 🛠️ Projeto de Teste de API - Postman

Este projeto contém testes automatizados para a API **X** utilizando **Postman** e **Newman**. O objetivo é validar os endpoints da API e garantir que funcionem conforme esperado.

## 📌 Tecnologias Utilizadas
- [Postman](https://www.postman.com/) - Plataforma para testes de API  
- [Newman](https://www.npmjs.com/package/newman) - Executor de testes do Postman via linha de comando  
- [JSON Schema Validation](https://json-schema.org/) - Para validação de respostas da API  

## 🚀 Como Executar os Testes
### 1️⃣ Clonar o repositório:

```sh
git clone https://github.com/BeatrizCamposPortifolio/PostmanAPI
cd PostmanAPI
```

2️⃣ Instalar o Newman (caso ainda não tenha):
```sh
npm install -g newman
```

3️⃣ Executar os testes:
```sh
newman run collections/minha-colecao.json -e environments/meu-ambiente.json
```

4️⃣ Gerar um relatório HTML dos testes (opcional):
```sh
newman run collections/minha-colecao.json -e environments/meu-ambiente.json -r html --reporter-html-export reports/relatorio.html
```


## 📂 Estrutura do Projeto


### 📁 projeto-teste-api

 ┣ 📂 collections       # Coleções de testes do Postman
 
 ┣ 📂 reports           # Relatórios gerados pelo Newman
 
 ┣ 📜 README.md         # Documentação do projeto
 


## 📄 Licença
Este projeto é de código aberto e está disponível sob a licença MIT.

<hr>

GET

```javascript
Script executado

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response contains user data", function () {
    pm.expect(pm.response.json().data).to.be.an('array');
});
```



Fez requisição no seguinte link: https://reqres.in/api/users?page=2\





