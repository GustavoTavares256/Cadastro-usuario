# Cadastro-usuario
API RESTful desenvolvida em Java 17 e Spring Boot para gerenciamento completo de usuários, com persistência em banco de dados H2 e integração JPA/Hibernate.

# 🚀 API REST — Sistema de Cadastro de Usuários

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
