---
title: Medições Pauli
description: Aprenda a trabalhar com operações de medição de Pauli de solteiro e multi-qubit.
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
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
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 7f10c4ad5eb325da97552d60ff47ea89a699f08d
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269478"
---
# <a name="pauli-measurements"></a><span data-ttu-id="81495-103">Medições Pauli</span><span class="sxs-lookup"><span data-stu-id="81495-103">Pauli Measurements</span></span>

<span data-ttu-id="81495-104">Nas discussões anteriores, concentrámo-nos em medições computacionais.</span><span class="sxs-lookup"><span data-stu-id="81495-104">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="81495-105">Na verdade, existem outras medições comuns que ocorrem na computação quântica que, do ponto de vista notacional, são convenientes de expressar em termos de medições de base computacional.</span><span class="sxs-lookup"><span data-stu-id="81495-105">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="81495-106">À medida que trabalha com Q#, o tipo de medições mais comum que irá encontrar provavelmente serão *as medições de Pauli*, que generalizam as medições de base computacional para incluir medições em outras bases, e de paridade entre diferentes qubits.</span><span class="sxs-lookup"><span data-stu-id="81495-106">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="81495-107">Nestes casos, é comum discutir a medição de um operador Pauli, em geral um operador como $X,Y,Z $ ou $Z \otimes Z, X \otimes X, X \otimes Y , $ etc.</span><span class="sxs-lookup"><span data-stu-id="81495-107">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
> <span data-ttu-id="81495-108">Em Q#, os operadores de Pauli multi-qubit são geralmente representados por matrizes do tipo `Pauli[]` .</span><span class="sxs-lookup"><span data-stu-id="81495-108">In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
> <span data-ttu-id="81495-109">Por exemplo, para representar $X \otimes Z \otimes $ Y, pode utilizar a matriz `[PauliX, PauliZ, PauliY]` .</span><span class="sxs-lookup"><span data-stu-id="81495-109">For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="81495-110">Discutir a medição em termos de operadores pauli é especialmente comum no subcampo da correção de erros quânticos.</span><span class="sxs-lookup"><span data-stu-id="81495-110">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="81495-111">Em Q#, seguimos uma convenção semelhante; agora explicamos esta visão alternativa das medições.</span><span class="sxs-lookup"><span data-stu-id="81495-111">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="81495-112">Antes de aprofundar os detalhes de como pensar de uma medição de Pauli, é útil pensar sobre o que medir um único qubit dentro de um computador quântico faz ao estado quântico.</span><span class="sxs-lookup"><span data-stu-id="81495-112">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="81495-113">Imagine que temos um $ estado quântico $n-qubit; em seguida, medir um qubit imediatamente exclui metade das possibilidades de $2^n em que o $ estado poderia estar dentro.</span><span class="sxs-lookup"><span data-stu-id="81495-113">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="81495-114">Por outras palavras, a medição projeta o estado quântico num dos dois semi-espaços.</span><span class="sxs-lookup"><span data-stu-id="81495-114">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="81495-115">Podemos generalizar a forma como pensamos sobre a medição para refletir esta intuição.</span><span class="sxs-lookup"><span data-stu-id="81495-115">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="81495-116">Para identificar concisamente estes subespaços, precisamos de uma linguagem para os descrever.</span><span class="sxs-lookup"><span data-stu-id="81495-116">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="81495-117">Uma forma de descrever os dois subespaços é especificando-os através de uma matriz que tem apenas dois valores eigenvalues únicos, tomados por convenção para ser $\pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="81495-117">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="81495-118">Para um simples exemplo de descrever subespaços desta forma, considere $ $Z:</span><span class="sxs-lookup"><span data-stu-id="81495-118">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

<span data-ttu-id="81495-119">$$ \start{align}</span><span class="sxs-lookup"><span data-stu-id="81495-119">$$ \begin{align}</span></span>
  <span data-ttu-id="81495-120">Z & = \{ bmatrix } 1 & 0 \\ \\ 0 & -1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="81495-120">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="81495-121">\end{align}</span><span class="sxs-lookup"><span data-stu-id="81495-121">\end{align}</span></span>
$$

<span data-ttu-id="81495-122">Ao ler os elementos diagonais da matriz Pauli-$Z, $ podemos ver que $Z $ tem dois eigenvectors, $\ket{0$ } e $\ket{1 } $, com correspondentes eigenvalues $\pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="81495-122">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="81495-123">Assim, se medirmos o qubit e `Zero` obtermos (correspondente ao estado $\ket{0 } $), sabemos que o estado do nosso qubit é um estado de $+1 $ do operador $ $Z.</span><span class="sxs-lookup"><span data-stu-id="81495-123">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="81495-124">Da mesma forma, se `One` obtivermos, sabemos que o estado do nosso qubit é um estado de $ $1 de $Z $ .</span><span class="sxs-lookup"><span data-stu-id="81495-124">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="81495-125">Este processo é referido na linguagem das medições de Pauli como "medição de Pauli $Z $ ", e é inteiramente equivalente a realizar uma medição de base computacional.</span><span class="sxs-lookup"><span data-stu-id="81495-125">This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="81495-126">Qualquer matriz de \times $2 2 $ que seja uma transformação unitária de $Z $ também satisfaz estes critérios.</span><span class="sxs-lookup"><span data-stu-id="81495-126">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="81495-127">Ou seja, também poderíamos usar uma matriz $A=U^\dagger Z $ U, onde $U $ é qualquer outra matriz unitária, para dar uma matriz que define os dois resultados de uma medição nos seus $\pm 1 $ eigenvectors.</span><span class="sxs-lookup"><span data-stu-id="81495-127">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="81495-128">A notação das medições de Pauli refere esta equivalência unitária identificando as medições $X,Y,Z $ como medidas equivalentes que se poderia fazer para obter informações a partir de um qubit.</span><span class="sxs-lookup"><span data-stu-id="81495-128">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="81495-129">Estas medições são dadas abaixo para conveniência.</span><span class="sxs-lookup"><span data-stu-id="81495-129">These measurements are given below for convenience.</span></span>


|<span data-ttu-id="81495-130">Medição de Pauli</span><span class="sxs-lookup"><span data-stu-id="81495-130">Pauli Measurement</span></span>  |<span data-ttu-id="81495-131">Transformação unitária</span><span class="sxs-lookup"><span data-stu-id="81495-131">Unitary transformation</span></span>  |
|-------------------|------------------------|
| <span data-ttu-id="81495-132">$Z$</span><span class="sxs-lookup"><span data-stu-id="81495-132">$Z$</span></span>               | <span data-ttu-id="81495-133">$\boldone$</span><span class="sxs-lookup"><span data-stu-id="81495-133">$\boldone$</span></span>             |
| <span data-ttu-id="81495-134">$X$</span><span class="sxs-lookup"><span data-stu-id="81495-134">$X$</span></span>               | <span data-ttu-id="81495-135">$H$</span><span class="sxs-lookup"><span data-stu-id="81495-135">$H$</span></span>                    |
| <span data-ttu-id="81495-136">$Y$</span><span class="sxs-lookup"><span data-stu-id="81495-136">$Y$</span></span>               | <span data-ttu-id="81495-137">$HS^{\dagger}$</span><span class="sxs-lookup"><span data-stu-id="81495-137">$HS^{\dagger}$</span></span>         |

<span data-ttu-id="81495-138">Ou seja, usando esta linguagem, "medir $ $Y" é equivalente a aplicar $HS^\dagger $ e, em seguida, medir na base computacional, onde [`S`](xref:microsoft.quantum.intrinsic.s) é uma operação quântica intrínseca às vezes chamada de "portão de fase", e pode ser simulada pela matriz unitária</span><span class="sxs-lookup"><span data-stu-id="81495-138">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

<span data-ttu-id="81495-139">$$ \start{align}</span><span class="sxs-lookup"><span data-stu-id="81495-139">$$ \begin{align}</span></span>
    <span data-ttu-id="81495-140">S = \start{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="81495-140">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="81495-141">1 & 0 \\ \\ 0 & i \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="81495-141">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="81495-142">\end{align}</span><span class="sxs-lookup"><span data-stu-id="81495-142">\end{align}</span></span>
$$

<span data-ttu-id="81495-143">É também equivalente à aplicação de $HS^\dagger $ ao vetor de estado quântico e, em seguida, medir $Z $ , de modo que a seguinte operação é equivalente `Measure([PauliY], [q])` a:</span><span class="sxs-lookup"><span data-stu-id="81495-143">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="81495-144">O estado correto seria então encontrado transformando-se de volta à base computacional, que equivale a aplicar $SH $ ao vetor de estado quântico; no corte acima, a transformação de volta à base computacional é tratada automaticamente pela utilização do `within … apply` bloco.</span><span class="sxs-lookup"><span data-stu-id="81495-144">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="81495-145">Em Q#, dizemos o resultado---é, a informação clássica extraída de interagir com o estado---is é dada por um `Result` valor $j \in \\ {\texttt{Zero, } \texttt{One } \\ }$ indicando se o resultado está no espaço $(-1)^j $ eigenspace do operador Pauli medido.</span><span class="sxs-lookup"><span data-stu-id="81495-145">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="81495-146">Medições de múltiplos qubits</span><span class="sxs-lookup"><span data-stu-id="81495-146">Multiple-qubit measurements</span></span>

<span data-ttu-id="81495-147">As medições dos operadores de Pauli multi-qubit são definidas da mesma forma, como visto a partir de:</span><span class="sxs-lookup"><span data-stu-id="81495-147">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

<span data-ttu-id="81495-148">$$ Z \otimes Z = \start} bmatrix }1 &0 &0&\\\\ 0 & 0 -1&0&0 \\\\ 0&0-1 &&0&\\\\ 0&0&1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="81495-148">$$ Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="81495-149">Assim, os produtos de tensor de dois operadores Pauli-$Z $ formam uma matriz composta por dois espaços compostos por $+1 $ e $-1 $ egévaues.</span><span class="sxs-lookup"><span data-stu-id="81495-149">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="81495-150">Tal como acontece com o caso single-qubit, ambos constituem um meio espaço, o que significa que metade do espaço vetorial acessível pertence ao espaço de $+1 $ e a restante metade para o espaço eigenspace de $-1. $</span><span class="sxs-lookup"><span data-stu-id="81495-150">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="81495-151">Em geral, é fácil constatar pela definição do produto tensor que qualquer produto tensor de operadores pauli-$Z $ e a identidade também obebe.</span><span class="sxs-lookup"><span data-stu-id="81495-151">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="81495-152">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="81495-152">For example,</span></span>

<span data-ttu-id="81495-153">$$ \start{align}</span><span class="sxs-lookup"><span data-stu-id="81495-153">$$ \begin{align}</span></span>
    <span data-ttu-id="81495-154">Z \otimes \boldone = \start{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="81495-154">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="81495-155">1 & 0 & 0 & \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & -1 & 0 \\ \\ & 0 & 0 & -1 \end. bmatrix }</span><span class="sxs-lookup"><span data-stu-id="81495-155">1 &  0 &  0 &  0 \\\\ 0 &  1 &  0 &  0 \\\\ 0 &  0 & -1 &  0 \\\\ 0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="81495-156">\end{align}</span><span class="sxs-lookup"><span data-stu-id="81495-156">\end{align}</span></span>
$$

<span data-ttu-id="81495-157">Como antes, qualquer transformação unitária de tais matrizes também descreve dois semi-espaços rotulados por $\pm 1 $ eigenvalues.</span><span class="sxs-lookup"><span data-stu-id="81495-157">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="81495-158">Por exemplo, $X \otimes X = \otimes H(Z \otimes Z)H \otimes H da identidade que $ $Z=HXH $ .</span><span class="sxs-lookup"><span data-stu-id="81495-158">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="81495-159">Semelhante ao caso de um qubit, todas as medições pauli de dois qubits podem ser escritas como $U^\dagger (Z \otimes \id) U $ por $4 \times 4 $ matrizes unitárias $U $ .</span><span class="sxs-lookup"><span data-stu-id="81495-159">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$.</span></span> <span data-ttu-id="81495-160">Enumeramos as transformações na tabela seguinte.</span><span class="sxs-lookup"><span data-stu-id="81495-160">We enumerate the transformations in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="81495-161">Na tabela abaixo, usamos $\operatorname{SWAP } $ para indicar a matriz $$ \start{align}</span><span class="sxs-lookup"><span data-stu-id="81495-161">In the table below, we use $\operatorname{SWAP}$ to indicate the matrix $$ \begin{align}</span></span>
>     <span data-ttu-id="81495-162">\operatorname{SWAP } & = \left(\start{matrix}</span><span class="sxs-lookup"><span data-stu-id="81495-162">\operatorname{SWAP} & = \left(\begin{matrix}</span></span>
>         <span data-ttu-id="81495-163">1 & 0 & 0 & 0 \\ \\ & 0 & 1 & \\ \\ 0 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{matrix } \end {right) \end{align}</span><span class="sxs-lookup"><span data-stu-id="81495-163">1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{matrix}\right) \end{align}</span></span>
> <span data-ttu-id="81495-164">$$ usado para simular a operação intrínseca. [`SWAP`](xref:microsoft.quantum.intrinsic)</span><span class="sxs-lookup"><span data-stu-id="81495-164">$$ used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

|<span data-ttu-id="81495-165">Medição de Pauli</span><span class="sxs-lookup"><span data-stu-id="81495-165">Pauli Measurement</span></span>     |<span data-ttu-id="81495-166">Transformação unitária</span><span class="sxs-lookup"><span data-stu-id="81495-166">Unitary transformation</span></span>  |
|----------------------|------------------------|
| <span data-ttu-id="81495-167">$Z \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="81495-167">$Z \otimes \boldone$</span></span> | <span data-ttu-id="81495-168">$\boldone \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="81495-168">$\boldone \otimes \boldone$</span></span> |
| <span data-ttu-id="81495-169">$Z \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="81495-169">$Z\otimes \boldone$</span></span> | <span data-ttu-id="81495-170">$\boldone \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="81495-170">$\boldone\otimes \boldone$</span></span> |
| <span data-ttu-id="81495-171">$X \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="81495-171">$X\otimes \boldone$</span></span> | <span data-ttu-id="81495-172">$H \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="81495-172">$H\otimes \boldone$</span></span> |
| <span data-ttu-id="81495-173">$Y \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="81495-173">$Y\otimes \boldone$</span></span> | <span data-ttu-id="81495-174">$HS^\dagger \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="81495-174">$HS^\dagger\otimes \boldone$</span></span> |
| <span data-ttu-id="81495-175">$\boldone \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="81495-175">$\boldone \otimes Z$</span></span> | <span data-ttu-id="81495-176">$\operatorname{SWAP}$</span><span class="sxs-lookup"><span data-stu-id="81495-176">$\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="81495-177">$\boldone \otimes X$</span><span class="sxs-lookup"><span data-stu-id="81495-177">$\boldone \otimes X$</span></span> | <span data-ttu-id="81495-178">$(H \otimes \boldone)\operatorname{SWAP}$</span><span class="sxs-lookup"><span data-stu-id="81495-178">$(H\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="81495-179">$\boldone \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="81495-179">$\boldone \otimes Y$</span></span> | <span data-ttu-id="81495-180">$(HS^\dagger \otimes \boldone)\operatorname{SWAP}$</span><span class="sxs-lookup"><span data-stu-id="81495-180">$(HS^\dagger\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="81495-181">$Z \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="81495-181">$Z\otimes Z$</span></span> | <span data-ttu-id="81495-182">$\operatorname{CNOT } \_ {10}$</span><span class="sxs-lookup"><span data-stu-id="81495-182">$\operatorname{CNOT}\_{10}$</span></span> |
| <span data-ttu-id="81495-183">$X \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="81495-183">$X\otimes Z$</span></span> | <span data-ttu-id="81495-184">$\operatorname{CNOT } \_ {10 } (H \otimes \boldone)$</span><span class="sxs-lookup"><span data-stu-id="81495-184">$\operatorname{CNOT}\_{10}(H\otimes \boldone)$</span></span> |
| <span data-ttu-id="81495-185">$Y \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="81495-185">$Y\otimes Z$</span></span> | <span data-ttu-id="81495-186">$\operatorname{CNOT } \_ {10 } (HS^\dagger \otimes \boldone)$</span><span class="sxs-lookup"><span data-stu-id="81495-186">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$</span></span> |
| <span data-ttu-id="81495-187">$Z \otimes X$</span><span class="sxs-lookup"><span data-stu-id="81495-187">$Z\otimes X$</span></span> | <span data-ttu-id="81495-188">$\operatorname{CNOT } \_ {10 } (\boldone \otimes H)$</span><span class="sxs-lookup"><span data-stu-id="81495-188">$\operatorname{CNOT}\_{10}(\boldone\otimes H)$</span></span> |
| <span data-ttu-id="81495-189">$X \otimes X$</span><span class="sxs-lookup"><span data-stu-id="81495-189">$X\otimes X$</span></span> | <span data-ttu-id="81495-190">$\operatorname{CNOT } \_ {10 } (H \otimes H)$</span><span class="sxs-lookup"><span data-stu-id="81495-190">$\operatorname{CNOT}\_{10}(H\otimes H)$</span></span> |
| <span data-ttu-id="81495-191">$Y \otimes X$</span><span class="sxs-lookup"><span data-stu-id="81495-191">$Y\otimes X$</span></span> | <span data-ttu-id="81495-192">$\operatorname{CNOT } \_ {10 } (HS^\dagger \otimes H)$</span><span class="sxs-lookup"><span data-stu-id="81495-192">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$</span></span> |
| <span data-ttu-id="81495-193">$Z \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="81495-193">$Z\otimes Y$</span></span> | <span data-ttu-id="81495-194">$\operatorname{CNOT } \_ {10 } (\boldone \otimes HS^\dagger)$</span><span class="sxs-lookup"><span data-stu-id="81495-194">$\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="81495-195">$X \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="81495-195">$X\otimes Y$</span></span> | <span data-ttu-id="81495-196">$\operatorname{CNOT } \_ {10 } \otimes (HS^\dagger)$</span><span class="sxs-lookup"><span data-stu-id="81495-196">$\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="81495-197">$Y \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="81495-197">$Y\otimes Y$</span></span> | <span data-ttu-id="81495-198">$\operatorname{CNOT } \_ {10 } (HS^\dagger \otimes HS^\dagger)$</span><span class="sxs-lookup"><span data-stu-id="81495-198">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$</span></span> |

<span data-ttu-id="81495-199">Aqui, a [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operação aparece pelo seguinte motivo.</span><span class="sxs-lookup"><span data-stu-id="81495-199">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="81495-200">Cada medição de Pauli que não inclua a matriz de $\boldone $ equivale a um unitário a $Z Z \otimes pelo raciocínio $ acima.</span><span class="sxs-lookup"><span data-stu-id="81495-200">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="81495-201">Os valores de eigenvalus de $Z \otimes Z $ dependem apenas da paridade dos qubits que compõem cada vetor de base computacional, e as operações não controladas servem para calcular esta paridade e armazená-la na primeira parte.</span><span class="sxs-lookup"><span data-stu-id="81495-201">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="81495-202">Depois, uma vez medida a primeira parte, podemos recuperar a identidade do meio-espaço resultante, o que equivale a medir o operador Pauli.</span><span class="sxs-lookup"><span data-stu-id="81495-202">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="81495-203">Uma nota adicional: embora possa ser tentador assumir que medir $Z Z é o mesmo que \otimes $ medir sequencialmente $Z \otimes \mathbb{1$ } e, em seguida, $\mathbb{1 } \otimes $ Z, esta suposição seria falsa.</span><span class="sxs-lookup"><span data-stu-id="81495-203">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="81495-204">A razão é que a medição $Z \otimes Z projeta o estado $ quântico para o estado de $+1 $ ou $-1 $ destes operadores.</span><span class="sxs-lookup"><span data-stu-id="81495-204">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="81495-205">Medindo $Z \otimes \mathbb{1$ } e, em seguida, $\mathbb{1 } \otimes Z $ projeta o vetor de estado quântico primeiro em um meio espaço de $Z \otimes \mathbb{1$ } e, em seguida, em um meio espaço de $\mathbb{1 } \otimes Z $ . Como existem quatro vetores de base computacional, realizar ambas as medições reduz o estado a um quarto de espaço e, portanto, reduz-o a um único vetor de base computacional.</span><span class="sxs-lookup"><span data-stu-id="81495-205">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="81495-206">Correlações entre qubits</span><span class="sxs-lookup"><span data-stu-id="81495-206">Correlations between qubits</span></span>
<span data-ttu-id="81495-207">Outra forma de olhar para a medição de produtos de tensor de matrizes Pauli, como $X \otimes X $ ou $Z \otimes $ Z, é que estas medições permitem olhar para a informação armazenada nas correlações entre os dois qubits.</span><span class="sxs-lookup"><span data-stu-id="81495-207">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="81495-208">Medir $X \otimes \id $ permite-lhe olhar para informações que são armazenadas localmente no primeiro qubit.</span><span class="sxs-lookup"><span data-stu-id="81495-208">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="81495-209">Embora ambos os tipos de medições sejam igualmente valiosos na computação quântica, o primeiro ilumina o poder da computação quântica.</span><span class="sxs-lookup"><span data-stu-id="81495-209">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="81495-210">Revela que na computação quântica, muitas vezes a informação que deseja aprender não é armazenada em qualquer qubit, mas sim armazenada não localmente em todos os qubits ao mesmo tempo, e, portanto, apenas olhando para ela através de uma medição conjunta (por exemplo, $Z \otimes Z $ ) esta informação torna-se manifesta.</span><span class="sxs-lookup"><span data-stu-id="81495-210">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="81495-211">Por exemplo, na correção de erros, muitas vezes queremos saber que erro ocorreu enquanto não aprendemos nada sobre o estado que estamos a tentar proteger.</span><span class="sxs-lookup"><span data-stu-id="81495-211">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="81495-212">A [amostra de código bit-flip](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) mostra um exemplo de como pode fazê-lo usando medidas como $Z \otimes Z \otimes \id $ e $\id \otimes Z \otimes Z $ .</span><span class="sxs-lookup"><span data-stu-id="81495-212">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$.</span></span>
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

<span data-ttu-id="81495-213">Operadores arbitrários de Pauli, tais como $X \otimes Y \otimes Z \otimes \boldone $ também podem ser medidos.</span><span class="sxs-lookup"><span data-stu-id="81495-213">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="81495-214">Todos estes produtos de tensor dos operadores pauli têm apenas dois eigenvalues $\pm 1 $ e ambos os espaços eigen constituem meio espaço de todo o espaço vetorial.</span><span class="sxs-lookup"><span data-stu-id="81495-214">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="81495-215">Assim, coincidem com os requisitos acima indicados.</span><span class="sxs-lookup"><span data-stu-id="81495-215">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="81495-216">Em Q#, tais medições regressam $j $ se a medição render um resultado no espaço eigen do sinal $(-1)^j $ .</span><span class="sxs-lookup"><span data-stu-id="81495-216">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="81495-217">Ter as medidas Pauli como uma característica incorporada em Q# é útil porque a medição de tais operadores requer longas cadeias de portões NÃO controlados e transformações de base para descrever a diagonalização $U $ portão necessário para expressar a operação como um produto de tensor de $Z e $ $\id $ . Ao ser capaz de especificar que deseja fazer uma destas medições pré-definidas, não precisa de se preocupar em como transformar a sua base de modo a que uma medição de base computacional forneça as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="81495-217">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$. By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="81495-218">Q# lida automaticamente com todas as transformações de base necessárias para si.</span><span class="sxs-lookup"><span data-stu-id="81495-218">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="81495-219">Para mais informações, consulte as [`Measure`](xref:microsoft.quantum.intrinsic.measure) [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operações e operações.</span><span class="sxs-lookup"><span data-stu-id="81495-219">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="81495-220">O Teorema da Não Clonagem</span><span class="sxs-lookup"><span data-stu-id="81495-220">The No-Cloning Theorem</span></span>

<span data-ttu-id="81495-221">A informação quântica é poderosa.</span><span class="sxs-lookup"><span data-stu-id="81495-221">Quantum information is powerful.</span></span>
<span data-ttu-id="81495-222">Permite-nos fazer coisas incríveis, como números de fatores exponencialmente mais rápidos do que os algoritmos clássicos mais conhecidos, ou simular eficientemente sistemas de eletrões correlacionados que clássicamente requerem custos exponenais para simular com precisão.</span><span class="sxs-lookup"><span data-stu-id="81495-222">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="81495-223">No entanto, existem limitações ao poder da computação quântica.</span><span class="sxs-lookup"><span data-stu-id="81495-223">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="81495-224">Uma dessas limitações é dada pelo Teorema da *Não Clonagem.*</span><span class="sxs-lookup"><span data-stu-id="81495-224">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="81495-225">O teorema de não clonagem tem o nome apropriado.</span><span class="sxs-lookup"><span data-stu-id="81495-225">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="81495-226">Não permite a clonagem de estados quânticos genéricos por um computador quântico.</span><span class="sxs-lookup"><span data-stu-id="81495-226">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="81495-227">A prova do teorema é notavelmente simples.</span><span class="sxs-lookup"><span data-stu-id="81495-227">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="81495-228">Embora uma prova completa do teorema da não clonagem seja um pouco técnica demais para a nossa discussão aqui, a prova no caso de não haver qubits auxiliares adicionais está dentro do nosso âmbito (qubits auxiliares são qubits usados para o espaço de risco durante um cálculo e são facilmente utilizados e geridos em Q#, ver [qubits emprestados).](xref:microsoft.quantum.guide.qubits#borrowed-qubits)</span><span class="sxs-lookup"><span data-stu-id="81495-228">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="81495-229">Para tal computador quântico, a operação de clonagem deve ser descrita por uma matriz unitária.</span><span class="sxs-lookup"><span data-stu-id="81495-229">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="81495-230">Não permitimos a medição, uma vez que iria corromper o estado quântico que estamos a tentar clonar.</span><span class="sxs-lookup"><span data-stu-id="81495-230">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="81495-231">Para simular a operação de clonagem, queremos que a matriz unitária tenha a propriedade que $$ U \ket { } \psi \ket {0 } = \ket { } \psi \ket { \ket \psi}</span><span class="sxs-lookup"><span data-stu-id="81495-231">To simulate the cloning operation, we want the unitary matrix used to have the property that $$ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
<span data-ttu-id="81495-232">$$ por qualquer estado $\ket { \psi } $.</span><span class="sxs-lookup"><span data-stu-id="81495-232">$$ for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="81495-233">A propriedade linear da multiplicação da matriz implica então que para qualquer segundo estado quântico $\ket { \phi } $,</span><span class="sxs-lookup"><span data-stu-id="81495-233">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

<span data-ttu-id="81495-234">$$ \start{align}</span><span class="sxs-lookup"><span data-stu-id="81495-234">$$ \begin{align}</span></span>
    <span data-ttu-id="81495-235">U\frac{1 } {\sqrt{2 } }\left\ket { \phi } \ket { \\ket \psi } \direita) \ket{0}</span><span class="sxs-lookup"><span data-stu-id="81495-235">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="81495-236">& = \frac{1 } {\sqrt{2 } } U \ket { \phi } \ket{0}</span><span class="sxs-lookup"><span data-stu-id="81495-236">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="81495-237">+ \frac{1 } {\sqrt{2 } } U \ket { } \ket {0 } \\ \\ & = \frac{1 } {\sqrt{2 } } \ket { } \phi \ket { \phi } \ket \ket { \ket \ket } \ket { \ket \ket \ket \psi \ket \ket \psi}</span><span class="sxs-lookup"><span data-stu-id="81495-237">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\ & = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="81495-238">\direita) \\ \\ & \ne \esquerda\ \frac{1 } {\sqrt{2}\left\ket } { \ket \phi } +\ket { \psi } \right) \otimes \f\frac{1 } {\sqrt{2}\left(\ket } { \phi } +\ket { \psi } \right).</span><span class="sxs-lookup"><span data-stu-id="81495-238">\right) \\\\ & \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
<span data-ttu-id="81495-239">\end{align}</span><span class="sxs-lookup"><span data-stu-id="81495-239">\end{align}</span></span>
$$

<span data-ttu-id="81495-240">Isto fornece a intuição fundamental por trás do Teorema da Não Clonagem: qualquer dispositivo que copie um estado quântico desconhecido deve induzir erros em pelo menos alguns dos estados que copia.</span><span class="sxs-lookup"><span data-stu-id="81495-240">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="81495-241">Embora o pressuposto-chave de que o cloner age linearmente sobre o estado de entrada pode ser violado através da adição e medição de qubits auxiliares, tais interações também vazam informações sobre o sistema através das estatísticas de medição e impedem a clonagem exata em tais casos também.</span><span class="sxs-lookup"><span data-stu-id="81495-241">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="81495-242">Para obter uma prova mais completa do teorema de não clonagem consulte [para mais informações](xref:microsoft.quantum.more-information).</span><span class="sxs-lookup"><span data-stu-id="81495-242">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="81495-243">O teorema da não clonagem é importante para a compreensão qualitativa da computação quântica, porque se pudéssemos clonar estados quânticos de forma barata, então seria-lhe concedida uma capacidade quase mágica de aprender com os estados quânticos.</span><span class="sxs-lookup"><span data-stu-id="81495-243">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="81495-244">Na verdade, pode violar o princípio vago de Heisenberg.</span><span class="sxs-lookup"><span data-stu-id="81495-244">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="81495-245">Em alternativa, você poderia usar um clone ideal para tirar uma única amostra de uma distribuição quântica complexa e aprender tudo o que você poderia aprender sobre essa distribuição a partir de apenas uma amostra.</span><span class="sxs-lookup"><span data-stu-id="81495-245">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="81495-246">Seria como se lançasses uma moeda e observasses as cabeças e, em seguida, ao contares a um amigo sobre o resultado, respondendo "Ah, a distribuição dessa moeda deve ser Bernoulli com $p=0,512643\ldots!" $</span><span class="sxs-lookup"><span data-stu-id="81495-246">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="81495-247">Tal declaração não seria sensata porque uma parte da informação (o resultado das cabeças) simplesmente não pode fornecer as muitas informações necessárias para codificar a distribuição sem informações prévias substanciais.</span><span class="sxs-lookup"><span data-stu-id="81495-247">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="81495-248">Da mesma forma, sem informação prévia não podemos perfeitamente clonar um estado quântico, tal como não podemos preparar um conjunto de tais moedas sem saber $p $ .</span><span class="sxs-lookup"><span data-stu-id="81495-248">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="81495-249">A informação não é gratuita na computação quântica.</span><span class="sxs-lookup"><span data-stu-id="81495-249">Information is not free in quantum computing.</span></span>
<span data-ttu-id="81495-250">Cada qubit medido dá um único pedaço de informação, e o Teorema de Não Clonagem mostra que não há uma porta traseira que possa ser explorada para contornar a troca fundamental entre a informação obtida sobre o sistema e a perturbação invocada sobre ele.</span><span class="sxs-lookup"><span data-stu-id="81495-250">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
