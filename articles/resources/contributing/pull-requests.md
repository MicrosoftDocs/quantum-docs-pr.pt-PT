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
# <a name="opening-pull-requests"></a><span data-ttu-id="dae7b-103">Abrir Pedidos Pull</span><span class="sxs-lookup"><span data-stu-id="dae7b-103">Opening Pull Requests</span></span> #

<span data-ttu-id="dae7b-104">Toda a documentação para o Kit de Desenvolvimento Quântico é gerida utilizando o sistema de controlo da versão Git através da utilização de vários repositórios alojados no GitHub.</span><span class="sxs-lookup"><span data-stu-id="dae7b-104">All of the documentation for the Quantum Development Kit is managed using the Git version control system through the use of several repositories hosted on GitHub.</span></span>
<span data-ttu-id="dae7b-105">A utilização de Git e GitHub em conjunto facilita a colaboração amplamente no Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="dae7b-105">Using Git and GitHub together makes it easy to collaborate widely on the Quantum Development Kit.</span></span>
<span data-ttu-id="dae7b-106">Em particular, qualquer repositório de Git pode ser clonado ou forcado para fazer uma cópia completamente independente desse repositório.</span><span class="sxs-lookup"><span data-stu-id="dae7b-106">In particular, any Git repository can be cloned or forked to make a completely independent copy of that repository.</span></span>
<span data-ttu-id="dae7b-107">Isto permite-lhe trabalhar a sua contribuição com as ferramentas e a um ritmo que prefere.</span><span class="sxs-lookup"><span data-stu-id="dae7b-107">This allows you to work on your contribution with the tools and at a pace that you prefer.</span></span>

<span data-ttu-id="dae7b-108">Quando estiver pronto, pode enviar-nos um pedido para incluir a sua contribuição nos nossos repos, utilizando a funcionalidade de pedido de _pull_ do GitHub.</span><span class="sxs-lookup"><span data-stu-id="dae7b-108">When you're ready, you can send us a request to include your contribution into our repos, using GitHub's _pull request_ functionality.</span></span>
<span data-ttu-id="dae7b-109">A página para cada pedido de pull inclui detalhes de todas as alterações que fazem a sua contribuição, uma lista de comentários sobre a sua contribuição, e um conjunto de ferramentas de revisão que outros membros da comunidade podem usar para fornecer feedback e conselhos.</span><span class="sxs-lookup"><span data-stu-id="dae7b-109">The page for each pull request includes details of all the changes that make your contribution, a list of comments on your contribution, and a set of review tools that other members of the community can use to provide feedback and advice.</span></span>

> [!NOTE]
> <span data-ttu-id="dae7b-110">Enquanto um tutorial completo em Git está fora do âmbito deste guia, podemos sugerir as seguintes ligações para mais recursos na aprendizagem de Git:</span><span class="sxs-lookup"><span data-stu-id="dae7b-110">While a full tutorial on Git is beyond the scope of this guide, we can suggest the following links for more resources on learning Git:</span></span>
>
> - <span data-ttu-id="dae7b-111">[Learn Git](https://www.atlassian.com/git): Um conjunto de tutoriais git de Atlassian.</span><span class="sxs-lookup"><span data-stu-id="dae7b-111">[Learn Git](https://www.atlassian.com/git): A set of Git tutorials from Atlassian.</span></span>
> - <span data-ttu-id="dae7b-112">[Version Control in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): Um guia sobre como usar o Código do Estúdio Visual como GUI para Git.</span><span class="sxs-lookup"><span data-stu-id="dae7b-112">[Version Control in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): A guide on how to use Visual Studio Code as a GUI for Git.</span></span>
> - <span data-ttu-id="dae7b-113">[GitHub Learning Lab](https://lab.github.com/): Um conjunto de cursos online para a utilização de Git, GitHub e tecnologias relacionadas.</span><span class="sxs-lookup"><span data-stu-id="dae7b-113">[GitHub Learning Lab](https://lab.github.com/): A set of online courses for using Git, GitHub, and related technologies.</span></span>
> - <span data-ttu-id="dae7b-114">[Visualização do Git](https://git-school.github.io/visualizing-git/): Uma ferramenta interativa para visualizar como os comandos de Git mudam o estado de um repositório.</span><span class="sxs-lookup"><span data-stu-id="dae7b-114">[Visualizing Git](https://git-school.github.io/visualizing-git/): An interactive tool for visualizing how Git commands change the state of a repository.</span></span>
> - <span data-ttu-id="dae7b-115">[Versão Controle com Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): Um tutorial git orientado para a computação científica.</span><span class="sxs-lookup"><span data-stu-id="dae7b-115">[Version Control with Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): A Git tutorial oriented towards scientific computing.</span></span>
> - <span data-ttu-id="dae7b-116">[Aprenda Git Branching](https://learngitbranching.js.org/): Um conjunto interativo de quebra-cabeças de ramificação e rebasing para ajudar a aprender novas funcionalidades de Git.</span><span class="sxs-lookup"><span data-stu-id="dae7b-116">[Learn Git Branching](https://learngitbranching.js.org/): An interactive set of branching and rebasing puzzles to help learn new Git features.</span></span>

## <a name="what-is-a-pull-request"></a><span data-ttu-id="dae7b-117">O que é um pedido de puxar?</span><span class="sxs-lookup"><span data-stu-id="dae7b-117">What is a Pull Request?</span></span> ##

<span data-ttu-id="dae7b-118">Dito isto, é útil tirar alguns momentos para dizer o que **é**um pedido de retirada.</span><span class="sxs-lookup"><span data-stu-id="dae7b-118">Having said the above, it's helpful to take a few moments to say what a pull request **is**.</span></span>
<span data-ttu-id="dae7b-119">Ao trabalhar com Git, quaisquer alterações são representadas como _compromissos_ que descrevem como essas mudanças estão relacionadas com o estado do repositório antes dessas mudanças.</span><span class="sxs-lookup"><span data-stu-id="dae7b-119">When working with Git, any changes are represented as _commits_ that describe how those changes are related to the state of the repository before those changes.</span></span>
<span data-ttu-id="dae7b-120">Muitas vezes desenhamos diagramas em que os compromissos são desenhados como círculos com setas de compromissos anteriores.</span><span class="sxs-lookup"><span data-stu-id="dae7b-120">We'll often draw diagrams in which commits are drawn as circles with arrows from previous commits.</span></span>

<span data-ttu-id="dae7b-121">Suponha que tenha iniciado uma contribuição numa _sucursal_ `feature` chamada.</span><span class="sxs-lookup"><span data-stu-id="dae7b-121">Suppose you have started a contribution in a _branch_ called `feature`.</span></span>
<span data-ttu-id="dae7b-122">Então o seu garfo da **Microsoft/Quantum** pode parecer algo assim:</span><span class="sxs-lookup"><span data-stu-id="dae7b-122">Then your fork of **Microsoft/Quantum** might look something like this:</span></span>

![Um ramo de trabalho em GitHub](~/media/git-workflow-step0.png)

<span data-ttu-id="dae7b-124">Se fizer as suas alterações no seu repositório local, pode _puxar_ as alterações de outro repositório para o seu para acompanhar quaisquer alterações que ocorreram a montante.</span><span class="sxs-lookup"><span data-stu-id="dae7b-124">If you make your changes in your local repository, you can _pull_ changes from another repository into yours to catch up to any changes that happened upstream.</span></span>

![Puxar e fundir alterações a partir de um repo a montante](~/media/git-workflow-step1.png)

<span data-ttu-id="dae7b-126">Os pedidos de puxar funcionam da mesma forma, mas ao contrário: quando abre um pedido de puxar, pede-se que o repositório a montante puxe a sua contribuição.</span><span class="sxs-lookup"><span data-stu-id="dae7b-126">Pull requests work the same way, but in reverse: when you open a pull request, you ask for the upstream repository to pull your contribution in.</span></span>

![Solicitando para puxar as suas alterações de volta para o repo original](~/media/git-workflow-step2.png)

<span data-ttu-id="dae7b-128">Quando você abrir um pedido de puxar para um dos nossos repositórios, o GitHub oferecerá uma oportunidade para que outros na comunidade vejam um resumo das suas mudanças, para comentá-las, e para fazer sugestões de como ajudar a dar um contributo ainda melhor.</span><span class="sxs-lookup"><span data-stu-id="dae7b-128">When you open a pull request to one of our repositories, GitHub will offer an opportunity for others in the community to see a summary of your changes, to comment on them, and to make suggestions for how to help make an even better contribution.</span></span>

![Screenshot de um pedido de puxar em GitHub](~/media/pull-request-header.png)

<span data-ttu-id="dae7b-130">A utilização deste processo ajuda-nos a usar a funcionalidade GitHub para melhorar as contribuições e manter um produto de alta qualidade para a comunidade de programação quântica.</span><span class="sxs-lookup"><span data-stu-id="dae7b-130">Using this process helps us use GitHub functionality to improve contributions and to maintain a high-quality product for the quantum programming community.</span></span>

## <a name="how-to-make-a-pull-request"></a><span data-ttu-id="dae7b-131">Como fazer um pedido de puxar</span><span class="sxs-lookup"><span data-stu-id="dae7b-131">How to Make a Pull Request</span></span> ##

<span data-ttu-id="dae7b-132">Há duas maneiras principais de fazer um pedido de atração.</span><span class="sxs-lookup"><span data-stu-id="dae7b-132">There are two main ways to make a pull request.</span></span>  
<span data-ttu-id="dae7b-133">Para pequenas alterações que apenas afetam um único ficheiro, a interface web GitHub pode ser usada para fazer um pedido de pull inteiramente on-line.</span><span class="sxs-lookup"><span data-stu-id="dae7b-133">For small changes that only affect a single file, the GitHub web interface can be used to make a pull request entirely online.</span></span> <span data-ttu-id="dae7b-134">Basta navegar para o ficheiro que pretende editar e utilizar o ícone de edição.</span><span class="sxs-lookup"><span data-stu-id="dae7b-134">Simply navigate to the file you want to edit and use the edit icon.</span></span>  
<span data-ttu-id="dae7b-135">Para contribuições mais complicadas, é mais fácil clonar o repositório para o seu computador local para se preparar primeiro para um pedido de puxar.</span><span class="sxs-lookup"><span data-stu-id="dae7b-135">For more complicated contributions, it's most often easier to clone the repository to your local computer to prepare for a pull request first.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="dae7b-136">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="dae7b-136">Next steps</span></span> ##

<span data-ttu-id="dae7b-137">Parabéns por usar Git para ajudar a comunidade do Kit de Desenvolvimento Quântico!</span><span class="sxs-lookup"><span data-stu-id="dae7b-137">Congratulations on using Git to help out the Quantum Development Kit community!</span></span>
<span data-ttu-id="dae7b-138">Para saber mais sobre como contribuir com o código, continue com o seguinte guia.</span><span class="sxs-lookup"><span data-stu-id="dae7b-138">To learn more about how to contribute code, please continue with the following guide.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="dae7b-139">Saiba como contribuir com o código</span><span class="sxs-lookup"><span data-stu-id="dae7b-139">Learn how to contribute code</span></span>](xref:microsoft.quantum.contributing.code)
