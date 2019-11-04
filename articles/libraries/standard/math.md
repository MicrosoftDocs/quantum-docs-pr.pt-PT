---
title: 'P # bibliotecas padrão-matemática | Microsoft Docs'
description: 'P # bibliotecas padrão-matemática'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 7ac9d321f59f7cc95ad8939a4cf7c36e0c5e0491
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184462"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="48605-103">Funções matemáticas clássicas</span><span class="sxs-lookup"><span data-stu-id="48605-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="48605-104">Essas funções são usadas principalmente para trabalhar com os tipos de dados internos Q # `Int`, `Double`e `Range`.</span><span class="sxs-lookup"><span data-stu-id="48605-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="48605-105">A operação de <xref:microsoft.quantum.intrinsic.random> tem `(Double[] => Int)`de assinatura.</span><span class="sxs-lookup"><span data-stu-id="48605-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="48605-106">Ele usa uma matriz de duplicatas como entrada e retorna um índice selecionado aleatoriamente para a matriz como um `Int`.</span><span class="sxs-lookup"><span data-stu-id="48605-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="48605-107">A probabilidade de selecionar um índice específico é proporcional ao valor do elemento de matriz nesse índice.</span><span class="sxs-lookup"><span data-stu-id="48605-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="48605-108">n elementos da matriz que são iguais a zero são ignorados e seus índices nunca são retornados.</span><span class="sxs-lookup"><span data-stu-id="48605-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="48605-109">Se qualquer elemento de matriz for menor que zero, ou se nenhum elemento de matriz for maior que zero, a operação falhará.</span><span class="sxs-lookup"><span data-stu-id="48605-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>