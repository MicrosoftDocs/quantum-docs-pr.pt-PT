---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: Operação AddFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 60b7cad3d0bd8800e67830ca921f8e2d705b8f39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843863"
---
# <a name="addfxp-operation"></a><span data-ttu-id="bb595-102">Operação AddFxP</span><span class="sxs-lookup"><span data-stu-id="bb595-102">AddFxP operation</span></span>

<span data-ttu-id="bb595-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bb595-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bb595-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="bb595-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="bb595-105">Adiciona dois números de ponto fixo armazenados em registos quânticos.</span><span class="sxs-lookup"><span data-stu-id="bb595-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="bb595-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="bb595-106">Description</span></span>

<span data-ttu-id="bb595-107">Tendo em conta dois registos de ponto fixo, respectivamente nos estados $\ket{f_1}$ e $\ket{f_2},, executa a operação $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span><span class="sxs-lookup"><span data-stu-id="bb595-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="bb595-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="bb595-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="bb595-109">FP1 : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="bb595-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="bb595-110">Primeiro número de ponto fixo</span><span class="sxs-lookup"><span data-stu-id="bb595-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="bb595-111">FP2 : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="bb595-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="bb595-112">O segundo número de ponto fixo será atualizado para conter a soma das duas entradas.</span><span class="sxs-lookup"><span data-stu-id="bb595-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bb595-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bb595-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bb595-114">Observações</span><span class="sxs-lookup"><span data-stu-id="bb595-114">Remarks</span></span>

<span data-ttu-id="bb595-115">A implementação atual requer que os dois números de ponto fixo tenham a mesma posição de ponto contando a partir da parte menos significativa, ou seja, $n_i$ e $p_i$ devem ser iguais.</span><span class="sxs-lookup"><span data-stu-id="bb595-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>