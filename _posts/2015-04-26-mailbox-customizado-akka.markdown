---
title: "Como criar um Mailbox customizado com akka"
layout: post
date: 2015-04-26 22:48
author: ravpacheco
lang: pt
ref: customizing-akka-mailbox
tag:
- akka
- mailbox
- java
blog: true
description: Exemplo prático de como criar um maibox customizado para o akka. 
externalLink: true
category: blog
---

Uma das estruturas mais importantes do toolkit akka são os mailbox presentes em todos os atores.

Cada ator possui um mailbox, que pode ser único ou compartilhado por vários atores. É através deles que os atores são capazes de receber mensagens enviadas por outros atores. A cada ciclo de execução o ator verifica seu mailbox e caso exista mensagem a mesma é consumida.

Existem diversas implementações de mailboxes nativas no akka, como por exemplo: ([clique aqui](http://doc.akka.io/docs/akka/current/java/mailboxes.html) para consultar todos os tipos)

1. UnboundedMailbox – O mailbox padrão
    * Utiliza “ConcurrentLinkedQueue” como estrutura de armazenamento
    * Não possui bloqueio
    * Não possui limite de mensagens

2. BoundedMailbox – Mailbox com limite de mensagens
    * Utiliza “LinkedBlockingQueue” como estrutura de armazenamento
    * Possui bloqueio durante as operações
    * Possui um número limite de mensagens.

Apesar de todas as opções oferecidas pelo akka em alguns momentos pode ser necessário que você crie a sua própria implementação de um mailbox.

Para implementar sua própria versão de mailbox é muito simples, basta implementar a interface “MailboxType”.

```java
public class MyUnboundedMailbox implements MailboxType{

   // Este construtor deve existir. Esta assinatura é usada por reflection pelo Akka
   public MyUnboundedMailbox(ActorSystem.Settings settings, Config config) {
        //Coloque outras inicializações aqui
   }

   //Método da interface MaiboxType que deve ser implementado
   public MessageQueue create(Option<ActorRef> owner, Option<ActorSystem> system) {
        return new MyMessageQueue();
   }

}
```

A interface MailboxType exige que o método “create” que retorna um objeto MessageQueue seja implementado. O objeto MessageQueue é a estrutura que armazena todas as mensagens enviadas para o ator.

Além do método create, é necessário que você acrescente um construtor com os parametros “ActorSystem.Settings” e “Config”, este construtor é utilizado internamente pelo akka.

Um exemplo de implementação para uma MessageQueue é apresentado abaixo.

```java
public static class MyMessageQueue implements MessageQueue, MyUnboundedMessageQueueSemantics {
    private final Queue<Envelope> queue = new ConcurrentLinkedQueue<Envelope>();

    // these must be implemented; queue used as example
    public void enqueue(ActorRef receiver, Envelope handle) {
        queue.offer(handle);
    }
    
    public Envelope dequeue() { return queue.poll(); }
    public int numberOfMessages() { return queue.size(); }
    public boolean hasMessages() { return !queue.isEmpty(); }
    
    public void cleanUp(ActorRef owner, MessageQueue deadLetters) {
        for (Envelope handle: queue) {
            deadLetters.enqueue(owner, handle);
        }
    }
}
```

Note que neste caso um “ConcurrentLinkedQueue” (Lista encadeada concorrente padrão do Java) é usada para armazenar as mensagens.

Após implementar seu mailbox basta configurar algum ator para utiliza-lá. Uma forma bem simples de para fazer isso é utilizar o método “withMailbox()” do objeto de propriedades “Props” no momento de criar um novo ator.

```java
ActorRef specialActor = 
                system.actorOf(Props.create(SpecialActor.class)
                      .withMailbox("my-mailbox"));
```

A string “my-mailbox” deve ser configurada no arquivo application.conf de sua aplicação.
Para este exemplo, configure o arquivo application.conf com o código abaixo.

```java
my-mailbox {
    mailbox-type = "your_namespace.MyUnboundedMailbox"
}
```

*Obs.: Altere “your_namespace.MyUnboundedMailbox”
de acordo com o namespace que utilizou para criar seu Mailbox.

Coloquei no meu GitHub um código de exemplo de uma aplicação simples que utiliza uma implementação customizada de um Mailbox.

Agora você já pode alterar todo o comportamento da estrutura de armazenamento de mensagens de seus atores.

E ai, gostou desta dica ?
Envie seu feedback, dúvida e sugestões. Ah, e não esqueça de fazer e compartilhar suas implementações.

# Referências:

1. [akka Mailbox documentation](http://doc.akka.io/docs/akka/current/java/mailboxes.html)