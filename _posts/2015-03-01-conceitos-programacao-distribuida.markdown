---
title: "Conceitos de programação distribuída"
layout: post
date: 2015-03-01 22:48
author: ravpacheco
lang: pt
ref: distributed-programming
image: /assets/images/markdown.jpg
headerImage: false
tag:
- programacao distribuida
- teoria
blog: true
description: Alguns conceitos básicos importantes em programação concorrente e distribuída. 
externalLink: true
category: blog
---

Nos últimos dias comecei a estudar o framework Akka, para programação baseada em atores (discutirei mais sobre o Akka em  uma póxima oportunidade), e por isso me vi obrigado a revisitar alguns conceitos simples, mas confusos sobre programação distribuída. Este post é uma compilação de alguns destes tópicos. Caso tenha alguma dúvida, crítica ou sugestão deixe seu comentário.

* **Concorrêcia vs Paralelismo**

Apesar de serem conceitos relacionados existem difêrencas entre concorrência e paralelismo.
Dois processos são ditos concorrentes quando disputam (concorrem a) algum recurso, ou seja não podem ser executados simultâneamente.Já o paralelismo, por outro lado, diz respeito a processos que podem ser executados no mesmo instante de tempo.
Para exemplificar imagine um processador com um único núcleo que deseja executar 2 processos (A e B). Neste cenário A e B serão concorrentes, mesmo que cada um dos processos seja dividido em pequenas tarefas e as mesmas sejam executadas de forma embaralhada.
De outra forma, um processador com dois ou mais núcleos pode executar os mesmos processos A e B, de forma paralela.

* **Assíncrono vs Síncrono**

Uma chamada a algum processo (ou método) é considerada síncrona se o sujeito que realiza a chamada não puder progredir em sua execução até que receba um retorno. Já os processos assíncronos não precisam esperar nenhum tipo de retorno em relação as suas chamadas. Neste caso são utilizados mecanismos adicionais para sinalizar o retorno de suas chamadas, tais como callback, mensagem, entidades futuras (Futures) entre outros. Use, sempre que possível, chamadas assíncronas.

* **Blocking vs Non-blocking**

Blocking (processos bloqueantes) são processos que podem ficar bloqueados indefinidamente por algum motivo. Em contra partida Non-blocking são tarefas que não ficam bloquadas de forma indefinida. Um exemplo simples de processos Blocking são códigos com loop infinito.

* **Deadlock**

Quando diferentes processos esperam um ao outro atigirem um determinado estado e não conseguem prosseguir em sua execução dizemos que os processos estão em deadlock. Imagine dois processos P1 e P2 em um estado qualquer A com o objetivo de alcançar o estado B. Em um dado momento P1 espera que P2 mude para o estado B para que consiga atingir o estado B. Entretanto P2 também precisa esperar que P1 mude para o estado B para alcançar o estado B. Neste momento existe um deadlock entre os processos P1 e P2.

* **Starvation**

Enquanto no deadlock nenhum dos processos pode progredir em sua execução, durante um estado de starvation apenas alguns processos são impedidos de executar. Um exemplo clássico do processo de starvation acontece em “schedules” de tarefas com prioridades. Dependendo da taxa de entrada de tarefas com prioridade alta as demais tarefas de baixa prioridade podem nunca serem executadas.

* **Race condition (Condição de corrida)**

Quando a ordem de execução de tarefas faz diferenca no resultado final de um processo dizemos que este processo pode causar race condition. Um exemplo são os pacotes UDP que podem ser enviados de um ponto a outro por diferentes rotas e consequentemente chegar ao destinatário em ordem diferente. Neste caso é necessário que as partes envolvidas no processo possuam alguma forma de identificar a ordem de envio das mensagens. Caso não exista algum processo de sincronização das mensagens surge uma condição de corrida.
A título de curiosidade o framework akka garante que as mensagens enviadas entre atores tem sua ordem de envio preservada.

## Referências:

1. The Art of Multiprocessor Programming, M. Herlihy and N Shavit, 2008. ISBN 978-0123705914
2. Java Concurrency in Practice, B. Goetz, T. Peierls, J. Bloch, J. Bowbeer, D. Holmes and D. Lea, 2006. ISBN 978-0321349606
3. Akka 2.3.9 [documentation](http://doc.akka.io/docs/akka/2.3.9/java.html)