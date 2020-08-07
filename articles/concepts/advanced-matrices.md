---
<span data-ttu-id="4f572-101">título: Descrição de conceitos de matriz avançada: Saiba mais sobre eigenvectors, eigenvalues e exponencials da matriz, as ferramentas fundamentais usadas para descrever e simular algoritmos quânticos.</span><span class="sxs-lookup"><span data-stu-id="4f572-101">title: Advanced matrix concepts description: Learn about eigenvectors, eigenvalues, and matrix exponentials, the fundamental tools used to describe and simulate quantum algorithms.</span></span>
<span data-ttu-id="4f572-102">autor: QuantumWriter uid: microsoft.quantum.concepts.matrix-advanced ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span><span class="sxs-lookup"><span data-stu-id="4f572-102">author: QuantumWriter uid: microsoft.quantum.concepts.matrix-advanced ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="4f572-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="4f572-103">"Q#"</span></span>
- <span data-ttu-id="4f572-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="4f572-104">"$$v"</span></span>
- <span data-ttu-id="4f572-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="4f572-105">"$$"</span></span>
- <span data-ttu-id="4f572-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="4f572-106">"$$"</span></span>
- <span data-ttu-id="4f572-107">"$"</span><span class="sxs-lookup"><span data-stu-id="4f572-107">"$"</span></span>
- <span data-ttu-id="4f572-108">"$"</span><span class="sxs-lookup"><span data-stu-id="4f572-108">"$"</span></span>
- <span data-ttu-id="4f572-109">"$"</span><span class="sxs-lookup"><span data-stu-id="4f572-109">"$"</span></span>
- <span data-ttu-id="4f572-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="4f572-110">"$$"</span></span>
- <span data-ttu-id="4f572-111">"$$$"</span><span class="sxs-lookup"><span data-stu-id="4f572-111">"$$$"</span></span>
- <span data-ttu-id="4f572-112">"$$$"</span><span class="sxs-lookup"><span data-stu-id="4f572-112">"$$$"</span></span>
- <span data-ttu-id="4f572-113">"$$$"</span><span class="sxs-lookup"><span data-stu-id="4f572-113">"$$$"</span></span>
- <span data-ttu-id="4f572-114">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="4f572-114">"\cdots"</span></span>
- <span data-ttu-id="4f572-115">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="4f572-115">"bmatrix"</span></span>
- <span data-ttu-id="4f572-116">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="4f572-116">"\ddots"</span></span>
- <span data-ttu-id="4f572-117">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="4f572-117">"\equiv"</span></span>
- <span data-ttu-id="4f572-118">"\sum"</span><span class="sxs-lookup"><span data-stu-id="4f572-118">"\sum"</span></span>
- <span data-ttu-id="4f572-119">"\begin"</span><span class="sxs-lookup"><span data-stu-id="4f572-119">"\begin"</span></span>
- <span data-ttu-id="4f572-120">"\end"</span><span class="sxs-lookup"><span data-stu-id="4f572-120">"\end"</span></span>
- <span data-ttu-id="4f572-121">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="4f572-121">"\sqrt"</span></span>
- <span data-ttu-id="4f572-122">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="4f572-122">"\otimes"</span></span>
- <span data-ttu-id="4f572-123">"{"</span><span class="sxs-lookup"><span data-stu-id="4f572-123">"{"</span></span>
- <span data-ttu-id="4f572-124">"}"</span><span class="sxs-lookup"><span data-stu-id="4f572-124">"}"</span></span>
- <span data-ttu-id="4f572-125">"\text"</span><span class="sxs-lookup"><span data-stu-id="4f572-125">"\text"</span></span>
- <span data-ttu-id="4f572-126">"\phi"</span><span class="sxs-lookup"><span data-stu-id="4f572-126">"\phi"</span></span>
- <span data-ttu-id="4f572-127">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="4f572-127">"\kappa"</span></span>
- <span data-ttu-id="4f572-128">"\psi"</span><span class="sxs-lookup"><span data-stu-id="4f572-128">"\psi"</span></span>
- <span data-ttu-id="4f572-129">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="4f572-129">"\alpha"</span></span>
- <span data-ttu-id="4f572-130">"\beta"</span><span class="sxs-lookup"><span data-stu-id="4f572-130">"\beta"</span></span>
- <span data-ttu-id="4f572-131">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="4f572-131">"\gamma"</span></span>
- <span data-ttu-id="4f572-132">"\delta"</span><span class="sxs-lookup"><span data-stu-id="4f572-132">"\delta"</span></span>
- <span data-ttu-id="4f572-133">"\omega"</span><span class="sxs-lookup"><span data-stu-id="4f572-133">"\omega"</span></span>
- <span data-ttu-id="4f572-134">"\bra"</span><span class="sxs-lookup"><span data-stu-id="4f572-134">"\bra"</span></span>
- <span data-ttu-id="4f572-135">"\ket"</span><span class="sxs-lookup"><span data-stu-id="4f572-135">"\ket"</span></span>
- <span data-ttu-id="4f572-136">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="4f572-136">"\boldone"</span></span>
- <span data-ttu-id="4f572-137">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="4f572-137">"\\\\"</span></span>
- <span data-ttu-id="4f572-138">"\\"</span><span class="sxs-lookup"><span data-stu-id="4f572-138">"\\"</span></span>
- <span data-ttu-id="4f572-139">"="</span><span class="sxs-lookup"><span data-stu-id="4f572-139">"="</span></span>
- <span data-ttu-id="4f572-140">"\frac"</span><span class="sxs-lookup"><span data-stu-id="4f572-140">"\frac"</span></span>
- <span data-ttu-id="4f572-141">"\text"</span><span class="sxs-lookup"><span data-stu-id="4f572-141">"\text"</span></span>
- <span data-ttu-id="4f572-142">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="4f572-142">"\mapsto"</span></span>
- <span data-ttu-id="4f572-143">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="4f572-143">"\dagger"</span></span>
- <span data-ttu-id="4f572-144">"\to"</span><span class="sxs-lookup"><span data-stu-id="4f572-144">"\to"</span></span>
- <span data-ttu-id="4f572-145">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="4f572-145">"\begin{cases}"</span></span>
- <span data-ttu-id="4f572-146">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="4f572-146">"\end{cases}"</span></span>
- <span data-ttu-id="4f572-147">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="4f572-147">"\operatorname"</span></span>
- <span data-ttu-id="4f572-148">"\braket"</span><span class="sxs-lookup"><span data-stu-id="4f572-148">"\braket"</span></span>
- <span data-ttu-id="4f572-149">"\id"</span><span class="sxs-lookup"><span data-stu-id="4f572-149">"\id"</span></span>
- <span data-ttu-id="4f572-150">"\expect"</span><span class="sxs-lookup"><span data-stu-id="4f572-150">"\expect"</span></span>
- <span data-ttu-id="4f572-151">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="4f572-151">"\defeq"</span></span>
- <span data-ttu-id="4f572-152">"\variance"</span><span class="sxs-lookup"><span data-stu-id="4f572-152">"\variance"</span></span>
- <span data-ttu-id="4f572-153">"\dd"</span><span class="sxs-lookup"><span data-stu-id="4f572-153">"\dd"</span></span>
- <span data-ttu-id="4f572-154">"&"</span><span class="sxs-lookup"><span data-stu-id="4f572-154">"&"</span></span>
- <span data-ttu-id="4f572-155">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="4f572-155">"\begin{align}"</span></span>
- <span data-ttu-id="4f572-156">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="4f572-156">"\end{align}"</span></span>
- <span data-ttu-id="4f572-157">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="4f572-157">"\Lambda"</span></span>
- <span data-ttu-id="4f572-158">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="4f572-158">"\lambda"</span></span>
- <span data-ttu-id="4f572-159">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="4f572-159">"\Omega"</span></span>
- <span data-ttu-id="4f572-160">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="4f572-160">"\mathrm"</span></span>
- <span data-ttu-id="4f572-161">"\left"</span><span class="sxs-lookup"><span data-stu-id="4f572-161">"\left"</span></span>
- <span data-ttu-id="4f572-162">"\right"</span><span class="sxs-lookup"><span data-stu-id="4f572-162">"\right"</span></span>
- <span data-ttu-id="4f572-163">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="4f572-163">"\qquad"</span></span>
- <span data-ttu-id="4f572-164">"\times"</span><span class="sxs-lookup"><span data-stu-id="4f572-164">"\times"</span></span>
- <span data-ttu-id="4f572-165">"\big"</span><span class="sxs-lookup"><span data-stu-id="4f572-165">"\big"</span></span>
- <span data-ttu-id="4f572-166">"\langle"</span><span class="sxs-lookup"><span data-stu-id="4f572-166">"\langle"</span></span>
- <span data-ttu-id="4f572-167">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="4f572-167">"\rangle"</span></span>
- <span data-ttu-id="4f572-168">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="4f572-168">"\bigg"</span></span>
- <span data-ttu-id="4f572-169">"\Big"</span><span class="sxs-lookup"><span data-stu-id="4f572-169">"\Big"</span></span>
- <span data-ttu-id="4f572-170">"|"</span><span class="sxs-lookup"><span data-stu-id="4f572-170">"|"</span></span>
- <span data-ttu-id="4f572-171">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="4f572-171">"\mathbb"</span></span>
- <span data-ttu-id="4f572-172">"\vec"</span><span class="sxs-lookup"><span data-stu-id="4f572-172">"\vec"</span></span>
- <span data-ttu-id="4f572-173">"\in"</span><span class="sxs-lookup"><span data-stu-id="4f572-173">"\in"</span></span>
- <span data-ttu-id="4f572-174">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="4f572-174">"\texttt"</span></span>
- <span data-ttu-id="4f572-175">"\ne"</span><span class="sxs-lookup"><span data-stu-id="4f572-175">"\ne"</span></span>
- <span data-ttu-id="4f572-176">"<"</span><span class="sxs-lookup"><span data-stu-id="4f572-176">"<"</span></span>
- <span data-ttu-id="4f572-177">">"</span><span class="sxs-lookup"><span data-stu-id="4f572-177">">"</span></span>
- <span data-ttu-id="4f572-178">"\leq"</span><span class="sxs-lookup"><span data-stu-id="4f572-178">"\leq"</span></span>
- <span data-ttu-id="4f572-179">"\geq"</span><span class="sxs-lookup"><span data-stu-id="4f572-179">"\geq"</span></span>
- <span data-ttu-id="4f572-180">"~~"</span><span class="sxs-lookup"><span data-stu-id="4f572-180">"~~"</span></span>
- <span data-ttu-id="4f572-181">"~"</span><span class="sxs-lookup"><span data-stu-id="4f572-181">"~"</span></span>
- <span data-ttu-id="4f572-182">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="4f572-182">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="4f572-183">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="4f572-183">"\end{bmatrix}"</span></span>
- <span data-ttu-id="4f572-184">"\_"</span><span class="sxs-lookup"><span data-stu-id="4f572-184">"\_"</span></span>

---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="4f572-185">Conceitos de matriz avançada</span><span class="sxs-lookup"><span data-stu-id="4f572-185">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="4f572-186">Estendemos agora a nossa manipulação de Matrizes a [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) e [*Exponencials*](https://en.wikipedia.org/wiki/Matrix_exponential) que formam um conjunto fundamental de ferramentas que precisamos para descrever e implementar algoritmos quânticos.</span><span class="sxs-lookup"><span data-stu-id="4f572-186">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="4f572-187">Eigenvalues e Eigenvectors</span><span class="sxs-lookup"><span data-stu-id="4f572-187">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="4f572-188">Deixe $ M ser uma matriz quadrada e v ser um $ $ $ vetor que não é o vetor de todos os zeros (ou seja, o vetor com todas as entradas iguais a $ 0 $ ).</span><span class="sxs-lookup"><span data-stu-id="4f572-188">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="4f572-189">Dizemos que $ v $ é um [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) de $ M se $ $ Mv cv para algum número = $ c $ $ .</span><span class="sxs-lookup"><span data-stu-id="4f572-189">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="4f572-190">Dizemos que $ c $ é o [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) correspondente ao eigenvector $ v $ .</span><span class="sxs-lookup"><span data-stu-id="4f572-190">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="4f572-191">Em geral, uma matriz $ M pode transformar um $ vetor em qualquer outro vetor, mas um eigenvector é especial porque é deixado inalterado exceto por ser multiplicado por um número.</span><span class="sxs-lookup"><span data-stu-id="4f572-191">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="4f572-192">Note que se $ v $ é um eigenvector com eigenvalue $ $ c, então $ av é também um $ eigenvector (para qualquer não zero a $ ) com o mesmo $ eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="4f572-192">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="4f572-193">Por exemplo, para a matriz de identidade, cada vetor $ v $ é um eigenvector com eigenvalue $ 1 $ .</span><span class="sxs-lookup"><span data-stu-id="4f572-193">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="4f572-194">Como outro exemplo, considere uma [*matriz diagonal*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ D que só tem entradas $ nãozero na diagonal:</span><span class="sxs-lookup"><span data-stu-id="4f572-194">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

$$
\begin{bmatrix}
<span data-ttu-id="4f572-195">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ & 0 0 & d_3 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="4f572-195">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="4f572-196">Os vetores</span><span class="sxs-lookup"><span data-stu-id="4f572-196">The vectors</span></span>

<span data-ttu-id="4f572-197">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} , \begin{bmatrix} 0 \\\\ 1 \\\\ 0 e \end{bmatrix} \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="4f572-197">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="4f572-198">são os eigenvectors desta matriz com d_1 de eigenvalues, $ $ d_2 e $ $ $ $ d_3, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="4f572-198">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="4f572-199">Se $ d_1 , d_2 , e d_3 são $ $ $ $ $ números distintos, então estes vetores (e seus múltiplos) são os únicos eigenvectors da matriz $ D $ . Em geral, para uma matriz diagonal é fácil ler os eigenvalues e os eigenvectors.</span><span class="sxs-lookup"><span data-stu-id="4f572-199">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$. In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="4f572-200">Os eigenvalues são todos os números que aparecem na diagonal, e os respetivos eigenvectors são os vetores unitários com uma entrada igual a $ 1 $ e as restantes entradas iguais a $ 0 $ .</span><span class="sxs-lookup"><span data-stu-id="4f572-200">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="4f572-201">Note no exemplo acima que os eigenvectors de $ D $ formam uma base para $ $ vetores 3-dimensional.</span><span class="sxs-lookup"><span data-stu-id="4f572-201">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="4f572-202">Uma base é um conjunto de vetores de modo que qualquer vetor pode ser escrito como uma combinação linear deles.</span><span class="sxs-lookup"><span data-stu-id="4f572-202">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="4f572-203">Mais explicitamente, $ $ v_1, $ $ v_2, e $ v_3 $ formam uma base se qualquer vetor $ v pode ser escrito como v a_1 v_1 + a_2 v_2 + a_3 v_3 para $ $ = $ alguns números $ a_1 , a_2 , e $ $ $ $ $ a_3.</span><span class="sxs-lookup"><span data-stu-id="4f572-203">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="4f572-204">Recorde-se que uma matriz hermitiana (também chamada de auto-adjacente) é uma matriz quadrada complexa igual à sua própria transposição conjugada complexa, enquanto uma matriz unitária é uma matriz quadrada complexa cujo inverso é igual ao seu transposto conjugado adjacente ou complexo.</span><span class="sxs-lookup"><span data-stu-id="4f572-204">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate transpose, while a unitary matrix is a complex square matrix whose inverse is equal to its adjoint or complex conjugate transpose.</span></span>
<span data-ttu-id="4f572-205">Para as matrizes hermitianas e unitárias, que são essencialmente as únicas matrizes encontradas na computação quântica, existe um resultado geral conhecido como [*teorema espectral,*](https://en.wikipedia.org/wiki/Spectral_theorem)que afirma o seguinte: Para qualquer matriz eremita ou unitária $ $ M, existe um U unitário $ tal que M $ $ = U^ D U para alguma \dagger matriz $ diagonal $ D $ . Além disso, as entradas diagonais de $ D $ serão os valores de eigenvalues de $ M $ .</span><span class="sxs-lookup"><span data-stu-id="4f572-205">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$. Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="4f572-206">Já sabemos calcular os eigenvalues e os eigenvectors de uma matriz diagonal $ D $ . Usando este teorema sabemos que se $ v $ é um eigenvector de $ D com $ eigenvalue $ c , isto $ é, Dv cv , $ = $ então $ U^ v será um \dagger $ eigenvector de $ M com $ eigenvalue $ c $ .</span><span class="sxs-lookup"><span data-stu-id="4f572-206">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$. Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="4f572-207">Isto é porque</span><span class="sxs-lookup"><span data-stu-id="4f572-207">This is because</span></span>

<span data-ttu-id="4f572-208">$$M(U^ \dagger v) = U^ \dagger D U (U^ \dagger v) = U^ D \dagger (U U^ \dagger ) v = U^ D v c \dagger = U^ \dagger v.$$</span><span class="sxs-lookup"><span data-stu-id="4f572-208">$$M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="4f572-209">Exponencial da Matriz</span><span class="sxs-lookup"><span data-stu-id="4f572-209">Matrix Exponentials</span></span>
<span data-ttu-id="4f572-210">Uma [*matriz exponencial*](https://en.wikipedia.org/wiki/Matrix_exponential) também pode ser definida em analogia exata à função exponencial.</span><span class="sxs-lookup"><span data-stu-id="4f572-210">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="4f572-211">A matriz exponencial de uma matriz $ A pode ser expressa $ como</span><span class="sxs-lookup"><span data-stu-id="4f572-211">The matrix exponential of a matrix $A$ can be expressed as</span></span>

$$
<span data-ttu-id="4f572-212">e^A = \boldone + A + \frac { A^2 } { 2! } + \frac { A^3 } { 3!}+\cdots</span><span class="sxs-lookup"><span data-stu-id="4f572-212">e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots</span></span>
$$

<span data-ttu-id="4f572-213">Isto é importante porque a evolução do tempo mecânico quântico é descrita por uma matriz unitária da forma $ e^ { iB } $ para a matriz hermitiana $ B $ .  Por esta razão, a realização de exponencials da matriz é uma parte fundamental da computação quântica e, como tal, Q# oferece rotinas intrínsecas para descrever estas operações.</span><span class="sxs-lookup"><span data-stu-id="4f572-213">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.  For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="4f572-214">Existem muitas maneiras na prática de calcular uma matriz exponencial em um computador clássico, e em geral numericamente aproximando tal exponencial está cheio de perigo.</span><span class="sxs-lookup"><span data-stu-id="4f572-214">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="4f572-215">Ver [*Cleve Moler e Charles Van Loan. "Dezanove formas duvidosas de calcular o exponencial de uma matriz." Revisão do SIAM 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) para mais informações sobre os desafios envolvidos.</span><span class="sxs-lookup"><span data-stu-id="4f572-215">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="4f572-216">A maneira mais fácil de entender como calcular o exponencial de uma matriz é através dos eigenvalues e eigenvectors dessa matriz.</span><span class="sxs-lookup"><span data-stu-id="4f572-216">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="4f572-217">Especificamente, o teorema espectral discutido acima diz que para cada matriz hermitiana ou unitária $ A existe uma matriz $ unitária U e uma matriz $ $ diagonal $ D tal que A $ $ = U^ D U \dagger $ .  Devido às propriedades da unitaridade temos que $ A^2 = U^ \dagger D^2 U $ e similarmente para qualquer potência $ p $ $ A^p = U^ \dagger D^p U $ .  Se substituirmos isto na definição do operador exponencial, obtemos:</span><span class="sxs-lookup"><span data-stu-id="4f572-217">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

$$
<span data-ttu-id="4f572-218">e^A = U^ \dagger \left \boldone (+D + \frac { D^2 } { 2! } + \cdots \right ) U = U^ \dagger \begin{bmatrix} \exp(D_ { 11 } ) & 0 & \cdots & 0 \\\\ 0 & \exp(D_ { 22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp(D_ { NN } ) \end{bmatrix} U.$$</span><span class="sxs-lookup"><span data-stu-id="4f572-218">e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="4f572-219">Por outras palavras, se se transformar na eigenbasis da matriz $ $ A, então a computação da matriz exponencial equivale a computação do exponencial comum dos valores eigenvalues da matriz.</span><span class="sxs-lookup"><span data-stu-id="4f572-219">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="4f572-220">Como muitas operações na computação quântica envolvem a realização de exponencials da matriz, este truque de transformar-se na eigenbasis de uma matriz para simplificar a execução exponencial do operador aparece frequentemente e é a base por trás de muitos algoritmos quânticos, como métodos de simulação quântica ao estilo Trotter-Suzuki discutidos mais tarde neste guia.</span><span class="sxs-lookup"><span data-stu-id="4f572-220">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="4f572-221">Outra propriedade útil é se $ B $ é simultaneamente unitário e hermitiano, ou seja, $ B = B^ { -1 } = B^ \dagger $ e $ B^2 = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="4f572-221">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="4f572-222">Aplicando esta regra à expansão acima da matriz exponencial e agrupondo os $ \boldone $ termos e os termos $ B em $ conjunto, pode ver-se que por qualquer valor real $ x a $ identidade</span><span class="sxs-lookup"><span data-stu-id="4f572-222">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

<span data-ttu-id="4f572-223">$$e^ { iBx } = \boldone \cos (x)+ iB\sin(x)$$</span><span class="sxs-lookup"><span data-stu-id="4f572-223">$$e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="4f572-224">mantém.</span><span class="sxs-lookup"><span data-stu-id="4f572-224">holds.</span></span> <span data-ttu-id="4f572-225">Este truque é especialmente útil porque permite raciocinar sobre as ações que os exponenciales da matriz têm, mesmo que a dimensão de $ B $ seja exponencialmente grande, para o caso especial quando $ B é $ simultaneamente unitário e eremita.</span><span class="sxs-lookup"><span data-stu-id="4f572-225">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
