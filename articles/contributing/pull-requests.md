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
# <a name="opening-pull-requests"></a><span data-ttu-id="c98bb-103">Abrindo solicitações pull</span><span class="sxs-lookup"><span data-stu-id="c98bb-103">Opening Pull Requests</span></span> #

<span data-ttu-id="c98bb-104">Toda a documentação do kit de desenvolvimento Quantum é gerenciada usando o sistema de controle de versão do git por meio do uso de vários repositórios hospedados no GitHub.</span><span class="sxs-lookup"><span data-stu-id="c98bb-104">All of the documentation for the Quantum Development Kit is managed using the Git version control system through the use of several repositories hosted on GitHub.</span></span>
<span data-ttu-id="c98bb-105">O uso do git e do GitHub juntos torna mais fácil colaborar amplamente no kit de desenvolvimento Quantum.</span><span class="sxs-lookup"><span data-stu-id="c98bb-105">Using Git and GitHub together makes it easy to collaborate widely on the Quantum Development Kit.</span></span>
<span data-ttu-id="c98bb-106">Em particular, qualquer repositório git pode ser clonado ou bifurcado para fazer uma cópia completamente independente desse repositório.</span><span class="sxs-lookup"><span data-stu-id="c98bb-106">In particular, any Git repository can be cloned or forked to make a completely independent copy of that repository.</span></span>
<span data-ttu-id="c98bb-107">Isso permite que você trabalhe em sua contribuição com as ferramentas e em um ritmo que preferir.</span><span class="sxs-lookup"><span data-stu-id="c98bb-107">This allows you to work on your contribution with the tools and at a pace that you prefer.</span></span>

<span data-ttu-id="c98bb-108">Quando estiver pronto, você pode nos enviar uma solicitação para incluir sua contribuição em nosso repositórios, usando a funcionalidade de _solicitação de pull_ do github.</span><span class="sxs-lookup"><span data-stu-id="c98bb-108">When you're ready, you can send us a request to include your contribution into our repos, using GitHub's _pull request_ functionality.</span></span>
<span data-ttu-id="c98bb-109">A página de cada solicitação de pull inclui detalhes de todas as alterações que fazem sua contribuição, uma lista de comentários sobre sua contribuição e um conjunto de ferramentas de revisão que outros membros da Comunidade podem usar para fornecer comentários e conselhos.</span><span class="sxs-lookup"><span data-stu-id="c98bb-109">The page for each pull request includes details of all the changes that make your contribution, a list of comments on your contribution, and a set of review tools that other members of the community can use to provide feedback and advice.</span></span>

> [!NOTE]
> <span data-ttu-id="c98bb-110">Embora um tutorial completo sobre o Git esteja além do escopo deste guia, podemos sugerir os links a seguir para obter mais recursos no aprendizado do git:</span><span class="sxs-lookup"><span data-stu-id="c98bb-110">While a full tutorial on Git is beyond the scope of this guide, we can suggest the following links for more resources on learning Git:</span></span>
>
> - <span data-ttu-id="c98bb-111">[Aprenda sobre o Git](https://www.atlassian.com/git): um conjunto de tutoriais do git do Atlassian.</span><span class="sxs-lookup"><span data-stu-id="c98bb-111">[Learn Git](https://www.atlassian.com/git): A set of Git tutorials from Atlassian.</span></span>
> - <span data-ttu-id="c98bb-112">[Controle de versão no Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): um guia sobre como usar Visual Studio Code como uma GUI para git.</span><span class="sxs-lookup"><span data-stu-id="c98bb-112">[Version Control in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): A guide on how to use Visual Studio Code as a GUI for Git.</span></span>
> - <span data-ttu-id="c98bb-113">[Laboratório de aprendizado do GitHub](https://lab.github.com/): um conjunto de cursos online para usar git, GitHub e tecnologias relacionadas.</span><span class="sxs-lookup"><span data-stu-id="c98bb-113">[GitHub Learning Lab](https://lab.github.com/): A set of online courses for using Git, GitHub, and related technologies.</span></span>
> - <span data-ttu-id="c98bb-114">[Visualizando o Git](https://git-school.github.io/visualizing-git/): uma ferramenta interativa para visualizar como os comandos git alteram o estado de um repositório.</span><span class="sxs-lookup"><span data-stu-id="c98bb-114">[Visualizing Git](https://git-school.github.io/visualizing-git/): An interactive tool for visualizing how Git commands change the state of a repository.</span></span>
> - <span data-ttu-id="c98bb-115">[Controle de versão com git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): um tutorial do git voltado para A computação científica.</span><span class="sxs-lookup"><span data-stu-id="c98bb-115">[Version Control with Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): A Git tutorial oriented towards scientific computing.</span></span>
> - <span data-ttu-id="c98bb-116">[Aprenda a ramificação do git](https://learngitbranching.js.org/): um conjunto interativo de quebra-cabeças e REBASE para ajudar a aprender novos recursos do git.</span><span class="sxs-lookup"><span data-stu-id="c98bb-116">[Learn Git Branching](https://learngitbranching.js.org/): An interactive set of branching and rebasing puzzles to help learn new Git features.</span></span>

## <a name="what-is-a-pull-request"></a><span data-ttu-id="c98bb-117">O que é uma solicitação de pull?</span><span class="sxs-lookup"><span data-stu-id="c98bb-117">What is a Pull Request?</span></span> ##

<span data-ttu-id="c98bb-118">Dito isso, é útil levar alguns minutos para dizer o que **é**uma solicitação pull.</span><span class="sxs-lookup"><span data-stu-id="c98bb-118">Having said the above, it's helpful to take a few moments to say what a pull request **is**.</span></span>
<span data-ttu-id="c98bb-119">Ao trabalhar com o Git, todas as alterações são representadas como _confirmações_ que descrevem como essas alterações estão relacionadas ao estado do repositório antes dessas alterações.</span><span class="sxs-lookup"><span data-stu-id="c98bb-119">When working with Git, any changes are represented as _commits_ that describe how those changes are related to the state of the repository before those changes.</span></span>
<span data-ttu-id="c98bb-120">Em geral, desenhamos diagramas nos quais as confirmações são desenhadas como círculos com setas de confirmações anteriores.</span><span class="sxs-lookup"><span data-stu-id="c98bb-120">We'll often draw diagrams in which commits are drawn as circles with arrows from previous commits.</span></span>

<span data-ttu-id="c98bb-121">Suponha que você tenha iniciado uma contribuição em uma _ramificação_ chamada `feature`.</span><span class="sxs-lookup"><span data-stu-id="c98bb-121">Suppose you have started a contribution in a _branch_ called `feature`.</span></span>
<span data-ttu-id="c98bb-122">Em seguida, sua bifurcação da **Microsoft/Quantum** pode ser semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="c98bb-122">Then your fork of **Microsoft/Quantum** might look something like this:</span></span>

![](~/media/git-workflow-step0.png)

<span data-ttu-id="c98bb-123">Se você fizer as alterações em seu repositório local, poderá efetuar _pull_ de alterações de outro repositório em seu para obter as alterações que ocorreram upstream.</span><span class="sxs-lookup"><span data-stu-id="c98bb-123">If you make your changes in your local repository, you can _pull_ changes from another repository into yours to catch up to any changes that happened upstream.</span></span>

![](~/media/git-workflow-step1.png)

<span data-ttu-id="c98bb-124">As solicitações de pull funcionam da mesma forma, mas na ordem inversa: quando você abre uma solicitação de pull, solicita o repositório upstream para efetuar o pull da sua contribuição.</span><span class="sxs-lookup"><span data-stu-id="c98bb-124">Pull requests work the same way, but in reverse: when you open a pull request, you ask for the upstream repository to pull your contribution in.</span></span>

![](~/media/git-workflow-step2.png)

<span data-ttu-id="c98bb-125">Quando você abre uma solicitação de pull para um de nossos repositórios, o GitHub oferecerá uma oportunidade para que outras pessoas na Comunidade vejam um resumo das suas alterações, para comentar sobre elas e para fazer sugestões de como ajudar a fazer uma contribuição ainda melhor.</span><span class="sxs-lookup"><span data-stu-id="c98bb-125">When you open a pull request to one of our repositories, GitHub will offer an opportunity for others in the community to see a summary of your changes, to comment on them, and to make suggestions for how to help make an even better contribution.</span></span>

![](~/media/pull-request-header.png)

<span data-ttu-id="c98bb-126">O uso desse processo nos ajuda a usar a funcionalidade do GitHub para melhorar as contribuições e manter um produto de alta qualidade para a comunidade de programação Quantum.</span><span class="sxs-lookup"><span data-stu-id="c98bb-126">Using this process helps us use GitHub functionality to improve contributions and to maintain a high-quality product for the quantum programming community.</span></span>

## <a name="how-to-make-a-pull-request"></a><span data-ttu-id="c98bb-127">Como fazer uma solicitação de pull</span><span class="sxs-lookup"><span data-stu-id="c98bb-127">How to Make a Pull Request</span></span> ##

<span data-ttu-id="c98bb-128">Há duas maneiras principais de fazer uma solicitação de pull.</span><span class="sxs-lookup"><span data-stu-id="c98bb-128">There are two main ways to make a pull request.</span></span>
<span data-ttu-id="c98bb-129">Para pequenas alterações que afetam apenas um único arquivo, a interface da Web do GitHub pode ser usada para fazer uma solicitação pull totalmente online.</span><span class="sxs-lookup"><span data-stu-id="c98bb-129">For small changes that only affect a single file, the GitHub web interface can be used to make a pull request entirely online.</span></span>
<span data-ttu-id="c98bb-130">Para contribuições mais complicadas, geralmente é mais fácil usar seu computador local para se preparar primeiro para uma solicitação de pull.</span><span class="sxs-lookup"><span data-stu-id="c98bb-130">For more complicated contributions, it's most often easier to use your local computer to prepare for a pull request first.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="c98bb-131">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="c98bb-131">Next steps</span></span> ##

<span data-ttu-id="c98bb-132">Parabéns por usar o Git para ajudar a Comunidade do kit de desenvolvimento do Quantum!</span><span class="sxs-lookup"><span data-stu-id="c98bb-132">Congratulations on using Git to help out the Quantum Development Kit community!</span></span>
<span data-ttu-id="c98bb-133">Para saber mais sobre como contribuir com código, continue com o guia a seguir.</span><span class="sxs-lookup"><span data-stu-id="c98bb-133">To learn more about how to contribute code, please continue with the following guide.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c98bb-134">Saiba como contribuir com código</span><span class="sxs-lookup"><span data-stu-id="c98bb-134">Learn how to contribute code</span></span>](xref:microsoft.quantum.contributing.code)
