---
title: Oráculos quânticos
description: Aprenda a trabalhar e a definir oráculos quânticos, operações de caixa preta que são usadas como entrada para outro algoritmo.
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 31e43940fc0607b15ccefcfae6be7122227b3d64
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630326"
---
# <a name="quantum-oracles"></a><span data-ttu-id="59075-103">Oráculos Quânticos</span><span class="sxs-lookup"><span data-stu-id="59075-103">Quantum Oracles</span></span>

<span data-ttu-id="59075-104">Um oráculo $O $ é uma operação de "caixa preta" que é usada como entrada para outro algoritmo.</span><span class="sxs-lookup"><span data-stu-id="59075-104">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="59075-105">Frequentemente, tais operações são definidas utilizando uma função clássica $f : \\ {0, 1 \\ }^n \a \\ {0, \\ 1}^m $ que leva uma entrada binária de $n $ -bit e produz uma saída binária de $ $m-bit.</span><span class="sxs-lookup"><span data-stu-id="59075-105">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="59075-106">Para tal, considere uma entrada binária específica $x = (x_{0 } , x_{1 } , \pontos, x_{n-1 } )$.</span><span class="sxs-lookup"><span data-stu-id="59075-106">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="59075-107">Podemos rotular os estados qubit como $\ket { \vec{x} } = \ket{x_{0} } \otimes \ket{x_{1 } } \otimes \otimes \ket{{x_{n-1 } }$.</span><span class="sxs-lookup"><span data-stu-id="59075-107">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="59075-108">Podemos primeiro tentar definir $O $ de modo que $O \ket {x = } \ket{f(x)}$,, mas isto tem alguns problemas.</span><span class="sxs-lookup"><span data-stu-id="59075-108">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="59075-109">Em primeiro lugar, $f $ podem ter um tamanho diferente de entrada e saída ($n \ne $ m), de tal forma que a aplicação de $O $ alteraria o número de qubits no registo.</span><span class="sxs-lookup"><span data-stu-id="59075-109">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="59075-110">Em segundo lugar, mesmo que $n = $ m, a função pode não ser invertível: se $f(x) = f(y)$ para algum $x \ne y $ , em seguida, $O \ket {x = O } \ket {y } $ mas $O^\dagger O \ket {x } \ne O^\dagger O \ket {y } $.</span><span class="sxs-lookup"><span data-stu-id="59075-110">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="59075-111">Isto significa que não seremos capazes de construir a operação adjacente $O^\dagger $ , e os oráculos têm de ter um adjacente definido para eles.</span><span class="sxs-lookup"><span data-stu-id="59075-111">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="59075-112">Definição de um oráculo pelo seu efeito em estados de base computacional</span><span class="sxs-lookup"><span data-stu-id="59075-112">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="59075-113">Podemos lidar com estes dois problemas introduzindo um segundo registo de $m $ qubits para manter a nossa resposta.</span><span class="sxs-lookup"><span data-stu-id="59075-113">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="59075-114">Em seguida, definiremos o efeito do oráculo em todos os estados de base computacional: para todos os $x \in \\ {0, \\ 1}^n $ e $y \in \\ {0, \\ 1}^m, $</span><span class="sxs-lookup"><span data-stu-id="59075-114">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

<span data-ttu-id="59075-115">$$ \start{align}</span><span class="sxs-lookup"><span data-stu-id="59075-115">$$ \begin{align}</span></span>
    <span data-ttu-id="59075-116">O(\ket{x } \otimes \ket{y } ) = \ket{x } \otimes \ket{y \oplus f(x)}.</span><span class="sxs-lookup"><span data-stu-id="59075-116">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="59075-117">\end{align}</span><span class="sxs-lookup"><span data-stu-id="59075-117">\end{align}</span></span>
$$

<span data-ttu-id="59075-118">Agora $O = O^\punhal $ por construção, assim resolvemos ambos os problemas anteriores.</span><span class="sxs-lookup"><span data-stu-id="59075-118">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
> <span data-ttu-id="59075-119">Para ver que $O = O^{\dagger } $, note que $O^2 = \boldone $ desde $a \oplus b \oplus b = a $ para todos os $a, b \in \{ 0, 1 \} $.</span><span class="sxs-lookup"><span data-stu-id="59075-119">To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
> <span data-ttu-id="59075-120">Como resultado, $O \ket{x } \ket{y \oplus f(x)} = \ket{x } \ket{y \ket{y \oplus f(x) \oplus f(x)} = \ket{x } \ket{y } $.</span><span class="sxs-lookup"><span data-stu-id="59075-120">As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="59075-121">Importante, definir um oráculo desta forma para cada estado de base computacional $\ket{x } \ket{y } $ também define como $O atua para qualquer outro $ estado.</span><span class="sxs-lookup"><span data-stu-id="59075-121">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="59075-122">Isto resulta imediatamente do facto de $O $ , como todas as operações quânticas, ser linear no estado em que atua.</span><span class="sxs-lookup"><span data-stu-id="59075-122">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="59075-123">Considere a operação Hadamard, por exemplo, que é definida por $H \ket{0 } = \ket { +}$ e $H \ket{1 } = \ket { -}$.</span><span class="sxs-lookup"><span data-stu-id="59075-123">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="59075-124">Se quisermos saber como $H $ atua em $\ket { +}$, podemos usar esse $H $ é linear,</span><span class="sxs-lookup"><span data-stu-id="59075-124">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

<span data-ttu-id="59075-125">$$ \start{align}</span><span class="sxs-lookup"><span data-stu-id="59075-125">$$ \begin{align}</span></span>
<span data-ttu-id="59075-126">H \ket { +} & = \frac{1 } {\sqrt{2 } } H(\ket{0 } + \ket{1) } = \frac{1 } {\sqrt{2 } } (H \ket {0 } + H \ket {1 } ) & = \\ \\ \frac {1 } {\sqrt{2 } } (\ket { +} + \ket { -}) = \frac12 (\ket{0 } + \ket{1 } + \ket{0 } - \ket{1 } ) = \ket{0 } .</span><span class="sxs-lookup"><span data-stu-id="59075-126">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
<span data-ttu-id="59075-127">\end{align}</span><span class="sxs-lookup"><span data-stu-id="59075-127">\end{align}</span></span>
$$

<span data-ttu-id="59075-128">No caso de definir o nosso oráculo $ $O, podemos igualmente usar que qualquer estado $\ket { \psi } $ em $n + m $ qubits pode ser escrito como</span><span class="sxs-lookup"><span data-stu-id="59075-128">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

<span data-ttu-id="59075-129">$$ \start{align}</span><span class="sxs-lookup"><span data-stu-id="59075-129">$$ \begin{align}</span></span>
<span data-ttu-id="59075-130">\ket { \psi } & = \sum_{x \in \\ {0, \\ 1}^n, y \in \\ {0, \\ 1}^m } \alpha(x, y) \ket{x } \ket{y}</span><span class="sxs-lookup"><span data-stu-id="59075-130">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
<span data-ttu-id="59075-131">\end{align}</span><span class="sxs-lookup"><span data-stu-id="59075-131">\end{align}</span></span>
$$

<span data-ttu-id="59075-132">onde $\alpha : \\ {0, 1 \\ }^n \times \\ {0, 1 \\ }^m \to \mathbb{C$ } representa os coeficientes do estado $\ket { \psi } $.</span><span class="sxs-lookup"><span data-stu-id="59075-132">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="59075-133">Assim,</span><span class="sxs-lookup"><span data-stu-id="59075-133">Thus,</span></span>

<span data-ttu-id="59075-134">$$ \start{align}</span><span class="sxs-lookup"><span data-stu-id="59075-134">$$ \begin{align}</span></span>
<span data-ttu-id="59075-135">O \ket { \psi } & = O \sum_{x \in \\ {0, \\ 1}^n, y \in \\ {0, \\ 1}^m } \alpha(x, y) \ket{x } \ket{y } \\ \\ & = \sum_{x \in \\ {0, \\ 1}^n, y \in \\ {0, \\ 1}^m } \alpha(x, y) O \ket{x } \ket{y } \\ \\ & = \sum_{x \in \\ {0, \\ 1}^n, y \in \\ {0, \\ 1}^m } \alpha(x, y) } \ket{\ket{y\y\y\y\ket{y\y\y\ket{y\y\ket{y\y\y\y\y\ket{y\y\y\y\y\ket{y\y\y\y\y\y\ket{y\y\ket{y\y\ket{y\y\ket{y\y\ket{y\y\y\ket{y\y\y\ket{y\y\ket{y\y\ket{y\y\ket{y\y\ket{y\y\y\ket{y\y\y\ket{y\y\y\</span><span class="sxs-lookup"><span data-stu-id="59075-135">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="59075-136">\end{align}</span><span class="sxs-lookup"><span data-stu-id="59075-136">\end{align}</span></span>
$$

## <a name="phase-oracles"></a><span data-ttu-id="59075-137">Oráculos de fase</span><span class="sxs-lookup"><span data-stu-id="59075-137">Phase oracles</span></span>
<span data-ttu-id="59075-138">Em alternativa, podemos codificar $f $ num $O oráculo $ aplicando uma _fase_ baseada na entrada para $O $ .</span><span class="sxs-lookup"><span data-stu-id="59075-138">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$.</span></span>
<span data-ttu-id="59075-139">Por exemplo, podemos definir $O $ tal que $$ \start{align}</span><span class="sxs-lookup"><span data-stu-id="59075-139">For instance, we might define $O$ such that $$ \begin{align}</span></span>
    <span data-ttu-id="59075-140">O \ket{x } = (-1)^{f(x)} \ket{x } .</span><span class="sxs-lookup"><span data-stu-id="59075-140">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
<span data-ttu-id="59075-141">\end{align}</span><span class="sxs-lookup"><span data-stu-id="59075-141">\end{align}</span></span>
<span data-ttu-id="59075-142">$$ Se um oráculo de fase agir num registo inicialmente numa base computacional estado $\ket{x } $, então esta fase é uma fase global e, portanto, não observável.</span><span class="sxs-lookup"><span data-stu-id="59075-142">$$ If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="59075-143">Mas tal oráculo pode ser um recurso muito poderoso se aplicado a uma superposição ou como uma operação controlada.</span><span class="sxs-lookup"><span data-stu-id="59075-143">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="59075-144">Por exemplo, considere uma fase orcale $O_f $ para uma função de um único qubit $f $ .</span><span class="sxs-lookup"><span data-stu-id="59075-144">For example, consider a phase orcale $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="59075-145">Então, $$ \start{align}</span><span class="sxs-lookup"><span data-stu-id="59075-145">Then, $$ \begin{align}</span></span>
    <span data-ttu-id="59075-146">O_f \ket { +} & = O_f (\ket{0 } + \ket{1 } ) / \sqrt{2 & = } \\ \\ ((-1)^{f(0)} \ket{0 + } (-1)^{f(1)} \ket{1) \ ket{1 } ) / \sqrt{2 } \\ \\ & = (-1)^{f(0)} (\ket{0 + } (-1)^{f(1) - f(0)} \ket{1 } ) / \sqrt{2 } \\ \\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket { +}</span><span class="sxs-lookup"><span data-stu-id="59075-146">O_f \ket{+} & = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\ & = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
<span data-ttu-id="59075-147">\end{align}</span><span class="sxs-lookup"><span data-stu-id="59075-147">\end{align}</span></span>
$$

<span data-ttu-id="59075-148">De uma forma mais geral, ambas as vistas dos oráculos podem ser alargadas para representar funções clássicas que devolvem números reais em vez de apenas um bit.</span><span class="sxs-lookup"><span data-stu-id="59075-148">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="59075-149">Escolher a melhor maneira de implementar um oráculo depende muito de como este oráculo será usado dentro de um determinado algoritmo.</span><span class="sxs-lookup"><span data-stu-id="59075-149">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="59075-150">Por exemplo, o [algoritmo Deutsch-Jozsa baseia-se](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) no oráculo implementado de primeira forma, enquanto o [algoritmo de Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) depende do oráculo implementado da segunda forma.</span><span class="sxs-lookup"><span data-stu-id="59075-150">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="59075-151">Para mais detalhes, sugerimos a discussão em [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span><span class="sxs-lookup"><span data-stu-id="59075-151">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
