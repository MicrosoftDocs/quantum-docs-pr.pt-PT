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
# <a name="develop-with-no-locq-and-binder"></a>Desenvolver com Q# e Binder

Pode utilizar o Binder para executar e partilhar os seus Jupyter Notebooks online.

## <a name="use-binder-with-the-microsoft-qdk-samples"></a>Utilize o Binder com as amostras do Microsoft QDK

Para configurar o Binder automaticamente para utilizar as amostras do Microsoft QDK:

1. Abra um browser e execute https://aka.ms/try-qsharp.
1. Na página de destino **Amostras do Quantum Development Kit**, clique em **Bloco de notas Q#** para saber como utilizar o IQ# para escrever os seus próprios blocos de notas para aplicações quânticas.

![Página de destino do QDK](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a>Utilize o Binder com os seus próprios blocos de notas e repositório

Se já tiver blocos de notas num repositório do GitHub, pode configurar o Binder para trabalhar com o seu repositório:

1. Verifique se há um ficheiro chamado *Dockerfile* na raiz do repositório. O ficheiro tem de conter, pelo menos, as seguintes linhas:

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > Pode verificar a versão mais atual do IQ# nas [Notas de Versão](xref:microsoft.quantum.relnotes).

    Para obter mais informações sobre como criar um Dockerfile, veja a [Referência do Dockerfile](https://docs.docker.com/engine/reference/builder/).

2. Abra um browser para [mybinder.org](https://mybinder.org).
3. Introduza o nome do repositório como o **URL do GitHub** (por exemplo *MyName/MyRepo*) e clique em **Iniciar**.

![Formulário MyBinder](~/media/mybinder.png)
    
## <a name="next-steps"></a>Passos seguintes

Agora que configurou o seu ambiente do Binder, pode escrever e executar [o seu primeiro programa quântico](xref:microsoft.quantum.quickstarts.qrng).
