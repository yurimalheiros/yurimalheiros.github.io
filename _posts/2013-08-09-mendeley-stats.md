---
layout: post
title: Mapeamento sistemático para hackers
date: 2013-08-09 9:00:00
comments: true
---

Nesses últimos dias eu estava coletando vários trabalhos para realizar um mapeamento sistemático. Esse tipo de mapeamento é feito quando se deseja ter uma visão geral de uma área que está sendo pesquisada. Assim, é possível identificar os principais trabalhos numa área, aprender o que já foi feito e o que merece contribuição, descobrir falhas que você pode resolver, etc.

Para organizar minha biblioteca de artigos eu utilizo o [Mendeley](http://www.mendeley.com/), um software gratuito, bastante eficiente nas suas tarefas e que possui um API para que programadores consigam criar soluções usando os seus serviços.

Num mapeamento sistemático é importante extrair informações do tipo: quantos artigos foram publicados em cada ano, ou quais autores possuem mais artigos, ou ainda quais meios de publicação foram mais utilizado pelos pesquisadores nessa área.

Isso pode ser feito manualmente, mas com todos esses dados disponíveis no Mendeley, eu não aceitaria facilmente fazer isso assim.

Algumas horas depois de começar a explorar a API do Mendeley eu tinha o primeiro protótipo do Mendeley Stats, uma ferramenta para extrair automaticamente informações importantes para um mapeamento sistemático. Com um pouco mais de trabalho eu organizei tudo o que tinha e disponibilizei o [repositório no Github](https://github.com/yurimalheiros/mendeleystats).

O funcionamento do Mendeley Stats é simples. Ele é uma ferramenta de linha de comando que extrai informações de uma pasta no Mendeley. Dessa forma, é só colocar todos os papers do seu mapeamento sistemático numa pasta e executar o Mendeley Stats.

A ferramenta tem duas funcionalidades principais: gerar gráficos e gerar arquivos .csv. Gráficos são ótimos para que se entenda alguns dados facilmente, mas em certos casos, os dados não podem ser apresentados adequadamente em gráficos, então é melhor usar a alternativa de gravar num .csv.

Além de escolher o tipo de output (gráfico ou .csv), o usuário também precisa escolher que dados ele quer analisar. Por enquanto o Mendeley Stats suporta ano, tipo (se o paper é de conferência, de revista, etc.), autores, palavras-chaves e meio de publicação. Ao escolher, por exemplo, a análise por anos, o Mendeley Stats retornará a quantidade de artigos por ano que estão contidas na pasta especificada.

Exemplo de uso:

`mendeleystats --info year --output chart --folder datamining`

Nesse caso, a ferramenta retornará em forma de gráfico (--output chart), quantos artigos por ano (--info year) existem na pasta datamining no Mendeley (--folder datamining).

No geral, a ferramenta suporta os seguintes parâmetros:

```
mendeleystats --info {year,type,authors,keywords,publishedin}
              --output {chart,csv} --folder FOLDER
```

Espero que essa simples ferramenta seja útil para outras pessoas também e fiquem a vontade para dar sugestões ou para contribuir com o projeto.
