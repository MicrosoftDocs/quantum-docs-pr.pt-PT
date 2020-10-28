---
uid: Microsoft.Quantum.Arrays.ColumnAtUnchecked
title: Função ColumnAtUnchecked
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAtUnchecked
qsharp.summary: This function does not check for matrix shape
ms.openlocfilehash: 17211c1ae1fe12fcadf34a9411f9b0cf0cdcab50
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719447"
---
# <a name="columnatunchecked-function"></a><span data-ttu-id="b89dc-102">Função ColumnAtUnchecked</span><span class="sxs-lookup"><span data-stu-id="b89dc-102">ColumnAtUnchecked function</span></span>

<span data-ttu-id="b89dc-103">Espaço de nome: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b89dc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b89dc-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b89dc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b89dc-105">Esta função não verifica a forma da matriz</span><span class="sxs-lookup"><span data-stu-id="b89dc-105">This function does not check for matrix shape</span></span>

```qsharp
function ColumnAtUnchecked<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="b89dc-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="b89dc-106">Description</span></span>

<span data-ttu-id="b89dc-107">Esta função pode ser utilizada noutras funções multidimensionais, que já verificam a matriz de entrada para uma forma retangular válida.</span><span class="sxs-lookup"><span data-stu-id="b89dc-107">This function can be used in other multidimensional functions, which already check the input matrix for a valid rectangular shape.</span></span>

## <a name="input"></a><span data-ttu-id="b89dc-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="b89dc-108">Input</span></span>

### <a name="column--int"></a><span data-ttu-id="b89dc-109">coluna : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b89dc-109">column : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="matrix--t"></a><span data-ttu-id="b89dc-110">matriz : 'T[][]</span><span class="sxs-lookup"><span data-stu-id="b89dc-110">matrix : 'T[][]</span></span>





## <a name="output--t"></a><span data-ttu-id="b89dc-111">Saída : 'T].</span><span class="sxs-lookup"><span data-stu-id="b89dc-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b89dc-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="b89dc-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b89dc-113">'T</span><span class="sxs-lookup"><span data-stu-id="b89dc-113">'T</span></span>

