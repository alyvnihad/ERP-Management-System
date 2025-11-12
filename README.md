# ERP Management System

![GitHub Workflow Status](https://img.shields.io/badge/build-passing-brightgreen) ![Language](https://img.shields.io/badge/language-Java-red) ![Framework](https://img.shields.io/badge/framework-SpringBoot-green)
![RestTemplate](https://img.shields.io/badge/RestTemplate-darkgreen) ![Event Driven](https://img.shields.io/badge/eventdriven-RabbitMQ-orange)  ![PostgreSQL](https://img.shields.io/badge/database-PostgreSQL-blue)

A **microservices-based, fully modular ERP system** designed to manage customers, products, orders, and sales reports for enterprises. Built for high performance, security, and scalability.  

---

## Microservices

The system consists of **5 main microservices**:

| Service | Description | GitHub Link |
| ------- | ----------- | ----------- |
| API Gateway | Routing, load balancing, and security for all services | [API Gateway](https://github.com/alyvnihad/API-Gateway) |
| Auth Service | User registration, login, and authentication | [Auth Service](https://github.com/alyvnihad/Auth-Service) |
| Inventory Service | Customer and product management, stock updates | [Inventory Service](https://github.com/alyvnihad/Inventory-Service) |
| Order Service | Order management, PDF invoices, email notifications | [Order Service](https://github.com/alyvnihad/Order-Service) |
| Report Service | Sales reports, analytics, and Excel export | [Report Service](https://github.com/alyvnihad/Report-Service) |

---

## Architecture

**ERP System Architecture**

**Flow:**  

1. API Gateway handles all incoming requests.  
2. Auth Service manages authentication and JWT tokens.  
3. Inventory Service manages products, customers, and stock updates via RabbitMQ.  
4. Order Service handles orders, generates PDF invoices (iText), and sends emails.  
5. Report Service generates sales reports (Apache POI) and stores analytics.  

***Event-driven communication** ensures stock updates and sales reporting are asynchronous and scalable.*  

---

## Key Features

### API Gateway

- Load balancing and routing  
- Authentication and security for all endpoints  
- Microservice monitoring and logging  

### Auth Service

- User registration and login  
- JWT-based authentication  
- Access token refresh mechanism  

### Inventory Service

- Full CRUD for customers and products  
- Email-based customer search and validation  
- Stock updates via RabbitMQ consumer  

### Order Service

- Create and manage orders  
- Generate PDF invoices automatically  
- Send emails with order details  
- Check product stock via InventoryService  
- Event-driven stock reduction  

### Report Service

- Generate top 10 selling products report  
- Monthly sales reports  
- Export Excel reports using Apache POI  

---

## Technologies

- **Spring Boot** – Microservices framework  
- **Spring Data JPA** – Database operations  
- **RabbitMQ** – Event-driven communication  
- **iText** – PDF invoice generation  
- **Apache POI** – Excel reporting  
- **RestTemplate** – HTTP calls between microservices  
- **JavaMailSender** – Email sending  
- **PostgreSQL** – Database  

---

## Installation

1. Configure `application.properties` for each service (port, DB, credentials).  
2. Start PostgreSQL and RabbitMQ.  
3. Start microservices in order:  
   1. Auth Service  
   2. Inventory Service  
   3. Order Service  
   4. Report Service  
   5. API Gateway  
4. Access endpoints through API Gateway.  

---

## Security & Performance

- JWT token-based authentication  
- Role-based access control  
- Asynchronous operations via event-driven communication  
- Built-in monitoring and logging infrastructure  

---

## License

*This project you are free to use, modify, and distribute the code, but the **author retains copyright**.* 


