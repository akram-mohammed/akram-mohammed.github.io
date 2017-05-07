---
title:  "Facilitando a criação de seu chatbot através das extensões BLiP"
layout: post
date:   2017-01-09 14:00:00 +0000
author: ravpacheco
lang: pt
ref: blip-extensions
image: /assets/images/2017-01-09-entendendo-extensoes-blip-ai/image_0.jpg
headerImage: true
tag: 
- chatbot
- blip.ai
- blip-sdk-csharp
blog: true
star: true
description: Acelere o desenvolvimento de seu chatbot com as extensões da plataforma blip.ai
externalLink: true
category: blog
---

<span class="evidence">Observação: Este post foi originalmente escrito para o [blog](http://blog.blip.ai/2016/12/28/entendendo-as-extensoes.html) do blip.ai</span>

Se você já criou algum chatbot, provavelmente já precisou de várias ferramentas auxiliares. Agendar o envio de alguma mensagem, salvar informações de seus clientes em 
um local seguro ou *trackear* eventos ocorridos, são exemplos de tarefas simples que podem demandar um grande esforço para serem realizadas.

Pensando nisso, a plataforma [BLiP](https://blip.ai/) possui diversas [extensões](https://portal.blip.ai/#/docs/extensions). As extensões são serviços que provêm funcionalidades 
para facilitar a vida dos desenvolvedores no momento da construção dos chatbots. Imagine que cada extensão seja um plugin, conectado à plataforma, que pode receber comandos e mensagens, 
dos próprios chatbots, para realizar alguma ação.

O objetivo deste artigo é demonstrar como é fácil e rápido utilizar estas extensões durante a criação de um chatbot. Todos os exemplos apresentados aqui utilizam o [SDK 
C#](https://portal.blip.ai/#/docs/sdks/csharp).

# Extensões disponíveis

Atualmente, o BLiP possui as seguintes extensões disponíveis:

<table>
  <tr>
    <td><b>Extensão</b></td>
    <td><b>Descrição</b></td>
    <td></td>
  </tr>
  <tr>
    <td>Agendamento</td>
    <td>Realiza o envio de mensagens, em nome do seu chatbot, para uma data e horário específico</td>
    <td><a href="https://portal.blip.ai/#/docs/extensions/scheduler" target="_blank">Saiba mais</a></td>
  </tr>
  <tr>
    <td>Envio em massa</td>
    <td>Gerencia listas de usuários de seu chatbot e envia mensagens para todos os usuários de uma lista</td>
    <td><a href="https://portal.blip.ai/#/docs/extensions/broadcast" target="_blank">Saiba mais</a></td>
  </tr>
  <tr>
    <td>Armazenamento</td>
    <td>Permite o armazenamento de dados, no formato de documentos JSON, em um local seguro e isolado, acessível apenas pelo seu chatbot</td>
    <td><a href="https://portal.blip.ai/#/docs/extensions/bucket" target="_blank">Saiba mais</a></td>
  </tr>
  <tr>
    <td>Diretório</td>
    <td>Consulta informações dos usuários (de acordo com o canal utilizado) de seu chatbot, como nome e outros dados pessoais</td>
    <td><a href="https://portal.blip.ai/#/docs/extensions/directory" target="_blank">Saiba mais</a></td>
  </tr>
  <tr>
    <td>Análise de eventos</td>
    <td>Permite o registro e a coleta de eventos ocorridos em seu chatbot</td>
    <td><a href="https://portal.blip.ai/#/docs/extensions/event-track" target="_blank">Saiba mais</a></td>
  </tr>
  <tr>
    <td>Histórico de conversas</td>
    <td>Possibilita a consulta das últimas mensagens trocadas entre seu chatbot e um determinado usuário de um canal</td>
    <td><a href="https://portal.blip.ai/#/docs/extensions/threads" target="_blank">Saiba mais</a></td>
  </tr>
  <tr>
    <td>Delegação</td>
    <td>Atribui permissão para que outras extensões possam enviar mensagens em nome do seu chatbot</td>
    <td><a href="https://portal.blip.ai/#/docs/extensions/delegation" target="_blank">Saiba mais</a></td>
  </tr>
</table>

A extensão de **Delegação** é uma extensão especial. Através dela, é possível dar permissão para que outras identidades (extensões ou chatbots) da plataforma envie mensagens 
em nome do seu chatbot. Atualmente, apenas as estensões de **Agendamento** e **Envio em massa** precisam de delegação para funcionarem. Entretanto, estas já são concedidas, por 
padrão, no momento da criação do chatbot. Dessa forma, para os exemplos que serão apresentados neste artigo não será preciso preocupar com a delegação de permissões.

# Mãos à obra

Para exemplificar o uso das extensões vamos criar um chatbot utilizando o SDK C#. O processo de criação é bem simples e está explicado, passo a passo, 
[neste link](https://portal.blip.ai/#/docs/sdks/csharp/installing). A utilização de cada extensão será apresentada através de exemplos simples, mas indispensáveis para quem 
está desenvolvendo qualquer chatbot.

![Chatbots com extensões](../assets/images/2017-01-09-entendendo-extensoes-blip-ai/image.png)

**Obs.: Todos os casos abaixo foram criados tomando como base a classe *PlainTextMessageReceiver*, adicionada automaticamente no momento da instalação do SDK C#.**

## Agendando uma mensagem

Ao criar um chatbot de lembretes, é imprescindível a funcionalidade de agendamento de mensagem.
Imagine que o usuário enviou uma mensagem para o chatbot com a seguinte sentença.

> Lembrar-me de tomar remédio em 10 minutos

Neste caso, seu chatbot precisa enteder o contexto da conversa, extrair as infromações de comando e finalmente agendar uma mensagem para os próximos 10 minutos.
Para entender o contexto e extrair as inforamações necessárias você pode utilizar o [TextC](https://github.com/takenet/textc-csharp) por exemplo. 
Os artigos [Chatbots e a importância do contexto](http://blog.blip.ai/2016/12/15/chatbots-e-a-importancia-do-contexto.html) e 
[Construindo um chatbot assistente virtual utilizando o Textc](http://blog.blip.ai/2016/10/17/chatbots-com-textc.html) explicam como utilizar o TextC na difícil e importante tarefa 
de entender o contexto de uma conversa.

Neste artigo, Vamos nos preocupar apenas com o agendamento da mensagem. 

Para isso, serão necessários duas modificações em seu MessageReceiver:

1. Adicione a interface *ISchedulerExtension* no construtor de seu MessageReceiver. **Obs.: Ele será injetado automaticamente pelo SDK**
2. Utilize o método *ScheduleMessageAsync(Meesage m, DateTimeOffset d)* para agendar sua mensagem

O código abaixo apresenta a utilização da extensão de agendamento.

```csharp
//Note that I just changed the MessageReceiver class name from PlainTextMessageReceiver to SchedulerExtensionMessageReceiver
public class SchedulerExtensionMessageReceiver : IMessageReceiver
{
    private readonly ISchedulerExtension _schedulerExtension;
    private readonly IMessagingHubSender _sender;

    public SchedulerExtensionMessageReceiver(IMessagingHubSender sender, ISchedulerExtension schedulerExtension)
    {
        _schedulerExtension = schedulerExtension;
        _sender = sender;
    }

    //Schedule a message to next 10 minutes
    public async Task ReceiveAsync(Message receivedMessage, CancellationToken cancellationToken)
    {
        var schedullingDate = DateTimeOffset.Now.AddMinutes(10);
        var messageContent = "tomar remédio";

        var message = new Message
        {
            Id = Guid.NewGuid().ToString(),
            To = receivedMessage.From,
            Content = new PlainText { Text = messageContent }
        };

        await _schedulerExtension.ScheduleMessageAsync(message, schedullingDate);
    }
}
```

## Crie uma lista de distribuição de conteúdo

Para alguns chatbots, a distribuição de conteúdo é a principal funcionalidade. O chatbot de uma empresa varejista, por exemplo, precisa enviar mensalmente
cupons de promoções para um determinado perfil de clientes. Para isso, é necessário separar os clientes que devem receber os cupons daqueles que não devem e, finalmente, 
enviar as mensagens para o grupo correto.

Para resolver este problema basta utilizar a extensão de listas.

1. Adicione a interface *IBroadcastExtension* no construtor de seu MessageReceiver. **Obs.: Ele será injetado automaticamente pelo SDK**
2. Crie uma nova lista de distribuição utilizando o método *CreateDistributionListAsync(string listName)*
3. Adicione um novo usuário à sua lista com o método *AddRecipientAsync(string listName, Identity recipientIdentity)*
4. Finalmente, envie uma mensagem para todos os usuários de sua lista com o método *SendMessageAsync(string listName, Document d)*

```csharp
public class BroadcastMessageReceiver : IMessageReceiver
{
    private readonly IBroadcastExtension _broadcastExtension;
    private readonly IMessagingHubSender _sender;
    public BroadcastMessageReceiver(IMessagingHubSender sender, IBroadcastExtension broadcastExtension)
    {
        _broadcastExtension = broadcastExtension;
        _sender = sender;
    }
    public async Task ReceiveAsync(Message message, CancellationToken cancellationToken)
    {
        var listName = "couponUsers";
        //Add a new distribution list with name couponUsers
        await _broadcastExtension.CreateDistributionListAsync(listName);
        //Add some users to couponUsers list
        await _broadcastExtension.AddRecipientAsync(listName, message.From.ToIdentity());
        //Send a message to couponUsers list users
        await _broadcastExtension.SendMessageAsync(listName, new PlainText { Text = "Olá você ganhou um novo cupom de descontos" });
    }
}
```

## Armazenando o último acesso de um usuário

Imagine agora que seu desafio seja armazenar a última vez que seu usuário utilizou um determinado serviço do chatbot.

Para isso, vamos precisar de:

1. Adicione a interface *IBucketExtension* no construtor de seu MessageReceiver. **Obs.: Ele será injetado automaticamente pelo SDK**
2. Utilize o método *SetAsync(string resourceId, Document d)* para armazenar um documento contendo a data de último acesso.
3. **Obs.: Utilize o método *GetAsync(string resourceId)* para recuperar as informações salvas anteriormente.**

O código abaixo mostra como salvar um documento json contendo a data de último acesso.

```csharp
public class BucketMessageReceiver : IMessageReceiver
{
    private readonly IBucketExtension _bucketExtension;
    private readonly IMessagingHubSender _sender;
    public BucketMessageReceiver(IMessagingHubSender sender, IBucketExtension bucketExtension)
    {
        _bucketExtension = bucketExtension;
        _sender = sender;
    }
    public async Task ReceiveAsync(Message message, CancellationToken cancellationToken)
    {
        //Store last access date
        var jsonLastAccess = new JsonDocument();
        jsonLastAccess.Add("lastAccessDate", DateTimeOffset.Now);
        await _bucketExtension.SetAsync(message.From.ToString(), jsonLastAccess);

        //Get last access date
        await _bucketExtension.GetAsync<JsonDocument>(message.From.ToString());
    }
}
```

## *Track* de usuários que utilizaram uma determinada funcionalidade 

Por fim, pense na tarefa de *trackear* quantos usuários utilizaram uma determinada funcionalidade (ou enviaram um determinado conteúdo) para o chatbot.

Para isso, vamos utilizar a extensão de análise de eventos:

1. Adicione a interface *IEventTrackExtension* no construtor de seu MessageReceiver. **Obs.: Ele será injetado automaticamente pelo SDK**
2. Utilize o método *AddAsync(string eventName, string eventAction)* para computar uma nova incidência de um evento.

Veja o exemplo abaixo

```csharp
public class EventTrackMessageReceiver : IMessageReceiver
{
    private readonly IEventTrackExtension _eventTrackExtension;
    private readonly IMessagingHubSender _sender;
    public EventTrackMessageReceiver(IMessagingHubSender sender, IEventTrackExtension eventTrackExtension)
    {
        _sender = sender;
        _eventTrackExtension = eventTrackExtension;
    }
    public async Task ReceiveAsync(Message message, CancellationToken cancellationToken)
    {
        await _eventTrackExtension.AddAsync("featureX", "used");
    }
}
```

# Conclusão

Este artigo apresentou o que é e quais são as extensões da plataforma [BLiP](https://blip.ai/). Através de exemplos reais, do dia a dia de um desenvolvedor, ficou comprovado 
que utilizar essas extensões pode ajudar, e muito, a acelerar a implementação de diversas tarefas de um chatbots.

Para ver mais detalhes sobre as extensões, verifique [a seção de mesmo nome na página de documentação](https://portal.blip.ai/#/docs/extensions/) do BLiP

Todo o código desenvolvido para este artigo está disponível no [github](https://github.com/takenet/messaginghub-client-csharp/tree/master/src/Samples/Extensions).
Caso tenha gostado sinta-se a vontade para utilizá-los como ponto de partida em seu chatbot.
