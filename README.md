# Microservice LSIM

Este é um projeto de microsserviços que implementa um sistema de pedidos e pagamentos. O projeto utiliza Spring Cloud para gerenciamento dos microsserviços e inclui um servidor Eureka para service discovery, um API Gateway para roteamento, e serviços de pedidos e pagamentos.

## Arquitetura

O projeto é composto por 4 microsserviços:

- **server-lsim**: Servidor Eureka para service discovery (porta 8761)
- **gateway-lsim**: API Gateway para roteamento de requisições (porta 8762)
- **pedidos-lsim**: Serviço de gerenciamento de pedidos (porta dinâmica)
- **pagamentos-lsim**: Serviço de gerenciamento de pagamentos (porta dinâmica)

## Pré-requisitos

- Git
- Docker
- Docker Compose

## Como executar

1. Clone o repositório:

```bash
git clone @https://github.com/WellysonP/microservice-lsim.git
```

2. Entre no diretório do projeto:
   
```bash
cd microservice-lsim
```
3. Inicialize os submódulos:
   
```bash
git submodule init
```

4. Atualize os submódulos:
   
```bash
git submodule update
```

5. Inicie os containers:
   
```bash
docker compose up
```


## Acessando os Serviços

Após iniciar os containers, você pode acessar:

- **Eureka Server**: http://localhost:8761
- **Swagger UI**: http://localhost:8762/docs/swagger
- **API Gateway**: http://localhost:8762

### Endpoints Principais

#### Pagamentos
- GET `/pagamentos` - Lista todos os pagamentos
- GET `/pagamentos/{id}` - Busca pagamento por ID
- POST `/pagamentos` - Cria novo pagamento
- PUT `/pagamentos/{id}` - Atualiza pagamento
- DELETE `/pagamentos/{id}` - Remove pagamento
- PATCH `/pagamentos/{id}/confirmar` - Confirma pagamento

#### Pedidos
- GET `/pedidos` - Lista todos os pedidos
- GET `/pedidos/{id}` - Busca pedido por ID
- POST `/pedidos` - Cria novo pedido
- PUT `/pedidos/{id}/status` - Atualiza status do pedido
- PUT `/pedidos/{id}/pago` - Marca pedido como pago

## Banco de Dados

O projeto utiliza MySQL como banco de dados. As configurações podem ser encontradas no arquivo `docker-compose.yml`.

- **Database**: MySQL
- **Porta**: 3306
- **Usuário**: root
- **Senha**: mysql
- **Bancos**:
  - lsimfood-pagamentos
  - lsimfood-pedidos

## Documentação

A documentação completa da API está disponível através do Swagger UI em:
http://localhost:8762/docs/swagger

## Tecnologias Utilizadas

- Spring Boot
- Spring Cloud
- Spring Cloud Gateway
- Netflix Eureka
- Spring Data JPA
- MySQL
- Docker
- Swagger/OpenAPI
- Gradle/Maven
- Flyway Migration

## Estrutura do Projeto

```
microservice-lsim/
├── server-lsim/ # Servidor Eureka
├── gateway-lsim/ # API Gateway
├── pagamentos-lsim/ # Serviço de Pagamentos
├── pedidos-lsim/ # Serviço de Pedidos
└── docker-compose.yml
```


## Contribuindo

Para contribuir com o projeto:

1. Faça um fork do repositório
2. Crie uma branch para sua feature (`git checkout -b feature/nova-feature`)
3. Commit suas mudanças (`git commit -am 'Adiciona nova feature'`)
4. Push para a branch (`git push origin feature/nova-feature`)
5. Crie um Pull Request

## Licença

Este projeto está sob a licença MIT.