---
title: Modelos Quânticos para Sistemas Eletrónicos
description: Saiba como os sistemas eletrónicos moleculares são simulados usando modelação quântica.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.quantummodels
no-loc:
- Q#
- $$v
ms.openlocfilehash: c12ab277f06bed61991a26af96953ccdbf72b642
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856227"
---
# <a name="quantum-models-for-electronic-systems"></a>Modelos Quânticos para Sistemas Eletrónicos

Para simular os sistemas eletrónicos, temos de começar por especificar o Hamiltonian, que pode ser encontrado pelo procedimento de quantificação canónica acima descrito.
Especificamente, para $N_e$ eletrões com momenta $p_i$ (em três dimensões) e $m_e$ e vetores de posição $x_i$ juntamente com núcleos com encargos $Z_k e$ em posições $y_k$, o operador hamiltoniano lê \begin{equação} \hat{H}= \soma \_ {i=1}^{N \_ e} \frac{\hat{p} \_ i^2}{2m \_ e} + \frac {1} {2} \frac \sum \_ {i\ne j} \frac{e^02}{|\hat{x} \_ i - \hat{x} \_ j|} -\sum \_ {i,k} \frac{Z \_ ke^2}{|\hat{x} \_ i - {y} \_ k|} +\frac {1} {2} \sum_{k\ne k'} \frac{Z \_ kZ \_ {k'}e^2}{|y \_ k - y \_ k'|}. \label{eq:Ham} \end{equation} Os operadores momenta $\hat{p} \_ i^2$ podem ser vistos no espaço real como operadores laplacianos, ou seja, $\hat{p} \_ i^2 = -\parcial \_ {x \_ i}^2 - \parcial \_ {y \_ i}^2 - \parcial \_ {z \_ i}2$.
Aqui fizemos a suposição simplificadora de que os núcleos estão em repouso para a molécula.
Isto é conhecido como a aproximação Born-Oppenheimer e tende a ser válido para o espectro de energia de baixa energia de $\hat{H}$ uma vez que a massa de eletrões é de cerca de $1/1836$ a massa de um protão.
Este operador hamiltoniano pode ser facilmente encontrado escrevendo a energia para um sistema de \_ eletrões e$ $N e aplicando o processo de quantificação canónica descrito na [Quantum Dynamics](xref:microsoft.quantum.chemistry.concepts.quantumdynamics).

Para construir a representação da matriz unitária para $e^{-i\hat{H} t}$ precisamos de representar o operador $\hat{H}$ como uma matriz.
Para isso, temos de escolher um sistema de coordenadas ou uma base para representar o problema.
Por exemplo, se $\psi_j$ são um conjunto de funções de base ortogonal para os eletrões $N_e$ então podemos definir a matriz

\start{equação} H \_ {i,j} = \int \_ {-\\infty}\\int{\int \_ {-\int {-\infty}\infty \* \psi^1 \_ \_ \_ \_ \_ \_

Enquanto, em princípio, o operador $\hat{H}$ não é ilimitado e não atua num espaço dimensional finito, a matriz com elementos $H \_ \{ i,j$ \} acima.
Isto significa que os erros são incorridos ao escolher um conjunto de bases demasiado pequeno; no entanto, escolher uma grande base pode tornar a simulação da dinâmica química impraticável.
Por esta razão, escolher uma base que possa representar concisamente o problema é vital para resolver o problema da estrutura electrónica.

Existem muitas bases apropriadas que podem ser usadas e a escolha de uma boa base para se adaptar ao problema é grande parte da arte da química quântica.
Talvez os conjuntos de base mais simples sejam os Slater-Type-Orbitals (STO) que são soluções (ortogonalizadas) para a equação de Schrödinger (ou seja, eigenfunções de $\hat{H}$) para átomos semelhantes a hidrogénio.
Outros conjuntos de bases, como ondas de plano ou orbitais do espaço real, podem ser usados e para mais detalhes remetemos o leitor curioso para o texto padrão ['Teoria Electronic-Structure Molecular'](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572) de Helgaker.

Embora os estados utilizados no modelo acima possam parecer arbitrários, a mecânica quântica coloca restrições aos estados que podem ser encontrados na natureza.
Em especial, todos os estados quânticos eletrónicos válidos devem ser antissimétricos sob troca de rótulos de eletrões.
Ou seja, se $\psi (x_1,x_2)$ fosse a função de onda para o estado quântico conjunto de dois eletrões, então devemos ter que $$ \psi (x_1,x_2)= - \psi (x_2,x_1).
$$ O princípio de exclusão de Pauli que proíbe que dois eletrões estejam no mesmo estado quântico é, fascinantemente, uma consequência direta desta lei que pode ser intuida pelo facto de que se trocarmos dois eletrões localizados na mesma posição $\psi(x_1,x_1)x_1\mapsto \psi (x_1,x_1) \ne-\psi(x_1,x_1)$ ,x_1)=0$.
Assim, os estados iniciais devem ser escolhidos para obedecer a esta propriedade anti-simetria e, por sua vez, nunca ter dois eletrões no mesmo estado ao mesmo tempo.
Isto é crucial para a estrutura electrónica porque proíbe vários eletrões de estarem no mesmo estado, e por sua vez permite que os computadores quânticos utilizem uma única bit quântica para armazenar o número de eletrões num dado estado quântico.

Embora a mecânica quântica possa ser simulada num computador quântico, desconectando estes estados, a maioria dos trabalhos no campo evitou esta abordagem porque requer muitos qubits para armazenar os estados e precisa de um complicado procedimento de preparação do estado para preparar um estado inicial antissimétrico.
Felizmente, porém, estes problemas podem ser desviados ao ver o problema da simulação de uma perspetiva diferente.
