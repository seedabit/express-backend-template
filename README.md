# Template de projetos backend em Express

Este é o template usado como base em projetos de backend. Trate como um guia, não como uma regra definitiva de como seguir um projeto. Cada um tem sua individualidade. 

## Stack do template

* Node (feito na versão 22.2.0)
* Express (4.21.1)
* Prisma (5.21.1)
* TypeScript

## Organização de pastas

O template divide o código nas seguintes pastas:

* controllers: responsável por manter todos os arquivos de rota do servidor.
  Cada rota é uma instância diferente da classe AppRoute. A 
  partir dela você pode usar o atributo routes para definir as rotas
  como definiria no Express.
* models: responsável por manter todos os arquivos relacionados a
  modelagem de entidade do servidor. Aqui deve-se por qualquer lógica
  referente a validação, criação ou construção das entidades.
* repository: camada de acesso ao banco de dados, responsável por manter
  a tipagem e a separação de responsabilidades.
* services: responsável também por regras de negócio, mas principalmente
  voltada para regras que dependem de acesso ao banco de dados. Esse diretório
  é dividido em subpastas para cada entidade (definida em models), e dentro
  dessas subpastas, cada arquivo representa um UseCase.
* utils: classes de utilidades tanto de infraestrutura como scripts simples.

## Rodando o projeto

Faça um clone deste repositório e após entrar no diretório, abra um terminal e digite:

 - `npm install`

Após as dependências serem instaladas, crie um arquivo chamado `.env`, e deve ser adicionado o
seguinte conteúdo. Substitua `<url do database>` por um URL de um banco de dados Postgresql:

- `DATABASE_URL="<url do database>"`

Com isso configurado, rode as migrações do Prisma:

- `npx prisma migrate dev`

Após isso, você poderá rodar a aplicação utilizando o comando:

- `npm run dev`

### Made with <3 by Seed a Bit
