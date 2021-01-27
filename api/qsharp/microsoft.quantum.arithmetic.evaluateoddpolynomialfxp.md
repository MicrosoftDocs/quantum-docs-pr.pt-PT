---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: Avaliação OperaçãoOddPolynomialFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: 852e986cd09c3b2e31263f53e381d9da73298415
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846672"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="62bc2-102">Avaliação OperaçãoOddPolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="62bc2-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="62bc2-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="62bc2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="62bc2-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="62bc2-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="62bc2-105">Avalia um polinômio ímpar numa representação de ponto fixo.</span><span class="sxs-lookup"><span data-stu-id="62bc2-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="62bc2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="62bc2-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="62bc2-107">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="62bc2-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="62bc2-108">Coeficientes do polinómio ímpar como uma matriz dupla, ou seja, a matriz $[a_0, a_1, ..., a_k]$ para o estranho polinomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^2k+1$}</span><span class="sxs-lookup"><span data-stu-id="62bc2-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="62bc2-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="62bc2-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="62bc2-110">Inserir número de ponto fixo para avaliar o polinómio.</span><span class="sxs-lookup"><span data-stu-id="62bc2-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="62bc2-111">resultado : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="62bc2-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="62bc2-112">Número de ponto fixo de saída que irá conter P(x).</span><span class="sxs-lookup"><span data-stu-id="62bc2-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="62bc2-113">Deve estar no estado $\ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="62bc2-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="62bc2-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="62bc2-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

