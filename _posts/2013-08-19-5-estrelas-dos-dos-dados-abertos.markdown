---
layout: post
title: 5 estrelas dos dados abertos
date: 2013-08-19 13:00:00
comments: true
---

Vários países têm aberto inúmeros dados importantes tornando o governo mais transparente para a população, dando poder para as pessoas consiguerem analisar os dados e poderem criar as mais diversas aplicações e visualizações.

As possibilidades são grandes e as vantagens para a população também, mas para que seja possível fazer algo, o governo precisa colaborar primeiro. Não adianta ter desenvolvedores, designers e cientistas juntos se não existir a base para o trabalho, ou seja, os dados.

[Tim Berners-Lee](http://en.wikipedia.org/wiki/Tim_Berners-Lee), o pai da web, criou um modelo para classificar dados abertos publicados. Este modelo é conhecido como o [modelo das 5 estrelas](http://5stardata.info/), onde dados com 1 estrela estão na forma mais pobre e simples e dados com 5 estrelas são mais ricos e complexos.

A classificação proposta pelo Berners-Lee é a seguinte:

- ★ : dados disponíveis na web (não importa o formato) sob uma licença aberta. Por exemplo, um PDF.
- ★ ★ : dados disponíveis de forma estruturada. Por exemplo, um arquido Excel.
- ★ ★ ★ : dados disponíveis em formatos não-proprietários. Por exemplo, um CSV.
- ★ ★ ★ ★ : use URIs para denotar os dados, assim outras pessoas podem criar links para eles. Por exemplo, um RDF.
- ★ ★ ★ ★ ★ : link os seus dados a outros. Por exemplo, um RDF que tenha links para outros RDF.

O trabalho de publicar os dados até a terceira estrela é simples e o esforço é praticamente o mesmo. Faz pouco sentido publicar dados num arquivo .xlsx, quando o próprio Excel pode salvar como .csv. Então, quem estiver publicando dados abertos, por favor, faça com que eles tenham pelo menos 3 estrelas. As pessoas que estiverem usando vão agradecer e mais aplicações serão criadas usando esses dados.

Para publicar dados com 4 ou 5 estrelas é necessário ter um conhecimento extra. Criar um RDF já não é tão simples quanto criar um arquivo CSV. E, para criar RDFs com links é necessário também conhecer outras fontes de dados. Não é por acaso que ainda temos muitos dados abertos com no máximo 3 estrelas.

Por outro lado, RDFs com links fornecem um poder muito maior para quem os utiliza, pois, além de ter os dados, também é possível navegar por eles e descobrir informações e relações totalmente novas. Por exemplo, você pode ter um RDF com dados de todos os prefeitos do seu estado e que um dos dados disponíveis para cada prefeito é a sua cidade natal. O RDF pode trazer um link fazendo referência à cidade, que se for seguido, fornecerá dados sobre ela, por exemplo, o estado que ela pertence e a sua população. Dessa forma, apenas publicando os dados do prefeito e seus respectivos links, seria possível ter informação suficiente para separar os prefeitos que são nascidos no mesmo estado da cidade que governa ou saber se a maioria dos prefeitos são de cidades grandes (com mais de 1 milhão de habitantes), entre muitas outras possibilidades.

RDFs com links (dados ligados) são a base da web semântica.

Infelizmente ainda é difícil conseguir dados abertos em várias cidades do Brasil, mesmo com apenas 1 estrela. Entretanto, temos bons exemplos de dados ligados em outras áreas. Uma das maiores bases de dados é o [Freebase](http://www.freebase.com/), mantido pelo Google. Naveguem nele
para sentir um pouco do poder de ter dados 5 estrelas. Outra opção é a [DBpedia](http://dbpedia.org/).
