
# 🎓 EduCloud — MVP de Gestão Educacional

> 🌍 Available in: [Português](#português) | [English](#english) | [Français](#français)

![Java](https://img.shields.io/badge/Java-17-orange?logo=openjdk)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.x-brightgreen?logo=springboot)
![React](https://img.shields.io/badge/Frontend-React.js-blue?logo=react)
![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-316192?logo=postgresql)
![License](https://img.shields.io/badge/license-MIT-lightgrey)
![Status](https://img.shields.io/badge/status-MVP-blue)

---

### 🇧🇷 **Português**
🎓 **EduCloud — MVP de Gestão Educacional**  
EduCloud é um MVP de plataforma SaaS voltado para escolas e universidades, permitindo o gerenciamento de **alunos, professores, cursos e diplomas** de forma centralizada e segura.  
Desenvolvido com **Spring Boot**, **React.js** e **PostgreSQL**, o projeto adota uma arquitetura moderna baseada em **microserviços**, **DTOs** e **boas práticas de clean code**.

---

### 🇬🇧 **English**
🎓 **EduCloud — Educational Management MVP**  
EduCloud is a SaaS MVP designed for schools and universities, enabling centralized and secure management of **students, teachers, courses, and diplomas**.  
Built with **Spring Boot**, **React.js**, and **PostgreSQL**, the project follows a modern architecture using **microservices**, **DTOs**, and **clean code best practices**.

---

### 🇫🇷 **Français**
🎓 **EduCloud — MVP de Gestion Éducative**  
EduCloud est un MVP SaaS destiné aux écoles et universités, permettant la gestion centralisée et sécurisée des **étudiants, enseignants, cours et diplômes**.  
Développé avec **Spring Boot**, **React.js** et **PostgreSQL**, le projet adopte une architecture moderne basée sur les **microservices**, les **DTOs**, et les **bonnes pratiques de clean code**.

---

📂 **Structure du Projet / Project Structure**

classDiagram

## 🧱 Class Diagram — EduCloud MVP



# Arquitetura do SaaS Educacional

Este diagrama mostra a arquitetura completa do SaaS educacional, incluindo frontend, microservices, bancos de dados e mensageria.


```mermaid

flowchart TD
    %% ==========================
    %% FRONTEND
    %% ==========================
    A[Frontend React SPA] --> B[API Gateway]

    %% ==========================
    %% GATEWAY PARA MICROSERVICES
    %% ==========================
    B --> C[Identity Service]
    B --> D[Academic Service]
    B --> E[Payment Service]
    B --> F[Library Service]
    B --> G[Messaging Service]
    B --> H[Exam Service]
    B --> I[Diploma Service]
    B --> J[Enrollment Service]

    %% ==========================
    %% MICROSERVICES PARA SEUS BANCOS POSTGRESQL
    %% ==========================
    C --> CDB[(PostgreSQL: identitydb)]
    D --> DDB[(PostgreSQL: academicdb)]
    E --> EDB[(PostgreSQL: paymentdb)]
    F --> FDB[(PostgreSQL: librarydb)]
    G --> GDB[(PostgreSQL: messagingdb)]
    H --> HDB[(PostgreSQL: examdb)]
    I --> IDB[(PostgreSQL: diplomadb)]
    J --> JDB[(PostgreSQL: enrollmentdb)]

    %% ==========================
    %% MENSAGERIA (RabbitMQ / SQS / SNS)
    %% ==========================
    C --> MQ[Notification / Queue]
    D --> MQ
    E --> MQ
    F --> MQ
    G --> MQ
    H --> MQ
    I --> MQ
    J --> MQ
