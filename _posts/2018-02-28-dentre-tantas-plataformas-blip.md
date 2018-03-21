---
title:  "Dentre tantas plataformas de bots, por que o BLiP ?"
layout: post
date:   2018-02-28 14:00:00 +0000
author: ravpacheco
lang: pt
ref: blip-best-platform
tag: 
- blip
- platform
- opinion
- vida
blog: true
star: false
description: Algumas reflexões sobre porque acredito que o BLiP é uma ótima plataforma para construção de bots.
externalLink: true
category: blog
---

Apesar de não ser novo, o termo bot (ou chatterbot, chatbot, contatos inteligentes, robôs de mensagem, entre outros…) tem ganhado grande relevância desde o final de 2016, com a abertura da API do Messenger (se por acaso, você não sabe o que é um “chatbot” [clique aqui](https://medium.com/botsbrasil/o-que-%C3%A9-um-chatbot-7fa2897eac5d) 😉).

Visto do alto, construir um bot é algo simples. Você precisa, basicamente, **de uma API** que **receba mensagens de um canal** (como o Facebook Messenger por exemplo); **analise o conteúdo da mensagem** (utilizando ou não algoritmos de Inteligência Artificial); e **responda o cliente** com requisições na API do canal.

![Arquitetura mínima para criar um bot.](https://cdn-images-1.medium.com/max/1000/1*TMTDp0Vceghulz5nhXxQKg.png)
*Arquitetura mínima para criar um bot.*

Apesar disso, quem já construiu, ou está construindo, um bot sabe que a tarefa não é assim tão trivial. Design de conversa, integrações, presença *omni channel*, gestão e manutenção, evolução da base de conhecimento, transbordo para um atendente humano, análise e insights dos eventos gerados, métricas para avaliação do sucesso, testes AB, criação de bots e sub-bots, são apenas alguns dos desafios de quem cria bons bots.

![Complexidade em construir um bom bot](https://cdn-images-1.medium.com/max/600/1*SjVWZ7-45QR2E66Hr2LaHw.png)

> “Lembre-se: construir um bot é fácil, mas construir um bom bot pode ser bem difícil”

Pensando nisso, algumas empresas desenvolveram plataformas (ou frameworks) para facilitar o processo de ideação e criação de um bot.

Semanalmente, recebo dúvidas e questionamentos sobre os motivos que levariam uma pessoa, interessada em bots, a avaliar a plataforma [BLiP](https://blip.ai).

Meu objetivo neste artigo é apresentar o meu ponto de vista, sobre a plataforma [BLiP](https://blip.ai) e porque a considero a melhor plataforma de construção de bots do mundo.

...

![Plataformas](https://cdn-images-1.medium.com/max/2000/1*hQq0yD2mdon2FRW1kdRp7Q.png)
*Algumas plataformas/ferramentas do ecossistema de bots no mundo. Fonte: Sergio Passos*

> Alerta: Apesar de ser um dos desenvolvedores e o evangelizador da plataforma BLiP, testo, regularmente, ferramentas relacionadas ao mundo de bots, desenvolvidas por qualquer empresa do mundo.

Sendo assim, **antes** de apresentar os **motivos pelos quais acredito** que o BLiP (produto da [Take](https://take.net)) é uma excelente plataforma, tenha em mente que **já testei e experimentei** as principais ferramentas do mercado, **e não encontrei, em nenhuma delas, todo o potencial do BLiP**.

# 10 motivos para testar/experimentar/conhecer o BLiP

## 1. Builder

**É possível construir bots complexos sem nenhuma linha de código.**

O BLiP permite a criação de 2 tipos de bots: utilizando um dos templates disponíveis ou bots 100% customizáveis, seja através de código (utilizando um SDK ou requisições HTTP) ou através do Builder. **O Builder é construtor visual de fluxos** que permite que qualquer pessoa (com ou sem conhecimento de programação) crie bots complexos em pouco tempo. A imagem abaixo ilustra o fluxo de um bot criado a partir do **Builder do BLiP** (para saber mais como funciona clique aqui 👈).

![Exemplo de bot construido através do Builder do BLiP](https://cdn-images-1.medium.com/max/800/1*92L7C0w_EL0qg2luvKeUUg.png)

*Exemplo de bot construido através do Builder do BLiP*

O componente Builder do BLiP foi pensado para ajudar uma equipe desde o processo de ideação até a implementação. Antes mesmo de detalhar o conteúdo da conversa, é possível desenhar a visão macro de seu bot e ajudar todos os envolvidos no projeto a entender como a informação esta organizada. Além disso, está integrado a todos as funcionalidades do BLiP, e assim como outras opções do mercado, permite a realização de requisições HTTP para integração com APIs externas.

## 2. Pay as you go

**Versão gratuita sem limitação de features.**

Como desenvolvedor, me sinto um pouco incomodado quando não consigo testar todas as funcionalidades de um produto antes de realizar algum tipo de pagamento.

O BLiP possui planos pagos e uma versão gratuita (para ver o modelo de tarifação clique aqui). O que mais me agrada no modelo adotado pelo BLiP é que **além de conseguir usufruir de todas as funcionalidades da ferramenta, a versão gratuita não tem tempo de testes limitado.** Enquanto seu bot não estiver preparado o suficiente para escalar, você não tem custo. Quando seu projeto ganhar tração, escolha qual modelo se aplica melhor ao seu contexto.

## 3. Seja LIVRE

**Tenha TOTAL controle sobre TODOS os dados do seu bot a qualquer momento.**

Você já refletiu sobre quem é realmente **dono do seu bot**? Quase todas as plataformas de criação de bot do mercado tem o controle da base de clientes da sua aplicação. Caso você precise deixar de utilizar a plataforma, perderá a referência das contas que já conversaram com seu bot.

No BLiP, nenhum dado é ocultado pela plataforma. Você está livre para entrar ou deixar a ferramenta a qualquer momento e com todas as informações geradas por seu bot. É possível também consumir todos os dados programaticamente.

Durante a construção do seu bot você é 100% livre para utilizar qualquer outra ferramenta que, por ventura, não esteja disponível no BLiP, para compôr o design ideal da sua aplicação. **Nada mais justo, não acha?**

## 4. Flexibilidade

**Não fique preso a nenhum algoritmo de IA, ferramenta de análise ou de atendimento humano.**

Diversas plataformas de construção de bots possuem seus algoritmos próprios de IA - Inteligência Artificial. Nesses casos, você está condicionado a utilizar um único algoritmo, mesmo que, por algum motivo (língua, qualidade de confiança na análise, entre outros), ele não atenda corretamente à sua demanda.

**O BLiP não é um provedor de IA.** Melhor do que estar preso a uma única solução, o BLiP esta integrado aos melhores provedores (ou ferramentas) de IA do mercado ([IBM Watson](https://www.ibm.com/watson/), [Microsoft LUIS](http://luis.ai/) *e em breve DialogFlow e Wit.ai*), você só precisa escolher qual delas é a melhor para o seu negócio.

Além disso, é possível importar sua base de conhecimento (intenções e entidades) pré-existente, bem como migrar de um provedor de IA para outro **com apenas um clique**. Você não precisa implementar nenhuma nova integração, nem se preocupar com o processo de migração entre diferentes provedores, o BLiP cuida disso para você. Esteja a um clique do concorrente do seu provedor atual. **Mais uma vez, seja livre!**

**Qual o melhor local para analisar os dados do seu bot?** O BLiP possui uma ferramenta completa para análise de dados e geração de relatórios customizados para seu bot. Entretanto, caso queira, também é possível ver seus dados no [Chatbase](http://chatbase.com/) (ferramenta de analytics para bots do Google) ou em alguma ferramenta customizada através de um **webhook**.

**Qual o melhor local para atender manualmente os clientes do seu bot?**
O BLiP possui uma ferramenta, para que um ser humano consiga ajudar seu bot a responder melhor, qualquer tipo de cliente - o BLiP Desk. Entretanto, caso queira, também é possível redirecionar atendimentos manuais para ferramentas como: Email, [Zendesk](https://www.zendesk.com.br/) e em breve [Intercom](https://www.intercom.com/).

## 5. Hospedagem customizada

**Tenha total flexibilidade para hospedar seu bot.**

Imagine que sua empresa quer utilizar uma ferramenta para construção de bots, mas por algum motivo precisa *hostear* (hospedar) a aplicação em sua infraestrutura.

No BLiP, os bots criados podem utilizar a infraestrutura (ou cloud) que mais lhe agrada. *Excelente opção para quem desenvolve bots para terceiros.*

Não quer se preocupar com hospedagem do seu bot ? Tudo bem, por padrão, todos os bots criados através do **Builder do BLiP são hospedados automaticamente e sem custos adicionais 👍.**

## 6. Código First

**Acesso por código a qualquer recurso da plataforma.**

Algumas pessoas não desenvolvem, e portanto podem optar por construir seus bots com o auxílio do Builder. Entretanto, alguns desenvolvedores (ou empresas) podem precisar de total flexibilidade para realizar qualquer tipo de customização ou criação de aplicações para terceiros.

Pensando nisso, o BLiP disponibiliza SDKs (*C\#, JavaScript e JAVA*) e uma API HTTP para possibilitar qualquer tipo de automatização durante a construção de um bot. Essa pode ser uma opção muito interessante para quem está no mundo de IOT (*Internet of things*)

## 7. Visão completa

**Acesso a ferramentas de criação, gestão, monitoramento e evolução do seu bot.**

Diferente da grande maioria de plataformas de bots, o BLiP possui diversas ferramentas que acompanham a equipe durante todo o ciclo de vida de um bot, desde sua ideação até sua evolução.

![Bots life cycle](https://cdn-images-1.medium.com/max/800/1*tW-B0x-XSGlozpFPnsBjbQ.png)

*Ciclo de vida de um bot.*

### Ideação

O Builder permite que o designer de conversas crie a visão macro e defina como o conteúdo será apresentado ao cliente, antes mesmo de o desenvolvedor implementar uma linha de código. Neste primeiro estágio é possível dedicar-se a temas como: personas, jornada dos clientes, tom de conversa, e as features principais da aplicação.

### Criação/Testes

Além de todas as funcionalidades destacadas anteriormente, o BLiP possui várias extensões (funções básicas já implementadas) que facilitam a vida de qualquer desenvolvedor de bot.

* Precisa do histórico da conversa de um usuário com seu bot ? Use a extensão [Histórico](https://docs.blip.ai/#chat-history)
* Precisa armazenar algum tipo de informação ? Use a extensão de [Armazenamento](https://docs.blip.ai/#bucket)
* Precisa disparar um *broadcast* para seus clientes (ou para um grupo específico) ? Use a extensão [Broadcast](https://docs.blip.ai/#broadcast)
* Precisa agendar o envio de alguma mensagem para algum cliente? Use a extensão [Schedule](https://docs.blip.ai/#schedule)

[Clique aqui](https://docs.blip.ai/#extensions) para consultar a lista completa de extensões.

Ainda na fase de criação, é possível aproveitar as diversas integrações pré-existentes na plataforma. Essas integrações permitem que seu bot esteja conectado a várias ferramentas sem que você precise se preocupar em aprender o dialeto de cada uma delas. Veja abaixo alguns exemplos de integrações disponíveis no BLiP:

* Pagamentos através do [PagSeguro](http://pagseguro.uol.com.br/);
* Gerenciamento de Leads através do [RD Station](https://www.rdstation.com/);
* Customer Chat Plugin do Messenger;
* Em breve, gerenciamento de suas campanhas de ADs do Facebook com a [Sugar Ads](http://sugarads.io/hotsite/index.html);

Seu bot está pronto ? Só falta testar ? O BLiP te deixa à um clique de um simulador de conversa com o seu bot ;). (Obs.: se precisar de mais informações sobre testes em chatbots, confira este [blog](http://taketest.take.net/))

### Gerenciamento/Manutenção

Assim como em qualquer aplicação real, após o processo de publicação em um ambiente de produção, é necessário um gerenciamento constante para que tudo saia como esperado.

O painel principal do BLiP age como um *heath monitor* (monitor de saúde) trazendo várias informações, indispensáveis, para o gerenciamento do seu bot. É possível saber, em tempo real, por exemplo, se o bot está disponível, qual a quantidade de mensagens trafegadas, qual os assuntos mais discutidos, o tempo médio de resposta do bot, quantidade de usuários ativos, entre várias outras.

![Exemplo do dashboard de informações gerais de um bot no BLiP.](https://cdn-images-1.medium.com/max/800/1*ZiQ_XL8wfai_qOrZOYxjVQ.png)

*Exemplo do dashboard de informações gerais de um bot no BLiP.*

### Análise/Promoção

Além de construir seu bot, provavelmente você precisará divulgá-lo e analisá-lo.

Pensando nisso, o BLiP disponibiliza ferramentas de promoção, como BLiP Chat, e análise, através de todos os relatórios customizados disponíveis na ferramenta.

Por fim, existe ainda a total flexibilidade para utilização de ferramentas de análise customizadas, junto as opções entregues pela plataforma.

### Evolução

É possível utilizar os módulos de **Aprimoramento** e **Aprovação** (*aprendizado supervisionado*) para aprender com todas as interações dos clientes e fazer com que sua base de conhecimento fique cada vez mais “*inteligente*”.

## 8. Trabalho em equipe

**Construir um bot envolve várias pessoas, coloque todas juntas no mesmo barco! 🚣🏼‍**

Uma das premissas do BLiP é que durante todo o ciclo de vida de um bot são necessárias várias pessoas. Pensando nisso, o portal da plataforma permite que cada membro da equipe tenha a visão e os acessos necessários para desempenhar **corretamente**, seu trabalho.

![Central de permissão da equipe](https://cdn-images-1.medium.com/max/800/1*OejYMPM3N7kt5uM2bYXIcA.png)

*Central de permissão da equipe*

## 9. Multi Canal

**Crie seu bot uma única vez e disponibilize-o em vários canais.**

Apesar do Messenger se apresentar hoje como o **canal** (aplicativo de mensagem que suporta bots) mais importante, existem ainda diversos outros canais importantes, com uma boa base de usuários, capazes de trazer muita audiência para sua aplicação.

Atualmente, o BLiP permite que você crie seu bot uma única vez e o disponibilize em 7 canais: *Telegram*, *Messenger*, *Workplace*, *Skype*, *Email*, *SMS* e **BLiP Chat** (canal próprio do BLiP que permite colocar seu bot em um **site** ou em um aplicativo móvel **Android** e **iOS**).

![Canais do BLiP](https://cdn-images-1.medium.com/max/800/1*QRV7a_2ZhJ5pc3ytjLs8aA.png)

Em breve, bots criados no BLiP estarão disponíveis também em canais como: *Whatsapp*, *Slack*, *Rocket Chat*, *Google RCS*, *Google Assistant*, *Alexa*, *Business Chat* da Apple entre outros.

## 10. Bots e sub-bots

**Reaproveite seus bots para ir mais longe.**

Quem já teve a experiência de fazer um bot real (lançado oficialmente e testado pelos clientes) sabe da dificuldade em modelar uma base de conhecimento capaz de tratar a maior quantidade possível de assuntos.

Imagine que seu desafio é criar um bot especialista em eventos de culinária. Criar e gerenciar uma base para esse bot envolve conhecimentos em duas áreas diferentes mas que se completam para um determinado momento. 
Ao invés de se preocupar com todos os assuntos em um mesmo lugar, você pode adotar uma estratégia diferente. Crie três bots: um especialista em eventos, outro especialista em culinária e um terceiro bot, composto pelos dois anteriores, especialista em eventos de culinária.

Assim como reaproveitamos serviços através de APIs, através da arquitetura de bots e sub-bots do BLiP **é possível reaproveitar suas aplicações conversacionais**.

## Bônus. Estabilidade e robustez

**A plataforma é confiável ?**

Em quase todos os contextos, uma alta disponibilidade do bot pode ser a chave para seu sucesso. Por isso, adotar ferramentas estáveis e consolidadas pode ser um importante requisito para seu projeto

* Take possui 18 anos no mercado de mensageria
* Take possui parcerias com as principais empresas de bots no mundo, como Facebook, Google, Microsoft e IBM.
* \+ de 2.700 cadastros completos
* \+ de 4000 chatbots já criados.
* Alguns dos clientes do BLiP

![Algumas empresas que já usam o BLiP](https://cdn-images-1.medium.com/max/800/1*HNIlGFVQ8BSatIhN6cCVtg.png)

*Algumas empresas que já usam o BLiP*

## Quem está falando do BLiP ?

* [Facebook](https://www.facebook.com/business/products/messenger-for-business/development-providers)
* [IBM](https://www-03.ibm.com/marketing/br/vitrinedecanais/casosdesucesso/Take_Blip.pdf)
* [Chatbase](https://techcrunch.com/2017/11/16/googles-chatbot-analytics-platform-chatbase-launches-to-public/) (Google)


E você, concorda com meus argumentos? Tem alguma sugestão? Gostaria de sugerir outro ponto de vista ou crítica? Deixe seu comentário abaixo 👇. Se gostar do artigo compartilhe com seus amigos ❤️ , quem sabe ele pode ser útil para outra pessoa também! 😉

**Links importantes para mais informações:**

[Portal do BLiP](https://preview.blip.ai)
[Help Center](https://help.blip.ai)
[Fórum do BLiP](https://forum.blip.ai) 
[Comunidade do Facebook](https://www.facebook.com/groups/BLiP.Community/)

