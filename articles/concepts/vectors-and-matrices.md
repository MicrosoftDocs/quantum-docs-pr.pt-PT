---
title: Vetores e matrizes em computação quântica
description: Aprenda o básico de como trabalhar com vetores e matrizes.
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
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
ms.openlocfilehash: f9d4e14742b7d06a6e90af0902b31fbdf17aedab
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269546"
---
# <a name="vectors-and-matrices"></a><span data-ttu-id="814de-103">Vetores e Matrizes</span><span class="sxs-lookup"><span data-stu-id="814de-103">Vectors and Matrices</span></span>

<span data-ttu-id="814de-104">Alguma familiaridade com vetores e matrizes é essencial para entender a computação quântica.</span><span class="sxs-lookup"><span data-stu-id="814de-104">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="814de-105">Fornecemos uma breve introdução abaixo e os leitores interessados são recomendados a ler uma referência padrão em álgebra linear como *Strang, G. (1993). Introdução à álgebra linear (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* ou uma referência online como [álgebra linear.](http://joshua.smcvt.edu/linearalgebra/)</span><span class="sxs-lookup"><span data-stu-id="814de-105">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="814de-106">Um vetor de coluna (ou simplesmente [*vetor)*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))$v $ de dimensão (ou tamanho) $n $ é uma coleção de números complexos $n $ $(v_1,v_2,\ldots,v_n)$ dispostos como uma coluna:</span><span class="sxs-lookup"><span data-stu-id="814de-106">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="814de-107">$$v =\start{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-107">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="814de-108">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-108">v_1\\\\</span></span>
<span data-ttu-id="814de-109">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-109">v_2\\\\</span></span>
<span data-ttu-id="814de-110">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-110">\vdots\\\\</span></span>
<span data-ttu-id="814de-111">v_n \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="814de-111">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="814de-112">A norma de um vetor $v $ é definida como $\sqrt { \sum i \_ \_ #v i | ^2 } $.</span><span class="sxs-lookup"><span data-stu-id="814de-112">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="814de-113">Diz-se que um vetor é de norma unitária (ou, em alternativa, é chamado de [*vetor unitário)*](https://en.wikipedia.org/wiki/Unit_vector)se a sua norma for $1 $ .</span><span class="sxs-lookup"><span data-stu-id="814de-113">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="814de-114">O [*adjacente de um vetor*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v é $ denotado $v^\dagger $ e é definido como o vetor de linha seguinte onde $ \* $ denota o conjugado complexo,</span><span class="sxs-lookup"><span data-stu-id="814de-114">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="814de-115">$$\begin{ bmatrix }v_1 \\ \\ \vdots \\ \\ v_n \end{\dagger bmatrix } = \begin{ bmatrix }v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="814de-115">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="814de-116">A forma mais comum de multiplicar dois vetores juntos é através do [*produto interno,*](https://en.wikipedia.org/wiki/Inner_product_space)também conhecido como um produto ponto.</span><span class="sxs-lookup"><span data-stu-id="814de-116">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="814de-117">O produto interno dá a projeção de um vetor para outro e é inestimável na descrição de como expressar um vetor como uma soma de outros vetores mais simples.</span><span class="sxs-lookup"><span data-stu-id="814de-117">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="814de-118">O produto interno entre $u $ e $v $ , denotado $\left \langle u, v é definido \right \rangle $ como</span><span class="sxs-lookup"><span data-stu-id="814de-118">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

<span data-ttu-id="814de-119">$$ \langle u, v \rangle = u^\dagger v=u \_ 1^{ \* } v_1 + \cdots + u \_ n^} \* } v \_ n.</span><span class="sxs-lookup"><span data-stu-id="814de-119">$$ \langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="814de-120">Esta notação também permite que a norma de um vetor $v $ ser escrito como $\sqrt { \langle v, \rangle } v$.</span><span class="sxs-lookup"><span data-stu-id="814de-120">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="814de-121">Podemos multiplicar um vetor com um número $c $ para formar um novo vetor cujas entradas são multiplicadas por $ $c.</span><span class="sxs-lookup"><span data-stu-id="814de-121">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="814de-122">Também podemos adicionar dois vetores $u $ e $v para formar um novo $ vetor cujas entradas são a soma das entradas de $u $ e $ $v.</span><span class="sxs-lookup"><span data-stu-id="814de-122">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="814de-123">Estas operações são retratadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="814de-123">These operations are depicted below:</span></span>

<span data-ttu-id="814de-124">$$\mathrm{If } ~u =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-124">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="814de-125">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-125">u_1\\\\</span></span>
<span data-ttu-id="814de-126">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-126">u_2\\\\</span></span>
<span data-ttu-id="814de-127">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-127">\vdots\\\\</span></span>
<span data-ttu-id="814de-128">u_n bmatrix } \end{~\mathrm{e } ~ v =\start{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-128">u_n \end{bmatrix}~\mathrm{and}~ v =\begin{bmatrix}</span></span>
    <span data-ttu-id="814de-129">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-129">v_1\\\\</span></span>
    <span data-ttu-id="814de-130">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-130">v_2\\\\</span></span>
    <span data-ttu-id="814de-131">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-131">\vdots\\\\</span></span>
    <span data-ttu-id="814de-132">v_n \{ bmatrix } .~\mathrm{then } ~ au+bv =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-132">v_n \end{bmatrix},~\mathrm{then}~ au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="814de-133">au_1+bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-133">au_1+bv_1\\\\</span></span>
<span data-ttu-id="814de-134">au_2+bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-134">au_2+bv_2\\\\</span></span>
<span data-ttu-id="814de-135">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-135">\vdots\\\\</span></span>
<span data-ttu-id="814de-136">au_n+bv_n \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="814de-136">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="814de-137">Uma [*matriz*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) de tamanho $m \times n $ é uma coleção de números complexos $mn $ dispostos em $m $ linhas e colunas $n $ como mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="814de-137">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="814de-138">$$M = \start{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-138">$$M = \begin{bmatrix}</span></span>
<span data-ttu-id="814de-139">M_{11 } ~~ M_{12 } ~~ \cdots ~~ M_{1n } \\ \\ M_{21 } ~~ M_{22 } ~~ \cdots ~~ M_{2n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-139">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="814de-140">M_{m1 } ~~ M_{m2 } ~~ \cdots ~~ M_{mn } \\ \\ \end. bmatrix }</span><span class="sxs-lookup"><span data-stu-id="814de-140">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\ \end{bmatrix}.$$</span></span>

<span data-ttu-id="814de-141">Note que um vetor de dimensão $n $ é simplesmente uma matriz de tamanho $n \vezes 1 $ .</span><span class="sxs-lookup"><span data-stu-id="814de-141">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="814de-142">Tal como acontece com os vetores, podemos multiplicar uma matriz com um número $c $ para obter uma nova matriz onde cada entrada é multiplicada com $ $c, e podemos adicionar duas matrizes do mesmo tamanho para produzir uma nova matriz cujas entradas são a soma das respetivas entradas das duas matrizes.</span><span class="sxs-lookup"><span data-stu-id="814de-142">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="814de-143">Multiplicação de matriz e produtos de tensor</span><span class="sxs-lookup"><span data-stu-id="814de-143">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="814de-144">Podemos também multiplicar duas matrizes $M $ de dimensão $m \times n e $N de $ $ dimensão $n \times p $ para obter uma nova matriz $P de $ dimensão $m \vezes p $ da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="814de-144">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

<span data-ttu-id="814de-145">\iniciar{alinhar}</span><span class="sxs-lookup"><span data-stu-id="814de-145">\begin{align}</span></span>
<span data-ttu-id="814de-146">&\{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-146">&\begin{bmatrix}</span></span>
    <span data-ttu-id="814de-147">M_{11 } ~~ M_{12 } ~~ \cdots ~~ M_{1n } \\ \\ M_{21 } ~~ M_{22 } ~~ \cdots ~~ M_{2n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-147">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
    <span data-ttu-id="814de-148">M_{m1 } ~~ M_{m2 } ~~ \cdots ~~ M_{mn}</span><span class="sxs-lookup"><span data-stu-id="814de-148">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
<span data-ttu-id="814de-149">\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-149">\end{bmatrix}</span></span>
<span data-ttu-id="814de-150">\começar{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-150">\begin{bmatrix}</span></span>
<span data-ttu-id="814de-151">N_{11 } ~~ N_{12 } ~~ \cdots ~~ N_{1p } \\ \\ N_{21 } ~~ N_{22 } ~~ \cdots ~~ N_{2p } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-151">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\ N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="814de-152">N_{n1 } ~~ N_{n2 } ~~ \cdots ~~ N_{np}</span><span class="sxs-lookup"><span data-stu-id="814de-152">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
<span data-ttu-id="814de-153">bmatrix } \end{\beginbmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-153">\end{bmatrix}=\begin{bmatrix}</span></span>
<span data-ttu-id="814de-154">P_{11 } ~~ P_{12 } ~~ \cdots ~~ P_{1p } \\ \\ P_{21 } ~~ P_{22 } ~~ \cdots ~~ P_{2p } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-154">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\ P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="814de-155">P_{m1 } ~~ P_{m2 } ~~ \cdots ~~ P_{mp}</span><span class="sxs-lookup"><span data-stu-id="814de-155">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
<span data-ttu-id="814de-156">\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-156">\end{bmatrix}</span></span>
<span data-ttu-id="814de-157">\end{align}</span><span class="sxs-lookup"><span data-stu-id="814de-157">\end{align}</span></span>

<span data-ttu-id="814de-158">onde as entradas de $P $ são $P_{ik } = \sum_j M_{ij}N_{jk } $.</span><span class="sxs-lookup"><span data-stu-id="814de-158">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="814de-159">Por exemplo, a entrada $P_{11$ } é o produto interno da primeira linha de $M com a primeira coluna de $N $ $ .</span><span class="sxs-lookup"><span data-stu-id="814de-159">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$.</span></span> <span data-ttu-id="814de-160">Note que uma vez que um vetor é simplesmente um caso especial de uma matriz, esta definição estende-se à multiplicação de vetores de matriz.</span><span class="sxs-lookup"><span data-stu-id="814de-160">Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="814de-161">Todas as matrizes que consideramos serão matrizes quadradas, onde o número de linhas e colunas são iguais, ou vetores, o que corresponde apenas a uma coluna de $ $1.</span><span class="sxs-lookup"><span data-stu-id="814de-161">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="814de-162">Uma matriz quadrada especial é a [*matriz identitária,*](https://en.wikipedia.org/wiki/Identity_matrix)denotada $\boldone, $ que tem todos os seus elementos diagonais iguais a $1 e os $ restantes elementos iguais a $0 $ :</span><span class="sxs-lookup"><span data-stu-id="814de-162">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

<span data-ttu-id="814de-163">$$\boldone = \beginbmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-163">$$\boldone=\begin{bmatrix}</span></span>
<span data-ttu-id="814de-164">1 ~~ ~~ ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-164">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="814de-165">0 ~~ ~~ ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-165">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="814de-166">~~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-166">~~ \ddots\\\\</span></span>
<span data-ttu-id="814de-167">0 ~~ ~~ ~~ \cdots ~~ 1 bmatrix } \end{.$$</span><span class="sxs-lookup"><span data-stu-id="814de-167">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="814de-168">Para uma matriz quadrada $ $A, dizemos que uma matriz $B $ é o seu [*inverso*](https://en.wikipedia.org/wiki/Invertible_matrix) se $AB = BA = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="814de-168">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="814de-169">O inverso de uma matriz não precisa de existir, mas quando existe é único e denotamos $A^{-1 } $.</span><span class="sxs-lookup"><span data-stu-id="814de-169">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="814de-170">Para qualquer $M matriz $ , o transposto cont ou conjugado de $M $ é uma matriz $N tal que $ $N_{ij } = M_{ji } ^ \* $.</span><span class="sxs-lookup"><span data-stu-id="814de-170">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="814de-171">O contíguo de $M $ é geralmente denotado $M^\dagger $ .</span><span class="sxs-lookup"><span data-stu-id="814de-171">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="814de-172">Dizemos que uma matriz $U $ é [*unitária*](https://en.wikipedia.org/wiki/Unitary_matrix) se $UU^\dagger = U^\dagger U = \boldone $ ou equivalentemente, $U^{-1 } = U^\dagger $ .</span><span class="sxs-lookup"><span data-stu-id="814de-172">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="814de-173">Talvez a propriedade mais importante das matrizes unitárias é que eles preservam a norma de um vetor.</span><span class="sxs-lookup"><span data-stu-id="814de-173">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="814de-174">Isto acontece porque</span><span class="sxs-lookup"><span data-stu-id="814de-174">This happens because</span></span> 

<span data-ttu-id="814de-175">$$\langle v,v \rangle=v^\\dagger v = v^\dagger U^{-1 } U v = v^\dagger U^\dagger U v = \langle U v, U v \rangle .$$</span><span class="sxs-lookup"><span data-stu-id="814de-175">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="814de-176">Diz-se que uma matriz $M $ é [*hermitiana*](https://en.wikipedia.org/wiki/Hermitian_matrix) se $M=M^\dagger $ .</span><span class="sxs-lookup"><span data-stu-id="814de-176">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="814de-177">Por último, o [*produto tensor*](https://en.wikipedia.org/wiki/Tensor_product) (ou produto Kronecker) de duas matrizes $M $ de tamanho $m n e $N de tamanho $p \times $ $ \vezes q $ é uma matriz maior $P=M \otimes N de tamanho $mp $ \times $ nq, e é obtido a partir de $M e $N $ $ seguintes:</span><span class="sxs-lookup"><span data-stu-id="814de-177">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

<span data-ttu-id="814de-178">\iniciar{alinhar}</span><span class="sxs-lookup"><span data-stu-id="814de-178">\begin{align}</span></span>
    <span data-ttu-id="814de-179">M\otimes N &= \start{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-179">M \otimes N &= \begin{bmatrix}</span></span>
        <span data-ttu-id="814de-180">M_{11 } ~~ \cdots ~~ M_{1n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-180">M_{11} ~~ \cdots ~~ M_{1n} \\\\ \ddots\\\\</span></span>
        <span data-ttu-id="814de-181">M_{m1 } ~~ \cdots ~~ M_{mn}</span><span class="sxs-lookup"><span data-stu-id="814de-181">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    <span data-ttu-id="814de-182">\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-182">\end{bmatrix}</span></span>
    <span data-ttu-id="814de-183">\otimes \{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-183">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="814de-184">N_{11 } ~~ \cdots ~~ N_{1q } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-184">N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="814de-185">N_{p1 } ~~ \cdots ~~ N_{pq}</span><span class="sxs-lookup"><span data-stu-id="814de-185">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    <span data-ttu-id="814de-186">\end{ bmatrix } \\ \\ &= \start{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-186">\end{bmatrix}\\\\ &= \begin{bmatrix}</span></span>
        <span data-ttu-id="814de-187">M_{11 } \start{N_ bmatrix } 11 {11 } ~~ \cdots ~~ N_{1q } \\ \\ \ddots \\\\ N_{p1 } ~~ \cdots ~~ N_{pq } \end{ bmatrix } ~~ \cdots ~~ M_{1n } \start{ bmatrix } N_ {11 } ~~ \cdots ~~ N_{1q } \\ \\ \ddots \\\\ N_{p1 } ~~ \cdots ~~ N_{pq } \end{ bmatrix } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="814de-187">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="814de-188">M_{m1 } \start{{N_ bmatrix } 11 } ~~ \cdots ~~ N_{1q } \\ \\ \ddots \\\\ N_{p1 } ~~ \cdots ~~ N_{pq } \end{ bmatrix } ~~ \cdots ~~ M_{mn } \start{ bmatrix } N_ {11 } ~~ \cdots ~~ N_{1q } \\ \\ \ddots \\\\ N_{p1 } ~~ \cdots ~~ N_{pq } \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-188">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="814de-189">bmatrix } \end{.</span><span class="sxs-lookup"><span data-stu-id="814de-189">\end{bmatrix}.</span></span>
<span data-ttu-id="814de-190">\end{align}</span><span class="sxs-lookup"><span data-stu-id="814de-190">\end{align}</span></span>

<span data-ttu-id="814de-191">Isto é melhor demonstrado com alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="814de-191">This is better demonstrated with some examples:</span></span>

<span data-ttu-id="814de-192">$$ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-192">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="814de-193">a \\ \\ b \end{ bmatrix } \otimes \begin{d bmatrix } e \\ \\ \\ \\ \end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-193">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix}</span></span>
        <span data-ttu-id="814de-194">a \begin{ bmatrix } c d e \\ \\ \\ \\ \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-194">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="814de-195">\\\\[1.5em] b \start{d bmatrix } \\ \\ \\ \\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-195">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    <span data-ttu-id="814de-196">\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-196">\end{bmatrix}</span></span>
    <span data-ttu-id="814de-197">= \start{ bmatrix } a c a d a \\ \\ e b \\ \\ b b \\ \\ \\ \\ d \\ \\ ser\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-197">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="814de-198">e</span><span class="sxs-lookup"><span data-stu-id="814de-198">and</span></span>

<span data-ttu-id="814de-199">$$ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-199">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="814de-200">a\ b \\ \\ c\ d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-200">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    <span data-ttu-id="814de-201">\otimes \{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-201">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="814de-202">e\ f \\ \\ g\ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-202">e\ f\\\\g\ h \end{bmatrix}</span></span>
     <span data-ttu-id="814de-203">= \start{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-203">= \begin{bmatrix}</span></span>
    <span data-ttu-id="814de-204">um\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-204">a\begin{bmatrix}</span></span>
    <span data-ttu-id="814de-205">e\ f \\\\ g\ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-205">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="814de-206">b\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-206">b\begin{bmatrix}</span></span>
    <span data-ttu-id="814de-207">e\ f \\\\ g\ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-207">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="814de-208">\\\\[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-208">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="814de-209">e\ f \\\\ g\ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-209">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="814de-210">d\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-210">d\begin{bmatrix}</span></span>
    <span data-ttu-id="814de-211">e\ f \\\\ g\ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-211">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="814de-212">\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-212">\end{bmatrix}</span></span>
    <span data-ttu-id="814de-213">= \start{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="814de-213">= \begin{bmatrix}</span></span>
    <span data-ttu-id="814de-214">ae\ af\ be\ bf \\ \\ ag\ ah\ bg\ bh \\ \\ ce\ cf\ de\ df \\ \\ cg\ ch\ d\dh \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="814de-214">ae\ af\ be\ bf \\\\ ag\ ah\ bg\ bh \\\\ ce\ cf\ de\ df \\\\ cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="814de-215">Uma convenção notacional útil final em torno de produtos tensores é que, para qualquer $v vetorial $ ou $M matriz , $ $v^{\otimes n } $ ou $M^{\otimes } n$ é mão curta para um $ produto de tensor repetido $n- fold repetida.</span><span class="sxs-lookup"><span data-stu-id="814de-215">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="814de-216">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="814de-216">For example:</span></span>

<span data-ttu-id="814de-217">\iniciar{alinhar}</span><span class="sxs-lookup"><span data-stu-id="814de-217">\begin{align}</span></span>
<span data-ttu-id="814de-218">&\start{ bmatrix } 1 \\ \\ 0 bmatrix \end{\\otimes } 1 } = \start{ bmatrix } \\ \\ 1 0 \end{ bmatrix } , \qquad \begin{bmatrix} 1 \\ \\ 0 \end{ bmatrix } {\otimes 2 } = \start{ bmatrix } 1 \\ \\ 0 \\ \\ \\ \\ 0 0 \0 \fim{ bmatrix } , \qquad \begin{bmatrix} 1 \\ \\ -1 bmatrix \end{\otimes } 2 } = \start{ bmatrix } 1 \\ \\ \\ \\ -1 \\ \\ -1 1 \end{ bmatrix } , \\ \\ &\begin{ bmatrix } 0 & \\ \\ 1 & 0 \end{\\\\\\\\\\\\\\\\\\\\\\\otimes bmatrix } 1 } = \start{ bmatrix } & 0 \\ \\ 1 & 1 0 \end{ bmatrix }&&&\begin{bmatrix} &0 \\ \\ & bmatrix } } bmatrix } 10 &\\ \\ 0&1&\\ \\ 0 &1&0&0 \\\\ 1 &0&0&0 \end{bmatrix} 0 .</span><span class="sxs-lookup"><span data-stu-id="814de-218">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\ &\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}    0& 1 \\\\ 1& 0  \end{bmatrix},  \qquad\begin{bmatrix} 0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
<span data-ttu-id="814de-219">\end{align}</span><span class="sxs-lookup"><span data-stu-id="814de-219">\end{align}</span></span>
