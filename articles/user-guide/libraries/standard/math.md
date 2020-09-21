---
title: Matemática nas Q# bibliotecas padrão
description: Conheça as funções matemáticas clássicas nas Q# bibliotecas padrão que são usadas com os tipos de dados incorporados.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 55b1ef70eed1eb47ab0c6b30e2b8203c38c9a67a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833593"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="1c033-103">Funções Matemáticas Clássicas</span><span class="sxs-lookup"><span data-stu-id="1c033-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="1c033-104">Estas funções são usadas principalmente para trabalhar com os Q# tipos de dados incorporados, `Int` e `Double` `Range` .</span><span class="sxs-lookup"><span data-stu-id="1c033-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="1c033-105">A <xref:microsoft.quantum.intrinsic.random> operação tem `(Double[] => Int)` assinatura.</span><span class="sxs-lookup"><span data-stu-id="1c033-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="1c033-106">Requer uma série de duplos como entrada, e devolve um índice selecionado aleatoriamente para a matriz como um `Int` .</span><span class="sxs-lookup"><span data-stu-id="1c033-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="1c033-107">A probabilidade de selecionar um índice específico é proporcional ao valor do elemento matriz nesse índice.</span><span class="sxs-lookup"><span data-stu-id="1c033-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="1c033-108">n Elementos de matriz que são iguais a zero são ignorados e os seus índices nunca são devolvidos.</span><span class="sxs-lookup"><span data-stu-id="1c033-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="1c033-109">Se qualquer elemento de matriz for inferior a zero, ou se nenhum elemento de matriz for maior que zero, então a operação falha.</span><span class="sxs-lookup"><span data-stu-id="1c033-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
