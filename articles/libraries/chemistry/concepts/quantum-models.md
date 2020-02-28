---
title: Modelos Quânticos para Sistemas Eletrónicos
description: Saiba como os sistemas eletrónicos moleculares são simulados usando modelação quântica.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantummodels
ms.openlocfilehash: 9f9fc37944dd76026c2641d9cdf126e71053a598
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904422"
---
# <a name="quantum-models-for-electronic-systems"></a>Modelos Quânticos para Sistemas Eletrónicos

Para simular sistemas eletrónicos, temos de começar por especificar o Hamiltoniano, que pode ser encontrado pelo procedimento de quantificação canónica acima descrito.
Especificamente, para eletrões $N_e$ com momento$p_i$ (em três dimensões) e vetores de massa $m_e$ e vetores de posição $x_i$ juntamente com núcleos com cargas $Z_k e$ em posições $y_k$, o operador hamiltoniano lê \begin {equation} \hat{H}= \sum\_{i=1}^{N\_e} \frac{{p}\_i^2}{2m\_e} + \frac{1}{2}\sum\_{i\ne j} \frac{e2}{{\hat{x}\_- \hat{x}\_\_j ,k} \frac{Z\_ke^2}{\hat{x}\_i - {y}\_k} +\frac{1}{2} \sum_{k\ne k'} \frac{Z\_kZ\_{k'}e^2}{y\_k - y\_k'}. \label{eq:Ham} \end{equation} Os operadores momenta $\hat{p}\_i^2$ podem ser vistos no espaço real como operadores laplacianos, ou seja, $\hat{p}\_i^2 = -\parcial\_{x\_i}^2 - \parcial\_{y\_i}^2 -\_parcial {z\_i}^2$.
Aqui fizemos a suposição simplificadora de que os núcleos estão em repouso para a molécula.
Isto é conhecido como a aproximação born-oppenheimer e tende a ser válido para o espectro energético de baixa energia de $\hat{H}$ uma vez que a massa de eletrões é de cerca de $1/1836$ a massa de um protão.
Este operador hamiltoniano pode ser facilmente encontrado escrevendo a energia para um sistema de $N\_eletrões de e$e aplicando o processo de quantificação canónica descrito na [Quantum Dynamics.](xref:microsoft.quantum.chemistry.concepts.quantumdynamics)

Para construir a representação da matriz unitária para $e^{-i\hat{H} t}$ precisamos representar o operador $\hat{H}$ como uma matriz.
Para isso, temos de escolher um sistema de coordenadas ou base para representar o problema.
Por exemplo, se $\psi_j$ são um conjunto de funções de base ortogonal para os eletrões $N_e$ então podemos definir a matriz

\begin{equation} H\_{i,j} = \int\_{-\infty}\infty\infty\int\_{-\infty}^\infty \psi^{\*}\_(x\_1) \hat{H} \psi\_j(x\_2) \dd^3x\_1 \dd^3x\_2.\\label{eq:discreteHam} \end{equação

Enquanto, em princípio, o operador $\hat{H}$ está ilimitado e não atua num espaço dimensional finito, a matriz com elementos $H\_\{i,j\}$ acima.
Isto significa que os erros são incorridos através da escolha de um conjunto de bases demasiado pequeno; no entanto, escolher uma grande base pode tornar a simulação da dinâmica química impraticável.
Por esta razão, escolher uma base que possa representar concisamente o problema é vital para resolver o problema da estrutura electrónica.

Há muitas bases apropriadas que podem ser usadas e a escolha de uma boa base para se adaptar ao problema é grande parte da arte da química quântica.
Talvez os conjuntos de base mais simples sejam slater-type-orbitals (STO) que são (ortogonais) soluções para a equação de Schrödinger (isto é, eigenfunctions de $\hat{H}$) para átomos semelhantes a hidrogénio.
Outros conjuntos de base, como ondas de avião ou orbitais do espaço real, podem ser usados e para mais detalhes remetemos o leitor curioso para o texto padrão ['Molecular Electronic-Structure Theory'](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572) de Helgaker.

Embora os estados utilizados no modelo acima possam parecer arbitrários, a mecânica quântica impõe restrições aos Estados que podem ser encontrados na natureza.
Em especial, todos os estados quânticos eletrónicos válidos devem ser antissimétricos sob a troca de etiquetas de eletrões.
Ou seja, se $\psi (x_1,x_2)$ foram a função de onda para o estado quântico conjunto de dois eletrões, então devemos ter aquele $$ \psi (x_1,x_2)= - \psi (x_2,x_1).
$$ O princípio de exclusão de Pauli que proíbe dois eletrões de estarem no mesmo estado quântico é, fascinantemente, uma consequência direta desta lei, como se pode intuir pelo facto de se trocarmos dois eletrões localizados na mesma posição $\psi (x_1,x_1)\mapsto \psi. x_1,x_1) \ne -\psi(x_1,x_1)$ a menos que $\psi (x_1,x_1)=0$.
Assim, os estados iniciais devem ser escolhidos para obedecer a esta propriedade anti-simetria e, por sua vez, nunca ter dois eletrões no mesmo estado ao mesmo tempo.
Isto é crucial para a estrutura electrónica porque proíbe múltiplos eletrões de estarem no mesmo estado, e por sua vez permite que os computadores quânticos usem uma única parte quântica para armazenar o número de eletrões num dado estado quântico.

Enquanto a mecânica quântica pode ser simulada num computador quântico, desbloqueando estes estados, a maioria dos trabalhos no campo evitou esta abordagem porque requer muitos qubits para armazenar os estados e precisa de um procedimento complicado de preparação do Estado para preparar um estado inicial antissimétrico.
Felizmente, porém, estes problemas podem ser desviados ao ver o problema da simulação de uma perspetiva diferente.
