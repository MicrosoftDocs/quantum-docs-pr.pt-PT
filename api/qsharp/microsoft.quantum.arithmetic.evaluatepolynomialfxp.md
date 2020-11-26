---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: Avaliação Operação PolynomialFxP
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: 4f6ed4b34af2e63dd8ee31fb9b93119e06e3ecbc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223192"
---
# <a name="evaluatepolynomialfxp-operation"></a><span data-ttu-id="d1e18-102">Avaliação Operação PolynomialFxP</span><span class="sxs-lookup"><span data-stu-id="d1e18-102">EvaluatePolynomialFxP operation</span></span>

<span data-ttu-id="d1e18-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d1e18-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d1e18-104">Pacote: [Microsoft.Quantum.Nummerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="d1e18-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="d1e18-105">Avalia um polinómio numa representação de ponto fixo.</span><span class="sxs-lookup"><span data-stu-id="d1e18-105">Evaluates a polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d1e18-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d1e18-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="d1e18-107">coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d1e18-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d1e18-108">Coeficientes do polinómio como uma matriz dupla, ou seja, a matriz $[a_0, a_1, ..., a_d]$ para o $P polinomial(x) = a_0 + a_1 x + \cdots + a_d x^d$.</span><span class="sxs-lookup"><span data-stu-id="d1e18-108">Coefficients of the polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_d]$ for the polynomial $P(x) = a_0 + a_1 x + \cdots + a_d x^d$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="d1e18-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="d1e18-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="d1e18-110">Inserir número de ponto fixo para avaliar o polinómio.</span><span class="sxs-lookup"><span data-stu-id="d1e18-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="d1e18-111">resultado : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="d1e18-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="d1e18-112">Número de ponto fixo de saída que terá $P(x)$.</span><span class="sxs-lookup"><span data-stu-id="d1e18-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="d1e18-113">Deve estar no estado $\ket {0} $ inicialmente.</span><span class="sxs-lookup"><span data-stu-id="d1e18-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d1e18-114">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d1e18-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

