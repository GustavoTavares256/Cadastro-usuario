Markdown# 🚀 API REST — Sistema de Cadastro de Usuários

[![Java](https://img.shields.io/badge/Java-17-orange.svg)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-brightgreen.svg)](https://spring.io/projects/spring-boot)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

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
- [Licença](#-licença)

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
🛠️ Tecnologias UtilizadasLinguagem: Java 17Framework Principal: Spring BootPersistência de Dados: Spring Data JPA / HibernateBase de Dados Dev: H2 Database (In-Memory)Utilitários: Lombok (Injeção de dependências e eliminação de código boilerplate)Gerenciador de Dependências: Apache Maven🔗 Endpoints da APIAbaixo estão listadas as rotas disponíveis na aplicação:MétodoEndpointDescriçãoParâmetros / BodyPOST/usuarioCadastra um novo utilizadorBody JSON (nome, email)GET/usuarioProcura um utilizador por e-mailQuery Param (?email=...)PUT/usuarioAtualiza os dados de um utilizadorQuery Param (?id=...) + Body JSONDELETE/usuarioElimina um utilizador por e-mailQuery Param (?email=...)Exemplos de Requisições1. Criar Utilizador (POST /usuario)Body (JSON):JSON{
  "nome": "Gustavo Tavares",
  "email": "gustavo@email.com"
}
Resposta (200 OK):JSON{
  "id": 1,
  "nome": "Gustavo Tavares",
  "email": "gustavo@email.com"
}
🚀 Como Executar o ProjetoPré-requisitosJDK 17 ou superior instalado.Maven configurado (ou utilização do wrapper ./mvnw).Ferramenta para testes de API (como Postman, Insomnia ou HTTPie).Passos de InstalaçãoClona este repositório para a tua máquina local:Bashgit clone [https://github.com/SEU-USUARIO/Cadastro-usuario.git](https://github.com/SEU-USUARIO/Cadastro-usuario.git)
Acede à pasta do projeto:Bashcd Cadastro-usuario
Compila e executa a aplicação via Maven:Bashmvn spring-boot:run
A API estará operacional no endereço: http://localhost:8080🗄️ Acesso ao H2 ConsolePara visualizar a base de dados em tempo real no navegador:Garante que a aplicação está em execução.NAVEGA até http://localhost:8080/h2-consolePreenche as credenciais conforme configurado no application.properties:JDBC URL: jdbc:h2:mem:usuarioUser Name: GustavoDevPassword: 12345Clica em Connect.⚠️ Tratamento de ExceçõesO sistema conta com validações internas contra violação de integridade. Tentativas de cadastrar um e-mail já existente resultam em restrição de integridade na base de dados, garantindo a consistência das informações.📄 LicençaEste projeto está sob a licença MIT. Consulta o ficheiro LICENSE para mais detalhes.Developed by Gustavo Tavares 🚀
