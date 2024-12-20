# Spring Boot Product API

Este é um projeto de exemplo de uma API RESTful para gerenciar produtos, construída com Spring Boot.

## Requisitos

- Java 21
- Maven
- PostgreSQL

## Configuração

1. Clone o repositório:
    ```sh
    git clone <URL_DO_REPOSITORIO>
    cd springboot
    ```

2. Configure o banco de dados PostgreSQL:
    - Crie um banco de dados chamado `products_api`.
    - Atualize as credenciais do banco de dados no arquivo [application.properties](http://_vscodecontentref_/0) se necessário.

3. Compile e execute o projeto:
    ```sh
    ./mvnw spring-boot:run
    ```

## Endpoints da API

### Criar um produto

- **URL:** `/products`
- **Método:** `POST`
- **Corpo da Requisição:**
    ```json
    {
        "name": "Nome do Produto",
        "value": 100.00
    }
    ```
- **Resposta de Sucesso:**
    ```json
    {
        "idProduct": "UUID",
        "name": "Nome do Produto",
        "value": 100.00
    }
    ```

### Listar todos os produtos

- **URL:** `/products`
- **Método:** `GET`
- **Resposta de Sucesso:**
    ```json
    [
        {
            "idProduct": "UUID",
            "name": "Nome do Produto",
            "value": 100.00
        }
    ]
    ```

### Obter um produto por ID

- **URL:** `/products/{id}`
- **Método:** `GET`
- **Resposta de Sucesso:**
    ```json
    {
        "idProduct": "UUID",
        "name": "Nome do Produto",
        "value": 100.00
    }
    ```
- **Resposta de Erro:**
    ```json
    {
        "message": "Product not found"
    }
    ```

### Atualizar um produto

- **URL:** `/products/{id}`
- **Método:** `PUT`
- **Corpo da Requisição:**
    ```json
    {
        "name": "Nome Atualizado",
        "value": 150.00
    }
    ```
- **Resposta de Sucesso:**
    ```json
    {
        "idProduct": "UUID",
        "name": "Nome Atualizado",
        "value": 150.00
    }
    ```
- **Resposta de Erro:**
    ```json
    {
        "message": "Product not found"
    }
    ```

### Deletar um produto

- **URL:** `/products/{id}`
- **Método:** `DELETE`
- **Resposta de Sucesso:**
    ```json
    {
        "message": "Product deleted successfully"
    }
    ```
- **Resposta de Erro:**
    ```json
    {
        "message": "Product not found"
    }
    ```

## Estrutura do Projeto

- [springboot](http://_vscodecontentref_/1): Contém o código principal da aplicação.
- [resources](http://_vscodecontentref_/2): Contém os recursos da aplicação, como o arquivo de configuração [application.properties](http://_vscodecontentref_/3).

## Dependências

As principais dependências utilizadas neste projeto são:

- Spring Boot Starter Data JPA
- Spring Boot Starter Validation
- Spring Boot Starter Web
- PostgreSQL Driver
- Spring Boot Starter Test
