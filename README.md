# 🧾 PFA Go - Processador de Pedidos

Este projeto é uma aplicação desenvolvida em Go que processa pedidos recebidos via RabbitMQ, calcula o valor final com base em impostos, persiste os dados em um banco MySQL 
e disponibiliza um endpoint HTTP para consulta do total acumulado.

---

## 🚀 Funcionalidades

- 🧮 Calcula o valor final dos pedidos com imposto
- 🐇 Escuta mensagens da fila RabbitMQ
- 🗃️ Armazena pedidos em banco de dados MySQL
- 🌐 Endpoint HTTP `/total` para consulta do total de pedidos processados
- 🧵 Suporte a múltiplos workers (concorrência com Goroutines)

---

## 🧰 Tecnologias utilizadas

- [Go](https://golang.org/)
- [RabbitMQ](https://www.rabbitmq.com/)
- [MySQL](https://www.mysql.com/)
- [Docker](https://www.docker.com/) (opcional)
- `amqp091-go`, `database/sql`

---

## 📦 Estrutura do projeto

```bash

├── cmd/
│   └── consumer/        # Worker principal que escuta fila e processa pedidos
├── internal/
│   └── order/
│       ├── entity/      # Entidades de domínio
│       ├── infra/       # Implementação da infraestrutura (ex: banco de dados)
│       └── usecase/     # Casos de uso (regras de negócio)
├── pkg/
│   └── rabbitmq/        # Código de integração com RabbitMQ
├── go.mod
└── README.md
