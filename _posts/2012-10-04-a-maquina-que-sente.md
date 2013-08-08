---
layout: post
title: "A máquina que sente e as eleições"
date: 2012-10-04 9:41:00
categories: pesquisa
comments: true
---

Máquinas em geral são frias. Elas são ótimas em fazer tarefas repetitivas e exatas, atividades que os seres humanos não são tão bons em fazer. Por outro lado os seres humanos têm uma característica que passa longe das máquinas, a capacidade de ter e perceber sentimentos.

Será mesmo?

Antes de continuar falando em sentimentos preciso introduzir um outro assunto. As eleições.

Várias vezes as pesquisas de intenção de voto aqui na Paraíba foram questionadas. Quando alguém cita uma pesquisa desse tipo numa conversa sempre refutam "e quem acredita nessas pesquisas?".

Outro tipo de comentário que inspirou o que será apresentado a seguir era que algumas pessoas me falavam que as pesquisas não refletiam o que elas ouviam das pessoas nem o que elas viam em redes sociais. "Candidato X recebe tanto apoio nas redes sociais, mas está muito mal nas pesquisas."

Será que isso era realmente verdade? O que eu posso fazer para saber se as pessoas estão falando bem ou mal dos candidatos? Ou melhor, tem como medir o grau de positividade ou negatividade dos comentários?

Essas questões ficaram martelando na minha cabeça, até eu colocar as mãos e a mente para trabalhar.

Eu poderia usar diversas técnicas para saber o que estão falando de cada candidato. A mais simples seria pegar mensagens e classificar manualmente em bom ou ruim, técnica que é utilizada até hoje nas campanhas. Mas eu não iria fazer isso, primeiro eu não teria tempo, segundo seria muito chato e terceiro eu queria fazer o computador extrapolar suas tarefas frias e exatas e passar a entender sentimentos.

Isso pode parecer algo mágico ou longe da realidade para quem não conhece muito bem, mas a área de <a href="http://en.wikipedia.org/wiki/Sentiment_analysis" target="_blank">análise de sentimentos</a> já mostrou ser possível identificar sentimentos através de operações exatas.

Com isso, eu analisei alguns trabalhos e resolvi utilizar o <a href="http://sentic.net/" target="_blank">Senticnet</a>. Que resumidamente é um <a href="http://en.wikipedia.org/wiki/Resource_Description_Framework" target="_blank">RDF</a> com uma grande quantidade de palavras e expressões classificadas de acordo com uma polaridade que varia de 1 a -1. Onde, 1 é o mais positivo possível e -1 o mais negativo possível. Por exemplo, a expressão "friday night", algo bom, possui polaridade +0.728, já a palavra "monday", dia odiado por muita gente, tem valor -0.847.

Com o Senticnet eu tinha a possibilidade de classificar mensagens textuais de redes sociais em positivas e negativas e ainda saber se uma mensagem é mais positiva que a outra ou mais negativa. Eu fiz um experimento inicial para saber que tipo de resultado eu teria. Existem inúmeros pontos que podem ser melhorados no experimento e ele está longe de ser perfeito, mas mesmo assim compartilharei com vocês o que eu fiz e quais foram os resultados.

Ainda é muito fácil pegar texto de tweets através de uma query. A avalanche de dados do microblog é um prato cheio para pesquisadores, então eu aproveitei e usei os tweets como minha fonte de informação para saber o que as pessoas estava falando sobre os candidatos na eleição.

Eu coletei aproximadamente 300 tweets para cada candidato por dia durante 14 dias. A coleta era feita em 3 horários diferentes do dia, 100 tweets de cada vez. Vocês perceberão no gráfico mais abaixo que existe um salto do dia 13/09 para o dia 19/09. Isso aconteceu por alguns problemas técnicos que me impediram de coletar tweets. O número de 300 tweets por candidato não é exato, pois eu estava rodando a coleta manualmente e aconteceu de alguns dias eu conseguir rodar apenas 2 coletas.

Ao pegar um tweet, o texto era dividido de três em três palavras e para cada conjunto de três palavras era feita uma tentativa de classificação usando o Senticnet. Se a expressão fosse encontrada, o valor da polaridade era atribuído a ela e as três palavras eram removidas do texto. O mesmo processo era feito para conjuntos de duas e uma palavra. Para finalizar a classificação do tweet era tirada a média das polaridades encontradas.

O Senticnet traz expressões em inglês e eu estava coletando mensagens em português. Para resolver esse problema eu traduzi cada tweet do português para inglês usando a API do Bing. Eu fiquei preocupado com esse passo, mas a tradução de mensagens pequenas como tweets se mostrou boa.

O gráfico abaixo mostra o resultado das classificações. Os valores no eixo y são as médias das classificações de todos os tweets de um candidato num certo dia. E os valores no eixo x são os dias.

![Eleições de João Pessoa - Gráfico de polaridades]({{ site.url }}/images/eleicoes.png)

O interessante desse gráfico é que ele não reflete muito bem as pesquisas eleitorais. Isso significa que alguém está errado? Não necessariamente. O que podemos afirmar é que a opinião do público das redes sociais, mais especificamente o Twitter, está refletida no gráfico e que talvez as redes sociais não tenham um impacto tão significativo nas eleições da Paraíba.

Entretanto, existem dados no gráfico que confirmam pesquisas e outras métricas das redes sociais. Podemos perceber, por exemplo, a candidata Estela com uma polaridade média maior em quase todos os dias. Se formos analisar as páginas dos candidatos no Facebook a métrica "Pessoas falando sobre isto" de Estela é bem maior que a dos outros, ou seja, os eleitores dela são mais participativos nas redes sociais.

Outros pontos de destaque é o pico de mensagens positivas do candidato Cícero no dia 25/09, mesmo ele tendo os menores valores em vários dias. E a subida do candidato Luciano Cartaxo nos últimos dias, o que se mostrou uma tendência nas pesquisas eleitorais também.

Espero que tenham gostado do experimento e ficaria muito feliz com o feedback de vocês seja através de dúvidas, sugestões, etc.
