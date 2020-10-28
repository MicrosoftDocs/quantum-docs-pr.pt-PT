---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: Avaliação OperaçãoOddPolynomialFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: d52da4092f16d43ab9d08b03f798a4d6789c7348
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721198"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="9d4aa-102">Avaliação OperaçãoOddPolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="9d4aa-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="9d4aa-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9d4aa-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9d4aa-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9d4aa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9d4aa-105">Avalia um polinômio ímpar numa representação de ponto fixo.</span><span class="sxs-lookup"><span data-stu-id="9d4aa-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="9d4aa-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="9d4aa-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="9d4aa-107">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9d4aa-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9d4aa-108">Coeficientes do polinómio ímpar como uma matriz dupla, ou seja, a matriz $[a_0, a_1, ..., a_k]$ para o estranho polinomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^2k+1$}</span><span class="sxs-lookup"><span data-stu-id="9d4aa-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="9d4aa-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="9d4aa-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="9d4aa-110">Inserir número de ponto fixo para avaliar o polinómio.</span><span class="sxs-lookup"><span data-stu-id="9d4aa-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="9d4aa-111">resultado : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="9d4aa-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="9d4aa-112">Número de ponto fixo de saída que irá conter P(x).</span><span class="sxs-lookup"><span data-stu-id="9d4aa-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="9d4aa-113">Deve estar no estado $\ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="9d4aa-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9d4aa-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9d4aa-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

