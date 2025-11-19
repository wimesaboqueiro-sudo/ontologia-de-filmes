Ontologia de Filmes – Linked Data & DBpedia
Este repositório contém uma ontologia OWL completa para representar o domínio cinematográfico, incluindo filmes, pessoas envolvidas, gêneros, estúdios e premiações.
A ontologia segue princípios de Web Semântica, Linked Data e reutilização de vocabulários externos via DBpedia .

Objetivos
Representar semanticamente entidades do domínio de filmes.
Formar base para consultas SPARQL, análises semânticas e sistemas inteligentes.
Integrar conceitos com dados abertos (Linked Open Data), especialmente o "DBpedia".
Estrutura da Ontologia
Aulas Principais | # Subclasses |
---------------------|----------------------------------------------------------------------|

Filme | - FilmeLongaMetragem, FilmeCurtaMetragem, Documentário, SérieDeTV |
pessoa | - Ator, Diretor, Produtor, Roteirista, Editor |
Estúdio | - EstúdioDeProdução, Distribuidora |
Genero | - Ação, Comédia, Drama, Suspense, FiccaoCientifica, Terror |
Prêmio | - Oscar, GloboDeOuro, PalmaDeOuro |
Algumas classes principais e subclasses utilizam owl:equivalentClassou rdfs:seeAlsopara links diretos à DBpedia.

Integração com DBpedia
A ontologia contém links para entidades reais, por exemplo:

Classe	Link
Filme	http://dbpedia.org/resource/Film
Ator	http://dbpedia.org/resource/Actor
Distribuidora	http://dbpedia.org/resource/Film_distributor
Ficção Científica	http://dbpedia.org/resource/Science_fiction_film
Oscar	http://dbpedia.org/resource/Academy_Awards
Isso garante: ✔ interoperabilidade
✔ inferência multi-base
✔ compatibilidade com ferramentas semânticas

Propriedades Definidas
Propriedades de dados
temTituloOriginal
temDuração
temAnoDeLançamento
temOrçamento
temSinopse
temNomeCompleto
temDataNascimento
temNacionalidade
temNomeDoEstudio
Propriedades do objeto
/ foiDirigidoPor
em / temElenco
escrito / temRoteiro
foiProduzidoPorEstudio / produzidoFilme
pertenceAoGenero / contemFilmeDoGenero
ganhouPremio / foiCongA
éSequênciaDe
EstudioProd Distribuidora
Diagrama Visual da Ontologia
                            +----------------+
                          |     Premio     |
                          +----------------+
                          /      |       \
                  Oscar  GloboDeOuro   PalmaDeOuro

                               ^
                               |
+-----------+      +----------------+       +------------------+
|   Ator    |----> |     Filme      | <---- |     Diretor      |
+-----------+       \      ^      /         +------------------+
       \             \     |     /
        \             \    |    /
         \             \   |   /
      atuouEm         pertenceAoGenero
           \            /   |
            \          /    |
             v        v     v
          +----------------------+
          |        Genero        |
          +----------------------+
       /    |      |     |      \
   Acao  Comedia Drama Suspense FiccaoCientifica Terror


+-----------------------+      produz
|        Estudio        | <----------------- Filme
+-----------------------+
    /              \
EstudioProd   Distribuidora

                

Diagrama Descritivo
#Filme

Tem título, duração, orçamento etc.
Pertence a um gênero
Pode ser dirigido por diretores
Pode ter atores
Pode ganhar prêmios 
#Pode ser sequência de outro filme

#Pessoa Pode ser:
Ator
Diretor
Produtor
Roteirista
Editor #Pode ganhar sol

#Estudio
Pode produzir filmes
Pode distribuir filmes

#Gênero Agrupa filmes por tipo:
Ação
Comédia
Drama
Suspense
FiccaoCientifica
Terror
licença
Uso livre para fins acadêmicos e educacionais.
