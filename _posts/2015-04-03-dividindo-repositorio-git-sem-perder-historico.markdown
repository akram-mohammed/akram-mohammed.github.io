---
title: "Dividindo um repositório git sem perder histórico de modificações"
layout: post
date: 2015-04-03 22:48
author: ravpacheco
lang: pt
ref: split-git-repository
tag:
- git
blog: true
category: blog
description: Exemplo prático de como dividir um repositório git sem perder histórico de commits. 
externalLink: true
---

Recentemente precisei subdividir um reposório git em 2. Aparentemente a tarefa é trivial, o problema é que não queria perder todo o histórico de modificações realizado no código.


# Contexto 

Já possuiamos na empresa um repositório git que armazenava uma aplicação backend chamado, por exemplo, de **Plataforma**.
Começamos então o desenvolvimento de uma aplicação Mobile que consome os dados deste backend.

Colocamos o código do app mobile no mesmo repositório do backend em um subdiretório chamado **AppMobile** (Plataforma/AppMobile).

Depois de algum tempo encontramos dificuldades em manter os dois códigos no mesmo repositório, uma vez que a equipe foi subdividida e o desenvolvimento dos dois projetos foi paralelizado.

# Problema

Dividir o repositório **Plataforma** em 2, sem perder o histórico de commits.

1) **Plataforma**: Contendo apenas o código de backend;
2) **AppMobile**: Contendo o código do app mobile;

Solução:

1) Clone o repositório que será dividido (no meu caso Plataforma):

```shell
git clone --no-hardlinks C:/Git/Plataforma C:/Git/PlataformaClone
```

2) Vá para o novo repositório criado

```shell
cd C:/Git/PlataformaClone
```

3) Execute o comando filter-branch do git com o nome da pasta que você deseja transformar em outro repositório (no meu caso Plataforma/AppMobile).

```shell
git filter-branch --prune-empty --subdirectory-filter Plataforma/AppMobile&nbsp;master
```

*Obs.: Note que se você acessar o repositório clonado (PlataformaClone) verá que não existe nada no repositório a não ser as referências de todo o histórico do repositório inicial (Plataforma)*

4) Para recriar o repositório com todo o histórico de commits execute o comando reset do git

```shell
git reset --hard original/refs/heads/master
```

5) Remova todos os diretórios e arquivos que você não deseja que estejam presentes no novo repositório.

6) Altere a URL remota de seu repositório (no meu caso http://test.com/AppMobile.git)

```shell
git remote set-url origin &nbsp;http://test.com/AppMobile.git
```

7) Dê push em seu novo repositório

```shell
git push
```

# Resultado

Após executados os passos acima passamos a usar 2 repositórios ao invés de apenas 1, sem perder nenhuma informação.

**De:**

```shell
//Repositorio 1

Plataforma/ 
    AppMobile/
    outrosDiretorios/
```

**Para:**

```shell
//Repositorio 1

Plataforma/
    outrosDiretorios/
```

```shell
//Repositorio 2

AppMobile/
```

# Referências:

1. [https://help.github.com/articles/splitting-a-subfolder-out-into-a-new-repository/](https://help.github.com/articles/splitting-a-subfolder-out-into-a-new-repository/)
2. [http://blogs.atlassian.com/2014/04/tear-apart-repository-git-way/](http://blogs.atlassian.com/2014/04/tear-apart-repository-git-way/)