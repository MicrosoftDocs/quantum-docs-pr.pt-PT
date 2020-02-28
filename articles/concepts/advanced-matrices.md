---
title: Conceitos de matriz avançados
description: Aprenda sobre eigenvectors, eigenvalues e exponenciais matriciais, as ferramentas fundamentais usadas para descrever e simular algoritmos quânticos.
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: a83911e01ad758bbcb7f701000fd58b4f1c91cd2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907584"
---
# <a name="advanced-matrix-concepts"></a>Conceitos matriciais avançados #

Agora estendemos a nossa manipulação de Matrices a [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) e [*Exponencials*](https://en.wikipedia.org/wiki/Matrix_exponential) que formam um conjunto fundamental de ferramentas que precisamos para descrever e implementar algoritmos quânticos.

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues e Eigenvectors ##

Deixe $M$ seja uma matriz quadrada e $v$ seja um vetor que não é o vetor de todos os zeros (isto é, o vetor com todas as entradas iguais a $0$).

Dizemos que $v$ é um [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) de $M$ se $Mv = cv$ para algum número $c$. Dizemos $c$ é o [*valor eigen*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) correspondente ao eigenvector $v$. Em geral, uma matriz $M$ pode transformar um vetor em qualquer outro vetor, mas um eigenvector é especial porque é deixado inalterado exceto para ser multiplicado por um número. Note que se $v$ é um eigenvector com eigenvalue $c$, então $av$ é também um eigenvector (para qualquer $a zero$) com o mesmo eigenvalue.

Por exemplo, para a matriz de identidade, cada vetor $v$ é um eigenvector com eigenvalue $1$1$.

Como outro exemplo, considere uma [*matriz diagonal*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ que só tem entradas não zero na diagonal:

$$ \start{bmatrix} d_1 & 0 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.
$$

Os vetores

$$\start{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \start{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} e \start{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$

são eigenvectores desta matriz com valores eigen$d_1$, $d_2$, e $d_3$, respectivamente. Se $d_1$, $d_2$, e $d_3$ são números distintos, então estes vetores (e seus múltiplos) são os únicos eigenvectores da matriz $D$. Em geral, para uma matriz diagonal é fácil ler os valores eigenvectores. Os valores eigen são todos os números que aparecem na diagonal, e os respetivos eigenvectors são os vetores unitários com uma entrada igual a $1$ e as restantes entradas iguais a $0$.

Note no exemplo acima que os eigenvectors de $D$ formam uma base para vetores de $3$dimensional. Uma base é um conjunto de vetores de tal forma que qualquer vetor pode ser escrito como uma combinação linear deles. Mais explicitamente, $v_1$, $v_2$e $v_3$ formam uma base se qualquer vetor $v$ pode ser escrito como $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ para alguns números $a_1$, $a_2$e $a_3$.

Lembre-se que uma matriz hermitiana (também chamada auto-adjoint) é uma complexa matriz quadrada igual ao seu próprio conjugado complexo, enquanto uma matriz unitária é uma matriz quadrada complexa cujo inverso é igual ao seu complexo conjugado.
Para matrizes hermitárias e unitárias, que são essencialmente as únicas matrizes encontradas na computação quântica, há um resultado geral conhecido como [*teorema espectral*](https://en.wikipedia.org/wiki/Spectral_theorem), que afirma o seguinte: Para qualquer matriz hermitária ou unitária $M$, existe um $U unitário de tal forma que $M=U^\dagger U$ para alguma matriz diagonal $D$. Além disso, as entradas diagonais de $D$ serão os valores eigen de $M$.

Já sabemos calcular os valores eigenvectores de uma matriz diagonal $D$. Usando este teorema sabemos que se $v$ for um eigenvector de $D$ com eigenvalue $c$, ou seja, $Dv = cv$, então $U^\dagger v$ será um eigenvector de $M$ com eigenvalue $c$. Isto é porque

$$M(U^\dagger v) = U^\dagger D U (U^\dagger v) =U^\dagger D (U^\dagger) v = U^\dagger D = c U^\dagger v.$$

## <a name="matrix-exponentials"></a>Exponenciais matriciais
Uma [*matriz exponencial*](https://en.wikipedia.org/wiki/Matrix_exponential) também pode ser definida na analogia exata à função exponencial.  A matriz exponencial de uma matriz $A$ pode ser expressa como

$$ e^A=\boldone + A + \frac{A^2}{2!} +\frac{A^3}{3!} +\cdots $$

Isto é importante porque a evolução do tempo mecânico quântico é descrita por uma matriz unitária da forma $e^{iB}$ para a matriz hermitiana $B$.  Por esta razão, a realização de matrizes exponenciais é uma parte fundamental da computação quântica e, como tal, Q# oferece rotinas intrínsecas para descrever estas operações.
Existem muitas maneiras, na prática, calcular uma matriz exponencial num computador clássico, e em geral, aproximando-se numericamente tal exponencial está repleta de perigos.  Veja [*Cleve Moler e Charles Van Loan. "Dezanove maneiras duvidosas de calcular o exponencial de uma matriz." Análise sIAM 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) para mais informações sobre os desafios envolvidos.

A maneira mais fácil de entender como calcular o exponencial de uma matriz é através dos valores eigenvectores dessa matriz.  Especificamente, o teorema espectral discutido acima diz que para cada matriz hermitária ou unitária $A$ existe uma matriz unitária $U$ e uma matriz diagonal $D$ tal que $A=U^\dagger D U$.  Devido às propriedades da unitaridade temos que $A^2 = U^\dagger D^2 U$ e similarmente para qualquer poder $p$ $A^p = U^\dagger D^p U$.  Se substituirmos isto na definição de operador do operador exponencial obtemos:

$$ e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!} +\cdots \right)U= U^\dagger \start{bmatrix}\exp(D_{11}) e 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\\cdots&\exp(D_{NN}

Por outras palavras, se te transformares na base da matriz $A$ então calcular a matriz exponencial é equivalente à computação do exponencial comum dos valores eigen da matriz.  Como muitas operações na computação quântica envolvem executar a matriz exponencial, este truque de se transformar na base eigende de uma matriz para simplificar o desempenho exponencial do operador aparece frequentemente e é a base por trás de muitos algoritmos quânticos como Métodos de simulação quântica ao estilo Trotter-Suzuki discutidos mais tarde neste guia.

Outra propriedade útil é se $B$ é unitário e Hermitiano, ou seja, $B=B^{-1}=B^\dagger$ então $B^2=\boldone$. Ao aplicar esta regra à expansão acima da matriz exponencial e ao agrupar os termos $\boldone$ e $B$ juntos, pode ver-se que por qualquer valor real $x$ a identidade

$$e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$


segura. Este truque é especialmente útil porque permite raciocinar sobre as ações que os exponenciais matriciais têm, mesmo que a dimensão de $B$ seja exponencialmente grande, para o caso especial quando $B$ é unitário e hermitiano.
