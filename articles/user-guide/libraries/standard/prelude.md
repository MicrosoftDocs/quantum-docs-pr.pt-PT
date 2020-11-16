---
title: Operações e funções intrínsecas no QDK
description: Conheça as operações e funções intrínsecas no QDK, incluindo funções clássicas e operações unitárias, de rotação e medição.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.prelude
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 4d15226fe46be79b7d3e6f414f33f1debd691f40
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692112"
---
# <a name="the-prelude"></a><span data-ttu-id="7a77c-103">O Prelúdio</span><span class="sxs-lookup"><span data-stu-id="7a77c-103">The Prelude</span></span> #

<span data-ttu-id="7a77c-104">O Q# compilador e as máquinas-alvo incluídas no Kit de Desenvolvimento Quântico fornecem um conjunto de funções e operações intrínsecas que podem ser usadas ao escrever programas quânticos em Q# .</span><span class="sxs-lookup"><span data-stu-id="7a77c-104">The Q# compiler and the target machines included with the Quantum Development Kit provide a set of intrinsic functions and operations that can be used when writing quantum programs in Q#.</span></span>

## <a name="intrinsic-operations-and-functions"></a><span data-ttu-id="7a77c-105">Operações e Funções Intrínsecas</span><span class="sxs-lookup"><span data-stu-id="7a77c-105">Intrinsic Operations and Functions</span></span> ##

<span data-ttu-id="7a77c-106">As operações intrínsecas definidas na biblioteca padrão enquadram-se aproximadamente numa das várias categorias:</span><span class="sxs-lookup"><span data-stu-id="7a77c-106">The intrinsic operations defined in the standard library roughly fall into one of several categories:</span></span>

- <span data-ttu-id="7a77c-107">Funções clássicas essenciais, recolhidas no espaço de <xref:Microsoft.Quantum.Core> nomes.</span><span class="sxs-lookup"><span data-stu-id="7a77c-107">Essential classical functions, collected in the <xref:Microsoft.Quantum.Core> namespace.</span></span>
- <span data-ttu-id="7a77c-108">Operações que representam unitários compostos por [clifford e portões $T$](xref:microsoft.quantum.concepts.qubit).</span><span class="sxs-lookup"><span data-stu-id="7a77c-108">Operations representing unitaries composed of [Clifford and $T$ gates](xref:microsoft.quantum.concepts.qubit).</span></span>
- <span data-ttu-id="7a77c-109">Operações que representam rotações sobre vários operadores.</span><span class="sxs-lookup"><span data-stu-id="7a77c-109">Operations representing rotations about various operators.</span></span>
- <span data-ttu-id="7a77c-110">Operações implementando medições.</span><span class="sxs-lookup"><span data-stu-id="7a77c-110">Operations implementing measurements.</span></span>

<span data-ttu-id="7a77c-111">Uma vez que o conjunto de portas Clifford + $T$ é [universal](xref:microsoft.quantum.concepts.multiple-qubits) para computação quântica, estas operações são suficientes para implementar aproximadamente qualquer algoritmo quântico dentro de um erro insignificantemente pequeno.</span><span class="sxs-lookup"><span data-stu-id="7a77c-111">Since the Clifford + $T$ gate set is [universal](xref:microsoft.quantum.concepts.multiple-qubits) for quantum computing, these operations suffice to approximately implement any quantum algorithm within negligibly small error.</span></span>
<span data-ttu-id="7a77c-112">Ao fornecer rotações também, Q# permite que o programador trabalhe dentro da única biblioteca unitária de qubit e cnot gate.</span><span class="sxs-lookup"><span data-stu-id="7a77c-112">By providing rotations as well, Q# allows the programmer to work within the single qubit unitary and CNOT gate library.</span></span> <span data-ttu-id="7a77c-113">Esta biblioteca é muito mais fácil de pensar porque não requer que o programador expresse diretamente a decomposição Clifford + $T$ e porque existem métodos altamente eficientes para compilar unidades de qubit únicas em clifford e portões de $T$ (ver [aqui](xref:microsoft.quantum.more-information) para mais informações).</span><span class="sxs-lookup"><span data-stu-id="7a77c-113">This library is much easier to think about because it does not  require the programmer to directly express the Clifford + $T$ decomposition and because highly efficient methods exist for compiling single qubit unitaries into Clifford and $T$ gates (see [here](xref:microsoft.quantum.more-information) for more information).</span></span>

<span data-ttu-id="7a77c-114">Sempre que possível, as operações definidas no prelúdio que atuam sobre os qubits permitem a aplicação da `Controlled` variante, de modo a que a máquina-alvo efetue a decomposição adequada.</span><span class="sxs-lookup"><span data-stu-id="7a77c-114">Where possible, the operations defined in the prelude which act on qubits allow for applying the `Controlled` variant, such that the target machine will perform the appropriate decomposition.</span></span>

<span data-ttu-id="7a77c-115">Muitas das funções e operações definidas nesta parte do prelúdio estão no espaço de nomes, de tal forma que a maioria dos @"microsoft.quantum.intrinsic" Q# ficheiros de origem terá uma `open Microsoft.Quantum.Intrinsic;` diretiva imediatamente após a declaração inicial do espaço de nome.</span><span class="sxs-lookup"><span data-stu-id="7a77c-115">Many of the functions and operations defined in this portion of the prelude are in the @"microsoft.quantum.intrinsic" namespace, such that most Q# source files will have an `open Microsoft.Quantum.Intrinsic;` directive immediately following the initial namespace declaration.</span></span>
<span data-ttu-id="7a77c-116">O <xref:Microsoft.Quantum.Core> espaço de nome é aberto automaticamente, de modo que as funções como podem ser <xref:Microsoft.Quantum.Core.Length> usadas sem qualquer `open` declaração.</span><span class="sxs-lookup"><span data-stu-id="7a77c-116">The <xref:Microsoft.Quantum.Core> namespace is automatically opened, so that functions such as <xref:Microsoft.Quantum.Core.Length> can be used without an `open` statement at all.</span></span>

### <a name="common-single-qubit-unitary-operations"></a><span data-ttu-id="7a77c-117">Operações Unitárias Single-Qubit Comuns</span><span class="sxs-lookup"><span data-stu-id="7a77c-117">Common Single-Qubit Unitary Operations</span></span> ###

<span data-ttu-id="7a77c-118">O prelúdio também define muitas operações comuns [de um único qubit.](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)</span><span class="sxs-lookup"><span data-stu-id="7a77c-118">The prelude also defines many common [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).</span></span>
<span data-ttu-id="7a77c-119">Todas estas operações permitem tanto os `Controlled` `Adjoint` functores como os funtores.</span><span class="sxs-lookup"><span data-stu-id="7a77c-119">All of these operations allow both the `Controlled` and `Adjoint` functors.</span></span>

#### <a name="pauli-operators"></a><span data-ttu-id="7a77c-120">Operadores Pauli</span><span class="sxs-lookup"><span data-stu-id="7a77c-120">Pauli Operators</span></span> ####

<span data-ttu-id="7a77c-121">A <xref:Microsoft.Quantum.Intrinsic.X> operação implementa o operador pauli $X$.</span><span class="sxs-lookup"><span data-stu-id="7a77c-121">The <xref:Microsoft.Quantum.Intrinsic.X> operation implements the Pauli $X$ operator.</span></span>
<span data-ttu-id="7a77c-122">Isto às vezes também é conhecido como o `NOT` portão.</span><span class="sxs-lookup"><span data-stu-id="7a77c-122">This is sometimes also known as the `NOT` gate.</span></span>
<span data-ttu-id="7a77c-123">Tem `(Qubit => Unit is Adj + Ctl)` assinatura.</span><span class="sxs-lookup"><span data-stu-id="7a77c-123">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="7a77c-124">Corresponde ao monobit unitário:</span><span class="sxs-lookup"><span data-stu-id="7a77c-124">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="7a77c-125">\start{equation} \start{bmatrix} 0 & 1 \\ \\ % FIXME: isto utiliza atualmente o hack quadwhack.</span><span class="sxs-lookup"><span data-stu-id="7a77c-125">\begin{equation} \begin{bmatrix} 0 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="7a77c-126">1 & 0 \end{bmatrix} \end{equação}</span><span class="sxs-lookup"><span data-stu-id="7a77c-126">1 & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="7a77c-127">A <xref:Microsoft.Quantum.Intrinsic.Y> operação implementa o operador pauli $Y$.</span><span class="sxs-lookup"><span data-stu-id="7a77c-127">The <xref:Microsoft.Quantum.Intrinsic.Y> operation implements the Pauli $Y$ operator.</span></span>
<span data-ttu-id="7a77c-128">Tem `(Qubit => Unit is Adj + Ctl)` assinatura.</span><span class="sxs-lookup"><span data-stu-id="7a77c-128">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="7a77c-129">Corresponde ao monobit unitário:</span><span class="sxs-lookup"><span data-stu-id="7a77c-129">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="7a77c-130">\start{equation} \start{bmatrix} 0 & -i \\ \\ % FIXME: isto utiliza atualmente o hack quadwhack.</span><span class="sxs-lookup"><span data-stu-id="7a77c-130">\begin{equation} \begin{bmatrix} 0 & -i \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="7a77c-131">i & 0 \end{bmatrix} \end{equação}</span><span class="sxs-lookup"><span data-stu-id="7a77c-131">i & 0 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="7a77c-132">A <xref:Microsoft.Quantum.Intrinsic.Z> operação implementa o operador pauli $Z$.</span><span class="sxs-lookup"><span data-stu-id="7a77c-132">The <xref:Microsoft.Quantum.Intrinsic.Z> operation implements the Pauli $Z$ operator.</span></span>
<span data-ttu-id="7a77c-133">Tem `(Qubit => Unit is Adj + Ctl)` assinatura.</span><span class="sxs-lookup"><span data-stu-id="7a77c-133">It has signature `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="7a77c-134">Corresponde ao monobit unitário:</span><span class="sxs-lookup"><span data-stu-id="7a77c-134">It corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="7a77c-135">\start{equation} \start{bmatrix} 1 & 0 \\ \\ % FIXME: isto utiliza atualmente o hack quadwhack.</span><span class="sxs-lookup"><span data-stu-id="7a77c-135">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="7a77c-136">0 & -1 \end{bmatrix} \end{equação}</span><span class="sxs-lookup"><span data-stu-id="7a77c-136">0 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="7a77c-137">Abaixo vemos estas transformações mapeadas para a [esfera bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (o eixo de rotação em cada caso é realçado vermelho):</span><span class="sxs-lookup"><span data-stu-id="7a77c-137">Below we see these transformations mapped to the [Bloch sphere](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (the rotation axis in each case is highlighted red):</span></span>

![Operações de Pauli mapeadas na esfera bloch](~/media/prelude_pauliBloch.png)

<span data-ttu-id="7a77c-139">É importante notar que a aplicação do mesmo portão Pauli duas vezes ao mesmo qubit cancela a operação (porque já realizou uma rotação completa de 2π (360°) sobre a superfície para a Esfera bloch, chegando assim ao ponto de partida).</span><span class="sxs-lookup"><span data-stu-id="7a77c-139">It is important to note that applying the same Pauli gate twice to the same qubit cancels out the operation (because you have now performed a full rotation of 2π (360°) over the surface to the Bloch Sphere, thus arriving back at the starting point).</span></span> <span data-ttu-id="7a77c-140">Isto leva-nos à seguinte identidade:</span><span class="sxs-lookup"><span data-stu-id="7a77c-140">This brings us to the following identity:</span></span>

<span data-ttu-id="7a77c-141">$$ X^2=Y^2=Z^2=\\boldone $$</span><span class="sxs-lookup"><span data-stu-id="7a77c-141">$$ X^2=Y^2=Z^2=\boldone $$</span></span>

<span data-ttu-id="7a77c-142">Isto pode ser visualizado na esfera bloch:</span><span class="sxs-lookup"><span data-stu-id="7a77c-142">This can be visualised on the Bloch sphere:</span></span>

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a><span data-ttu-id="7a77c-144">Outros Single-Qubit Cliffords</span><span class="sxs-lookup"><span data-stu-id="7a77c-144">Other Single-Qubit Cliffords</span></span> ####

<span data-ttu-id="7a77c-145">A <xref:Microsoft.Quantum.Intrinsic.H> operação implementa o portão Hadamard.</span><span class="sxs-lookup"><span data-stu-id="7a77c-145">The <xref:Microsoft.Quantum.Intrinsic.H> operation implements the Hadamard gate.</span></span>
<span data-ttu-id="7a77c-146">Isto intermuta os eixos Pauli $X$ e $Z$ do qubit alvo, de tal forma que $H\ket {0} = \ket{+} \mathrel{:=} (\ket {0} + \ket) {1} / \sqrt {2} $ e $H\ket{+} = \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="7a77c-146">This interchanges the Pauli $X$ and $Z$ axes of the target qubit, such that $H\ket{0} = \ket{+} \mathrel{:=} (\ket{0} + \ket{1}) / \sqrt{2}$ and $H\ket{+} = \ket{0}$.</span></span>
<span data-ttu-id="7a77c-147">Tem assinatura `(Qubit => Unit is Adj + Ctl)` , e corresponde ao único qubit unitário:</span><span class="sxs-lookup"><span data-stu-id="7a77c-147">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="7a77c-148">\start{equation} \frac {1} {\sqrt {2} } \start{bmatrix} 1 & 1 \\ \\ % FIXME: isto utiliza atualmente o hack quadwhack.</span><span class="sxs-lookup"><span data-stu-id="7a77c-148">\begin{equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="7a77c-149">1 & -1 \end{bmatrix} \end{equação}</span><span class="sxs-lookup"><span data-stu-id="7a77c-149">1 & -1 \end{bmatrix} \end{equation}</span></span>

<span data-ttu-id="7a77c-150">O portão Hadamard é particularmente importante, pois pode ser usado para criar uma superposição dos estados $\ket {0} $ e $\ket$ {1} .</span><span class="sxs-lookup"><span data-stu-id="7a77c-150">The Hadamard gate is particularly important as it can be used to create a superposition of the $\ket{0}$ and $\ket{1}$ states.</span></span> <span data-ttu-id="7a77c-151">Na representação da esfera bloch, é mais fácil pensar nisto como uma rotação de $\ket{\psi}$ em torno do eixo x por $\pi$ radians ($180^\circ$) seguido por uma rotação (no sentido horário) em torno do eixo y por $\pi/2$ radians ($90^\circ$):</span><span class="sxs-lookup"><span data-stu-id="7a77c-151">In the Bloch sphere representation, it is easiest to think of this as a rotation of $\ket{\psi}$ around the x-axis by $\pi$ radians ($180^\circ$) followed by a (clockwise) rotation around the y-axis by $\pi/2$ radians ($90^\circ$):</span></span>

![Operação Hadamard mapeada na esfera bloch](~/media/prelude_hadamardBloch.png)

<span data-ttu-id="7a77c-153">A <xref:Microsoft.Quantum.Intrinsic.S> operação implementa o portão de fase $S$.</span><span class="sxs-lookup"><span data-stu-id="7a77c-153">The <xref:Microsoft.Quantum.Intrinsic.S> operation implements the phase gate $S$.</span></span>
<span data-ttu-id="7a77c-154">Esta é a raiz quadrada da operação Pauli $Z$.</span><span class="sxs-lookup"><span data-stu-id="7a77c-154">This is the matrix square root of the Pauli $Z$ operation.</span></span>
<span data-ttu-id="7a77c-155">Ou seja, $S^2 = Z$.</span><span class="sxs-lookup"><span data-stu-id="7a77c-155">That is, $S^2 = Z$.</span></span>
<span data-ttu-id="7a77c-156">Tem assinatura `(Qubit => Unit is Adj + Ctl)` , e corresponde ao único qubit unitário:</span><span class="sxs-lookup"><span data-stu-id="7a77c-156">It has signature `(Qubit => Unit is Adj + Ctl)`, and corresponds to the single-qubit unitary:</span></span>

<span data-ttu-id="7a77c-157">\start{equation} \start{bmatrix} 1 & 0 \\ \\ % FIXME: isto utiliza atualmente o hack quadwhack.</span><span class="sxs-lookup"><span data-stu-id="7a77c-157">\begin{equation} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quadwhack hack.</span></span>
<span data-ttu-id="7a77c-158">0 & i \end{bmatrix} \end{equação}</span><span class="sxs-lookup"><span data-stu-id="7a77c-158">0 & i \end{bmatrix} \end{equation}</span></span>

#### <a name="rotations"></a><span data-ttu-id="7a77c-159">Rotações</span><span class="sxs-lookup"><span data-stu-id="7a77c-159">Rotations</span></span> ####

<span data-ttu-id="7a77c-160">Além das operações de Pauli e Clifford acima, o Q# prelúdio fornece uma variedade de formas de expressar rotações.</span><span class="sxs-lookup"><span data-stu-id="7a77c-160">In addition to the Pauli and Clifford operations above, the Q# prelude provides a variety of ways of expressing rotations.</span></span>
<span data-ttu-id="7a77c-161">Como descrito em [operações de um único qubit,](xref:microsoft.quantum.concepts.qubit#single-qubit-operations)a capacidade de rotação é fundamental para algoritmos quânticos.</span><span class="sxs-lookup"><span data-stu-id="7a77c-161">As described in [single-qubit operations](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), the ability to rotate is critical to quantum algorithms.</span></span>

<span data-ttu-id="7a77c-162">Começamos por recordar que podemos expressar qualquer operação de um único qubit utilizando os portões $H$ e $T$, onde $H$ é a operação Hadamard, e onde \start{equação} T \mathrel{:=} \start{bmatrix} 1 & 0 \\ \\ % FIXME: isto atualmente utiliza o quad back whack hack.</span><span class="sxs-lookup"><span data-stu-id="7a77c-162">We start by recalling that we can express any single-qubit operation using the $H$ and $T$ gates, where $H$ is the Hadamard operation, and where \begin{equation} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ % FIXME: this currently uses the quad back whack hack.</span></span>
<span data-ttu-id="7a77c-163">0 & e^{i \pi / 4} \end{bmatrix} \end{equação} Esta é a raiz quadrada da <xref:Microsoft.Quantum.Intrinsic.S> operação, de tal forma que $T^2 = S$.</span><span class="sxs-lookup"><span data-stu-id="7a77c-163">0 & e^{i \pi / 4} \end{bmatrix} \end{equation} This is the square root of the <xref:Microsoft.Quantum.Intrinsic.S> operation, such that $T^2 = S$.</span></span>
<span data-ttu-id="7a77c-164">O portão $T$ é, por sua vez, implementado pela <xref:Microsoft.Quantum.Intrinsic.T> operação, e tem `(Qubit => Unit is Adj + Ctl)` assinatura, indicando que se trata de uma operação unitária num único qubit.</span><span class="sxs-lookup"><span data-stu-id="7a77c-164">The $T$ gate is in turn implemented by the <xref:Microsoft.Quantum.Intrinsic.T> operation, and has signature `(Qubit => Unit is Adj + Ctl)`, indicating that it is a unitary operation on a single-qubit.</span></span>

<span data-ttu-id="7a77c-165">Embora isto seja, em princípio, suficiente para descrever qualquer operação arbitrária de um único qubit, as diferentes máquinas-alvo podem ter representações mais eficientes para rotações sobre os operadores de Pauli, de modo a que o prelúdio inclua uma variedade de formas de expressar convienentemente tais rotações.</span><span class="sxs-lookup"><span data-stu-id="7a77c-165">Even though this is in principle sufficient to describe any arbitrary single-qubit operation, different target machines may have more efficient representations for rotations about Pauli operators, such that the prelude includes a variety of ways to convienently express such rotations.</span></span>
<span data-ttu-id="7a77c-166">O mais básico destes é a <xref:Microsoft.Quantum.Intrinsic.r> operação, que implementa uma rotação em torno de um eixo Pauli especificado, \start{equação} R(\sigma, \phi) \mathrel{:=} \exp(i\phi \sigma / 2), \end{equação} onde $\sigma$ é um operador Pauli, $\phi$ é um ângulo, e onde $\exp$ representa a matriz expoente.</span><span class="sxs-lookup"><span data-stu-id="7a77c-166">The most basic of these is the <xref:Microsoft.Quantum.Intrinsic.r> operation, which implements a rotation around a specified Pauli axis, \begin{equation} R(\sigma, \phi) \mathrel{:=} \exp(-i \phi \sigma / 2), \end{equation} where $\sigma$ is a Pauli operator, $\phi$ is an angle, and where $\exp$ represents the matrix exponential.</span></span>
<span data-ttu-id="7a77c-167">Tem assinatura `((Pauli, Double, Qubit) => Unit is Adj + Ctl)` , onde as duas primeiras partes da entrada representam os argumentos clássicos $\sigma$ e $\phi$ necessários para especificar o operador unitário $R(\sigma, \phi)$.</span><span class="sxs-lookup"><span data-stu-id="7a77c-167">It has signature `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`, where the first two parts of the input represent the classical arguments $\sigma$ and $\phi$ needed to specify the unitary operator $R(\sigma, \phi)$.</span></span>
<span data-ttu-id="7a77c-168">Podemos aplicar parcialmente $\sigma$ e $\phi$ para obter uma operação cujo tipo é o de um único qubit unitário.</span><span class="sxs-lookup"><span data-stu-id="7a77c-168">We can partially apply $\sigma$ and $\phi$ to obtain an operation whose type is that of a single-qubit unitary.</span></span>
<span data-ttu-id="7a77c-169">Por exemplo, `R(PauliZ, PI() / 4, _)` tem tipo `(Qubit => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="7a77c-169">For example, `R(PauliZ, PI() / 4, _)` has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

> [!NOTE]
> <span data-ttu-id="7a77c-170">A <xref:Microsoft.Quantum.Intrinsic.r> operação divide o ângulo de entrada por 2 e multiplica-o por -1.</span><span class="sxs-lookup"><span data-stu-id="7a77c-170">The <xref:Microsoft.Quantum.Intrinsic.r> operation divides the input angle by 2 and multiplies it by -1.</span></span>
> <span data-ttu-id="7a77c-171">Para $Z dólares rotações, isto significa que o $\ket {0} $ eigenstate é rodado por $-\phi / 2$ e o $\ket {1} $ eigenstate é rodado por $\phi / 2$, de modo que o $\ket {1} $ eigenstate é rodado por $\phi$ em relação ao $\ket {0} $ eigenstate.</span><span class="sxs-lookup"><span data-stu-id="7a77c-171">For $Z$ rotations, this means that the $\ket{0}$ eigenstate is rotated by $-\phi / 2$ and the $\ket{1}$ eigenstate is rotated by $\phi / 2$, so that the $\ket{1}$ eigenstate is rotated by $\phi$ relative to the $\ket{0}$ eigenstate.</span></span>
>
> <span data-ttu-id="7a77c-172">Isto significa, em particular, que `T` e `R(PauliZ, PI() / 8, _)` diferem apenas por uma [fase global](xref:microsoft.quantum.glossary#global-phase)irrelevante.</span><span class="sxs-lookup"><span data-stu-id="7a77c-172">In particular, this means that `T` and `R(PauliZ, PI() / 8, _)` differ only by an irrelevant [global phase](xref:microsoft.quantum.glossary#global-phase).</span></span>
> <span data-ttu-id="7a77c-173">Por esta razão, $T$ é por vezes conhecido como o $\frac{\pi} {8} $-gate.</span><span class="sxs-lookup"><span data-stu-id="7a77c-173">For this reason, $T$ is sometimes known as the $\frac{\pi}{8}$-gate.</span></span>
>
> <span data-ttu-id="7a77c-174">Note também que rodar em torno `PauliI` simplesmente aplica uma fase global de $\phi / 2$.</span><span class="sxs-lookup"><span data-stu-id="7a77c-174">Note also that rotating around `PauliI` simply applies a global phase of $\phi / 2$.</span></span> <span data-ttu-id="7a77c-175">Embora tais fases sejam irrelevantes, como [argumentam os documentos conceptuais,](xref:microsoft.quantum.concepts.qubit)são relevantes para `PauliI` rotações controladas.</span><span class="sxs-lookup"><span data-stu-id="7a77c-175">While such phases are irrelevant, as argued in [the conceptual documents](xref:microsoft.quantum.concepts.qubit), they are relevant for controlled `PauliI` rotations.</span></span>

<span data-ttu-id="7a77c-176">Dentro de algoritmos quânticos, é frequentemente útil expressar rotações como frações dyadic, de modo que $\phi = \pi k / 2^n$ para alguns $k \in \mathbb{Z}$ e $n \in \mathbb{N}$.</span><span class="sxs-lookup"><span data-stu-id="7a77c-176">Within quantum algorithms, it is often useful to express rotations as dyadic fractions, such that $\phi = \pi k / 2^n$ for some $k \in \mathbb{Z}$ and $n \in \mathbb{N}$.</span></span>
<span data-ttu-id="7a77c-177">A <xref:Microsoft.Quantum.Intrinsic.RFrac> operação implementa uma rotação em torno de um eixo Pauli especificado usando esta convenção.</span><span class="sxs-lookup"><span data-stu-id="7a77c-177">The <xref:Microsoft.Quantum.Intrinsic.RFrac> operation implements a rotation around a specified Pauli axis using this convention.</span></span>
<span data-ttu-id="7a77c-178">Difere da medida em que o ângulo de <xref:Microsoft.Quantum.Intrinsic.R> rotação é especificado como duas entradas do `Int` tipo, interpretadas como uma fração diádica.</span><span class="sxs-lookup"><span data-stu-id="7a77c-178">It differs from <xref:Microsoft.Quantum.Intrinsic.R> in that the rotation angle is specified as two inputs of type `Int`, interpreted as a dyadic fraction.</span></span>
<span data-ttu-id="7a77c-179">Assim, `RFrac` tem `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` assinatura.</span><span class="sxs-lookup"><span data-stu-id="7a77c-179">Thus, `RFrac` has signature `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="7a77c-180">Implementa o monobit unitário $\exp(i\pi k \sigma / 2^n)$, onde $\sigma$ é a matriz Pauli correspondente ao primeiro argumento, $k$ é o segundo argumento, e $n$ é o terceiro argumento.</span><span class="sxs-lookup"><span data-stu-id="7a77c-180">It implements the single-qubit unitary $\exp(i \pi k \sigma / 2^n)$, where $\sigma$ is the Pauli matrix corresponding to the first argument, $k$ is the second argument, and $n$ is the third argument.</span></span>
<span data-ttu-id="7a77c-181">`RFrac(_,k,n,_)` é o mesmo `R(_,-πk/2^n,_)` que; note que o ângulo é *o negativo* da fração.</span><span class="sxs-lookup"><span data-stu-id="7a77c-181">`RFrac(_,k,n,_)` is the same as `R(_,-πk/2^n,_)`; note that the angle is the *negative* of the fraction.</span></span>

<span data-ttu-id="7a77c-182">A <xref:Microsoft.Quantum.Intrinsic.Rx> operação implementa uma rotação em torno do eixo Pauli $X$.</span><span class="sxs-lookup"><span data-stu-id="7a77c-182">The <xref:Microsoft.Quantum.Intrinsic.Rx> operation implements a rotation around the Pauli $X$ axis.</span></span>
<span data-ttu-id="7a77c-183">Tem `((Double, Qubit) => Unit is Adj + Ctl)` assinatura.</span><span class="sxs-lookup"><span data-stu-id="7a77c-183">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="7a77c-184">`Rx(_, _)` é o mesmo `R(PauliX, _, _)` que.</span><span class="sxs-lookup"><span data-stu-id="7a77c-184">`Rx(_, _)` is the same as `R(PauliX, _, _)`.</span></span>

<span data-ttu-id="7a77c-185">A <xref:Microsoft.Quantum.Intrinsic.Ry> operação implementa uma rotação em torno do eixo Pauli $Y$.</span><span class="sxs-lookup"><span data-stu-id="7a77c-185">The <xref:Microsoft.Quantum.Intrinsic.Ry> operation implements a rotation around the Pauli $Y$ axis.</span></span>
<span data-ttu-id="7a77c-186">Tem `((Double, Qubit) => Unit is Adj + Ctl)` assinatura.</span><span class="sxs-lookup"><span data-stu-id="7a77c-186">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="7a77c-187">`Ry(_, _)` é o mesmo `R(PauliY,_ , _)` que.</span><span class="sxs-lookup"><span data-stu-id="7a77c-187">`Ry(_, _)` is the same as `R(PauliY,_ , _)`.</span></span>

<span data-ttu-id="7a77c-188">A <xref:Microsoft.Quantum.Intrinsic.Rz> operação implementa uma rotação em torno do eixo Pauli $Z$.</span><span class="sxs-lookup"><span data-stu-id="7a77c-188">The <xref:Microsoft.Quantum.Intrinsic.Rz> operation implements a rotation around the Pauli $Z$ axis.</span></span>
<span data-ttu-id="7a77c-189">Tem `((Double, Qubit) => Unit is Adj + Ctl)` assinatura.</span><span class="sxs-lookup"><span data-stu-id="7a77c-189">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="7a77c-190">`Rz(_, _)` é o mesmo `R(PauliZ, _, _)` que.</span><span class="sxs-lookup"><span data-stu-id="7a77c-190">`Rz(_, _)` is the same as `R(PauliZ, _, _)`.</span></span>

<span data-ttu-id="7a77c-191">A <xref:Microsoft.Quantum.Intrinsic.R1> operação implementa uma rotação pelo valor dado em torno de $\ket {1} $, o $-1$ eigenstate de $Z$.</span><span class="sxs-lookup"><span data-stu-id="7a77c-191">The <xref:Microsoft.Quantum.Intrinsic.R1> operation implements a rotation by the given amount around $\ket{1}$, the $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="7a77c-192">Tem `((Double, Qubit) => Unit is Adj + Ctl)` assinatura.</span><span class="sxs-lookup"><span data-stu-id="7a77c-192">It has signature `((Double, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="7a77c-193">`R1(phi,_)` é o mesmo `R(PauliZ,phi,_)` que seguido `R(PauliI,-phi,_)` por.</span><span class="sxs-lookup"><span data-stu-id="7a77c-193">`R1(phi,_)` is the same as `R(PauliZ,phi,_)` followed by `R(PauliI,-phi,_)`.</span></span>

<span data-ttu-id="7a77c-194">A <xref:Microsoft.Quantum.Intrinsic.R1Frac> operação implementa uma rotação fracionária pela quantidade dada em torno do estado de Z=1.</span><span class="sxs-lookup"><span data-stu-id="7a77c-194">The <xref:Microsoft.Quantum.Intrinsic.R1Frac> operation implements a fractional rotation by the given amount around the Z=1 eigenstate.</span></span>
<span data-ttu-id="7a77c-195">Tem `((Int,Int, Qubit) => Unit is Adj + Ctl)` assinatura.</span><span class="sxs-lookup"><span data-stu-id="7a77c-195">It has signature `((Int,Int, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="7a77c-196">`R1Frac(k,n,_)` é o mesmo `RFrac(PauliZ,-k.n+1,_)` que seguido `RFrac(PauliI,k,n+1,_)` por.</span><span class="sxs-lookup"><span data-stu-id="7a77c-196">`R1Frac(k,n,_)` is the same as `RFrac(PauliZ,-k.n+1,_)` followed by `RFrac(PauliI,k,n+1,_)`.</span></span>

<span data-ttu-id="7a77c-197">Um exemplo de uma operação de rotação (em torno do eixo Pauli $Z$, neste caso) mapeada na esfera bloch é mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="7a77c-197">An example of a rotation operation (around the Pauli $Z$ axis, in this instance) mapped onto the Bloch sphere is shown below:</span></span>

![Operação de rotação mapeada na esfera bloch](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a><span data-ttu-id="7a77c-199">Operações Multi-Qubit</span><span class="sxs-lookup"><span data-stu-id="7a77c-199">Multi-Qubit Operations</span></span> ####

<span data-ttu-id="7a77c-200">Além das operações de um único qubit acima, o prelúdio também define várias operações multi-qubit.</span><span class="sxs-lookup"><span data-stu-id="7a77c-200">In addition to the single-qubit operations above, the prelude also defines several multi-qubit operations.</span></span>

<span data-ttu-id="7a77c-201">Primeiro, a <xref:Microsoft.Quantum.Intrinsic.CNOT> operação executa um portão controlado padrão, `NOT` \start{equation} \operatorname{CNOT} \mathrel{:=} \start{bmatrix} 1 & 0 & 0 & \\ \\ 0 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & \\ \\ 10 & 0 & 1 & 0 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="7a77c-201">First, the <xref:Microsoft.Quantum.Intrinsic.CNOT> operation performs a standard controlled-`NOT` gate, \begin{equation} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}.</span></span>
<span data-ttu-id="7a77c-202">\end{equation} Tem `((Qubit, Qubit) => Unit is Adj + Ctl)` assinatura, representando que $\operatorname{CNOT}$ age unitariamente em dois qubits individuais.</span><span class="sxs-lookup"><span data-stu-id="7a77c-202">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`, representing that $\operatorname{CNOT}$ acts unitarily on two individual qubits.</span></span>
<span data-ttu-id="7a77c-203">`CNOT(q1, q2)` é o mesmo `(Controlled X)([q1], q2)` que.</span><span class="sxs-lookup"><span data-stu-id="7a77c-203">`CNOT(q1, q2)` is the same as `(Controlled X)([q1], q2)`.</span></span>
<span data-ttu-id="7a77c-204">Uma vez que o `Controlled` functor permite controlar um registo, usamos a matriz literal `[q1]` para indicar que queremos apenas um controlo.</span><span class="sxs-lookup"><span data-stu-id="7a77c-204">Since the `Controlled` functor allows for controlling on a register, we use the array literal `[q1]` to indicate that we want only the one control.</span></span>

<span data-ttu-id="7a77c-205">A <xref:Microsoft.Quantum.Intrinsic.CCNOT> operação executa o portão NÃO duplamente controlado, por vezes também conhecido como portão Toffoli.</span><span class="sxs-lookup"><span data-stu-id="7a77c-205">The <xref:Microsoft.Quantum.Intrinsic.CCNOT> operation performs doubly-controlled NOT gate, sometimes also known as the Toffoli gate.</span></span>
<span data-ttu-id="7a77c-206">Tem `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` assinatura.</span><span class="sxs-lookup"><span data-stu-id="7a77c-206">It has signature `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="7a77c-207">`CCNOT(q1, q2, q3)` é o mesmo `(Controlled X)([q1, q2], q3)` que.</span><span class="sxs-lookup"><span data-stu-id="7a77c-207">`CCNOT(q1, q2, q3)` is the same as `(Controlled X)([q1, q2], q3)`.</span></span>

<span data-ttu-id="7a77c-208">A <xref:Microsoft.Quantum.Intrinsic.SWAP> operação troca os estados quânticos de dois qubits.</span><span class="sxs-lookup"><span data-stu-id="7a77c-208">The <xref:Microsoft.Quantum.Intrinsic.SWAP> operation swaps the quantum states of two qubits.</span></span>
<span data-ttu-id="7a77c-209">Ou seja, implementa a matriz unitária \start{equação} \operatorname{SWAP} \mathrel{:=} \start{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="7a77c-209">That is, it implements the unitary matrix \begin{equation} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.</span></span>
<span data-ttu-id="7a77c-210">\end{equação} Tem assinatura `((Qubit, Qubit) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="7a77c-210">\end{equation} It has signature `((Qubit, Qubit) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="7a77c-211">`SWAP(q1,q2)` é equivalente a `CNOT(q1, q2)` seguido por `CNOT(q2, q1)` e, em `CNOT(q1, q2)` seguida, .</span><span class="sxs-lookup"><span data-stu-id="7a77c-211">`SWAP(q1,q2)` is equivalent to `CNOT(q1, q2)` followed by `CNOT(q2, q1)` and then `CNOT(q1, q2)`.</span></span>

> [!NOTE]
> <span data-ttu-id="7a77c-212">O portão SWAP *não* é o mesmo que reorganizar os elementos de uma variável com o tipo `Qubit[]` .</span><span class="sxs-lookup"><span data-stu-id="7a77c-212">The SWAP gate is *not* the same as rearranging the elements of a variable with type `Qubit[]`.</span></span>
> <span data-ttu-id="7a77c-213">A aplicação `SWAP(q1, q2)` provoca uma alteração ao estado dos qubits referidos `q1` `q2` e, embora `let swappedRegister = [q2, q1];` apenas afete a forma como nos referimos a esses qubits.</span><span class="sxs-lookup"><span data-stu-id="7a77c-213">Applying `SWAP(q1, q2)` causes a change to the state of the qubits referred to by `q1` and `q2`, while `let swappedRegister = [q2, q1];` only affects how we refer to those qubits.</span></span>
> <span data-ttu-id="7a77c-214">Além disso, `(Controlled SWAP)([q0], (q1, q2))` permite estar condicionado ao estado de um terceiro `SWAP` qubit, que não podemos representar através da reorganização de elementos.</span><span class="sxs-lookup"><span data-stu-id="7a77c-214">Moreover, `(Controlled SWAP)([q0], (q1, q2))` allows for `SWAP` to be conditioned on the state of a third qubit, which we cannot represent by rearranging elements.</span></span>
> <span data-ttu-id="7a77c-215">O portão swap controlado, também conhecido como o portão Fredkin, é poderoso o suficiente para incluir toda a computação clássica.</span><span class="sxs-lookup"><span data-stu-id="7a77c-215">The controlled-SWAP gate, also known as the Fredkin gate, is powerful enough to include all classical computation.</span></span>

<span data-ttu-id="7a77c-216">Por último, o prelúdio prevê duas operações para representar exponencial dos operadores de Pauli multi-qubit.</span><span class="sxs-lookup"><span data-stu-id="7a77c-216">Finally, the prelude provides two operations for representing exponentials of multi-qubit Pauli operators.</span></span>
<span data-ttu-id="7a77c-217">A <xref:Microsoft.Quantum.Intrinsic.Exp> operação executa uma rotação baseada num produto tensor de matrizes Pauli, representada pelo multi-qubit unitário \begin{equação} \operatorname{Exp}(\vec{\sigma}, \phi) \mathrel{:=} \exp\left(i\phi \sigma_0 \otimes \sigma_1 \otimes \otimes \otimes \sigma_n \right), \end{equation} where $\vec{\sigma} = (\sigma_0, \sigma_1, \pontos, \sigma_n)$ é uma sequência de operadores pauli de um único qubit, e onde $\phi$ é um ângulo.</span><span class="sxs-lookup"><span data-stu-id="7a77c-217">The <xref:Microsoft.Quantum.Intrinsic.Exp> operation performs a rotation based on a tensor product of Pauli matrices, as represented by the multi-qubit unitary \begin{equation} \operatorname{Exp}(\vec{\sigma}, \phi) \mathrel{:=} \exp\left(i \phi \sigma_0 \otimes \sigma_1 \otimes \cdots \otimes \sigma_n \right), \end{equation} where $\vec{\sigma} = (\sigma_0, \sigma_1, \dots, \sigma_n)$ is a sequence of single-qubit Pauli operators, and where $\phi$ is an angle.</span></span>
<span data-ttu-id="7a77c-218">A `Exp` rotação representa $\vec{\sigma}$ como uma variedade de `Pauli` elementos, de modo a que tenha assinatura `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` .</span><span class="sxs-lookup"><span data-stu-id="7a77c-218">The `Exp` rotation represents $\vec{\sigma}$ as an array of `Pauli` elements, such that it has signature `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="7a77c-219">A <xref:Microsoft.Quantum.Intrinsic.ExpFrac> operação executa a mesma rotação, utilizando a notação de fração dyad discutida acima.</span><span class="sxs-lookup"><span data-stu-id="7a77c-219">The <xref:Microsoft.Quantum.Intrinsic.ExpFrac> operation performs the same rotation, using the dyadic fraction notation discussed above.</span></span>
<span data-ttu-id="7a77c-220">Tem `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` assinatura.</span><span class="sxs-lookup"><span data-stu-id="7a77c-220">It has signature `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`.</span></span>

> [!WARNING]
> <span data-ttu-id="7a77c-221">As exponenciais do produto tensor dos operadores Pauli não são os mesmos que os produtos tensores dos exponencial dos operadores da Pauli.</span><span class="sxs-lookup"><span data-stu-id="7a77c-221">Exponentials of the tensor product of Pauli operators are not the same as tensor products of the exponentials of Pauli operators.</span></span>
> <span data-ttu-id="7a77c-222">Ou seja, $e^{i (Z \otimes Z) \phi} \ne e^{i Z \phi} \otimes e^{i Z \phi}$.</span><span class="sxs-lookup"><span data-stu-id="7a77c-222">That is, $e^{i (Z \otimes Z) \phi} \ne e^{i Z \phi} \otimes e^{i Z \phi}$.</span></span>

### <a name="measurements"></a><span data-ttu-id="7a77c-223">Medições</span><span class="sxs-lookup"><span data-stu-id="7a77c-223">Measurements</span></span> ###

<span data-ttu-id="7a77c-224">Ao medir, o valor de +1 do operador a ser medido corresponde a um `Zero` resultado e o -1 égénico para `One` um resultado.</span><span class="sxs-lookup"><span data-stu-id="7a77c-224">When measuring, the +1 eigenvalue of the operator being measured corresponds to a `Zero` result, and the -1 eigenvalue to a `One` result.</span></span>

> [!NOTE]
> <span data-ttu-id="7a77c-225">Embora esta convenção possa parecer estranha, tem duas vantagens muito boas.</span><span class="sxs-lookup"><span data-stu-id="7a77c-225">While this convention might seem odd, it has two very nice advantages.</span></span>
> <span data-ttu-id="7a77c-226">Em primeiro lugar, observar o resultado $\ket {0} $ é representado pelo `Result` `Zero` valor, enquanto observa $\ket {1} $ corresponde a `One` .</span><span class="sxs-lookup"><span data-stu-id="7a77c-226">First, observing the outcome $\ket{0}$ is represented by the `Result` value `Zero`, while observing $\ket{1}$ corresponds to `One`.</span></span>
> <span data-ttu-id="7a77c-227">Em segundo lugar, podemos escrever que o eigenvalue $\lambda$ correspondente a um resultado $r$ é $\lambda = (-1)^r$.</span><span class="sxs-lookup"><span data-stu-id="7a77c-227">Second, we can write out that the eigenvalue $\lambda$ corresponding to a result $r$ is $\lambda = (-1)^r$.</span></span>

<span data-ttu-id="7a77c-228">As operações de medição não suportam nem o `Adjoint` functor nem o `Controlled` functor.</span><span class="sxs-lookup"><span data-stu-id="7a77c-228">Measurement operations support neither the `Adjoint` nor the `Controlled` functor.</span></span>

<span data-ttu-id="7a77c-229">A <xref:Microsoft.Quantum.Intrinsic.Measure> operação efetua uma medição conjunta de um ou mais qubits no produto especificado dos operadores da Pauli.</span><span class="sxs-lookup"><span data-stu-id="7a77c-229">The <xref:Microsoft.Quantum.Intrinsic.Measure> operation performs a joint measurement of one or more qubits in the specified product of Pauli operators.</span></span>
<span data-ttu-id="7a77c-230">Se a matriz de Pauli e a matriz de qubits forem diferentes comprimentos, então a operação falha.</span><span class="sxs-lookup"><span data-stu-id="7a77c-230">If the Pauli array and qubit array are different lengths, then the operation fails.</span></span>
<span data-ttu-id="7a77c-231">`Measure` tem assinatura `((Pauli[], Qubit[]) => Result)` .</span><span class="sxs-lookup"><span data-stu-id="7a77c-231">`Measure` has signature `((Pauli[], Qubit[]) => Result)`.</span></span>

<span data-ttu-id="7a77c-232">Note que uma medição articular não é a mesma que medir cada qubit individualmente.</span><span class="sxs-lookup"><span data-stu-id="7a77c-232">Note that a joint measurement is not the same as measuring each qubit individually.</span></span>
<span data-ttu-id="7a77c-233">Por exemplo, considere o estado $\ket {11} = \ket {1} \otimes \ket {1} = X\otimes X \ket {00} $.</span><span class="sxs-lookup"><span data-stu-id="7a77c-233">For example, consider the state $\ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.</span></span>
<span data-ttu-id="7a77c-234">Medindo $Z_0$ e $Z_1$ cada um individualmente, obtemos os resultados $r_0 = 1$ e $r_1 = 1$.</span><span class="sxs-lookup"><span data-stu-id="7a77c-234">Measuring $Z_0$ and $Z_1$ each individually, we get the results $r_0 = 1$ and $r_1 = 1$.</span></span>
<span data-ttu-id="7a77c-235">Medindo $Z_0 Z_1$, no entanto, obtemos o único resultado $r_{\textrm{joint}} = 0$, representando que a paridade de $\ket {11} $ é positiva.</span><span class="sxs-lookup"><span data-stu-id="7a77c-235">Measuring $Z_0 Z_1$, however, we get the single result $r_{\textrm{joint}} = 0$, representing that the pairity of $\ket{11}$ is positive.</span></span>
<span data-ttu-id="7a77c-236">Dito de forma diferente, $(-1)^{r_0 + r_1} = (-1)^r_{\textrm{joint}})$.</span><span class="sxs-lookup"><span data-stu-id="7a77c-236">Put differently, $(-1)^{r_0 + r_1} = (-1)^r_{\textrm{joint}})$.</span></span>
<span data-ttu-id="7a77c-237">Criticamente, uma vez que *só* aprendemos a paridade com esta medida, qualquer informação quântica representada na superposição entre os dois estados de dois qubits de paridade positiva, $\ket {00} $ e $\ket {11} $, é preservada.</span><span class="sxs-lookup"><span data-stu-id="7a77c-237">Critically, since we *only* learn the parity from this measurement, any quantum information represented in the superposition between the two two-qubit states of positive parity, $\ket{00}$ and $\ket{11}$, is preserved.</span></span>
<span data-ttu-id="7a77c-238">Esta propriedade será essencial mais tarde, enquanto discutimos a correção de erros.</span><span class="sxs-lookup"><span data-stu-id="7a77c-238">This property will be essential later, as we discuss error correction.</span></span>

<span data-ttu-id="7a77c-239">Por conveniência, o prelúdio também fornece duas outras operações para medir qubits.</span><span class="sxs-lookup"><span data-stu-id="7a77c-239">For convenience, the prelude also provides two other operations for measuring qubits.</span></span>
<span data-ttu-id="7a77c-240">Em primeiro lugar, uma vez que a realização de medições de um único qubit é bastante comum, o prelúdio define uma abreviatura para este caso.</span><span class="sxs-lookup"><span data-stu-id="7a77c-240">First, since performing single-qubit measurements is quite common, the prelude defines a shorthand for this case.</span></span>
<span data-ttu-id="7a77c-241">A <xref:Microsoft.Quantum.Intrinsic.M> operação mede o operador pauli $Z$ num único qubit, e tem assinatura `(Qubit => Result)` .</span><span class="sxs-lookup"><span data-stu-id="7a77c-241">The <xref:Microsoft.Quantum.Intrinsic.M> operation measures the Pauli $Z$ operator on a single qubit, and has signature `(Qubit => Result)`.</span></span>
<span data-ttu-id="7a77c-242">`M(q)` é equivalente a `Measure([PauliZ], [q])`.</span><span class="sxs-lookup"><span data-stu-id="7a77c-242">`M(q)` is equivalent to `Measure([PauliZ], [q])`.</span></span>

<span data-ttu-id="7a77c-243">As <xref:microsoft.quantum.measurement.MultiM> medidas que o Operador Pauli $Z$ *separadamente* em cada uma de uma matriz de qubits, devolvendo a *matriz* de `Result` valores obtidos para cada qubit.</span><span class="sxs-lookup"><span data-stu-id="7a77c-243">The <xref:microsoft.quantum.measurement.MultiM> measures the Pauli $Z$ operator *separately* on each of an array of qubits, returning the *array* of `Result` values obtained for each qubit.</span></span>
<span data-ttu-id="7a77c-244">Em alguns casos, isto pode ser otimizado.</span><span class="sxs-lookup"><span data-stu-id="7a77c-244">In some cases this can be optimized.</span></span> <span data-ttu-id="7a77c-245">Tem assinatura ( `Qubit[] => Result[])` .</span><span class="sxs-lookup"><span data-stu-id="7a77c-245">It has signature (`Qubit[] => Result[])`.</span></span>
<span data-ttu-id="7a77c-246">`MultiM(qs)` equivale a:</span><span class="sxs-lookup"><span data-stu-id="7a77c-246">`MultiM(qs)` is equivalent to:</span></span>

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a><span data-ttu-id="7a77c-247">Funções e Operações de Extensão</span><span class="sxs-lookup"><span data-stu-id="7a77c-247">Extension Functions and Operations</span></span> ##

<span data-ttu-id="7a77c-248">Além disso, o prelúdio define um conjunto rico de funções de conversão matemática e tipo ao nível .NET para utilização dentro do Q# código.</span><span class="sxs-lookup"><span data-stu-id="7a77c-248">In addition, the prelude defines a rich set of mathematical and type conversion functions at the .NET level for use within Q# code.</span></span>
<span data-ttu-id="7a77c-249">Por exemplo, o <xref:Microsoft.Quantum.Math> espaço de nome define operações úteis tais como e <xref:Microsoft.Quantum.Math.Sin> <xref:Microsoft.Quantum.Math.Log> .</span><span class="sxs-lookup"><span data-stu-id="7a77c-249">For instance, the <xref:Microsoft.Quantum.Math> namespace defines useful operations such as <xref:Microsoft.Quantum.Math.Sin> and <xref:Microsoft.Quantum.Math.Log>.</span></span>
<span data-ttu-id="7a77c-250">A implementação fornecida pelo Kit de Desenvolvimento Quântico utiliza a clássica biblioteca de classe base .NET, podendo assim envolver uma viagem de ida e volta de comunicações adicional entre programas quânticos e seus condutores clássicos.</span><span class="sxs-lookup"><span data-stu-id="7a77c-250">The implementation provided by the Quantum Development Kit uses the classical .NET base class library, and thus may involve an additional communications round trip between quantum programs and their classical drivers.</span></span>
<span data-ttu-id="7a77c-251">Embora isto não apresente um problema para um simulador local, este pode ser um problema de desempenho ao usar um simulador remoto ou hardware real como uma máquina alvo.</span><span class="sxs-lookup"><span data-stu-id="7a77c-251">While this does not present a problem for a local simulator, this can be a performance issue when using a remote simulator or actual hardware as a target machine.</span></span>
<span data-ttu-id="7a77c-252">Dito isto, uma máquina-alvo individual pode mitigar este impacto de desempenho, sobrepôs-se a estas operações com versões mais eficientes para esse sistema específico.</span><span class="sxs-lookup"><span data-stu-id="7a77c-252">That said, an individual target machine may mitigate this performance impact by overriding these operations with versions that are more efficient for that particular system.</span></span>

### <a name="math"></a><span data-ttu-id="7a77c-253">Matemática</span><span class="sxs-lookup"><span data-stu-id="7a77c-253">Math</span></span> ###

<span data-ttu-id="7a77c-254">O <xref:Microsoft.Quantum.Math> espaço de nomes fornece muitas funções úteis da classe base da [ `System.Math` biblioteca](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1&preserve-view=true).NET.</span><span class="sxs-lookup"><span data-stu-id="7a77c-254">The <xref:Microsoft.Quantum.Math> namespace provides many useful functions from the .NET base class library's [`System.Math` class](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1&preserve-view=true).</span></span>
<span data-ttu-id="7a77c-255">Estas funções podem ser utilizadas da mesma forma que quaisquer Q# outras funções:</span><span class="sxs-lookup"><span data-stu-id="7a77c-255">These functions can be used in the same manner as any other Q# functions:</span></span>

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

<span data-ttu-id="7a77c-256">Quando um método estático .NET tiver sido sobrecarregado com base no tipo dos seus argumentos, a função correspondente Q# é anotada com um sufixo que indique o tipo da sua entrada:</span><span class="sxs-lookup"><span data-stu-id="7a77c-256">Where a .NET static method has been overloaded based on the type of its arguments, the corresponding Q# function is annotated with a suffix indicating the type of its input:</span></span>

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a><span data-ttu-id="7a77c-257">Operações Bitwise</span><span class="sxs-lookup"><span data-stu-id="7a77c-257">Bitwise Operations</span></span> ###

<span data-ttu-id="7a77c-258">Finalmente, o <xref:Microsoft.Quantum.Bitwise> espaço de nomes fornece várias funções úteis para manipular inteiros através de operadores bitwise.</span><span class="sxs-lookup"><span data-stu-id="7a77c-258">Finally, the <xref:Microsoft.Quantum.Bitwise> namespace provides several useful functions for manipulating integers through bitwise operators.</span></span>
<span data-ttu-id="7a77c-259">Por exemplo, <xref:Microsoft.Quantum.Bitwise.Parity> devolve a paridade de um inteiro como outro inteiro.</span><span class="sxs-lookup"><span data-stu-id="7a77c-259">For instance, <xref:Microsoft.Quantum.Bitwise.Parity> returns the bitwise parity of an integer as another integer.</span></span>
