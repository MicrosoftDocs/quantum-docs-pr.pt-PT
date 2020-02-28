---
title: Dinâmica Quântica
description: Aprenda as semelhanças e diferenças entre a dinâmica quântica e a dinâmica clássica.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantumdynamics
ms.openlocfilehash: 9cb74ccd4b7806a90c0701300860d777fa8e5d75
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904490"
---
# <a name="quantum-dynamics"></a>Dinâmica Quântica

A mecânica quântica é em grande parte o estudo da dinâmica quântica, que procura entender como um estado quântico inicial $\ket{\psi(0)}$ varia ao longo do tempo (ver os [docs conceptuais](xref:microsoft.quantum.concepts.dirac) na computação quântica para obter mais informações sobre a notação de Dirac).
Especificamente, dada esta condição inicial, um estado quântico, um tempo de evolução e uma especificação do sistema dinâmico quântico, é procurado um estado quântico $\ket{\psi(t)}$.
Antes de continuar a explicar a dinâmica quântica, é útil dar um passo atrás e pensar sobre a dinâmica clássica, uma vez que fornece insights sobre como a mecânica quântica não é realmente tão diferente da dinâmica clássica.

Na dinâmica clássica, sabemos pela segunda lei de movimento de Newton que a posição de uma partícula evolui de acordo com $F (x,t)=ma=m\frac{\dd^2}{\dd t^2}{x}(t)$, onde $F(x,t)$ é a força,$m$ é a massa e $a$ é a aceleração.
Então, dada a posição inicial $x(0)$, o tempo de evolução $t$, e a descrição das forças que atuam na partícula, podemos então encontrar $x(t)$ resolvendo a equação diferencial dada pelas equações de Newton para $x(t)$.
Especificar as forças desta forma é um pouco doloroso.
Assim, muitas vezes expressamos as forças em termos da energia potencial do sistema, que nos dá $-\partial_x V(x,t) = m \frac{\dd^2}{\dd t^2}{x}(t)$.
Assim, para uma partícula, a dinâmica do sistema é especificada apenas pela potencial função energética, pela massa de partículas e pelo tempo de evolução.

Uma linguagem mais ampla é frequentemente introduzida para dinâmicas clássicas que vai além de $F=ma$.
Uma formulação, que é particularmente útil na mecânica quântica, é a mecânica hamiltoniana.
Na mecânica hamiltoniana, a energia total de um sistema e as posições (generalizadas) e momenta dão toda a informação necessária para descrever o movimento de um objeto clássico arbitrário.
Especificamente, deixe $f (x,p,t)$ ser uma função das posições generalizadas $x$ e momenta $p$ de um sistema e deixar que $H (x,p,t)$ seja a função Hamiltonian.
Por exemplo, se tomarmos $f (x,p,t)= x(t)$ e $H (x,p,t)=p^2(t)/2m - V(x,t)$, então recuperaríamos o caso acima da dinâmica newtoniana.
Na generalidade, temos então aquele \begin{align} \frac{d}{dt} f &= \partial_t f- (\partial_x H\partial_p f + \partial_p H\partial_x f)\\\\ &\defeq \partial_t f + \\{f,H\\}.
\end{align} Aqui $\\{f,H\\}$ é chamado de [suporte Poisson](https://en.wikipedia.org/wiki/Poisson_bracket) e aparece ubiquicamente na dinâmica clássica devido ao papel central que desempenha na definição da dinâmica.

A dinâmica quântica pode ser descrita usando exatamente a mesma linguagem.
O Hamiltonian, ou energia total, especifica completamente a dinâmica de qualquer sistema quântico fechado.
Existem, no entanto, algumas diferenças substanciais entre as duas teorias.
Na mecânica clássica $x$ e $p$ são apenas números, enquanto na mecânica quântica não são.
Na verdade, nem sequer viajam: $xp \ne px$.

O conceito matemático certo para descrever estes objetos não-comutantes é um operador, que nos casos em que $x$ e $p$ só pode tomar um conjunto discreto de valores coincide com o conceito de matriz.
Assim, para a simplicidade, assumiremos que o nosso sistema quântico é finito para que possa ser descrito usando [vetores e matrizes.](xref:microsoft.quantum.concepts.vectors)
Exigimos ainda que estas matrizes sejam hermitianos (o que significa que a transposição conjugada da matriz é a mesma que a matriz original).
Isto garante que os valores eigen das matrizes são de valor real; uma condição que nos impusemos para garantir que quando medimos uma quantidade como a posição de que não consigamos voltar a sair de um número imaginário.

Da mesma forma que os análogos de posição e de dinâmica na mecânica quântica precisam de ser substituídos pelos operadores, a função Hamiltonian a função tem de ser igualmente substituída por um operador.
Por exemplo, para uma partícula em espaço livre temos essa $H (x,p) = p^2/2m$ enquanto na mecânica quântica o operador hamiltoniano {H}$ é $\hat{H}= \hat{p}^2/2m$ onde o $\hat{p}$ é o operador do impulso.
Nesta perspetiva, passar da dinâmica clássica à quântica apenas implica substituir as variáveis usadas nas dinâmicas ordinárias por operadores.
Uma vez construído o operador hamiltoniano traduzindo o hamiltoniano clássico comum para a linguagem quântica, podemos expressar a dinâmica de uma quantidade mecânica quântica arbitrária (ou seja, operador mecânico quântico) $\hat{f}(t)$ via \start{ { alinhar} \frac{d}{dt} \hat{f} = \partial_t \hat{f} + [\hat{f},\hat{H}], \end{align} onde $[f,H] = fH -Hf$ é conhecido como o comutador.
Esta expressão é exatamente como a expressão clássica dada acima com a diferença que o suporte poisson $\\{f,H\\}$ sendo substituído pelo comutador entre $f$ e $H$.
Este processo de tomar um hamiltoniano clássico e usá-lo para encontrar um hamiltoniano quântico é conhecido no jargão quântico como quantização canónica.

Em que operadores $f$ estamos mais interessados?  A resposta a isto depende do problema que queremos resolver.
Talvez a quantidade mais útil a encontrar seja o operador do Estado quântico, que, tal como discutido na documentação conceptual anterior, pode ser usado para extrair tudo o que gostaríamos de aprender sobre a dinâmica.
Depois de fazer isto (e simplificar o resultado para o caso em que se tem um estado puro), a equação de Schrödinger para o estado quântico é encontrada \begin {align} i\partial_t \ket {\psi(t)} = \hat{H}(t) \ket{\psi(t)}.
\fim{align}

Esta equação, embora talvez menos intuitiva do que a acima, produz talvez a expressão mais simples para entender como simular dinâmicas quânticas num computador quântico ou clássico.
Isto porque a solução para a equação diferencial pode ser expressa da seguinte forma (para o caso em que o Hamiltonian é constante em $t$) \start{align} \ket{\psi(t)} = e^{-iHt}\ket{\psi(0)}.
\fim{align} Aqui $e^{-iHt}$ é uma matriz unitária.
Isto significa que existe um circuito quântico que pode ser projetado para executá-lo porque os computadores quânticos podem aproximar-se de qualquer matriz unitária.
Este ato de encontrar um circuito quântico para implementar o operador de evolução do tempo quântico $e^{-iHt}$ é o que é frequentemente chamado de simulação quântica, ou em particular simulação quântica dinâmica.
