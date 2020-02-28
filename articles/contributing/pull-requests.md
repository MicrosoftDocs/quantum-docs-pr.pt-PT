---
title: Pedidos de abertura de pull
description: Saiba como submeter um pedido de pull GitHub quando estiver pronto para contribuir com código ou documentação para o Kit de Desenvolvimento Quântico da Microsoft.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: a4373a65688893c95e0475356c8f6fca0912f8c5
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907465"
---
# <a name="opening-pull-requests"></a>Abrir Pedidos Pull #

Toda a documentação para o Kit de Desenvolvimento Quântico é gerida utilizando o sistema de controlo da versão Git através da utilização de vários repositórios hospedados no GitHub.
A utilização do Git e do GitHub em conjunto facilita a colaboração ampla no Kit de Desenvolvimento Quântico.
Em particular, qualquer repositório Git pode ser clonado ou bifurcado para fazer uma cópia completamente independente desse repositório.
Isto permite-lhe trabalhar a sua contribuição com as ferramentas e a um ritmo que prefere.

Quando estiver pronto, pode enviar-nos um pedido para incluir a sua contribuição nos nossos repos, utilizando a funcionalidade de pedido de _puxão_ do GitHub.
A página de cada pedido de pull inclui detalhes de todas as alterações que fazem a sua contribuição, uma lista de comentários sobre a sua contribuição, e um conjunto de ferramentas de revisão que outros membros da comunidade podem usar para fornecer feedback e conselhos.

> [!NOTE]
> Enquanto um tutorial completo sobre Git está fora do âmbito deste guia, podemos sugerir os seguintes links para mais recursos na aprendizagem de Git:
>
> - [Learn Git](https://www.atlassian.com/git): Um conjunto de tutoriais git da Atlassian.
> - [Controlo de versão no Código do Estúdio Visual](https://code.visualstudio.com/docs/editor/versioncontrol): Um guia sobre como usar o Código do Estúdio Visual como GUI para Git.
> - [GitHub Learning Lab](https://lab.github.com/): Um conjunto de cursos online para a utilização de Git, GitHub e tecnologias relacionadas.
> - [Visualização do Git](https://git-school.github.io/visualizing-git/): Uma ferramenta interativa para visualizar como os comandos Git mudam o estado de um repositório.
> - [Controlo de Versão com Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): Um tutorial git orientado para a computação científica.
> - [Learn Git Branching](https://learngitbranching.js.org/): Um conjunto interativo de quebra-cabeças de ramificação e rebasquepara ajudar a aprender novas funcionalidades git.

## <a name="what-is-a-pull-request"></a>O que é um pedido de puxar? ##

Dito o que precede, é útil tirar alguns momentos para dizer o que **é**um pedido de atração.
Ao trabalhar com Git, quaisquer alterações são representadas como _compromissos_ que descrevem como essas alterações estão relacionadas com o estado do repositório antes dessas alterações.
Muitas vezes desenhamos diagramas em que os compromissos são desenhados como círculos com setas de compromissos anteriores.

Suponha que tenha começado uma contribuição num _ramo_ chamado `feature`.
Então o seu garfo de **Microsoft/Quantum** pode parecer algo assim:

![Um ramo de trabalho em GitHub](~/media/git-workflow-step0.png)

Se fizer as suas alterações no seu repositório local, pode _retirar_ alterações de outro repositório para o seu para acompanhar quaisquer alterações que ocorreram a montante.

![Puxando e fundindo mudanças de um repo a montante](~/media/git-workflow-step1.png)

Os pedidos de puxão funcionam da mesma forma, mas ao contrário: quando abre um pedido de puxão, pede-se que o repositório a montante puxe a sua contribuição.

![Solicitando para puxar as suas alterações de volta para o repo original](~/media/git-workflow-step2.png)

Ao abrir um pedido de atração a um dos nossos repositórios, o GitHub oferecerá uma oportunidade para outros da comunidade verem um resumo das suas alterações, para comentá-las e fazer sugestões sobre como ajudar a dar uma contribuição ainda melhor.

![Screenshot de um pedido de puxar no GitHub](~/media/pull-request-header.png)

A utilização deste processo ajuda-nos a usar a funcionalidade GitHub para melhorar as contribuições e manter um produto de alta qualidade para a comunidade de programação quântica.

## <a name="how-to-make-a-pull-request"></a>Como fazer um pedido de puxar ##

Há duas maneiras principais de fazer um pedido de atração.
Para pequenas alterações que apenas afetam um único ficheiro, a interface web GitHub pode ser usada para fazer um pedido de pull inteiramente on-line.
Para contribuições mais complicadas, é mais fácil usar o computador local para se preparar primeiro para um pedido de puxão.

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

Parabéns por usar git para ajudar a comunidade quantum development kit!
Para saber mais sobre como contribuir com o código, continue com o seguinte guia.

> [!div class="nextstepaction"]
> [Saiba como contribuir com código](xref:microsoft.quantum.contributing.code)
