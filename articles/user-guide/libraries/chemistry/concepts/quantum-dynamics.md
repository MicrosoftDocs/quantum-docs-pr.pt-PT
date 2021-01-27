---
title: Dinâmica Quântica
description: Aprenda as semelhanças e diferenças entre a dinâmica quântica e a dinâmica clássica.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.quantumdynamics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4dec0ed7346cde579e5692fcf13519d4ce05cb00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856247"
---
# <a name="quantum-dynamics"></a>Dinâmica Quântica

A Mecânica Quântica é em grande parte o estudo da dinâmica quântica, que procura entender como um estado quântico inicial $\ket{\psi(0)}} varia ao longo do tempo (ver [os docs conceptuais](xref:microsoft.quantum.concepts.dirac) sobre computação quântica para mais informações sobre notação dirac).
Especificamente, dada esta condição inicial um estado quântico, um tempo de evolução e uma especificação do sistema dinâmico quântico, é procurado um estado quântico $\ket{\psi(t)}$
Antes de continuar a explicar a dinâmica quântica, é útil dar um passo atrás e pensar na dinâmica clássica, uma vez que fornece insights sobre como a mecânica quântica não é realmente tão diferente da dinâmica clássica.

Na dinâmica clássica, sabemos pela segunda lei de movimento de Newton que a posição de uma partícula evolui de acordo com $F(x,t)=ma=m\frac{\dd^2}dd t^2}{x},(t)$, onde $F(x,t)$ é a força,$m$ é a massa e $a$ é a aceleração.
Então, dada a posição inicial $x(0)$, tempo de evolução $t$, e descrição das forças que atuam sobre a partícula, podemos então encontrar $x(t)$ resolvendo a equação diferencial dada pelas equações de Newton para $x(t)$.
Especificar as forças desta forma é um pouco chato.
Por isso, expressamos frequentemente as forças em termos da energia potencial do sistema, que nos dá $-\partial_x V(x,t) = m \frac{\dd^2}dd t^2}}x}(t)$.
Assim, para uma partícula, a dinâmica do sistema é especificada apenas pela potencial função energética, a massa de partículas e o tempo de evolução.

Uma linguagem mais ampla é frequentemente introduzida para as dinâmicas clássicas que vão além $F=ma$.
Uma formulação, que é particularmente útil na mecânica quântica, é a mecânica hamiltoniana.
Na mecânica hamiltoniana, a energia total de um sistema e as posições (generalizadas) e momenta dão toda a informação necessária para descrever o movimento de um objeto clássico arbitrário.
Especificamente, deixe $f(x,p,t)$ ser alguma função das posições generalizadas $x$ e momenta $p$ de um sistema e deixar $H (x,p,t)$ ser a função hamiltoniana.
Por exemplo, se tomarmos $f (x,p,t)= x(t)$ e $H(x,p,t)=p^2(t)/2m - V(x,t)$, então recuperaríamos o caso acima da dinâmica newtoniana.
Em geral, temos então que \begin{align} \frac{d}{dt} f &= \partial_t f- (\partial_x H\partial_p f + \partial_p H\partial_x f) \\ \\ &\defeq \partial_t f + \\ {f,H \\ }.
\end{align} Aqui $ \\ {f,H \\ }$ é chamado de [suporte Poisson](https://en.wikipedia.org/wiki/Poisson_bracket) e aparece ubiquicamente na dinâmica clássica devido ao papel central que desempenha na definição da dinâmica.

A dinâmica quântica pode ser descrita usando exatamente a mesma língua.
O Hamiltonian, ou energia total, especifica completamente a dinâmica de qualquer sistema quântico fechado.
Há, no entanto, algumas diferenças substanciais entre as duas teorias.
Na mecânica clássica $x dólares e $p dólares são apenas números, enquanto na mecânica quântica não são.
Na verdade, nem sequer viajam: $xp \ne px$.

O conceito matemático certo para descrever estes objetos não comutados é um operador, que nos casos em que $x$ e $p$ só pode levar um conjunto discreto de valores coincide com o conceito de uma matriz.
Assim, para a simplicidade, vamos assumir que o nosso sistema quântico é finito para que possa ser descrito usando [vetores e matrizes.](xref:microsoft.quantum.concepts.vectors)
Exigimos ainda que estas matrizes sejam hermitianas (o que significa que a transposição conjugada da matriz é a mesma que a matriz original).
Isto garante que os valores de eigenues das matrizes são valorizados em realidade; uma condição que impomos para garantir que quando medimos uma quantidade como posição que não temos de voltar a sair de um número imaginário.

Tal como os análogos de posição e dinâmica na mecânica quântica precisam de ser substituídos pelos operadores, a função hamiltoniana tem de ser igualmente substituída por um operador.
Por exemplo, para uma partícula no espaço livre temos que $H(x,p) = p^2/2m$ enquanto na mecânica quântica o operador hamiltoniano $\hat{H}} é $\hat{H}= \hat{p}^2/2m$ onde $\hat{p}$ é o operador de impulso.
Nesta perspetiva, passar da dinâmica clássica para a quântica envolve apenas substituir as variáveis utilizadas na dinâmica ordinária pelos operadores.
Uma vez que construímos o operador hamiltoniano traduzindo o hamiltoniano clássico comum para a linguagem quântica, podemos expressar a dinâmica de uma quantidade mecânica quântica arbitrária (ou seja, operador mecânico quântico) $\hat{f}(t)$ via \start{} \frac{d}{d}} \hat{f} = \partial_t \hat{f} + [\hat{f} + [\hat{f},,hat{H}], \end{align} onde $[f,H] = fH -Hf$
Esta expressão é exatamente igual à expressão clássica dada acima com a diferença de que o suporte poisson $ \\ {f,H \\ }$ sendo substituído pelo comutador entre $f$ e $H$.
Este processo de tomar um hamiltoniano clássico e usá-lo para encontrar um hamiltoniano quântico é conhecido no jargão quântico como quantização canónica.

Em que operadores $f$ estamos mais interessados?  A resposta a esta questão depende do problema que queremos resolver.
Talvez a quantidade mais útil a encontrar seja o operador do Estado quântico, que, como discutido na documentação conceptual anterior, pode ser usado para extrair tudo o que gostaríamos de aprender sobre a dinâmica.
Depois de o fazer (e simplificando o resultado para o caso em que se tem um estado puro), a equação de Schrödinger para o estado quântico é encontrada \start{align} i\partial_t \ket{\psi(t)} = \hat{H}(t) \ket\psi(t)}}
\end{align}

Esta equação, embora talvez menos intuitiva do que a acima dada, produz talvez a expressão mais simples para entender como simular dinâmicas quânticas num computador quântico ou clássico.
Isto porque a solução para a equação diferencial pode ser expressa da seguinte forma (para o caso em que o Hamiltonian é constante em $t$) \start{\ket{\psi(t)} = e^{-iHt}\ket{\psi(0)}}
\end{align} Aqui $e^{-iHt}$ é uma matriz unitária.
Isto significa que existe um circuito quântico que pode ser projetado para executá-lo porque os computadores quânticos podem aproximar-se de qualquer matriz unitária.
Este ato de encontrar um circuito quântico para implementar o operador de evolução do tempo quântico $e^{-iHt}} é o que é frequentemente chamado de simulação quântica, ou em particular simulação quântica dinâmica.
