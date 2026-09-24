Markdown# 🚀 API REST — Sistema de Cadastro de Usuários

[![Java](https://img.shields.io/badge/Java-17-orange.svg)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-brightgreen.svg)](https://spring.io/projects/spring-boot)

Uma API RESTful desenvolvida em **Java 17** utilizando a plataforma **Spring Boot** para o ecossistema de gestão e cadastro de utilizadores. O projeto implementa operações completas de CRUD (Create, Read, Update, Delete), validações de dados únicos e persistência em base de dados em memória.

---

## 📌 Tabela de Conteúdos

- [Sobre o Projeto](#-sobre-o-projeto)
- [Arquitetura do Sistema](#-arquitetura-do-sistema)
- [Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [Endpoints da API](#-endpoints-da-api)
- [Como Executar o Projeto](#-como-executar-o-projeto)
- [Acesso ao H2 Console](#-acesso-ao-h2-console)
- [Tratamento de Exceções](#-tratamento-de-exceções)

---

## 💻 Sobre o Projeto

A aplicação foi desenvolvida com o intuito de estruturar uma solução eficiente e modular para a criação e gestão de contas de utilizadores. 

### Principais Características:
- **Separação de Responsabilidades:** Arquitetura dividida em Camadas (*Controller*, *Service*, *Repository* e *Entities*).
- **Validação de Unicidade:** Garantia de que não existem e-mails duplicados registados na base de dados (`unique = true`).
- **Persistência Dinâmica:** Integração com Spring Data JPA e Hibernate para mapeamento objeto-relacional.

---

## 🏗️ Arquitetura do Sistema

O projeto segue o padrão de arquitetura em camadas tradicional do Spring:

```text
com.gust.Cadastro_usuario
 ├── controller/           # Endpoints HTTP da API (REST)
 ├── regrasDeNegocio/      # Regras de negócio da aplicação (Service)
 └── infrastructure/
      ├── entitys/         # Mapeamento de Entidades JPA
      └── repository/     # Interfaces de acesso à base de dados (Spring Data)

## 🛠️ Tecnologias Utilizadas

- **Linguagem:** Java 17
- **Framework Principal:** Spring Boot 3
- **Persistência de Dados:** Spring Data JPA / Hibernate
- **Banco de Dados (Dev):** H2 Database (In-Memory)
- **Utilitários:** Lombok (Injeção de dependências e eliminação de código boilerplate)
- **Gerenciador de Dependências:** Apache Maven

---

## 🔗 Endpoints da API

Abaixo estão listadas as rotas disponíveis na aplicação:

| Método | Endpoint | Descrição | Parâmetros / Body |
| :--- | :--- | :--- | :--- |
| `POST` | `/usuario` | Cadastra um novo usuário | Body JSON (`nome`, `email`) |
| `GET` | `/usuario` | Busca um usuário por e-mail | Query Param (`?email=...`) |
| `PUT` | `/usuario` | Atualiza os dados de um usuário | Query Param (`?id=...`) + Body JSON |
| `DELETE` | `/usuario` | Deleta um usuário por e-mail | Query Param (`?email=...`) |

### 🧪 Exemplos de Requisição

#### Criar Usuário (`POST /usuario`)

**Body (JSON):**
```json
{
  "id": 1,
  "nome": "Gustavo Tavares",
  "email": "gustavo@email.com"
}
## 🚀 Como Executar o Projeto

### Pré-requisitos
- **JDK 17** ou superior instalado.
- **Maven** configurado (ou utilização do wrapper `./mvnw` do projeto).
- Ferramenta para testes de API (**Postman**, **Insomnia** ou **HTTPie**).

### Passos de Instalação

1. Clone este repositório para a sua máquina local:
   ```bash
   git clone [https://github.com/SEU-USUARIO/Cadastro-usuario.git](https://github.com/SEU-USUARIO/Cadastro-usuario.git)
