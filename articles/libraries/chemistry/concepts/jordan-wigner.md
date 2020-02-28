---
title: Representação Jordan-Wigner
description: Saiba mais sobre a Representação Jordan-Wigner, que mapeia os operadores hamiltonianos para matrizes unitárias que podem ser mais facilmente implementadas num computador quântico.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
ms.openlocfilehash: 17cb473c6d33e3356d5da886f47985c3828d4d1f
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904524"
---
# <a name="jordan-wigner-representation"></a>Representação Jordan-Wigner

Enquanto os segundos hamiltonianos quantificados são convenientemente representados em termos de $a^\dagger$ (criação) e $a$ (aniquilação), estas operações não são operações fundamentais em computadores quânticos.
Como resultado, se desejarmos que os implemente num computador quântico, precisamos mapear os operadores para matrizes unitárias que podem ser implementadas num computador quântico.
A representação Jordan-Wigner dá um desses mapas.
No entanto, outros, como a representação Bravyi-Kitaev, também existem e têm as suas vantagens e desvantagens relativas.
A principal vantagem da representação Jordan-Wigner é a sua simplicidade.

A representação de Jordan-Wigner é direta para derivar.
Recorde-se que um estado de $\ket{0}_j$ implica que a rotação orbital $j$ está vazia e $\ket{1}_j$ implica que está ocupado.
Isto significa que os qubits podem naturalmente armazenar a ocupação de um dado giro orbital.
Temos então aquele $a^\dagger_j \ket{0}_j = \ket{1}_j$ e $a\\dagger_j \ket{1}_j = 0$.
É fácil verificar se \start{align} a^\dagger_j & 0 \\\ 1 &0 \end{bmatrix}=\frac{X_j - iY_j}{2}, \nonumber\\\\ a_j &= \start{bmatrix}0 & 1 \\\ 0 &0 \end{bmatrix}=\frac{X_j + iY_j}{2}, \end{align} onde $X_j$ e $Y_j$ são os operadores Pauli-$X$ e -$ $Y a agir em qubit$$j.

>[!NOTE]
> Em Q# o $\ket{0}$ $ estado representa o eigenstate +1 do operador $Z$. Em algumas áreas da física $\ket{0}$ representa o estado de terra de baixa energia e, portanto, o -1 eigenstate do operador $Z$. Portanto, algumas fórmulas podem diferir da literatura popular.

Na biblioteca de química usamos $\ket{0}$ para representar um spin-orbital desocupado.
Isto mostra que para uma única rotação orbital é fácil representar os operadores de criação e aniquilação em termos de matrizes unitárias que os computadores quânticos entendem.
Note que enquanto $X$ e $Y$ são unitários $a^\dagger$ e $a$ não são.
Veremos mais tarde que isto não representa um desafio para a simulação.

Um problema que resta é que, enquanto a construção acima funciona para uma única órbita de centrifugação, falha em sistemas com dois ou mais orbitais de centrifugação.
Como os Fermions são antissiméticos, sabemos que $a^\dagger_j a^\dagger_k = - a^\dagger_k a^\dagger_j$ por qualquer $j$ e $k$.
No entanto, $$ \left(\frac{X_j - iY_j}{2}\right)\left(\frac{X_k - iY_k}{2}\right) = \left(\frac{X_k - iY_k}{2}\direita) \frac{X_j - iY_j}{2}\direita).
$$ Por outras palavras, os dois operadores de criação não anti-viagem, conforme necessário.
Isto pode ser corrigido de forma simples, se deselegante.
A correção é notar que os operadores pauli naturalmente anti-deslocação.
Em particular, $XZ = -ZX$ e $YZ=-ZY$.
Assim, intercalando os operadores $Z$ na construção do operador, podemos imitar a anti-comutação correta.
A construção completa é a seguinte: 

\begin{align} a^\dagger_1 &amp;= \left(\frac{X-iY}{2}\right)\otimes 1 \otimes 1 \otimes 1 \otimes \otimes 1,\\\\ a^\dagger_2 &amp{2};\\\\ a^\dagger_3 &= Z\otimes \left(\frac{X-iY}{2}\right)\otimes 1 \otimes \cdots \otimes 1,\\\\ &\vdots\\\\ a^\dagger_N & otimes \left(\frac{X-iY}{2}\direita). \label{eq:JW} \end{align}

Também é conveniente expressar os operadores de números, $n_j$, em termos de operadores Pauli.
Felizmente, as cordas dos operadores $Z$ (conhecidas como cordas Jordan-Wigner) cancelam depois de uma fazer esta substituição.
Depois de efetuar isto (e recordando que $X_jY_j=iZ_j$), temos \start{equation} n_j = a^\dagger_j a_j = \frac{(1-Z_j)}{2}.
\end{equation}


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a>Construção de Hamiltonianos na Representação Jordan-Wigner

Uma vez invocado a representação jordana-wigner traduzindo o Hamiltonian para uma soma de operadores Pauli é direto para a frente.
Basta substituir cada um dos operadores $a^\dagger$ e $a$ no Hamiltonian Fermionic pelas cordas dos operadores pauli acima indicados.
Quando se realiza esta substituição, há apenas cinco classes de termos dentro do Hamiltonian.
Estas cinco aulas correspondem às diferentes formas de escolher os termos $p,q$ e $p,q,r, s$ no corpo e nos termos de dois corpos no Hamiltonian.
Estas cinco classes, para o caso em que $p>q>r>s$ e orbitais de valor real, são

\begin{align} h_{pp}a_p^\dagger a_p &= \sum_p \frac{h_{pp}}{2}(1 - Z_p)\\\\ h_{pq}(a_p^\dagger a_q + a^\dagger_q a_p) &= \frac{h_{pq}}{2}à esquerda (\prod_{j=q+1}{p-1} Z_j \direita)\esquerda( X_pX_q + Y_pY_q\direita)\\\\ h_{pqqp} n_p n_q &= \frac{h_{{pqqp}}{4}à esquerda (1-Z_p - Z_q +Z_pZ_q à direita)\\\\ H_{pqqr} & \frac{h_{pqqr}}{2}à esquerda (\prod_{{j= r+1}^{p-1} Z_j \direita)\esquerda( X_pX_r + Y_pY_r\direita)\esquerda(\frac{1-Z_q}{2}à direita)\\\\ H_{pqrs h_{{{pqrs}}{8}\prod_{j=s+1}{{r-1} Z_j\prod_{k=q+1}^{p-1} Z_k \Big(XXXX - XXYY+XYXY\nonumber\\\\ &\qquad\qquad\qquad\q \\\\quad\qquad\qquad\qquad\qquad\qquad\qquad\qquad\qquad\qquad\qquad+XYYX+YYYY\Big) \end{align}

Embora gerar tais Hamiltonianos à mão apenas requer a aplicação destas regras de substituição, fazê-lo seria inviável para grandes moléculas que podem consistir em milhões de termos hamiltonianos.
Como alternativa, podemos construir automaticamente o `JordanWignerEncoding` dada uma representação `FermionHamiltonian` do Hamiltoniano.

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

Uma vez que os Hamiltonians são construídos desta forma, podemos usar uma série de algoritmos de simulação quântica para compilar a dinâmica gerada por $e^{-iHt}$ numa sequência de portões elementares (dentro de algum utilizador de tolerância de erro definível).
Discutimos os dois métodos mais populares para simulação quântica, qubitização e fórmulas Trotter-Suzuki, na documentação algorítmica. Fornecemos implementações para ambos os métodos na biblioteca de simulação Hamiltonian.
