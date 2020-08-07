---
title: Pedidos de retirada de abertura
description: Saiba como submeter um pedido de retirada do GitHub quando estiver pronto para contribuir com código ou documentação para o Microsoft Quantum Development Kit.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8e04e6502e0a6005dfdf0f93450bf3ffd5aaa672
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866932"
---
# <a name="opening-pull-requests"></a>Abrir Pedidos Pull #

Toda a documentação para o Kit de Desenvolvimento Quântico é gerida utilizando o sistema de controlo da versão Git através da utilização de vários repositórios alojados no GitHub.
A utilização de Git e GitHub em conjunto facilita a colaboração amplamente no Kit de Desenvolvimento Quântico.
Em particular, qualquer repositório de Git pode ser clonado ou forcado para fazer uma cópia completamente independente desse repositório.
Isto permite-lhe trabalhar a sua contribuição com as ferramentas e a um ritmo que prefere.

Quando estiver pronto, pode enviar-nos um pedido para incluir a sua contribuição nos nossos repos, utilizando a funcionalidade de pedido de _pull_ do GitHub.
A página para cada pedido de pull inclui detalhes de todas as alterações que fazem a sua contribuição, uma lista de comentários sobre a sua contribuição, e um conjunto de ferramentas de revisão que outros membros da comunidade podem usar para fornecer feedback e conselhos.

> [!NOTE]
> Enquanto um tutorial completo em Git está fora do âmbito deste guia, podemos sugerir as seguintes ligações para mais recursos na aprendizagem de Git:
>
> - [Learn Git](https://www.atlassian.com/git): Um conjunto de tutoriais git de Atlassian.
> - [Version Control in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): Um guia sobre como usar o Código do Estúdio Visual como GUI para Git.
> - [GitHub Learning Lab](https://lab.github.com/): Um conjunto de cursos online para a utilização de Git, GitHub e tecnologias relacionadas.
> - [Visualização do Git](https://git-school.github.io/visualizing-git/): Uma ferramenta interativa para visualizar como os comandos de Git mudam o estado de um repositório.
> - [Versão Controle com Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): Um tutorial git orientado para a computação científica.
> - [Aprenda Git Branching](https://learngitbranching.js.org/): Um conjunto interativo de quebra-cabeças de ramificação e rebasing para ajudar a aprender novas funcionalidades de Git.

## <a name="what-is-a-pull-request"></a>O que é um pedido de puxar? ##

Dito isto, é útil tirar alguns momentos para dizer o que **é**um pedido de retirada.
Ao trabalhar com Git, quaisquer alterações são representadas como _compromissos_ que descrevem como essas mudanças estão relacionadas com o estado do repositório antes dessas mudanças.
Muitas vezes desenhamos diagramas em que os compromissos são desenhados como círculos com setas de compromissos anteriores.

Suponha que tenha iniciado uma contribuição numa _sucursal_ `feature` chamada.
Então o seu garfo da **Microsoft/Quantum** pode parecer algo assim:

![Um ramo de trabalho em GitHub](~/media/git-workflow-step0.png)

Se fizer as suas alterações no seu repositório local, pode _puxar_ as alterações de outro repositório para o seu para acompanhar quaisquer alterações que ocorreram a montante.

![Puxar e fundir alterações a partir de um repo a montante](~/media/git-workflow-step1.png)

Os pedidos de puxar funcionam da mesma forma, mas ao contrário: quando abre um pedido de puxar, pede-se que o repositório a montante puxe a sua contribuição.

![Solicitando para puxar as suas alterações de volta para o repo original](~/media/git-workflow-step2.png)

Quando você abrir um pedido de puxar para um dos nossos repositórios, o GitHub oferecerá uma oportunidade para que outros na comunidade vejam um resumo das suas mudanças, para comentá-las, e para fazer sugestões de como ajudar a dar um contributo ainda melhor.

![Screenshot de um pedido de puxar em GitHub](~/media/pull-request-header.png)

A utilização deste processo ajuda-nos a usar a funcionalidade GitHub para melhorar as contribuições e manter um produto de alta qualidade para a comunidade de programação quântica.

## <a name="how-to-make-a-pull-request"></a>Como fazer um pedido de puxar ##

Há duas maneiras principais de fazer um pedido de atração.  
Para pequenas alterações que apenas afetam um único ficheiro, a interface web GitHub pode ser usada para fazer um pedido de pull inteiramente on-line. Basta navegar para o ficheiro que pretende editar e utilizar o ícone de edição.  
Para contribuições mais complicadas, é mais fácil clonar o repositório para o seu computador local para se preparar primeiro para um pedido de puxar.

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

Parabéns por usar Git para ajudar a comunidade do Kit de Desenvolvimento Quântico!
Para saber mais sobre como contribuir com o código, continue com o seguinte guia.

> [!div class="nextstepaction"]
> [Saiba como contribuir com o código](xref:microsoft.quantum.contributing.code)
