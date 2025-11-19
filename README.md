# 🎬 Ontologia de Filmes – Linked Data & DBpedia

Esta ontologia foi projetada para representar o domínio cinematográfico de forma estruturada e semântica, utilizando o padrão **OWL**. teve como principal objetivo criar um modelo que abranja as principais entidades e relacionamentos do mundo dos filmes, possibilitando a integração com dados abertos via **DBpedia**.

A ontologia é útil para:
- Sistemas de recomendação de filmes
- Análise semântica de filmes e sua produção
- Criação de bases de conhecimento sobre filmes e produções cinematográficas

---

##  Objetivo

O objetivo principal dessa ontologia é representar o conhecimento sobre filmes, suas produções, atores, diretores, estúdios, gêneros e prêmios, além de estabelecer uma **integração com o DBpedia**. Essa ontologia é uma ferramenta que permite trabalhar com dados abertos na Web Semântica e pode ser usada em diversos contextos, como:

- **Consultas** para explorar dados relacionados a filmes.
- **Análise e visualização de grafos** com ferramentas de Web Semântica.
- **Integração com outras ontologias** e fontes de dados externas.

---

##  Escopo

A ontologia cobre os seguintes conceitos e suas relações:

- **Filmes**: Obras cinematográficas, incluindo detalhes como título, ano de lançamento, duração, orçamento, e sinopse.
- **Pessoas**: Indivíduos envolvidos na produção de filmes, como atores, diretores, produtores, roteiristas e editores.
- **Estúdios**: Empresas responsáveis pela produção e distribuição de filmes.
- **Gêneros**: Categorias de filmes como ação, comédia, drama, ficção científica, entre outros.
- **Prêmios**: Reconhecimentos importantes concedidos a filmes e pessoas, como o Oscar.

Além disso, a ontologia permite o relacionamento entre essas entidades, como "um ator atuou em um filme", "um diretor dirigiu um filme", "um filme pertence a um gênero", etc.

---

##  Estrutura de Classes

### ** Cclasses Principais **
1. **Filme**: A classe principal para obras cinematográficas.
2. **Pessoa**: Para representar indivíduos envolvidos na produção, como atores, diretores, produtores e roteiristas.
3. **Estúdio**: Para representar estúdios de produção e distribuidoras de filmes.
4. **Gênero**: Para categorizar os filmes em diferentes tipos de gênero.
5. **Prêmio**: Para representar prêmios cinematográficos importantes.

### **Subclasses**
Cada classe principal possui subclasses para detalhar mais aspectos específicos:
- **Filme**: `FilmeLongaMetragem`, `FilmeCurtaMetragem`, `Documentário`, `SérieDeTV`.
- **Pessoa**: `Ator`, `Diretor`, `Produtor`, `Roteirista`, `Editor`.
- **Estúdio**: `EstudioDeProducao`, `Distribuidora`.
- **Gênero**: `Ação`, `Comédia`, `Drama`, `Suspense`, `Ficção Científica`, `Terror`.
- **Prêmios**: `Oscar`, `GloboDeOuro`, `PalmaDeOuro`.

---

##  Propriedades da Ontologia

### **Data Properties (Atributos)**
- **Filme**: `temTituloOriginal`, `temDuracao`, `temAnoDeLancamento`, `temOrcamento`, `temSinopse`.
- **Pessoa**: `temNomeCompleto`, `temDataNascimento`, `temNacionalidade`.
- **Estúdio**: `temNomeDoEstudio`, `temAnoFundacao`.

### **Object Properties (Relacionamentos)**
- **dirigiu / foiDirigidoPor**: Relaciona um **Diretor** com um **Filme**.
- **atuouEm / temElenco**: Relaciona um **Ator** com um **Filme**.
- **escreveu / temRoteiro**: Relaciona um **Roteirista** com um **Filme**.
- **foiProduzidoPorEstudio / produziuFilme**: Relaciona um **Estúdio** com um **Filme**.
- **pertenceAoGenero / contemFilmeDoGenero**: Relaciona um **Filme** a um **Gênero**.
- **ganhouPremio / foiConcedidoA**: Relaciona um **Filme** ou **Pessoa** com um **Prêmio**.
- **ehSequenciaDe**: Relaciona um **Filme** com uma possível sequência de filmes.

---

##  Integração com DBpedia

A ontologia utiliza o DBpedia como fonte de dados externos para enriquecer e contextualizar as informações presentes nas classes e subclasses. As classes e indivíduos são relacionados ao DBpedia usando as propriedades `owl:equivalentClass` e `rdfs:seeAlso`.


A ontologia contém links para entidades reais, por exemplo:

| Classe | Link |
|--------|-----------------------------------|
| Filme | http://dbpedia.org/resource/Film |
| Ator | http://dbpedia.org/resource/Actor |
| Distribuidora | http://dbpedia.org/resource/Film_distributor |
| Ficção Científica | http://dbpedia.org/resource/Science_fiction_film |
| Oscar | http://dbpedia.org/resource/Academy_Awards |

Esses links permitem que a ontologia se conecte diretamente com a base de dados do DBpedia e utilize as informações presentes nesse repositório de dados abertos.

---



