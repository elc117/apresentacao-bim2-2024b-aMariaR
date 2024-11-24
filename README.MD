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
![](https://pt.wikipedia.org/wiki/Ficheiro:Erlang_logo.png)

A Erlang utilizava sua máquina virtual para gerenciar os processos, aos invés das threads do processador, não compartilhava memória, se comunicava através de mensagens assincronas e utilizava a ideia de supervisores que monitoravam os processos e reiniciava-os caso necessário. 
Isto solucionava os problemas da concorrência, mas a linguagem aindo tinha falhas de suporte ao desenvolvedor como features, com isso José Valim começou a deenvolver sua própria linguagem de programação, a Elixir surgiu como uma linguagem funcional e concorrente e que utiliza a BEAM como máquina virtual.

![](https://upload.wikimedia.org/wikipedia/commons/9/92/Official_Elixir_logo.png)
## Tópicos sobre concorrência:
-Processadores com muitos cores - concorrência é o futuro;

-Muitas linguagens já exploravam a conncorrência: Java, Go, Swift;

-Lingaugens com suporte limitado: Ruby, Python;

-Ênfase no paradigma funcional;
