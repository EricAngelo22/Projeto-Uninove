
# Projeto ASP.NET - CRUD Simples (Desafio)

## Descrição

Este projeto é um teste simplificado para candidatos a uma vaga de desenvolvedor. Ele consiste na criação de um CRUD básico (Create, Read, Update, Delete) utilizando **ASP.NET Core (versão 8)** com **MySQL** como banco de dados. O objetivo é avaliar as habilidades fundamentais do candidato em desenvolvimento backend com .NET e conhecimentos básicos de frontend para criar uma interface simples.

O projeto consiste em **duas telas**:

- **Tela 1:** Listagem de itens (entidade "Produto").
- **Tela 2:** Formulário de cadastro e edição de um item (entidade "Produto").

### Funcionalidades

1. **Listar Produtos:** Exibir uma lista com os produtos cadastrados.
2. **Cadastrar Novo Produto:** Formulário para inserir novos produtos.
3. **Editar Produto:** Formulário para editar um produto existente.
4. **Excluir Produto:** Permite remover um produto.

## Tecnologias Utilizadas

- **.NET 8**
- **ASP.NET Core MVC**
- **Entity Framework Core** (com MySQL)
- **MySQL** (para o banco de dados)
- **Bootstrap** (para layout básico)

## Estrutura do Projeto

```
/ProjetoCrud
├── /Controllers
│   └── ProdutosController.cs      # Controlador para o CRUD de Produtos
├── /Models
│   └── Produto.cs                 # Modelo da entidade Produto
├── /Views
│   └── /Produtos
│       ├── Index.cshtml           # Tela de listagem de produtos
│       ├── Create.cshtml          # Tela de criação de produto
│       └── Edit.cshtml            # Tela de edição de produto
├── /Data
│   └── ApplicationDbContext.cs    # Contexto do banco de dados
└── Program.cs                     # Arquivo de inicialização da aplicação
```

## Como Executar o Projeto

### Pré-requisitos

- [.NET 8 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) instalado
- [MySQL Server](https://dev.mysql.com/downloads/mysql/) instalado e rodando
- [Visual Studio 2022](https://visualstudio.microsoft.com/pt-br/vs/community/) instalado e rodando

### Passos para rodar o projeto localmente:

1 - **Faça um fork do repositório:**
   https://github.com/belinazzi/TesteCrud


2 - **Configure o banco de dados MySQL:**

   No arquivo `appsettings.json`, configure a string de conexão MySQL, substituindo os valores `server`, `user` e `password` pelas suas credenciais do MySQL:

   ```json
   {
     "ConnectionStrings": {
       "DefaultConnection": "Server=localhost;Database=cruddb;User=root;Password=sua_senha;"
     }
   }
   ```

3 - **Crie o banco de dados e execute as migrações:**

   Execute o seguinte comando para aplicar as migrações e criar o banco de dados:

   ```bash
   dotnet ef migrations add 'NomeMigration'
   dotnet ef database update
   ```

4 - **Execute o projeto:**

   Após configurar o banco de dados, inicie o projeto:

   ```bash
   dotnet run
   ```

   O projeto estará acessível no navegador em `http://localhost:5000`.

## Endpoints

- **Listar Produtos (GET):**  
  `GET /Produtos`  
  Exibe a lista de produtos.

- **Cadastrar Produto (GET/POST):**  
  `GET /Produtos/Create`  
  Exibe o formulário para cadastrar um novo produto.  
  `POST /Produtos/Create`  
  Envia os dados do formulário para criar um novo produto.

- **Editar Produto (GET/POST):**  
  `GET /Produtos/Edit/{id}`  
  Exibe o formulário de edição de um produto existente.  
  `POST /Produtos/Edit/{id}`  
  Envia os dados do formulário para atualizar um produto.

- **Excluir Produto (POST):**  
  `POST /Produtos/Delete/{id}`  
  Remove o produto do banco de dados.

## Considerações Finais

Este projeto tem como objetivo avaliar suas habilidades no desenvolvimento de uma aplicação simples com **ASP.NET Core** e **MySQL**. O foco está na clareza e organização do código, além da implementação correta das funcionalidades de CRUD.

**Dicas**:
- Use **Entity Framework Core** para realizar o mapeamento entre o modelo e o banco de dados.
- Garanta que a interface seja funcional e intuitiva, mesmo que o design seja simples.
- Trate adequadamente erros e validações no backend.
  
Boa sorte!
