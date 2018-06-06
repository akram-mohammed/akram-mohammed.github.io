---
title: "Você sabe o que é um <b>chatbot</b>?"
layout: post
date: 2016-11-08 22:44
author: ravpacheco
lang: pt
ref: what-is-chatbot
image: /assets/images/2016-11-08-voce-sabe-o-que-eh-um-chatbot/chatbot.jpg
headerImage: true
tag:
- chatbot
- teoria
- blip
- bots
blog: true
description: Overview sobre um novo modelo de aplicações, os chatbots.
externalLink: true
category: blog
---

Chatbots, também conhecidos como '*bots*', '*chatterbot*', '*smart contacts*' ou contatos inteligentes são aplicações que comportam-se como um contato, em uma conversa, com a finalidade de prover algum tipo de serviço. Atualmente, já é possível desenvolver chatbots para os principais canais de menssageria do mercado, como: Facebook Messenger, Telegram, Skype, SMS, Slack, Kik entre outros. Assim como nos comunicamos com nossos familiares, os chatbots nos permitem conversar com um sensor de terremoto, ou uma máquina de refrigerantes, por exemplo, através de mensagem.

Nos últimos meses, após o anúncio da abertura da plataforma Messenger para empresas, o termo **chatbot** vem ganhando grande destaque na mídia. Entretanto, o primeiro exemplo de um chatbot foi o projeto Eliza, em 1966. Esta foi uma das primeiras aplicações de processamento de linguagem natural que se tem notícia e foi desenvolvida, entre os anos de 1964 e 1966, no Laboratório de Inteligência Artificial do MIT, pelo professor Joseph Weizenbaum. Seu objetivo era apresentar, mesmo que superficialmente, uma aplicação capaz de estreitar a distância na comunicação entre homens e máquinas. 

Apesar de estar comummente associado a inteligência artificial, é preciso deixar claro que um chatbot **não é, necessariamente,** uma aplicação 'inteligente'. Um bot pode ser uma aplicação extremamente simples que apenas responde à um conjunto fixo e restrito de comandos. 

Com o avanço rápido de algumas técnicas de inteligência computacional e processamento de linguagens naturais a tendência é que os chatbots entendam uma quantidade, cada vez maior de símbolos e contextos.

## Mas porquê usar um chatbot ?

Assim como qualquer outra tecnologia os chatbots não são nenhuma bala de prata. Quando o browser foi desenvolvido e deu o pontapé inicial para *boom* da internet as aplicações desktop não foram eliminadas. Quando os aplicativos móveis tornaram-se populares as aplicações web ou desktop não foram extintas. O que observamos ao longo do tempo é que com o avanço das tecnologias, novas ferramentas vão se diversificando para nos auxiliar em diferentes cenários.

Dessa forma os chatbots surgem para facilitar e otimizar a forma que consumimos algumas informações. Através deles é possível acessar diversos serviços sem sair dos aplicativos que já utilizamos no dia a dia. Imagine, por exemplo, que você esteja conversando com alguém no Facebook e que durante a conversa vocês decidam saber mais sobre o próximo show na cidade. Uma opção seria ir até a loja de aplicativos de seu smartphone, baixar o app do show. Depois de perder alguns minutos e muitos mega bytes de seu pacote de dados, você fica sabendo sobre o evento e pode voltar para sua conversa no Facebook. Imagine agora que o show possua um chatbot. Neste caso, seu único trabalho seria mudar de conversa, buscar as informações e depois returnar para sua conversa incial. Dependendo do canal não seria necessario sequer sair da conversa. O Telegram por exemplo, permite que você adicione chatbots em suas conversas. 

## Onde posso disponibilizar meus chatbots ?

As principais plataformas de mensageria do mercado já possuem suporte para construção de chatbots. Algumas das que ainda não possuem, como o Whatsapp por exemplo, já anunciaram que terão nos próximos meses. A lista abaixo contém links para
mais detalhes sobre como desenvolver um chatbot para cada canal.

1. [Facebook Messenger](https://developers.facebook.com/docs/messenger-platform)
2. [Telegram](https://core.telegram.org/bots/api)
3. [Slack](https://api.slack.com/bot-users)
4. [Skype](https://docs.botframework.com/en-us/skype/getting-started/)
5. [Email](https://msdn.microsoft.com/en-us/microsoft-teams/bots)
6. [Kik](https://www.kik.com/)
7. SMS [1](https://broker.take.io/login.aspx?ReturnUrl=%2f) [2](https://www.twilio.com/blog/2016/08/writing-a-bot-for-ip-messaging-in-node-js.html)
8. [Office365](https://msdn.microsoft.com/en-us/microsoft-teams/bots)

Como deu pra perceber não é muito simples fazer com que seu chatbot esteja presente em todos os mensageiros do mercado.
Para isso, é necessário implementar sua aplicação, individualmente, em cada uma das plataformas, seguindo suas regras e 
conceitos próprios. 

## É possível facilitar ?

Sim. Felizmente algumas ferramentas se especializaram em facilitar a vida do desenvolvedor. Para isso, definem uma API única para o desenvolvimento dos chatbots. Elas funcionam como um *hub*, o desenvolvedor implementa uma única aplicação e 
pode, publicar (ou remover) seu chatbot em qualquer um dos canais. 

As principais vantagens de ferramentas com essa abordagem são: 

1. Redução do custo de criação e manutenção de seu chatbot. Além de desenvolver um único código, o custo para manter apenas uma aplicação funcionando é bem menor;
2. Não é necessário ter especialistas em todas as API's dos canais de mensagem. O time de desenvolvimento do chatbot 
precisa apenas conhecer a API do *hub* (O que gera, invariavelmente, redução dos custos ;) )
3. Estar presente, rapidamente, em todos os canais. Não importa a preferencia do seu usuário, estar presente onde quer que ele esteja, rapidamente, é muito importante.        

Dentre as opções disponíveis no mercado, estão [Blip.ai](https://blip.ai/), [BotFramework](https://dev.botframework.com/), 
[GupShup](https://www.gupshup.io/developer/home) e [PandoraBots](http://www.pandorabots.com/). [Blip.ai](https://blip.ai/) é a única ferramenta desse propósito no Brasil. Além de possuir uma API ela disponibiliza a opção de construir chatbots a partir de templates, sem codificar uma única linha de código. Caso queira conhecer melhor a plataforma leia [este post](http://ravpacheco.com/resumo-chatbot-webhook/), nele eu ensino como construir, passo a passo, um chatbot 'currículo'.  

## Conclusão

Neste post introduzi o conceito de chatbots, que de novo não tem nada. Apresentei contextos em que chatbots podem ser 
utilizados, e um exemplo em que os mesmos podem, inclusive, substituir outros modelos de aplicações. Além de frizar que 
chatbots **não tem** que ser necessariamente inteligente, mostrei que não é nada simples e barato publicar seu chatbot em 
vários canais. Para contornar esta dificuldade, apresentei algumas ferramentas que auxiliam o desenvolvedor a construir um único chatbot e disponibilizá-lo em qualquer canal.

Ficou com alguma dúvida, tem alguma sugestão ou crítica ? Mande seu comentário.        

 

