---
title: Pedidos de abertura de pull
description: Saiba como submeter um pedido de pull GitHub quando estiver pronto para contribuir com código ou documentação para o Kit de Desenvolvimento Quântico da Microsoft.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: 82af3b5123588cc06882f746ffcb0402ad3f0f2e
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82686840"
---
# <a name="opening-pull-requests"></a><span data-ttu-id="61a0c-103">Abrir Pedidos Pull</span><span class="sxs-lookup"><span data-stu-id="61a0c-103">Opening Pull Requests</span></span> #

<span data-ttu-id="61a0c-104">Toda a documentação para o Kit de Desenvolvimento Quântico é gerida utilizando o sistema de controlo da versão Git através da utilização de vários repositórios hospedados no GitHub.</span><span class="sxs-lookup"><span data-stu-id="61a0c-104">All of the documentation for the Quantum Development Kit is managed using the Git version control system through the use of several repositories hosted on GitHub.</span></span>
<span data-ttu-id="61a0c-105">A utilização do Git e do GitHub em conjunto facilita a colaboração ampla no Kit de Desenvolvimento Quântico.</span><span class="sxs-lookup"><span data-stu-id="61a0c-105">Using Git and GitHub together makes it easy to collaborate widely on the Quantum Development Kit.</span></span>
<span data-ttu-id="61a0c-106">Em particular, qualquer repositório Git pode ser clonado ou bifurcado para fazer uma cópia completamente independente desse repositório.</span><span class="sxs-lookup"><span data-stu-id="61a0c-106">In particular, any Git repository can be cloned or forked to make a completely independent copy of that repository.</span></span>
<span data-ttu-id="61a0c-107">Isto permite-lhe trabalhar a sua contribuição com as ferramentas e a um ritmo que prefere.</span><span class="sxs-lookup"><span data-stu-id="61a0c-107">This allows you to work on your contribution with the tools and at a pace that you prefer.</span></span>

<span data-ttu-id="61a0c-108">Quando estiver pronto, pode enviar-nos um pedido para incluir a sua contribuição nos nossos repos, utilizando a funcionalidade de pedido de _puxão_ do GitHub.</span><span class="sxs-lookup"><span data-stu-id="61a0c-108">When you're ready, you can send us a request to include your contribution into our repos, using GitHub's _pull request_ functionality.</span></span>
<span data-ttu-id="61a0c-109">A página de cada pedido de pull inclui detalhes de todas as alterações que fazem a sua contribuição, uma lista de comentários sobre a sua contribuição, e um conjunto de ferramentas de revisão que outros membros da comunidade podem usar para fornecer feedback e conselhos.</span><span class="sxs-lookup"><span data-stu-id="61a0c-109">The page for each pull request includes details of all the changes that make your contribution, a list of comments on your contribution, and a set of review tools that other members of the community can use to provide feedback and advice.</span></span>

> [!NOTE]
> <span data-ttu-id="61a0c-110">Enquanto um tutorial completo sobre Git está fora do âmbito deste guia, podemos sugerir os seguintes links para mais recursos na aprendizagem de Git:</span><span class="sxs-lookup"><span data-stu-id="61a0c-110">While a full tutorial on Git is beyond the scope of this guide, we can suggest the following links for more resources on learning Git:</span></span>
>
> - <span data-ttu-id="61a0c-111">[Learn Git](https://www.atlassian.com/git): Um conjunto de tutoriais git da Atlassian.</span><span class="sxs-lookup"><span data-stu-id="61a0c-111">[Learn Git](https://www.atlassian.com/git): A set of Git tutorials from Atlassian.</span></span>
> - <span data-ttu-id="61a0c-112">[Controlo de versão no Código do Estúdio Visual](https://code.visualstudio.com/docs/editor/versioncontrol): Um guia sobre como usar o Código do Estúdio Visual como GUI para Git.</span><span class="sxs-lookup"><span data-stu-id="61a0c-112">[Version Control in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): A guide on how to use Visual Studio Code as a GUI for Git.</span></span>
> - <span data-ttu-id="61a0c-113">[GitHub Learning Lab](https://lab.github.com/): Um conjunto de cursos online para a utilização de Git, GitHub e tecnologias relacionadas.</span><span class="sxs-lookup"><span data-stu-id="61a0c-113">[GitHub Learning Lab](https://lab.github.com/): A set of online courses for using Git, GitHub, and related technologies.</span></span>
> - <span data-ttu-id="61a0c-114">[Visualização do Git](https://git-school.github.io/visualizing-git/): Uma ferramenta interativa para visualizar como os comandos Git mudam o estado de um repositório.</span><span class="sxs-lookup"><span data-stu-id="61a0c-114">[Visualizing Git](https://git-school.github.io/visualizing-git/): An interactive tool for visualizing how Git commands change the state of a repository.</span></span>
> - <span data-ttu-id="61a0c-115">[Controlo de Versão com Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): Um tutorial git orientado para a computação científica.</span><span class="sxs-lookup"><span data-stu-id="61a0c-115">[Version Control with Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): A Git tutorial oriented towards scientific computing.</span></span>
> - <span data-ttu-id="61a0c-116">[Learn Git Branching](https://learngitbranching.js.org/): Um conjunto interativo de quebra-cabeças de ramificação e rebasquepara ajudar a aprender novas funcionalidades git.</span><span class="sxs-lookup"><span data-stu-id="61a0c-116">[Learn Git Branching](https://learngitbranching.js.org/): An interactive set of branching and rebasing puzzles to help learn new Git features.</span></span>

## <a name="what-is-a-pull-request"></a><span data-ttu-id="61a0c-117">O que é um pedido de puxar?</span><span class="sxs-lookup"><span data-stu-id="61a0c-117">What is a Pull Request?</span></span> ##

<span data-ttu-id="61a0c-118">Dito o que precede, é útil tirar alguns momentos para dizer o que **é**um pedido de atração.</span><span class="sxs-lookup"><span data-stu-id="61a0c-118">Having said the above, it's helpful to take a few moments to say what a pull request **is**.</span></span>
<span data-ttu-id="61a0c-119">Ao trabalhar com Git, quaisquer alterações são representadas como _compromissos_ que descrevem como essas alterações estão relacionadas com o estado do repositório antes dessas alterações.</span><span class="sxs-lookup"><span data-stu-id="61a0c-119">When working with Git, any changes are represented as _commits_ that describe how those changes are related to the state of the repository before those changes.</span></span>
<span data-ttu-id="61a0c-120">Muitas vezes desenhamos diagramas em que os compromissos são desenhados como círculos com setas de compromissos anteriores.</span><span class="sxs-lookup"><span data-stu-id="61a0c-120">We'll often draw diagrams in which commits are drawn as circles with arrows from previous commits.</span></span>

<span data-ttu-id="61a0c-121">Suponha que tenha começado `feature`uma contribuição num _ramo_ chamado.</span><span class="sxs-lookup"><span data-stu-id="61a0c-121">Suppose you have started a contribution in a _branch_ called `feature`.</span></span>
<span data-ttu-id="61a0c-122">Então o seu garfo de **Microsoft/Quantum** pode parecer algo assim:</span><span class="sxs-lookup"><span data-stu-id="61a0c-122">Then your fork of **Microsoft/Quantum** might look something like this:</span></span>

![Um ramo de trabalho em GitHub](~/media/git-workflow-step0.png)

<span data-ttu-id="61a0c-124">Se fizer as suas alterações no seu repositório local, pode _retirar_ alterações de outro repositório para o seu para acompanhar quaisquer alterações que ocorreram a montante.</span><span class="sxs-lookup"><span data-stu-id="61a0c-124">If you make your changes in your local repository, you can _pull_ changes from another repository into yours to catch up to any changes that happened upstream.</span></span>

![Puxando e fundindo mudanças de um repo a montante](~/media/git-workflow-step1.png)

<span data-ttu-id="61a0c-126">Os pedidos de puxão funcionam da mesma forma, mas ao contrário: quando abre um pedido de puxão, pede-se que o repositório a montante puxe a sua contribuição.</span><span class="sxs-lookup"><span data-stu-id="61a0c-126">Pull requests work the same way, but in reverse: when you open a pull request, you ask for the upstream repository to pull your contribution in.</span></span>

![Solicitando para puxar as suas alterações de volta para o repo original](~/media/git-workflow-step2.png)

<span data-ttu-id="61a0c-128">Ao abrir um pedido de atração a um dos nossos repositórios, o GitHub oferecerá uma oportunidade para outros da comunidade verem um resumo das suas alterações, para comentá-las e fazer sugestões sobre como ajudar a dar uma contribuição ainda melhor.</span><span class="sxs-lookup"><span data-stu-id="61a0c-128">When you open a pull request to one of our repositories, GitHub will offer an opportunity for others in the community to see a summary of your changes, to comment on them, and to make suggestions for how to help make an even better contribution.</span></span>

![Screenshot de um pedido de puxar no GitHub](~/media/pull-request-header.png)

<span data-ttu-id="61a0c-130">A utilização deste processo ajuda-nos a usar a funcionalidade GitHub para melhorar as contribuições e manter um produto de alta qualidade para a comunidade de programação quântica.</span><span class="sxs-lookup"><span data-stu-id="61a0c-130">Using this process helps us use GitHub functionality to improve contributions and to maintain a high-quality product for the quantum programming community.</span></span>

## <a name="how-to-make-a-pull-request"></a><span data-ttu-id="61a0c-131">Como fazer um pedido de puxar</span><span class="sxs-lookup"><span data-stu-id="61a0c-131">How to Make a Pull Request</span></span> ##

<span data-ttu-id="61a0c-132">Há duas maneiras principais de fazer um pedido de atração.</span><span class="sxs-lookup"><span data-stu-id="61a0c-132">There are two main ways to make a pull request.</span></span>  
<span data-ttu-id="61a0c-133">Para pequenas alterações que apenas afetam um único ficheiro, a interface web GitHub pode ser usada para fazer um pedido de pull inteiramente on-line.</span><span class="sxs-lookup"><span data-stu-id="61a0c-133">For small changes that only affect a single file, the GitHub web interface can be used to make a pull request entirely online.</span></span> <span data-ttu-id="61a0c-134">Basta navegar para o ficheiro que pretende editar e utilizar o ícone de edição.</span><span class="sxs-lookup"><span data-stu-id="61a0c-134">Simply navigate to the file you want to edit and use the edit icon.</span></span>  
<span data-ttu-id="61a0c-135">Para contribuições mais complicadas, é mais fácil clonar o repositório para o seu computador local para se preparar primeiro para um pedido de puxão.</span><span class="sxs-lookup"><span data-stu-id="61a0c-135">For more complicated contributions, it's most often easier to clone the repository to your local computer to prepare for a pull request first.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="61a0c-136">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="61a0c-136">Next steps</span></span> ##

<span data-ttu-id="61a0c-137">Parabéns por usar git para ajudar a comunidade quantum development kit!</span><span class="sxs-lookup"><span data-stu-id="61a0c-137">Congratulations on using Git to help out the Quantum Development Kit community!</span></span>
<span data-ttu-id="61a0c-138">Para saber mais sobre como contribuir com o código, continue com o seguinte guia.</span><span class="sxs-lookup"><span data-stu-id="61a0c-138">To learn more about how to contribute code, please continue with the following guide.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="61a0c-139">Saiba como contribuir com código</span><span class="sxs-lookup"><span data-stu-id="61a0c-139">Learn how to contribute code</span></span>](xref:microsoft.quantum.contributing.code)
