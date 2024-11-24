# PROGRAMAÇÃO CONCORRENTE 
## Um contexto

A linguagem Elixir surgiu em 2012, criada pelo desenvolvedor José Valim.
José trablhava com Rails, um framework open-source para aplicações web escrito em Ruby.

## A concorrência na época

Em entrevista, José contou que em muitos eventos de tecnologia se dizia que a concorrência era futuro, com o surgimento de processadores multicore a ideia de rodar uma aplicação nos diversos cores do processador trasnformava a programação, com isso a programação concorrente emergiu.
Porém as linguagens não estavam preparadas para a concorrência, com suportes limitados, haviam muitos bugs e erros de sincronização, e as soluções encontradas por vezes limitavam tanto a execução que acabava com a concorrência.

## Como solucionar?
Na busca por resolver os problemas da concorrência José citou dois pontos cruciais:

### O paradigma funcional
O paradigma funcional resolvia boa parte dos problemas da programação concorrente. A maioria dos problemas ocorria porque os elementos da memória eram alterados em um core enquanto outro core poderia estar requisitando o valor, ou alterando o valor antigo causando uma série de problemas. Esse problema não existe com a programação funcional, pois os elementos não são alterados na memória, são reescritos toda vez e o garbagge coletor se responsabiliza pelos dados não alterados alem de permitir códigos mais claros.

### Probelmas de distribuição 
Além de ser necessário sincronizar os cores, era necessário sincronizar as máquinas que rodavam a aplicação, na busca da solução, José se deparou com Erlang, uma linguagem de programação funcional e concorrente, criada pela empresa de telecomunicações Ericsson, voltada a sistemas distribuidos e com sua própria máquina virtual: a BEAM.
![](https://www.google.com/imgres?q=erlang&imgurl=https%3A%2F%2Fupload.wikimedia.org%2Fwikipedia%2Fcommons%2Fthumb%2F0%2F04%2FErlang_logo.svg%2F640px-Erlang_logo.svg.png&imgrefurl=https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FErlang_(programming_language)&docid=0OX59n-QAdBWUM&tbnid=EP53fFEEDv05eM&vet=12ahUKEwjY6bHJhfWJAxVXq5UCHTppLKAQM3oECF8QAA..i&w=640&h=561&hcb=2&ved=2ahUKEwjY6bHJhfWJAxVXq5UCHTppLKAQM3oECF8QAA)

![](https://www.google.com/url?sa=i&url=https%3A%2F%2Fpt.wikipedia.org%2Fwiki%2FErlang_%2528linguagem_de_programa%25C3%25A7%25C3%25A3o%2529&psig=AOvVaw3D49ZOqaneLm77PPSp9B8O&ust=1732540265759000&source=images&cd=vfe&opi=89978449&ved=0CBQQjRxqFwoTCKD80suF9YkDFQAAAAAdAAAAABAY)

A Erlang utilizava sua máquina virtual para gerenciar os processos, aos invés das threads do processador, não compartilhava memória, se comunicava através de mensagens assincronas e utilizava a ideia de supervisores que monitoravam os processos e reiniciava-os caso necessário. 
Isto solucionava os problemas da concorrência, mas a linguagem aindo tinha falhas de suporte ao desenvolvedor como features, com isso José Valim começou a deenvolver sua própria linguagem de programação, a Elixir surgiu como uma linguagem funcional e concorrente e que utiliza a BEAM como máquina virtual.

![](https://www.google.com/imgres?q=elixir%20linguagem%20quando%20foi%20criado&imgurl=http%3A%2F%2Fwww.each.usp.br%2Fpetsi%2Fjornal%2Fwp-content%2Fuploads%2F2018%2F09%2Felixir.png&imgrefurl=http%3A%2F%2Fwww.each.usp.br%2Fpetsi%2Fjornal%2F%3Fp%3D2459&docid=uYQqGT2TWeP27M&tbnid=xFUMJIdNI1ttZM&vet=12ahUKEwiSvZ6DhfWJAxUZrZUCHbiPOzoQM3oECGMQAA..i&w=720&h=250&hcb=2&ved=2ahUKEwiSvZ6DhfWJAxUZrZUCHbiPOzoQM3oECGMQAA)


## Tópicos sobre concorrência:
-Processadores com muitos cores - concorrência é o futuro;

-Muitas linguagens já exploravam a conncorrência: Java, Go, Swift;

-Lingaugens com suporte limitado: Ruby, Python;

-Ênfase no paradigma funcional;
