---
layout: post
title: Análise dos posts do grupo "Fui Assaltado - Grande João Pessoa"
date: 2015-07-21 11:00:00
comments: true
---

O grupo do Facebook "Fui Assaltado - Grande João Pessoa" é utilizado pelos usuários para relatar assaltos e outros crimes violentos ocorridos na capital da Paraíba. Com o crescimento da violência, fiquei curioso para saber quais bairros ou outros pontos de referência da cidade são os maiores alvos dos criminosos.

Assim, eu resolvi coletar todos os posts do grupo do Facebook e procurar nomes de bairros e lugares conhecidos de João Pessoa para ter uma ideia geral de onde os crimes estão acontecendo.

O primeiro passo foi coletar as mensagens do Facebook usando a biblioteca [Facebook SDK para Python](https://github.com/pythonforfacebook/facebook-sdk). As mensagens foram coletadas no dia 21 de Julho de 2015 às 10:40. Em seguida, eu escrevi um programa para procurar o nome de todos os bairros da cidade, além de pontos conhecidos como UFPB, Lagoa, Manaíra Shopping, etc. Por fim, com esses dados em mãos, eu gerei o gráfico a seguir, com o nome dos bairros e lugares no eixo X e a quantidade de ocorrências no eixo Y. (Clique na imagem para abrir uma versão maior)

[![Número de ocorrências por bairro]({{ site.url }}/images/fuiassaltadojp-1.png)]({{ site.url }}/images/fuiassaltadojp-1.png)

Sabíamos que a violência nos Bancários vem crescendo muito, mas a diferença apresentada no gráfico é assustadora. Entretanto, tenho que deixar claro que tal diferença pode ser causada por um viés na amostragem, ou seja, no grupo do Facebook talvez exista muito mais pessoas morando na zona sul da cidade, o que acarretaria mais posts sobre a região. Mesmo com essa possibilidade, o número de crimes reportados é muito grande. Ainda na análise, procurei o número de posts por mês no grupo e como pode ser visto no gráfico abaixo, ele passou a ser usado mais frequentemente apenas nos dois últimos meses. Se considerarmos apenas junho e julho, temos 59 crimes nos Bancários, o que dá quase 1 crime por dia. Isso apenas de acordo com os posts do grupo, se fosse possível somar com outros assaltos que não são reportados no Facebook, o número seria ainda maior.

<p><a href="/images/fuiassaltadojp-2.png"><img src="/images/fuiassaltadojp-2.png" alt="Número de posts por mês" style="width: 500px;"></a></p>

Espero que esse post sirva de alerta para que uma mudança na segurança seja feita,
não apenas em um bairro, mas em toda cidade, estado e país.
