---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: Avaliação Operação EvenPolynomialFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: e49a6d47553a60766b561525e8cfa37e95fda9e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721199"
---
# <a name="evaluateevenpolynomialfxp-operation"></a><span data-ttu-id="28bb5-102">Avaliação Operação EvenPolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="28bb5-102">EvaluateEvenPolynomialFxP operation</span></span>

<span data-ttu-id="28bb5-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="28bb5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="28bb5-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="28bb5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="28bb5-105">Avalia um polinómio uniforme numa representação de ponto fixo.</span><span class="sxs-lookup"><span data-stu-id="28bb5-105">Evaluates an even polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="28bb5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="28bb5-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="28bb5-107">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="28bb5-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="28bb5-108">Coeficientes do mesmo polinómio como uma matriz dupla, ou seja, a matriz $[a_0, a_1, ..., a_k]$ para o $P polinomial(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.</span><span class="sxs-lookup"><span data-stu-id="28bb5-108">Coefficients of the even polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the even polynomial $P(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="28bb5-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="28bb5-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="28bb5-110">Inserir número de ponto fixo para avaliar o polinómio.</span><span class="sxs-lookup"><span data-stu-id="28bb5-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="28bb5-111">resultado : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="28bb5-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="28bb5-112">Número de ponto fixo de saída que terá $P(x)$.</span><span class="sxs-lookup"><span data-stu-id="28bb5-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="28bb5-113">Deve estar no estado $\ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="28bb5-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="28bb5-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="28bb5-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

