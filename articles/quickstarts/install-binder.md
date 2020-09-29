---
title: Desenvolver com Q# e Binder
description: Saiba como criar uma aplicação Q# com o Binder.
author: bradben
ms.author: v-benbra
ms.date: 9/03/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.binder
no-loc:
- Q#
- $$v
ms.openlocfilehash: f993a1145dd8c01045d4cc7cfd0c98efd574ea78
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836556"
---
# <a name="develop-with-no-locq-and-binder"></a><span data-ttu-id="e3a16-103">Desenvolver com Q# e Binder</span><span class="sxs-lookup"><span data-stu-id="e3a16-103">Develop with Q# and Binder</span></span>

<span data-ttu-id="e3a16-104">Pode utilizar o Binder para executar e partilhar os seus Jupyter Notebooks online.</span><span class="sxs-lookup"><span data-stu-id="e3a16-104">You can use Binder to run and share your Jupyter Notebooks online.</span></span>

## <a name="use-binder-with-the-microsoft-qdk-samples"></a><span data-ttu-id="e3a16-105">Utilize o Binder com as amostras do Microsoft QDK</span><span class="sxs-lookup"><span data-stu-id="e3a16-105">Use Binder with the Microsoft QDK samples</span></span>

<span data-ttu-id="e3a16-106">Para configurar o Binder automaticamente para utilizar as amostras do Microsoft QDK:</span><span class="sxs-lookup"><span data-stu-id="e3a16-106">To configure Binder automatically to use the Microsoft QDK samples:</span></span>

1. <span data-ttu-id="e3a16-107">Abra um browser e execute https://aka.ms/try-qsharp.</span><span class="sxs-lookup"><span data-stu-id="e3a16-107">Open a browser and run https://aka.ms/try-qsharp.</span></span>
1. <span data-ttu-id="e3a16-108">Na página de destino **Amostras do Quantum Development Kit**, clique em **Bloco de notas Q#** para saber como utilizar o IQ# para escrever os seus próprios blocos de notas para aplicações quânticas.</span><span class="sxs-lookup"><span data-stu-id="e3a16-108">On the **Quantum Development Kit Samples** landing page, click **Q# notebook** to learn how to use IQ# to write your own quantum application notebooks.</span></span>

![Página de destino do QDK](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a><span data-ttu-id="e3a16-110">Utilize o Binder com os seus próprios blocos de notas e repositório</span><span class="sxs-lookup"><span data-stu-id="e3a16-110">Use Binder with your own notebooks and repository</span></span>

<span data-ttu-id="e3a16-111">Se já tiver blocos de notas num repositório do GitHub, pode configurar o Binder para trabalhar com o seu repositório:</span><span class="sxs-lookup"><span data-stu-id="e3a16-111">If you already have notebooks in a GitHub repository, you can configure Binder to work with your repo:</span></span>

1. <span data-ttu-id="e3a16-112">Verifique se há um ficheiro chamado *Dockerfile* na raiz do repositório.</span><span class="sxs-lookup"><span data-stu-id="e3a16-112">Ensure that there is a file named *Dockerfile* in the root of your repository.</span></span> <span data-ttu-id="e3a16-113">O ficheiro tem de conter, pelo menos, as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="e3a16-113">The file must contain at least the following lines:</span></span>

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > <span data-ttu-id="e3a16-114">Pode verificar a versão mais atual do IQ# nas [Notas de Versão](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="e3a16-114">You can verify the most current version of IQ# in the [Release Notes](xref:microsoft.quantum.relnotes).</span></span>

    <span data-ttu-id="e3a16-115">Para obter mais informações sobre como criar um Dockerfile, veja a [Referência do Dockerfile](https://docs.docker.com/engine/reference/builder/).</span><span class="sxs-lookup"><span data-stu-id="e3a16-115">For more information about creating a Dockerfile, see the [Dockerfile reference](https://docs.docker.com/engine/reference/builder/).</span></span>

2. <span data-ttu-id="e3a16-116">Abra um browser para [mybinder.org](https://mybinder.org).</span><span class="sxs-lookup"><span data-stu-id="e3a16-116">Open a browser to [mybinder.org](https://mybinder.org).</span></span>
3. <span data-ttu-id="e3a16-117">Introduza o nome do repositório como o **URL do GitHub** (por exemplo *MyName/MyRepo*) e clique em **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="e3a16-117">Enter your repository name as the **GitHub URL** (for example *MyName/MyRepo*), and click **launch**.</span></span>

![Formulário MyBinder](~/media/mybinder.png)
    
## <a name="next-steps"></a><span data-ttu-id="e3a16-119">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="e3a16-119">Next steps</span></span>

<span data-ttu-id="e3a16-120">Agora que configurou o seu ambiente do Binder, pode escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="e3a16-120">Now that you have set up your Binder environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
