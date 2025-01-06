# EduChain - Documentação

## 1. Introdução
EduChain é uma proposta de plataforma que utiliza blockchain em sua composição para validar certificados de cursos. A ideia é que empresas que forneçam serviços de educação e cursos, solicitem os serviços da empresa e a partir disso, os certificados dos estudantes possam ser emitidos na blockchain. Existem algumas vantagens em usar esse modelo de emissão de certificado, como:

- Imutabilidade dos certificados;
- Evitar riscos de fraude dos certificados;
- Método fácil e rápido de validar os certificados.

## 2. Projeto
- Utilizamos os serviços da **Infura** para conseguir um nó da blockchain para realizar as transações;
- Para o projeto, criamos uma API com **Node.js**, **Express.js** e **MongoDB**;
- Para fazer a integração com os nós da blockchain no backend, e ser possível realizar transações, utilizamos a biblioteca **Web3.js**;
- O Smart Contract, escrito em **Solidity**, foi emitido pelo **Remix** e o deploy foi feito através da **MetaMask**, na rede de testes da **Sepolia**;
- Por fim, criamos um **client** em React para se ter uma representação melhor de como funcionaria esse ambiente da EduChain para possíveis usuários.

### 2.1 Instalando o Projeto

A instalação da API e do Client são feitos através dos seguintes repositórios:

- Backend:
```bash
git clone https://github.com/pedrjose/educhain-api.git

cd educhain-api
git checkout educhain-develop

npm i
npm run dev
```

- Frontend:
```bash
git clone https://github.com/luizamorim2/educhain-front

cd educhain-front

npm i
npm run dev
```

**OBS: para testar o *Client*, os dois projetos precisam estar rodando de forma simutânea!**

### 2.2 API
Ao todo, foram criados quatro rotas na API para o projeto:
- Cadastrar instituição;
- Autenticar instituição;
- Emitir certificados;
- Validar certificados.

Caso você prefira, você pode usar a EduChain via server usando alguma tecnologia de **Client**, como **Postman** ou **Thunder Client**. Segue o [Link da Documentação](https://documenter.getpostman.com/view/28866924/2sAYJ7eyQL) caso você prefira utilizar o projeto dessa forma!

Para o projeto a API do projeto funcionar, é necessário o preenchimento das seguintes credenciais no ***.env***:
```bash
PRIVATE_KEY=0x19033841c1b8f639d156a91d696996cdf8750648dc5cee91db42ee1dbb1c6d2c
WALLET_ADDRESS=0x46bE5659009505d2709EFE28AF55eAA2107Ee205
INFURA_URL=https://sepolia.infura.io/v3/2978cbca49dc46b6a07d51aeace05440
CONTRACT_ADDRESS=0x4a634Dd47e29aAd60F4b51bbB814050d920164e2
```
**OBS: as credenciais acima estão sendo disponibilizadas apenas com o intuito de facilitar a avaliação do projeto. No caso de um ambiente real de produção, esses dados não seriam disponibilizados!**

### 2.3 Clint
O Client criado é uma forma mais dinâmica de simular um ambiente de usuário, para emitir e verificar os dados do certificado. Além do mais, foi feita integração com a **Etherscan**, para que o certificado seja validado diretamente por lá, e também funcionalidades como download do certificado em PDF.
