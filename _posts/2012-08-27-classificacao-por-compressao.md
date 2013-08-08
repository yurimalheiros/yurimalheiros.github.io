---
author: yuriadmin
comments: true
date: 2012-08-27 12:00:06+00:00
layout: post
slug: classificacao-por-compressao
title: Classificação por compressão
wordpress_id: 355
categories:
- inteligência artificial
---

Apesar de não parecer existir relação alguma ente comprimir e classificar dados, essa técnica na verdade é conhecida e bastante estudada, e faz muito sentido se a gente lembrar que compressão tem a ver com [teoria da informação](http://pt.wikipedia.org/wiki/Teoria_da_informa%C3%A7%C3%A3o). Eu mesmo já usei desse conhecimento para conseguir classificar texto.

O que eu nunca tinha feito era procurar uma forma que fosse simples para mostrar a técnica funcionando e que qualquer pessoa pudesse testar rapidamente. Até que recentemente assistindo vídeos da [ai-class.org](http://ai-class.org) eu vi o [Norvig](http://norvig.com/bio.html) fazendo um experimento de classificação com o gzip. A seguir eu vou mostrar um exemplo parecido, mas levemente modificado.

Nesse exemplo nós vamos tentar descobrir em que idioma um texto foi escrito usando o gzip direto na linha de comando. Para isso precisamos de duas coisas: textos para ensinar o computador idiomas e os textos que queremos classificar, ou seja, que queremos saber em que idioma foi escrito.

Vamos usar três idiomas: português, inglês e alemão. Para os textos de treinamento que vão ensinar o computador eu copiei parágrafos de notícias do G1 (português), New York Times (inglês) e DW (alemão), e colei em arquivos separados para cada idioma. Já para a classificação eu usarei parágrafos da biografia de Isaac Asimov tirados da Wikipédia.

Notem que não foi feita nenhuma escolha complicada dos textos, eu simplesmente peguei exemplos em cada um dos idiomas e vou usá-los para treinar e classificar. A única ressalva é quanto o tamanho dos arquivos de texto, para não influenciar no resultado da compressão eu limitei todos a aproximadamente 1000 caracteres.

Os arquivos de treinamento se chamam PT, EN e DE, respectivamente para os idiomas português, inglês e alemão. E os que serão classificados são ex-PT, ex-EN e ex-DE. Os arquivos que eu usei podem ser encontrados aqui: https://gist.github.com/3478618.

Depois disso só precisamos de algumas linhas de bash script para fazer o classificador funcionar.

```bash
`echo classificando texto em ingles:
(echo `cat EN ex-EN | gzip | wc -c` EN; \
echo `cat DE ex-EN | gzip | wc -c` DE; \
echo `cat PT ex-EN | gzip | wc -c` PT) \
| sort -n

echo
echo classificando texto em alemao:
(echo `cat EN ex-DE | gzip | wc -c` EN; \
echo `cat DE ex-DE | gzip | wc -c` DE; \
echo `cat PT ex-DE | gzip | wc -c` PT) \
| sort -n

echo
echo classificando texto em portugues:
(echo `cat EN ex-PT | gzip | wc -c` EN; \
echo `cat DE ex-PT | gzip | wc -c` DE; \
echo `cat PT ex-PT | gzip | wc -c` PT) \
| sort -n
`
```

A saída exibe a classificação para cada um dos idiomas. A lista apresentada mostra em cada linha o número de caracteres do arquivo comprimido e o idioma usado para aquela compressão. Isso significa que o primeiro da lista, ou seja, o que tiver menos caracteres como resultado da compressão é o idioma mais parecido com o texto que está sendo classificado.

A ideia por trás desse classificador é a seguinte. Quanto maior for a compressão da concatenação entre o arquivo de treinamento e o classificado, então mais parecido eles são. Dado que textos escritos num idioma em comum são mais parecidos entre si que textos de idiomas diferentes, então é possível classificá-los usando essa abordagem.

E por que a compressão entre textos mais parecidos é maior? Bom, os compressores costumam procurar padrões nos arquivos que se repetem para poder comprimir mais. Então se no texto a ser classificado existem muitos padrões que se repetem no texto de treinamento, o compressor vai conseguir comprimir mais. De fato é fácil perceber que existem muito mais padrões em comum entre textos de idiomas iguais que de idiomas diferentes. Um exemplo simples de padrão que se repete são as palavras, pois existem palavras exclusivas, ou que são mais frequentes, em cada idioma.

Façam alguns testes com diferentes textos, é interessante ver como os arquivos de treinamento podem influenciar. Também testem classificações diferentes, não precisa ser apenas classificação de idiomas, é possível, por exemplo, pegar notícias de esporte, política e sobre celebridades e tentar classificar em que categoria um texto se encaixa. Vale alertar que nem sempre o classificador acertará tudo, principalmente um classificador simples como esse apresentado.

