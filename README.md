# 🚀 API RESTful de E-commerce e Gestão de Vendas

[![Java](https://img.shields.io/badge/Java-25-ED8B00?style=flat-square&logo=java&logoColor=white)](https://www.java.com/)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.4.2-6DB33F?style=flat-square&logo=spring&logoColor=white)](https://spring.io/projects/spring-boot)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=flat-square&logo=postgresql&logoColor=white)](https://www.postgresql.org/)

## 📌 Sobre o Projeto
Esta é uma API RESTful robusta desenvolvida para gerenciar o ecossistema de um e-commerce. O projeto foca na aplicação de padrões de projeto modernos, arquitetura limpa em camadas (Web, Service e Data) e mapeamento objeto-relacional (ORM) complexo.

O sistema gerencia as entidades **Usuários, Pedidos, Produtos e Categorias**, garantindo a integridade dos dados e a eficiência nas operações de banco de dados.

## 🛠️ Tecnologias e Ferramentas
* **Java 25** (Utilizando as funcionalidades mais recentes da linguagem)
* **Spring Boot 3.x** (Web, Data JPA)
* **PostgreSQL** (Persistência relacional em produção)
* **H2 Database** (Ambiente de testes e seeding de dados)
* **Hibernate** (Implementação do JPA para ORM)
* **Maven** (Gerenciador de dependências)

## 💡 Diferenciais Técnicos e Aprendizados
Diferente de um CRUD comum, este projeto implementa estratégias de nível profissional:

* **Otimização com Proxies JPA:** No fluxo de atualização (`update`), utilizei `getReferenceById` para instanciar objetos via proxy, evitando consultas `SELECT` desnecessárias e melhorando a performance da aplicação.
* **Segurança na Camada de Serviço:** Implementação de lógica de proteção de dados no `updateData`, garantindo que campos sensíveis como IDs e senhas não sejam alterados via endpoints públicos.
* **Tratamento Global de Exceções:** Uso de `@ControllerAdvice` para capturar exceções customizadas (`ResourceNotFoundException`, `DatabaseException`) e retornar respostas HTTP semânticas (404, 400) em formato JSON padronizado.
* **Arquitetura Escalável:** Separação estrita de responsabilidades, facilitando a manutenção e a futura expansão para microsserviços.

## 🚧 Status do Projeto: Work in Progress
A infraestrutura e o domínio completo já estão modelados. Atualmente:
- ✅ **User:** CRUD completo e validado.
- 🔄 **Orders/Products/Categories:** Entidades e relacionamentos mapeados; endpoints em fase de implementação.

## ⚙️ Como executar
1. Clone o repositório.
2. Crie um banco PostgreSQL chamado `springboot_course`.
3. Verifique as credenciais no `application-dev.properties`.
4. Execute a aplicação e acesse `http://localhost:8080/users`.
