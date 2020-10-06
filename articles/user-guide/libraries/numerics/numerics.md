---
title: Utilização da Q# Biblioteca Dos Numéricos da Microsoft
description: Saiba mais sobre os tipos e operações disponíveis na biblioteca dos Numericos Quânticos da Microsoft.
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
no-loc:
- Q#
- $$v
ms.openlocfilehash: dfcb8e9e5a15d0881750d67cf58d7ad47cbecd3a
ms.sourcegitcommit: 897ace8b506adb2331e911ee5633dceced566174
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/06/2020
ms.locfileid: "91764123"
---
# <a name="using-the-numerics-library"></a><span data-ttu-id="8487f-103">Usando a biblioteca numérica</span><span class="sxs-lookup"><span data-stu-id="8487f-103">Using the Numerics library</span></span>

## <a name="overview"></a><span data-ttu-id="8487f-104">Descrição geral</span><span class="sxs-lookup"><span data-stu-id="8487f-104">Overview</span></span>

<span data-ttu-id="8487f-105">A biblioteca numérica é composta por três componentes</span><span class="sxs-lookup"><span data-stu-id="8487f-105">The Numerics library consists of three components</span></span>

1. <span data-ttu-id="8487f-106">**Aritmética de inteiros** básicos com suplementos inteiros e comparadores</span><span class="sxs-lookup"><span data-stu-id="8487f-106">**Basic integer arithmetic** with integer adders and comparators</span></span>
1. <span data-ttu-id="8487f-107">**Funcionalidade de número inteiro de alto nível** que é construída em cima da funcionalidade básica; inclui multiplicação, divisão, inversão, etc.  para inteiros assinados e não assinados.</span><span class="sxs-lookup"><span data-stu-id="8487f-107">**High-level integer functionality** that is built on top of the basic  functionality; it includes multiplication, division, inversion, etc.  for signed and unsigned integers.</span></span>
1. <span data-ttu-id="8487f-108">**Funcionalidade aritmética de ponto fixo** com inicialização de ponto fixo, adição, multiplicação, avaliação recíproca, polinomial e medição.</span><span class="sxs-lookup"><span data-stu-id="8487f-108">**Fixed-point arithmetic functionality** with fixed-point initialization,  addition, multiplication, reciprocal, polynomial evaluation, and measurement.</span></span>

<span data-ttu-id="8487f-109">Todos estes componentes podem ser acedidos através de uma única `open` declaração:</span><span class="sxs-lookup"><span data-stu-id="8487f-109">All of these components can be accessed using a single `open` statement:</span></span>
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a><span data-ttu-id="8487f-110">Tipos</span><span class="sxs-lookup"><span data-stu-id="8487f-110">Types</span></span>

<span data-ttu-id="8487f-111">A biblioteca numérica suporta os seguintes tipos</span><span class="sxs-lookup"><span data-stu-id="8487f-111">The numerics library supports the following types</span></span>

1. <span data-ttu-id="8487f-112">**`LittleEndian`**: Uma matriz qubit `qArr : Qubit[]` que representa um número inteiro onde `qArr[0]` denota a parte menos significativa.</span><span class="sxs-lookup"><span data-stu-id="8487f-112">**`LittleEndian`**: A qubit array `qArr : Qubit[]` that represents an integer where `qArr[0]` denotes the least significant bit.</span></span>
1. <span data-ttu-id="8487f-113">**`SignedLittleEndian`**: O mesmo `LittleEndian` que representa um número inteiro assinado armazenado no complemento de dois.</span><span class="sxs-lookup"><span data-stu-id="8487f-113">**`SignedLittleEndian`**: Same as `LittleEndian` except that it represents a signed integer stored in two's complement.</span></span>
1. <span data-ttu-id="8487f-114">**`FixedPoint`**: Representa um número real constituído por uma matriz de qubit `qArr2 : Qubit[]` e uma posição de ponto `pos` binário, que conta o número de dígitos binários à esquerda do ponto binário.</span><span class="sxs-lookup"><span data-stu-id="8487f-114">**`FixedPoint`**: Represents a real number consisting of a qubit array `qArr2 : Qubit[]` and a binary point position `pos`, which counts the number of binary digits to the left of the binary point.</span></span> <span data-ttu-id="8487f-115">`qArr2` é armazenado da mesma forma que `SignedLittleEndian` . .</span><span class="sxs-lookup"><span data-stu-id="8487f-115">`qArr2` is stored in the same way as `SignedLittleEndian`.</span></span>

## <a name="operations"></a><span data-ttu-id="8487f-116">Operações</span><span class="sxs-lookup"><span data-stu-id="8487f-116">Operations</span></span>

<span data-ttu-id="8487f-117">Para cada um dos três tipos acima, está disponível uma variedade de operações:</span><span class="sxs-lookup"><span data-stu-id="8487f-117">For each of the three types above, a variety of operations is available:</span></span>

1. **`LittleEndian`**
    - <span data-ttu-id="8487f-118">Adição</span><span class="sxs-lookup"><span data-stu-id="8487f-118">Addition</span></span>
    - <span data-ttu-id="8487f-119">Comparação</span><span class="sxs-lookup"><span data-stu-id="8487f-119">Comparison</span></span>
    - <span data-ttu-id="8487f-120">Multiplicação</span><span class="sxs-lookup"><span data-stu-id="8487f-120">Multiplication</span></span>
    - <span data-ttu-id="8487f-121">Esquartejar</span><span class="sxs-lookup"><span data-stu-id="8487f-121">Squaring</span></span>
    - <span data-ttu-id="8487f-122">Divisão (com o restante)</span><span class="sxs-lookup"><span data-stu-id="8487f-122">Division (with remainder)</span></span>

1. **`SignedLittleEndian`**
    - <span data-ttu-id="8487f-123">Adição</span><span class="sxs-lookup"><span data-stu-id="8487f-123">Addition</span></span>
    - <span data-ttu-id="8487f-124">Comparação</span><span class="sxs-lookup"><span data-stu-id="8487f-124">Comparison</span></span>
    - <span data-ttu-id="8487f-125">Complemento de inversão modulo 2</span><span class="sxs-lookup"><span data-stu-id="8487f-125">Inversion modulo 2's complement</span></span>
    - <span data-ttu-id="8487f-126">Multiplicação</span><span class="sxs-lookup"><span data-stu-id="8487f-126">Multiplication</span></span>
    - <span data-ttu-id="8487f-127">Esquartejar</span><span class="sxs-lookup"><span data-stu-id="8487f-127">Squaring</span></span>

1. **`FixedPoint`**
    - <span data-ttu-id="8487f-128">Preparação/ inicialização a valores clássicos</span><span class="sxs-lookup"><span data-stu-id="8487f-128">Preparation / initialization to a classical values</span></span>
    - <span data-ttu-id="8487f-129">Adição (constante clássica ou outro ponto fixo quântico)</span><span class="sxs-lookup"><span data-stu-id="8487f-129">Addition (classical constant or other quantum fixed-point)</span></span>
    - <span data-ttu-id="8487f-130">Comparação</span><span class="sxs-lookup"><span data-stu-id="8487f-130">Comparison</span></span>
    - <span data-ttu-id="8487f-131">Multiplicação</span><span class="sxs-lookup"><span data-stu-id="8487f-131">Multiplication</span></span>
    - <span data-ttu-id="8487f-132">Esquartejar</span><span class="sxs-lookup"><span data-stu-id="8487f-132">Squaring</span></span>
    - <span data-ttu-id="8487f-133">Avaliação polinomial com especialização para funções par e ímpares</span><span class="sxs-lookup"><span data-stu-id="8487f-133">Polynomial evaluation with specialization for even and odd functions</span></span>
    - <span data-ttu-id="8487f-134">Recíproco (1/x)</span><span class="sxs-lookup"><span data-stu-id="8487f-134">Reciprocal (1/x)</span></span>
    - <span data-ttu-id="8487f-135">Medição (duplo clássico)</span><span class="sxs-lookup"><span data-stu-id="8487f-135">Measurement (classical Double)</span></span>

<span data-ttu-id="8487f-136">Para obter mais informações e documentação detalhada para cada uma destas operações, consulte os documentos de referência da Q# biblioteca em [docs.microsoft.com](https://docs.microsoft.com/quantum)</span><span class="sxs-lookup"><span data-stu-id="8487f-136">For more information and detailed documentation for each of these operations, see the Q# library reference docs at [docs.microsoft.com](https://docs.microsoft.com/quantum)</span></span>

## <a name="sample-integer-addition"></a><span data-ttu-id="8487f-137">Amostra: Adição de inteiros</span><span class="sxs-lookup"><span data-stu-id="8487f-137">Sample: Integer addition</span></span>

<span data-ttu-id="8487f-138">Como exemplo básico, considere a operação $$ \ket x\ket y\mapsto \ket x\ket{x+y} $00, isto é, uma operação que leva um número inteiro n-qubit $x$ e um registo n-ou (n+1)-qubit $y$ como entrada, a última das quais mapeia para a soma $(x+y)$.</span><span class="sxs-lookup"><span data-stu-id="8487f-138">As a basic example, consider the operation $$ \ket x\ket y\mapsto \ket x\ket{x+y} $$ that is, an operation that takes an n-qubit integer $x$ and an n- or (n+1)-qubit register $y$ as input, the latter of which it maps to the sum $(x+y)$.</span></span> <span data-ttu-id="8487f-139">Note que a soma é computada modulo $2^n$ se $y$ for armazenado num registo de $n de $-bit.</span><span class="sxs-lookup"><span data-stu-id="8487f-139">Note that the sum is computed modulo $2^n$ if $y$ is stored in an $n$-bit register.</span></span>

<span data-ttu-id="8487f-140">Utilizando o Kit de Desenvolvimento Quântico, esta operação pode ser aplicada da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="8487f-140">Using the Quantum Development Kit, this operation can be applied as follows:</span></span>
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        let x = LittleEndian(xQubits); // define bit order
        let y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a><span data-ttu-id="8487f-141">Amostra: Avaliação de funções suaves</span><span class="sxs-lookup"><span data-stu-id="8487f-141">Sample: Evaluating smooth functions</span></span>

<span data-ttu-id="8487f-142">Para avaliar funções suaves como $\sin (x)$ num computador quântico, onde $x$ é um número quântico, `FixedPoint` a biblioteca numérica do Kit de Desenvolvimento Quântico fornece as operações `EvaluatePolynomialFxP` e `Evaluate[Even/Odd]PolynomialFxP` .</span><span class="sxs-lookup"><span data-stu-id="8487f-142">To evaluate smooth functions such as $\sin(x)$ on a quantum computer, where $x$ is a quantum `FixedPoint` number, the Quantum Development Kit numerics library provides the operations `EvaluatePolynomialFxP` and `Evaluate[Even/Odd]PolynomialFxP`.</span></span>

<span data-ttu-id="8487f-143">O primeiro, `EvaluatePolynomialFxP` permite avaliar um polinómio do formulário $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ onde $d$ denota o *grau*.</span><span class="sxs-lookup"><span data-stu-id="8487f-143">The first, `EvaluatePolynomialFxP`, allows to evaluate a polynomial of the form $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ where $d$ denotes the *degree*.</span></span> <span data-ttu-id="8487f-144">Para tal, tudo o que é necessário são os coeficientes polinómicos `[a_0,..., a_d]` (do `Double[]` tipo), a entrada `x : FixedPoint` e a saída `y : FixedPoint` (inicialmente zero):</span><span class="sxs-lookup"><span data-stu-id="8487f-144">To do so, all that is needed are the polynomial coefficients `[a_0,..., a_d]` (of type `Double[]`), the input `x : FixedPoint` and the output `y : FixedPoint` (initially zero):</span></span>
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="8487f-145">O resultado, $P(x)=1+2x$, será armazenado em `yFxP` .</span><span class="sxs-lookup"><span data-stu-id="8487f-145">The result, $P(x)=1+2x$, will be stored in `yFxP`.</span></span>

<span data-ttu-id="8487f-146">A segunda, `EvaluateEvenPolynomialFxP` e a `EvaluateOddPolynomialFxP` terceira, são especializações para os casos de funções par e ímpares, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="8487f-146">The second, `EvaluateEvenPolynomialFxP`, and the third, `EvaluateOddPolynomialFxP`, are specializations for the cases of even and odd functions, respectively.</span></span> <span data-ttu-id="8487f-147">Isto é, para uma função par/ímpar $f(x)$ e $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ é aproximadamente bem por $P_{even}(x)$ ou $P_{odd}(x) := x\cdot P_{even}(x)$, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="8487f-147">That is, for an even/odd function $f(x)$ and $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ is approximated well by $P_{even}(x)$ or $P_{odd}(x) := x\cdot P_{even}(x)$, respectively.</span></span>
<span data-ttu-id="8487f-148">Em Q# , estes dois casos podem ser tratados da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="8487f-148">In Q#, these two cases can be handled as follows:</span></span>
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="8487f-149">que avalia $P_{even}(x) = 1 + 2x^2$, e</span><span class="sxs-lookup"><span data-stu-id="8487f-149">which evaluates $P_{even}(x) = 1 + 2x^2$, and</span></span>
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
<span data-ttu-id="8487f-150">que avalia $P_{odd}(x) = x + 2x^3$.</span><span class="sxs-lookup"><span data-stu-id="8487f-150">which evaluates $P_{odd}(x) = x + 2x^3$.</span></span>

## <a name="more-samples"></a><span data-ttu-id="8487f-151">Mais exemplos</span><span class="sxs-lookup"><span data-stu-id="8487f-151">More samples</span></span>

<span data-ttu-id="8487f-152">Pode encontrar mais amostras no [repositório principal de amostras.](https://github.com/Microsoft/Quantum)</span><span class="sxs-lookup"><span data-stu-id="8487f-152">You can find more samples in the [main samples repository](https://github.com/Microsoft/Quantum).</span></span>

<span data-ttu-id="8487f-153">Para começar, clone o repo e abra a `Numerics` sub-página:</span><span class="sxs-lookup"><span data-stu-id="8487f-153">To get started, clone the repo and open the `Numerics` subfolder:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics
```

<span data-ttu-id="8487f-154">Em seguida, `cd` em uma das pastas de amostra e executar a amostra através</span><span class="sxs-lookup"><span data-stu-id="8487f-154">Then, `cd` into one of the sample folders and run the sample via</span></span>

```bash
dotnet run
```
