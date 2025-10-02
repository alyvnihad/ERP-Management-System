# ERP Management System

![GitHub Workflow Status](https://img.shields.io/badge/build-passing-brightgreen) ![Language](https://img.shields.io/badge/language-Java-red) ![Microservices](https://img.shields.io/badge/microservices-SpringBoot-orange)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-orange) ![RestTemplate](https://img.shields.io/badge/RestTemplate-blueviolet) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-blue)

A **microservices-based, fully modular ERP system** designed to manage customers, products, orders, and sales reports for enterprises. Built for high performance, security, and scalability.  

---

## Microservices

The system consists of **5 main microservices**:

| Service | Description | GitHub Link |
| ------- | ----------- | ----------- |
| API Gateway | Routing, load balancing, and security for all services | [API Gateway](https://github.com/alyvnihad/API-Gateway) |
| AuthService | User registration, login, and authentication | [Auth Service](https://github.com/alyvnihad/Auth-Service) |
| InventoryService | Customer and product management, stock updates | [Inventory Service](https://github.com/alyvnihad/Inventory-Service) |
| OrderService | Order management, PDF invoices, email notifications | [Order Service](https://github.com/alyvnihad/Order-Service) |
| ReportService | Sales reports, analytics, and Excel export | [Report Service](https://github.com/alyvnihad/Report-Service) |

---

## Architecture

**ERP System Architecture**

**Flow:**  

1. API Gateway handles all incoming requests.  
2. AuthService manages authentication and JWT tokens.  
3. InventoryService manages products, customers, and stock updates via RabbitMQ.  
4. OrderService handles orders, generates PDF invoices (iText), and sends emails.  
5. ReportService generates sales reports (Apache POI) and stores analytics.  

***Event-driven communication** ensures stock updates and sales reporting are asynchronous and scalable.*  

---

## Key Features

### API Gateway

- Load balancing and routing  
- Authentication and security for all endpoints  
- Microservice monitoring and logging  

### AuthService

- User registration and login  
- JWT-based authentication  
- Access token refresh mechanism  

### InventoryService

- Full CRUD for customers and products  
- Email-based customer search and validation  
- Stock updates via RabbitMQ consumer  

### OrderService

- Create and manage orders  
- Generate PDF invoices automatically  
- Send emails with order details  
- Check product stock via InventoryService  
- Event-driven stock reduction  

### ReportService

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
   1. AuthService  
   2. InventoryService  
   3. OrderService  
   4. ReportService  
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


