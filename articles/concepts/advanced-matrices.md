---
title: Conceitos de matriz avançada | Microsoft Docs
description: Conceitos de matriz avançada
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f87b3bcd19d2f98fea2a9724a280781a78c4cbb9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183765"
---
# <a name="advanced-matrix-concepts"></a>Conceitos de matriz avançada #

Agora, estendemos nossa manipulação de matrizes para [*eigenvalues, eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) e [*exponencials*](https://en.wikipedia.org/wiki/Matrix_exponential) que formam um conjunto fundamental de ferramentas que precisamos para descrever e implementar os algoritmos Quantum.

## <a name="eigenvalues-and-eigenvectors"></a>Eigenvalues e eigenvectors ##

Deixe $M $ seja uma matriz quadrada e $v $ seja um vetor que não seja o vetor todos os zeros (ou seja, o vetor com todas as entradas iguais a $0 $).

Dizemos $v $ é um [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) de $M $ If $MV = CV $ para um número $c $. Dizemos $c $ é o [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) correspondente ao eigenvector $v $. Em geral, uma matriz $M $ pode transformar um vetor em qualquer outro vetor, mas um eigenvector é especial porque é deixado inalterado, exceto por ser multiplicado por um número. Observe que, se $v $ for um eigenvector com eigenvalue $c $, $av $ também será um eigenvector (para qualquer $a $ diferente de zero) com o mesmo eigenvalue.

Por exemplo, para a matriz de identidade, cada vetor $v $ é um eigenvector com eigenvalue $1 $.

Como outro exemplo, considere uma [*matriz diagonal*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D $, que tem apenas entradas diferentes de zero na diagonal:

$ $ \begin{bmatrix} d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.
$$

Os vetores

$ $ \begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0 \ fim {bmatrix} e \begin{bmatrix}0 \\\\ 0 \\\\ 1 \ encerrar {bmatrix} $ $

são eigenvectors dessa matriz com eigenvalues $d _1 $, $d _2 $ e $d _3 $, respectivamente. Se $d _1 $, $d _2 $ e $d _3 $ forem números distintos, esses vetores (e seus múltiplos) serão os únicos eigenvectors da matriz $D $. Em geral, para uma matriz diagonal, é fácil ler eigenvalues e eigenvectors. Eigenvalues são todos os números que aparecem na diagonal, e seus respectivos eigenvectors são os vetores de unidade com uma entrada igual a $1 $ e as entradas restantes iguais a $0 $.

Observe no exemplo acima que o eigenvectors de $D $ forma uma base para vetores $3 $-dimensional. Uma base é um conjunto de vetores, de modo que qualquer vetor pode ser escrito como uma combinação linear deles. Mais explicitamente, $v _1 $, $v _2 $ e $v _3 $ formam uma base se qualquer vetor $v $ puder ser escrito como $v = a_1 v_1 + a_2 v_2 + a_3 v_3 $ para alguns números $a _1 $, $a _2 $ e $a _3 $.

Lembre-se de que uma matriz Hermitian (também chamada de auto-adjacente) é uma matriz quadrada complexa igual à sua própria conjugada complexa, enquanto uma matriz unitário é uma matriz quadrada complexa cujo inverso é igual ao seu conjugado complexo.
Para matrizes Hermitian e unitários, que são essencialmente as únicas matrizes encontradas na computação Quantum, há um resultado geral conhecido como [*Spectral teorema*](https://en.wikipedia.org/wiki/Spectral_theorem), que declara o seguinte: para qualquer matriz Hermitian ou unitário $M $, existe um o unitário $U $ de forma que $M = U ^ \dagger D U $ para alguma matriz diagonal $D $. Além disso, as entradas diagonais de $D $ serão o eigenvalues de $M $.

Já sabemos como calcular o eigenvalues e o eigenvectors de uma matriz diagonal $D $. Usando este teorema, sabemos que, se $v $ for um eigenvector de $D $ com eigenvalue $c $, ou seja, $Dv = CV $, $U ^ \dagger v $ será um eigenvector de $M $ com eigenvalue $c $. Isso ocorre porque

$ $M (U ^ \dagger v) = U ^ \dagger D U (U ^ \dagger v) = U ^ \dagger D (U U ^ \dagger) v = U ^ \dagger D v = c U ^ \dagger v. $ $

## <a name="matrix-exponentials"></a>Exponenciais de matriz
Um [*exponencial de matriz*](https://en.wikipedia.org/wiki/Matrix_exponential) também pode ser definido de acordo com a analogia exata com a função exponencial.  O exponencial de matriz de uma matriz $A $ pode ser expresso como

$ $ e ^ A = \boldone + A + \frac{A ^ 2} {2!} + \frac{A ^ 3} {3!} + \cdots $ $

Isso é importante porque a evolução do tempo mecânico da Quantum é descrita por uma matriz unitário do formulário $e ^ {iB} $ para a matriz Hermitian $B $.  Por esse motivo, a execução de exponencials de matriz é uma parte fundamental da computação Quantum e, como tal, Q # oferece rotinas intrínsecas para descrever essas operações.
Há muitas maneiras de fazer a computação de um exponencial de matriz em um computador clássico e, em geral, o aproximar de forma numérica como tal exponencial é muito perigoso com Peril.  Confira [*Cleve Moler e Charles Van empréstimo. "Dezenove duvidosa maneiras de computar o exponencial de uma matriz". SIAM revisar 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) para obter mais informações sobre os desafios envolvidos.

A maneira mais fácil de entender como computar o exponencial de uma matriz é por meio de eigenvalues e eigenvectors dessa matriz.  Especificamente, o Spectral teorema discutido acima diz que para cada matriz Hermitian ou unitário $A $ existe uma matriz unitário $U $ e uma matriz diagonal $D $ de forma que $A = U ^ \dagger D U $.  Devido às propriedades de unitarity, temos isso $A ^ 2 = U ^ \dagger D ^ 2 U $ e, da mesma forma, para qualquer energia $p $ $A ^ p = U ^ \dagger D ^ p U $.  Se substituímos isso na definição de operador do exponencial de operador, obtemos:

$ $ e ^ A = U ^ \dagger \left (\boldone + D + \frac{D ^ 2} {2!} + \cdots \right) U = U ^ \dagger \begin{bmatrix}\exp (D_{11}) & 0 & \cdots & 0\\\\ 0 & \exp (D_{22}) & \cdots & 0\\\\ \vdots & \vdots & \ddots & \vdots\\\\ 0 & 0 & \cdots & \exp (D_ {NN}) \end{bmatrix} U. $ $

Em outras palavras, se você transformar para o eigenbasis da matriz $A $, a computação do exponencial de matriz será equivalente a computar o exponencial comum do eigenvalues da matriz.  Como muitas operações na computação Quantum envolvem a execução de exponenciais de matriz, esse truque de transformar em eigenbasis de uma matriz para simplificar a execução do operador exponencial é exibido com frequência e é a base por trás de muitos algoritmos de Quantum, como Trotter – métodos de simulação do Quantum com estilo Suzuki discutidos posteriormente neste guia.

Outra propriedade útil é se $B $ for unitário e Hermitian, ou seja, $B = B ^{-1}= B ^ \dagger $, então $B ^ 2 = \boldone $. Ao aplicar essa regra à expansão acima do exponencial de matriz e ao agrupar o $ \boldone $ e os termos de $B $ juntos, ele pode ver que, para qualquer valor real $x $ a identidade

$ $e ^ {iBx} = \boldone \cos (x) + iB\sin (x) $ $


realiza. Esse truque é especialmente útil, pois ele permite que o motivo da matriz de ações exponencials tenha, mesmo se a dimensão de $B $ for exponencialmente grande, para o caso especial quando $B $ for unitário e Hermitian.
