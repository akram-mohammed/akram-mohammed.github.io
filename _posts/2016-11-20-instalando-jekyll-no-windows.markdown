---
title: "Instalando Jekyll no Windows"
layout: post
date: 2016-11-08 22:44
author: ravpacheco
lang: pt
ref: install-jekyll-windows
tag:
- jekyll
- windows
- getting starter
blog: true
star: true
description: Aprenda, passo a passo, como instalar o Jekyll no Windows.
hidden: true
externalLink: false
category: blog
---

[//]: # (entenda melhor porquê aqui)

Recentemente resolvi mudar meu blog do wordpress para o [Jekyll](https://jekyllrb.com/) , uma ferramenta para 
geração de blogs e sites estáticos. Na maior parte do tempo utilizo máquinas com sistema Windows e portanto precisei instalar e configurar 
o Jekyll em meu ambiente.    

Aparentemente esta parece ser uma tarefa simples, mas isso não é verdade. Assim como eu, vi na internet o 
relato de várias pessoas com problemas para a instalação e configuração do Jekyll no Windows. Com o objetivo de 
ajudar quem ainda vai utilizar o Jekyll, no windows, resolvi documentar a metodologia que utilizei.

## 1 - Instale o Chocolatey

Antes de qualquer coisa é desejável que você possua o [Chocolatey](https://chocolatey.org) já instalado em sua máquina. O Chocolatey é um 
'apt-get', para windows, que facilita muito a instalação e gerenciamento de qualquer aplicações.

[Clique aqui](https://chocolatey.org/install) e veja como instalar o Chocolatey. 

## 2 - Instale o Ruby

Para a versão mais recente do Jekyll o único pré requisito é o Ruby. Para instalar abra o prompt de comando e utilize 
o comando de instalação de pacote do Chocolatey.

```shell
choco install ruby
```

## 3 - Instale o Jekyll

Como você deve ter percebido o Jekyll foi escrito em Ruby e para instalá-lo é preciso utilizar o RubyGem (o gerenciador 
de pacotes do Ruby). Este gerenciador já vem embarcado no ambiente ruby que instalamos no passo anterior, por isso basta 
executar o comando abaixo no prompt e você já terá o Jekyll em sua máquina. 

```shell
gem install jekyll
```

Até aqui tudo parece muito Next > Next > Next. Mas é agora que as coisas começam a complicar.
Se você executou o comando acima, provavelmente recebeu o seguinte erro no console

```shell
ERROR:  Could not find a valid gem 'jekyll' (>= 0), here is why:
    Unable to download data from https://rubygems.org/ - SSL_connect returned=1 errno=0 state=SSLv3 read server certificate B: certificate verify failed (https://api.rubygems.org/specs.4.8.gz) 
```

Este é um problema conhecido no Ruby para Windows. Como dito na mensagem acima o gerenciador não consegue buscar 
pacotes a partir de uma url que utiliza SSL.

## 4 - Mudando o endereço do repositório dos pacotes do RubyGem

Para contornar este problema será necessário alterar o endereço do repositorio dos pacotes do RubyGem para 
uma url sem SSL. Para isso, use o comando abaixo para adicionar o novo endereço

 ```ruby
    gem sources -a http://rubygems.org/ - will add http source
 ```

Agora remova o endereço que possui **https**

```ruby
    gem sources --remove https://rubygems.org/ - will remove the https source
```

Para checar que a fonte dos pacotes está correta use o comando:

```ruby
    gem sources -check sources
```

A saída correta deverá ser:

```shell

*** CURRENT SOURCES ***

http://rubygems.org/

```

## 5 - Baixe um template ou crie o seu

Existem diversos templates para Jekyll de blogs e sites, caso esteja a procura de algum recomendo dar uma olhada 
[neste site](http://jekyllthemes.org/).   

Caso deseje iniciar do zero seu projeto use os seguintes comandos do jekyll

```shell
# create a empty jekyll project
jekyll new myblog
# go to your project
cd myblog
# start a local server for your project
jekyll serve
``` 

## Conclusão

Neste post compartilhei um pouco da minha experiência ao instalar, em uma máquina windows, todo o ambiente necessário 
para a construção de um site utilizando o Jekyll. Como disse inicialmente utilizei exatamente este passo a passo para 
configurar meu blog pessoal.  
Ficou com alguma dúvida, tem alguma sugestão ou crítica ? Mande seu comentário.        

 

