---
title: Representação Jordan-Wigner
description: Conheça a Representação Jordan-Wigner, que mapeia os operadores hamiltonianos para matrizes unitárias que podem ser mais facilmente implementadas num computador quântico.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
no-loc:
- Q#
- $$v
ms.openlocfilehash: 29abb4d2ef11239a58af45bc4eee3bd60d20a6c7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833858"
---
# <a name="jordan-wigner-representation"></a>Representação Jordan-Wigner

Embora os segundos hamiltonianos quantificados sejam convenientemente representados em termos de $a^\dagger$ (criação) e $a$ (aniquilação), estas operações não são operações fundamentais em computadores quânticos.
Como resultado, se quisermos implementá-los num computador quântico, precisamos de mapear os operadores para matrizes unitárias que podem ser implementadas num computador quântico.
A representação Jordan-Wigner dá um desses mapas.
No entanto, outros, como a representação Bravyi-Kitaev, também existem e têm as suas vantagens e desvantagens relativas.
A principal vantagem da representação jordan-wigner é a sua simplicidade.

A representação jordan-wigner é direta para derivar.
Lembre-se que um estado $\ket {0} _j$ implica que a rotação orbital $j$ está vazia e $\ket {1} _j$ implica que está ocupado.
Isto significa que os qubits podem naturalmente armazenar a ocupação de um dado volume orbital de rotação.
Temos então que $a^\dagger_j \ket {0} _j = \ket {1} _j$ e $a^\\dagger_j\ket _j {1} = 0$.
É fácil verificar se \start{align} a^\dagger_j &= \start{bmatrix}0 & 0 \\ \ 1 &0\end{bmatrix}=\frac{X_j - iY_j} {2} , \nonumber \\ \\ a_j &= \start{bmatrix}0 & iY_j 1 \\ \ 0 &0 \end{bmatrix}=\frac{X_j + iY_j} {2} , \end{align} onde $X_j$ e $Y_j$ são os operadores Pauli-$X$ e -$Y$ agindo em qubit $j$.

>[!NOTE]
> No Q# estado de $\ket {0} $ representa o estado de +1 do operador $Z$. Em algumas áreas da física $\ket {0} $ representa o estado terrestre de baixa energia e, portanto, o estado -1 do operador de $Z$. Portanto, algumas fórmulas podem diferir da literatura popular.

Na biblioteca de química usamos $\ket {0} $ para representar um spin-orbital desocupado.
Isto mostra que para um único giro orbital é fácil representar operadores de criação e aniquilação em termos de matrizes unitárias que os computadores quânticos entendem.
Note que enquanto $X$ e $Y$ são unitários $a^\dagger$ e $a$ não são.
Veremos mais tarde que isto não representa um desafio para a simulação.

Um problema que permanece é que enquanto a construção acima funciona para uma única rotação orbital, falha para sistemas com dois ou mais orbitais de rotação.
Como os Fermions são anti-simméticos, sabemos que $a^\dagger_j a^\dagger_k = - a^\dagger_k a^\dagger_j$ para qualquer $j$ e $k$.
No entanto, $$ \esquerda (\frac{X_j - iY_j} {2} \direita)\esquerda(\frac{X_k - iY_k} {2} \direita) = \esquerda{X_k - iY_k} {2} \direita) \esquerda(\frac{X_j - iY_j} {2} \direita).
$$ Por outras palavras, os dois operadores de criação não anti-deslocação, conforme necessário.
Isto pode ser corrigido de uma forma simples, se não deselegante.
A correção é notar que os operadores da Pauli são naturalmente anti-deslocação.
Em particular, $XZ = -ZX$ e $YZ=-ZY$.
Assim, intercalando os operadores $Z$ na construção do operador, podemos emular a correta contra-comutação.
A construção completa é a seguinte: 

\start{align} a^\dagger_1 &= \left(\frac{X-iY} {2} \right)\otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1, \\ \\ a^\dagger_2 &= Z\otimes\left(\frac{X-iY} {2} \direita)\otimes 1\otimes 1\otimes \cdots \otimes 1, \\ \\ a^\dagger_3 &= Z\otimes Z\otimes \left(\frac{X-iY} {2} \right)\otimes 1 \otimes \cdots \otimes 1, \\ \\ &\vdots \\ \\ a^\dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left(\frac{X-iY} {2} \direita). \label{eq:JW} \end{align}

Também é conveniente expressar os operadores de números, $n_j$, em termos de operadores pauli.
Felizmente, as cordas dos operadores de $Z$ (conhecidas como cordas Jordan-Wigner) cancelam depois de uma fazer esta substituição.
Depois de efetuar isto (e recordando que $X_jY_j=iZ_j$), temos \start{equation} n_j = a^\dagger_j a_j = \frac{(1-Z_j)} {2} .
\end{equação}


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a>Construção de Hamiltonians na Representação Jordan-Wigner

Uma vez invocada a representação Jordan-Wigner que traduz o Hamiltonian numa soma de operadores pauli é diretamente para a frente.
Basta substituir cada um dos operadores de $a^\dagger$ e $a$ no Fermionic Hamiltonian pelas cordas dos operadores Pauli acima indicados.
Quando se realiza esta substituição, há apenas cinco classes de termos dentro do Hamiltonian.
Estas cinco classes correspondem às diferentes formas de escolher os $p,q$ e $p,q,r,s$ nos termos de um corpo e dois corpos no Hamiltonian.
Estas cinco classes, para o caso em que $p>q>r>s$ e orbitais de valor real, são

\begin{align} h_{pp}a_p^\dagger a_p &= \sum_p \frac{h_{pp}} {2} (1 - Z_p) \\ \\ h_{pq}(a_p^\dagger a_q + a^\dagger_q a_p) &= \frac{h_{pq}} {2} \left(\prod_{j=q+1}^{p-1} Z_j \right)\left( X_pX_q + Y_pY_q\right) \\ \\ h_{pqqp} n_p n_q &= \frac{h_{pqqp}} {4} \left(1-Z_p - Z_q +Z_pZ_q \right) \\ \\ H_{pqqr} &= \frac{h_{pqqr}} {2} \left(\prod_{j=r+1}^{p-1} Z_j \right)\left( X_pX_r + Y_pY_r\right)\left(\frac{1-Z_q} {2} \right) \\ \\ H_{pqrs} &= \frac{h_{pqrs}} {8} \prod_{j=s+1}^{r-1} Z_j\prod_{k=q+1}^{p-1} Z_k \Big(XXXX - XXYY+XYXY\nonumber \\ \\ &\qquad\qquad\qquad\qquad\qquad+YXXY+YXYX-YYXX\nonumber \\ \\ &\qquad\qquad\qquad\qquad\qquad+XYYX+YYYY\Big) \end{align}

Embora gerar estes hamiltonianos à mão apenas requer a aplicação destas regras de substituição, fazê-lo seria inviável para grandes moléculas que podem consistir em milhões de termos hamiltonianos.
Como alternativa, podemos construir automaticamente uma `JordanWignerEncoding` `FermionHamiltonian` representação do Hamiltonian.

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

Uma vez que os Hamiltonianos são construídos nesta forma, podemos usar uma série de algoritmos de simulação quântica para compilar as dinâmicas geradas por $e^{-iHt}$ numa sequência de portões elementares (dentro de alguma tolerância de erro definível do utilizador).
Discutimos os dois métodos mais populares para a simulação quântica, qubitização e fórmulas Trotter-Suzuki, na documentação algorítmica. Fornecemos implementações para ambos os métodos na biblioteca de simulação Hamiltonian.
