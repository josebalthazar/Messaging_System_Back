# Messaging System

API REST desenvolvida com **Java e Spring Boot** com o objetivo de estudar e aplicar **boas práticas de desenvolvimento e Design Patterns**.

O principal foco deste projeto foi a implementação do **Factory Method** para trabalhar com diferentes providers de envio de mensagens.

## 🎯 Objetivo

O projeto simula um sistema capaz de enviar mensagens através de diferentes providers, como:

* 📧 E-mail
* 📱 SMS

A ideia foi evitar que a regra de negócio precisasse conhecer diretamente cada implementação de envio.

## 🏭 Factory Method

O **Factory Method** foi utilizado para centralizar a criação dos providers.

Em vez de criar diretamente uma implementação:

```java
EmailProvider provider = new EmailProvider();
```

a aplicação utiliza uma Factory responsável por decidir qual provider deve ser criado.

```text
                 ┌──────────────┐
                 │    Factory   │
                 └───────┬──────┘
                         │
              ┌──────────┴──────────┐
              │                     │
              ▼                     ▼
      EmailProvider           SmsProvider
              │                     │
              ▼                     ▼
         Spring Mail              Twilio
```

Dessa forma, a lógica responsável pelo envio depende de uma abstração, enquanto cada provider mantém sua própria implementação.

### Por que utilizei o Factory Method?

O objetivo foi praticar conceitos como:

* Separação de responsabilidades
* Baixo acoplamento
* Abstração
* Extensibilidade
* Princípios SOLID
* Design Patterns

A estrutura também facilita a adição de novos providers futuramente, por exemplo:

```text
WhatsAppProvider
PushNotificationProvider
TelegramProvider
```

sem precisar espalhar a lógica de criação desses objetos pela aplicação.

## 🛠️ Tecnologias

* Java
* Spring Boot
* Spring Data JPA
* PostgreSQL
* Spring Mail
* Twilio
* Maven
* OpenAPI / Swagger

## 🚀 Executando o projeto

Clone o repositório:

```bash
git clone https://github.com/josebalthazar/Messaging_System_Back.git
```

Entre no diretório:

```bash
cd Messaging_System_Back
```

Execute:

```bash
./mvnw spring-boot:run
```

No Windows:

```bash
mvnw.cmd spring-boot:run
```

## 📚 Sobre o projeto

Este projeto foi desenvolvido principalmente como um **exercício prático de arquitetura e Design Patterns**.

A implementação do Factory Method nos providers foi escolhida para entender, na prática, como um padrão de projeto pode ajudar a **desacoplar a criação de objetos da lógica que os utiliza**.

---

**José Rodrigo Balthazar**

[GitHub](https://github.com/josebalthazar)
