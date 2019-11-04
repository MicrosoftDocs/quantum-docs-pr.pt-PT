---
title: Abrindo solicitações pull | Microsoft Docs
description: Abrindo solicitações pull
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: d70a0a0319d14cfdae4910b897733d77b236f2f9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183731"
---
# <a name="opening-pull-requests"></a>Abrindo solicitações pull #

Toda a documentação do kit de desenvolvimento Quantum é gerenciada usando o sistema de controle de versão do git por meio do uso de vários repositórios hospedados no GitHub.
O uso do git e do GitHub juntos torna mais fácil colaborar amplamente no kit de desenvolvimento Quantum.
Em particular, qualquer repositório git pode ser clonado ou bifurcado para fazer uma cópia completamente independente desse repositório.
Isso permite que você trabalhe em sua contribuição com as ferramentas e em um ritmo que preferir.

Quando estiver pronto, você pode nos enviar uma solicitação para incluir sua contribuição em nosso repositórios, usando a funcionalidade de _solicitação de pull_ do github.
A página de cada solicitação de pull inclui detalhes de todas as alterações que fazem sua contribuição, uma lista de comentários sobre sua contribuição e um conjunto de ferramentas de revisão que outros membros da Comunidade podem usar para fornecer comentários e conselhos.

> [!NOTE]
> Embora um tutorial completo sobre o Git esteja além do escopo deste guia, podemos sugerir os links a seguir para obter mais recursos no aprendizado do git:
>
> - [Aprenda sobre o Git](https://www.atlassian.com/git): um conjunto de tutoriais do git do Atlassian.
> - [Controle de versão no Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): um guia sobre como usar Visual Studio Code como uma GUI para git.
> - [Laboratório de aprendizado do GitHub](https://lab.github.com/): um conjunto de cursos online para usar git, GitHub e tecnologias relacionadas.
> - [Visualizando o Git](https://git-school.github.io/visualizing-git/): uma ferramenta interativa para visualizar como os comandos git alteram o estado de um repositório.
> - [Controle de versão com git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): um tutorial do git voltado para A computação científica.
> - [Aprenda a ramificação do git](https://learngitbranching.js.org/): um conjunto interativo de quebra-cabeças e REBASE para ajudar a aprender novos recursos do git.

## <a name="what-is-a-pull-request"></a>O que é uma solicitação de pull? ##

Dito isso, é útil levar alguns minutos para dizer o que **é**uma solicitação pull.
Ao trabalhar com o Git, todas as alterações são representadas como _confirmações_ que descrevem como essas alterações estão relacionadas ao estado do repositório antes dessas alterações.
Em geral, desenhamos diagramas nos quais as confirmações são desenhadas como círculos com setas de confirmações anteriores.

Suponha que você tenha iniciado uma contribuição em uma _ramificação_ chamada `feature`.
Em seguida, sua bifurcação da **Microsoft/Quantum** pode ser semelhante a esta:

![](~/media/git-workflow-step0.png)

Se você fizer as alterações em seu repositório local, poderá efetuar _pull_ de alterações de outro repositório em seu para obter as alterações que ocorreram upstream.

![](~/media/git-workflow-step1.png)

As solicitações de pull funcionam da mesma forma, mas na ordem inversa: quando você abre uma solicitação de pull, solicita o repositório upstream para efetuar o pull da sua contribuição.

![](~/media/git-workflow-step2.png)

Quando você abre uma solicitação de pull para um de nossos repositórios, o GitHub oferecerá uma oportunidade para que outras pessoas na Comunidade vejam um resumo das suas alterações, para comentar sobre elas e para fazer sugestões de como ajudar a fazer uma contribuição ainda melhor.

![](~/media/pull-request-header.png)

O uso desse processo nos ajuda a usar a funcionalidade do GitHub para melhorar as contribuições e manter um produto de alta qualidade para a comunidade de programação Quantum.

## <a name="how-to-make-a-pull-request"></a>Como fazer uma solicitação de pull ##

Há duas maneiras principais de fazer uma solicitação de pull.
Para pequenas alterações que afetam apenas um único arquivo, a interface da Web do GitHub pode ser usada para fazer uma solicitação pull totalmente online.
Para contribuições mais complicadas, geralmente é mais fácil usar seu computador local para se preparar primeiro para uma solicitação de pull.

<!--
### Using the Web Interface ###

**TODO**

### Command-Line and GitHub Flow ###

Most of the time, it's easier to prepare a pull request on your own computer; that makes it easier to work incrementally, and to test your changes.
If you haven't already done so, the first step is to _fork_ the repository that you'd like to contribute to.
Forking makes a complete clone of the original repository, but under your GitHub account instead of under [Microsoft](http://github.com/Microsoft/) or [MicrosoftDocs](http://github.com/MicrosoftDocs/).
This way, you can edit your personal fork to your heart's content before making a pull request for your work.

**TODO: pick up here**

## Code Review and Etiquette ##

**TODO: PR ettiquette, reviews, etc.**

-->

## <a name="next-steps"></a>Passos seguintes ##

Parabéns por usar o Git para ajudar a Comunidade do kit de desenvolvimento do Quantum!
Para saber mais sobre como contribuir com código, continue com o guia a seguir.

> [!div class="nextstepaction"]
> [Saiba como contribuir com código](xref:microsoft.quantum.contributing.code)
