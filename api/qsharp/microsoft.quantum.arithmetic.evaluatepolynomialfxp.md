---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: Avaliação Operação PolynomialFxP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: d88f9002f4ce39b6a16091837c76168fb3a2f086
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843210"
---
# <a name="evaluatepolynomialfxp-operation"></a><span data-ttu-id="883a7-102">Avaliação Operação PolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="883a7-102">EvaluatePolynomialFxP operation</span></span>

<span data-ttu-id="883a7-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="883a7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="883a7-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="883a7-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="883a7-105">Avalia um polinómio numa representação de ponto fixo.</span><span class="sxs-lookup"><span data-stu-id="883a7-105">Evaluates a polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="883a7-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="883a7-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="883a7-107">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="883a7-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="883a7-108">Coeficientes do polinómio como uma matriz dupla, ou seja, a matriz $[a_0, a_1, ..., a_d]$ para o $P polinomial(x) = a_0 + a_1 x + \cdots + a_d x^d$.</span><span class="sxs-lookup"><span data-stu-id="883a7-108">Coefficients of the polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_d]$ for the polynomial $P(x) = a_0 + a_1 x + \cdots + a_d x^d$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="883a7-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="883a7-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="883a7-110">Inserir número de ponto fixo para avaliar o polinómio.</span><span class="sxs-lookup"><span data-stu-id="883a7-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="883a7-111">resultado : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="883a7-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="883a7-112">Número de ponto fixo de saída que terá $P(x)$.</span><span class="sxs-lookup"><span data-stu-id="883a7-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="883a7-113">Deve estar no estado $\ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="883a7-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="883a7-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="883a7-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

