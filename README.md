# 🚀 API RESTful de Gestão de Usuários e Pedidos (Spring Boot & JPA)

[![Java](https://img.shields.io/badge/Java-25-ED8B00?style=flat-square&logo=java&logoColor=white)](https://www.java.com/)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.X-6DB33F?style=flat-square&logo=spring&logoColor=white)](https://spring.io/projects/spring-boot)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=flat-square&logo=postgresql&logoColor=white)](https://www.postgresql.org/)

## 📌 Sobre o Projeto
Esta é uma API RESTful desenvolvida em Java com Spring Boot, focada no domínio de mapeamento objeto-relacional (ORM) e na construção de uma arquitetura limpa em camadas (Web, Service e Data).

O objetivo principal deste repositório não é apenas ter um CRUD, mas sim aplicar as **melhores práticas do mercado** no ecossistema Spring, incluindo tratamento global de exceções, modelagem de banco de dados e padronização de respostas HTTP.

## 🛠️ Tecnologias e Ferramentas
* **Java** (Linguagem principal)
* **Spring Boot** (Framework base)
* **Spring Data JPA & Hibernate** (Persistência de dados e ORM)
* **H2 Database** (Banco de dados em memória para testes rápidos e *seeding*)
* **PostgreSQL** (Banco de dados relacional para ambiente de desenvolvimento/produção)
* **Maven** (Gerenciamento de dependências)
* **Postman** (Testes de endpoints REST)

## 💡 Decisões Técnicas e Aprendizados (O Grande Diferencial)
Durante o desenvolvimento desta API, apliquei conceitos fundamentais para sistemas de alta performance:

* **Padrão Arquitetural REST:** Retornos HTTP estritamente semânticos. Exemplo: Ao criar um novo recurso (POST), a API retorna `201 Created` e injeta dinamicamente o URI do novo objeto no *header* `Location` da resposta, utilizando `ServletUriComponentsBuilder`.
* **Tratamento Global de Exceções:** Implementação do `@ControllerAdvice` e construção de um objeto `StandardError`. Em vez de vazar *stack traces* feias no servidor, a API intercepta erros (como tentar deletar um ID inexistente no banco) e retorna um JSON limpo e formatado com o status `404 Not Found`.
* **Separação de Ambientes (Profiles):** Configuração dos arquivos `application-test.properties` e `application-dev.properties` para alternar perfeitamente entre o banco H2 (para rodar testes de forma isolada) e o PostgreSQL (para persistência real de dados), resolvendo inclusive conflitos de palavras reservadas do SQL (ex: `@Table(name = "tb_user")`).

## ⚙️ Como executar o projeto na sua máquina

1. Clone este repositório:
   ```bash
   git clone [https://github.com/RodsonSSJunior/API-RESTful-de-Gestao-de-Utilizadores-e-Pedidos-SpringBoot-e-PostgreSQL.git](https://github.com/RodsonSSJunior/API-RESTful-de-Gestao-de-Utilizadores-e-Pedidos-SpringBoot-e-PostgreSQL.git)
   Importe o projeto na sua IDE de preferência (IntelliJ, Eclipse, VS Code).

2. Passo crucial para o banco de dados: Abra o seu SGBD (pgAdmin, DBeaver, etc.) e crie um banco de dados PostgreSQL vazio chamado springboot_course.

3. Verifique as credenciais: No arquivo src/main/resources/application.properties, confirme se as variáveis spring.datasource.username e spring.datasource.password correspondem ao seu usuário e senha locais do Postgres.

4. Atualize as dependências do Maven.

5. Execute a classe principal da aplicação. O Hibernate vai se encarregar de criar as tabelas (ddl-auto=update) e a API estará disponível em http://localhost:8080.
