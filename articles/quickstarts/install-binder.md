---
title: Desenvolver com Q# e Binder
description: Saiba como criar uma aplicação Q# com o Binder.
author: bradben
ms.author: v-benbra
ms.date: 9/03/2020
ms.topic: quickstart
uid: microsoft.quantum.install.binder
no-loc:
- Q#
- $$v
ms.openlocfilehash: f7e9b1ae67d6275ec7ba39ea411842dc537536c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856713"
---
# <a name="develop-with-no-locq-and-binder"></a><span data-ttu-id="05d9a-103">Desenvolver com Q# e Binder</span><span class="sxs-lookup"><span data-stu-id="05d9a-103">Develop with Q# and Binder</span></span>

<span data-ttu-id="05d9a-104">Pode utilizar o Binder para executar e partilhar os seus Jupyter Notebooks online.</span><span class="sxs-lookup"><span data-stu-id="05d9a-104">You can use Binder to run and share your Jupyter Notebooks online.</span></span>

## <a name="use-binder-with-the-microsoft-qdk-samples"></a><span data-ttu-id="05d9a-105">Utilize o Binder com as amostras do Microsoft QDK</span><span class="sxs-lookup"><span data-stu-id="05d9a-105">Use Binder with the Microsoft QDK samples</span></span>

<span data-ttu-id="05d9a-106">Para configurar o Binder automaticamente para utilizar as amostras do Microsoft QDK:</span><span class="sxs-lookup"><span data-stu-id="05d9a-106">To configure Binder automatically to use the Microsoft QDK samples:</span></span>

1. <span data-ttu-id="05d9a-107">Abra um browser e execute https://aka.ms/try-qsharp.</span><span class="sxs-lookup"><span data-stu-id="05d9a-107">Open a browser and run https://aka.ms/try-qsharp.</span></span>
1. <span data-ttu-id="05d9a-108">Na página de destino **Amostras do Quantum Development Kit**, clique em **Bloco de notas Q#** para saber como utilizar o IQ# para escrever os seus próprios blocos de notas para aplicações quânticas.</span><span class="sxs-lookup"><span data-stu-id="05d9a-108">On the **Quantum Development Kit Samples** landing page, click **Q# notebook** to learn how to use IQ# to write your own quantum application notebooks.</span></span>

![Página de destino do QDK](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a><span data-ttu-id="05d9a-110">Utilize o Binder com os seus próprios blocos de notas e repositório</span><span class="sxs-lookup"><span data-stu-id="05d9a-110">Use Binder with your own notebooks and repository</span></span>

<span data-ttu-id="05d9a-111">Se já tiver blocos de notas num repositório do GitHub, pode configurar o Binder para trabalhar com o seu repositório:</span><span class="sxs-lookup"><span data-stu-id="05d9a-111">If you already have notebooks in a GitHub repository, you can configure Binder to work with your repo:</span></span>

1. <span data-ttu-id="05d9a-112">Verifique se há um ficheiro chamado *Dockerfile* na raiz do repositório.</span><span class="sxs-lookup"><span data-stu-id="05d9a-112">Ensure that there is a file named *Dockerfile* in the root of your repository.</span></span> <span data-ttu-id="05d9a-113">O ficheiro tem de conter, pelo menos, as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="05d9a-113">The file must contain at least the following lines:</span></span>

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > <span data-ttu-id="05d9a-114">Pode verificar a versão mais atual do IQ# nas [Notas de Versão](xref:microsoft.quantum.relnotes).</span><span class="sxs-lookup"><span data-stu-id="05d9a-114">You can verify the most current version of IQ# in the [Release Notes](xref:microsoft.quantum.relnotes).</span></span>

    <span data-ttu-id="05d9a-115">Para obter mais informações sobre como criar um Dockerfile, veja a [Referência do Dockerfile](https://docs.docker.com/engine/reference/builder/).</span><span class="sxs-lookup"><span data-stu-id="05d9a-115">For more information about creating a Dockerfile, see the [Dockerfile reference](https://docs.docker.com/engine/reference/builder/).</span></span>

2. <span data-ttu-id="05d9a-116">Abra um browser para [mybinder.org](https://mybinder.org).</span><span class="sxs-lookup"><span data-stu-id="05d9a-116">Open a browser to [mybinder.org](https://mybinder.org).</span></span>
3. <span data-ttu-id="05d9a-117">Introduza o nome do repositório como o **URL do GitHub** (por exemplo *MyName/MyRepo*) e clique em **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="05d9a-117">Enter your repository name as the **GitHub URL** (for example *MyName/MyRepo*), and click **launch**.</span></span>

![Formulário MyBinder](~/media/mybinder.png)
    
## <a name="next-steps"></a><span data-ttu-id="05d9a-119">Passos seguintes</span><span class="sxs-lookup"><span data-stu-id="05d9a-119">Next steps</span></span>

<span data-ttu-id="05d9a-120">Agora que configurou o seu ambiente do Binder, pode escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).</span><span class="sxs-lookup"><span data-stu-id="05d9a-120">Now that you have set up your Binder environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
