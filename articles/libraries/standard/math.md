---
title: Matemática nas bibliotecas padrão Q#
description: Conheça as funções matemáticaclássicas nas bibliotecas padrão Q# que são usadas com os tipos de dados incorporados.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906156"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="3f5d6-103">Funções Matemáticas Clássicas</span><span class="sxs-lookup"><span data-stu-id="3f5d6-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="3f5d6-104">Estas funções são usadas principalmente para trabalhar com os tipos de dados incorporados Q# `Int`, `Double`e `Range`.</span><span class="sxs-lookup"><span data-stu-id="3f5d6-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="3f5d6-105">A operação <xref:microsoft.quantum.intrinsic.random> tem `(Double[] => Int)`de assinatura.</span><span class="sxs-lookup"><span data-stu-id="3f5d6-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="3f5d6-106">Leva uma série de duplos como entrada, e devolve um índice selecionado aleatoriamente na matriz como um `Int`.</span><span class="sxs-lookup"><span data-stu-id="3f5d6-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="3f5d6-107">A probabilidade de selecionar um índice específico é proporcional ao valor do elemento matriz nesse índice.</span><span class="sxs-lookup"><span data-stu-id="3f5d6-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="3f5d6-108">n Elementos matrizes que são iguais a zero são ignorados e os seus índices nunca são devolvidos.</span><span class="sxs-lookup"><span data-stu-id="3f5d6-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="3f5d6-109">Se qualquer elemento de matriz for inferior a zero, ou se nenhum elemento de matriz for superior a zero, então a operação falha.</span><span class="sxs-lookup"><span data-stu-id="3f5d6-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
