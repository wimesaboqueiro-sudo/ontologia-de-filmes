# 🎬 Ontologia de Filmes – Linked Data & DBpedia

Esta ontologia foi projetada para representar o domínio cinematográfico de forma estruturada e semântica, utilizando o padrão **OWL**. Seu objetivo é criar um modelo que abranja as principais entidades e relacionamentos do mundo dos filmes, possibilitando a integração com dados abertos via **DBpedia**.

A ontologia é útil para:
- Sistemas de recomendação de filmes
- Análise semântica de filmes e sua produção
- Integração com dados abertos da Web Semântica
- Criação de bases de conhecimento sobre filmes e produções cinematográficas

---

##  Objetivo

O objetivo principal dessa ontologia é representar de forma explícita o conhecimento sobre filmes, suas produções, atores, diretores, estúdios, gêneros e prêmios, além de estabelecer uma **integração com o DBpedia**. Essa ontologia é uma ferramenta poderosa para trabalhar com dados abertos na Web Semântica e pode ser usada em diversos contextos, como:

- **Consultas SPARQL** para explorar dados relacionados a filmes.
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

### **Classes Principais**
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

### **Exemplos de Links para DBpedia**
- **Filme** → `http://dbpedia.org/resource/Film`
- **Ator** → `http://dbpedia.org/resource/Actor`
- **Diretor** → `http://dbpedia.org/resource/Film_director`
- **Gênero** → `http://dbpedia.org/resource/Film_genre`
- **Oscar** → `http://dbpedia.org/resource/Academy_Awards`

Esses links permitem que a ontologia se conecte diretamente com a base de dados do DBpedia e utilize as informações presentes nesse repositório de dados abertos.

---

##  Classes com Equivalências

Algumas classes da ontologia possuem equivalências com entidades externas, principalmente com o DBpedia. Exemplos de equivalências são:

- **Filme** → `http://dbpedia.org/resource/Film`
- **Ator** → `http://dbpedia.org/resource/Actor`
- **Diretor** → `http://dbpedia.org/resource/Film_director`

Isso permite a interconexão de dados entre a ontologia e o DBpedia, facilitando consultas e ampliando o escopo de informações que podem ser acessadas.

---

##  Instâncias Conectadas e Exemplos de Instâncias

A ontologia contém exemplos de instâncias conectadas, com filmes, pessoas, gêneros, e estúdios. Aqui estão alguns exemplos de instâncias:

### **Instância de Filme: Matrix**
```xml
<owl:NamedIndividual rdf:about="#Matrix">
  <rdf:type rdf:resource="#Filme"/>
  <temTituloOriginal>The Matrix</temTituloOriginal>
  <temDuracao rdf:datatype="http://www.w3.org/2001/XMLSchema#integer">136</temDuracao>
  <temAnoDeLancamento rdf:datatype="http://www.w3.org/2001/XMLSchema#gYear">1999</temAnoDeLancamento>
  <pertenceAoGenero rdf:resource="#FiccaoCientifica"/>
</owl:NamedIndividual>
Instância de Pessoa: Keanu Reeves
xml
Copiar código
<owl:NamedIndividual rdf:about="#KeanuReeves">
  <rdf:type rdf:resource="#Ator"/>
  <temNomeCompleto>Keanu Reeves</temNomeCompleto>
</owl:NamedIndividual>
Instância de Estúdio: Warner Bros
xml
Copiar código
<owl:NamedIndividual rdf:about="#WarnerBros">
  <rdf:type rdf:resource="#EstudioDeProducao"/>
  <temNomeDoEstudio>Warner Bros</temNomeDoEstudio>
</owl:NamedIndividual>
Instância de Gênero: Ficção Científica
xml
Copiar código
<owl:NamedIndividual rdf:about="#FiccaoCientifica">
  <rdf:type rdf:resource="#Genero"/>
  <rdfs:label>Ficção Científica</rdfs:label>
</owl:NamedIndividual>
Essas instâncias são exemplos do uso da ontologia para representar filmes, atores, estúdios e gêneros de forma padronizada.
