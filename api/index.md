---
uid: microsoft.quantum.standardlibsintro
title: Biblioteca padrão Q# do Microsoft Quantum
description: Documentação de referência da biblioteca padrão Q# do Microsoft Quantum
author: natke
ms.author: nakersha
ms.date: 09/04/2019
ms.topic: landing-page
ms.openlocfilehash: 25a53e1cb8577761ef89cdcf2cfcddc509093f86
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "72999090"
---
# <a name="q-standard-libraries"></a><span data-ttu-id="53838-103">Bibliotecas padrão Q#</span><span class="sxs-lookup"><span data-stu-id="53838-103">Q# standard libraries</span></span> #

<span data-ttu-id="53838-104">A linguagem Q# é suportada por uma série de diferentes operações, funções e tipos definidos pelo utilizador úteis que constituem a *biblioteca padrão* Q#.</span><span class="sxs-lookup"><span data-stu-id="53838-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard library*.</span></span>
<span data-ttu-id="53838-105">A biblioteca padrão Q# está dividida em duas partes principais:</span><span class="sxs-lookup"><span data-stu-id="53838-105">The Q# standard library is split into two main parts:</span></span>

- <span data-ttu-id="53838-106">**O prelúdio**: operações e funções definidas como parte do compilador e do computador de destino, normalmente no código .NET nativo clássico.</span><span class="sxs-lookup"><span data-stu-id="53838-106">**The prelude**: operations and functions defined as a part of the target machine and compiler, typically in classical native .NET code.</span></span>
  <span data-ttu-id="53838-107">De forma geral, diferentes computadores de destino poderão ter diferentes interpretações sobre o prelúdio adequado para cada sistema.</span><span class="sxs-lookup"><span data-stu-id="53838-107">In general, different target machines may have different implementations of the prelude appropriate to each system.</span></span>
- <span data-ttu-id="53838-108">**O critério**: operações e funções definidas em Q# que criam a lógica definida no prelúdio.</span><span class="sxs-lookup"><span data-stu-id="53838-108">**The canon**: operations and functions defined in Q# building on the logic defined in the prelude.</span></span>
  <span data-ttu-id="53838-109">A implementação do critério é agnóstica relativamente aos computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="53838-109">The canon implementation is agnostic with respect to target machines.</span></span>
<span data-ttu-id="53838-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span><span class="sxs-lookup"><span data-stu-id="53838-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span></span>