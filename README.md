# Brise API Restful - Documentação
Repositório para elaboração e manutenção da documentação da **Brise API V3**, especificada em **OpenAPI (YAML)** e publicada via **Redoc**.

## Documentação da API
A documentação da API é gerada no formato YAML e pode ser acessada [aqui](https://briseapiv3.agst.com.br) hospedada no github pages.

## Sobre a API
A Brise API é **RESTful**, utilizando métodos HTTP padrão:
- `GET` → recuperar recursos
- `POST` → criar novos recursos
- `PUT` → atualizar recursos existentes
- `DELETE` → remover recursos
Toda a especificação dos endpoints, parâmetros e modelos de resposta está descrita no arquivo `brise.openapi.yaml`.

## Desenvolvimento Local
1. Se quiser visualizar a documentação localmente:
```bash
   git clone https://github.com/AGSTControlesEAutomacao/BriseAPIv3
   cd BriseAPIv3
```
2. Gere a documentação com Redocly CLI:
```bash
npx @redocly/cli build-docs brise.openapi.yaml -o index.html
```
Abra o arquivo `index.html` no navegador para visualizar a documentação.
3. Rodar um servidor local (opcional)
```bash
npm install -g redoc-cli
redoc-cli serve brise.openapi.yaml
```
Ou sem instalar nada:
```bash
npx @redocly/openapi-cli preview-docs brise.openapi.yaml
```
> Para rodar sem instalar a versão do nodejs ">=22.12.0 || >=20.19.0 <21.0.0" instalado. > Para instalar no Windows via Chocolatey: ´choco install nodejs´ (acesso administrador)

## Contribuição
Se você quiser contribuir com a documentação, sinta-se à vontade para abrir um issue ou uma discussão.

## Problemas ou Dúvidas
Se você encontrar algum problema ou tiver alguma dúvida em relação à API, por favor, abra uma issue no repositório para que possamos ajudá-lo.

# Apêndice – Conceitos Importantes
1. API
- Significa: Application Programming Interface (Interface de Programação de Aplicações).
- O que é: é um conjunto de regras e instruções que permite que diferentes aplicações de software se comuniquem e interajam entre si, funcionando como um intermediário que envia e recebe dados e funcionalidades de forma padronizada.
- Exemplo:
  - Quando um app de previsão do tempo busca dados do servidor, ele usa uma API.
  - Uma API pode ser local (entre bibliotecas de um programa) ou remota (via rede).
> Pense nela como o cardápio de um restaurante → você não entra na cozinha, apenas pede o prato de acordo com o menu (API).

2. OpenAPI
- Significa: OpenAPI Specification (OAS).
- O que é: um padrão de descrição de APIs REST em formato JSON ou YAML.
- Função: documentar de forma legível por pessoas e máquinas como funciona a API:
  - Quais endpoints existem (/users, /products),
  - Quais métodos aceitam (GET, POST, etc.),
  - Quais parâmetros e respostas são esperados.
> Ele é o contrato escrito da API.

3. REST
- Significa: Representational State Transfer.
- O que é: um estilo arquitetural para construir APIs usando HTTP de forma simples e padronizada.
- Princípios principais:
  - Cada recurso tem uma URL única (ex.: /clientes/123).
  - Usa métodos HTTP padrão (GET, POST, PUT, DELETE).
  - É stateless (cada requisição é independente, não guarda estado no servidor).
> REST não é uma tecnologia, mas um conjunto de boas práticas.

4. RESTful
- O que é: uma API que segue os princípios do REST de forma correta.
- Exemplo de API RESTful:
  - GET /clientes → retorna todos os clientes.
  - GET /clientes/123 → retorna o cliente de id 123.
  - POST /clientes → cria um cliente novo.
  - PUT /clientes/123 → atualiza o cliente 123.
  - DELETE /clientes/123 → remove o cliente 123.
- Exemplo de API não-RESTful (quebra boas práticas):
  - POST /getAllClients
  - GET /deleteClient?id=123
> Toda API RESTful é REST, mas nem toda API REST é totalmente RESTful.

5. Swagger
- O que era: o nome original da especificação OpenAPI (criada em 2010).
- Hoje:
  - "Swagger" é usado para se referir às ferramentas da SmartBear que trabalham com OpenAPI, como:
    - Swagger Editor → editor online de OpenAPI.
    - Swagger UI → interface web interativa para explorar uma API.
    - Swagger Codegen → gera código cliente/servidor a partir de OpenAPI.
  - Em 2016, a especificação foi doada para a Linux Foundation e passou a se chamar OpenAPI.