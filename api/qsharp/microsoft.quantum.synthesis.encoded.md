---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Função codificada
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855485"
---
# <a name="encoded-function"></a><span data-ttu-id="1f7cd-102">Função codificada</span><span class="sxs-lookup"><span data-stu-id="1f7cd-102">Encoded function</span></span>

<span data-ttu-id="1f7cd-103">Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="1f7cd-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="1f7cd-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1f7cd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1f7cd-105">Codificar a tabela da verdade na {1,-1} codificação</span><span class="sxs-lookup"><span data-stu-id="1f7cd-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="1f7cd-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1f7cd-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="1f7cd-107">tabela : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="1f7cd-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="1f7cd-108">Tabela da verdade como conjunto de valores da verdade</span><span class="sxs-lookup"><span data-stu-id="1f7cd-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="1f7cd-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="1f7cd-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="1f7cd-110">Tabela da verdade como conjunto {1,-1} de inteiros</span><span class="sxs-lookup"><span data-stu-id="1f7cd-110">Truth table as array of {1,-1} integers</span></span>

## <a name="example"></a><span data-ttu-id="1f7cd-111">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1f7cd-111">Example</span></span>

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```