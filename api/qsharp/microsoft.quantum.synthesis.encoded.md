---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Função codificada
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 803f35b9e7af547bc34f21de74684fba885bfda9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203183"
---
# <a name="encoded-function"></a><span data-ttu-id="7ae83-102">Função codificada</span><span class="sxs-lookup"><span data-stu-id="7ae83-102">Encoded function</span></span>

<span data-ttu-id="7ae83-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="7ae83-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="7ae83-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7ae83-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7ae83-105">Codificar a tabela da verdade na {1,-1} codificação</span><span class="sxs-lookup"><span data-stu-id="7ae83-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="7ae83-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="7ae83-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="7ae83-107">tabela : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="7ae83-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="7ae83-108">Tabela da verdade como conjunto de valores da verdade</span><span class="sxs-lookup"><span data-stu-id="7ae83-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="7ae83-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7ae83-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7ae83-110">Tabela da verdade como conjunto {1,-1} de inteiros</span><span class="sxs-lookup"><span data-stu-id="7ae83-110">Truth table as array of {1,-1} integers</span></span>