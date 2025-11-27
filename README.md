# 🎬 Modelagem de Dados em Grafos de um Serviço de Streaming - Neo4j

Bem-vindo ao desafio de projeto **Modelagem de Dados com Neo4j**! 

Este repositório contém a solução para o desafio de modelagem de um banco de dados orientado a grafos, simulando um cenário real de um serviço de streaming (como Netflix ou Amazon Prime), focado nas relações entre **Filmes** e **Atores**.

## 🎯 Objetivo do Desafio

O objetivo é transformar uma ideia de negócio em um modelo orientado a grafos utilizando o **Neo4j**. Através deste desafio, exploramos:
- Criação de **Nós (Nodes)** representando entidades (Filmes e Pessoas).
- Criação de **Relacionamentos (Relationships)** que conectam essas entidades.
- Geração de script **Cypher** (A linguagem de consulta do Neo4j).

## 📊 O Modelo de Grafo

O diagrama abaixo ilustra a modelagem proposta. A ideia central é conectar atores aos filmes em que trabalharam, permitindo consultas como "Quais filmes Keanu Reeves atuou?" ou "Quem atuou em Matrix?".

![Diagrama do Grafo](./Modelagem_de_Dados_em_Grafos_de_um_servico_de_Streaming.png)

*(Certifique-se de que a imagem acima esteja na mesma pasta deste README)*

### Estrutura Visualizada:
* **Nós (Nodes):**
    * `Movie` (Filme): Títulos disponíveis no catálogo.
    * `Person` (Pessoa/Ator): Atores e atrizes.
* **Relacionamentos:**
    * `(:Person)-[:ACTED_IN]->(:Movie)`: Indica que uma pessoa atuou em um filme.

---

## 🛠️ Tecnologias Utilizadas

* **[Arrows.app](https://arrows.app/):** Ferramenta online utilizada para o desenho e modelagem visual do grafo.
* **Neo4j Desktop** ou **Neo4j Aura:** Banco de dados orientado a grafos.
* **Linguagem Cypher:** Linguagem de consulta para inserção e busca de dados.

---

## 🚀 Como Reproduzir o Desafio

Para recriar este grafo no seu ambiente Neo4j, execute o seguinte script Cypher:

### 1. Criando e Conectando os Nós

```cypher
// Criação dos Atores
CREATE (keanu:Person {name: "Keanu Reeves"})
CREATE (laurence:Person {name: "Laurence Fishburne"})
CREATE (carrie:Person {name: "Carrie-Anne Moss"})
CREATE (sandra:Person {name: "Sandra Bullock"})

// Criação dos Filmes
CREATE (matrix:Movie {title: "The Matrix"})
CREATE (johnWick:Movie {title: "John Wick"})
CREATE (speed:Movie {title: "Velocidade Máxima"})

// Criação dos Relacionamentos
CREATE (keanu)-[:ACTED_IN]->(matrix)
CREATE (keanu)-[:ACTED_IN]->(johnWick)
CREATE (keanu)-[:ACTED_IN]->(speed)
CREATE (laurence)-[:ACTED_IN]->(matrix)
CREATE (carrie)-[:ACTED_IN]->(matrix)
CREATE (sandra)-[:ACTED_IN]->(speed)
