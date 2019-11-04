---
title: Quantum de dinâmica | Microsoft Docs
description: Documentos conceituais do Quantum Dynamics
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantumdynamics
ms.openlocfilehash: 0fd27e59921fdf8429bf164c4c64cfa3b8e44160
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185346"
---
# <a name="quantum-dynamics"></a>Dinâmica de Quantum

A mecânica quantum é basicamente o estudo da Quantum de dinâmica, que busca entender como um estado inicial de Quantum $ \ket{\psi (0)} $ varia ao longo do tempo (consulte os [documentos conceituais](xref:microsoft.quantum.concepts.dirac) na computação Quantum para obter mais informações sobre notação Dirac).
Especificamente, considerando essa condição inicial um estado Quantum, um tempo de evolução e uma especificação do sistema dinâmico Quantum, um estado Quantum $ \ket{\psi (t)} $ é procurado.
Antes de continuar a explicar a dinâmica do Quantum, é útil voltar um pouco e pensar sobre o Dynamics clássico, pois ele fornece informações sobre como a mecânica quantum não é tão diferente da dinâmica clássica.

No Dynamics clássico, sabemos da segunda lei do Newton sobre o Motion que a posição de uma partícula evolui de acordo com $F (x, t) = ma = m\frac {\ DD ^ 2} {\dd t ^ 2} {x} (t) $, em que $F (x, t) $ é a força, $m $ é a massa e $a $ é a aceleração.
Em seguida, dada uma posição inicial $x (0) $, tempo de evolução $t $ e descrição das forças que atuam na partícula, podemos encontrar $x (t) $ resolvendo a equação diferencial fornecida pelas equações de Newton para $x (t) $.
Especificar as forças dessa maneira é um pouco problemático.
Por isso, geralmente expressos as forças em termos da energia potencial do sistema, que nos dá $-\partial_x V (x, t) = m \frac{\dd ^ 2} {\dd t ^ 2} {x} (t) $.
Portanto, para uma partícula, a dinâmica do sistema é especificada somente pela função de energia potencial, pela massa de partículas e pelo tempo de evolução.

Uma linguagem mais ampla é geralmente introduzida para o Dynamics clássico que vai além de $F = ma $.
Uma formulação, que é particularmente útil na mecânica quantum, é a mecânica Hamiltonian.
Na Hamiltonian mecânica, a energia total de um sistema e as posições (generalizadas) e o momento de fornecem todas as informações necessárias para descrever o movimento de um objeto clássico arbitrário.
Especificamente, permita que $f (x, p, t) $ seja alguma função das posições generalizadas $x $ e enquanto $p $ de um sistema e permita que $H (x, p, t) $ seja a função Hamiltonian.
Por exemplo, se levarmos $f (x, p, t) = x (t) $ e $H (x, p, t) = p ^ 2 (t)/2M-V (x, t) $, recuperaremos o caso acima do Newtonian Dynamics.
Em geral, temos o \begin{align} \frac{d}{dt} f & = \partial_t f-(\partial_x H\partial_p f + \partial_p H\partial_x f)\\\\ & \defeq \partial_t f + \\{f, H\\}.
\end{align} aqui $\\{f, H\\} $ é chamado de [colchete Poisson](https://en.wikipedia.org/wiki/Poisson_bracket) e aparece de forma onipresente no Dynamics clássico devido à função central que ele desempenha na definição do Dynamics.

A dinâmica da Quantum pode ser descrita usando exatamente o mesmo idioma.
O Hamiltonian, ou o total de energia, especifica completamente o Dynamics de qualquer sistema Quantum fechado.
No entanto, há algumas diferenças significativas entre as duas teorias.
Na mecânica clássica $x $ e $p $ são apenas números, enquanto que na mecânica quantum eles não são.
Na verdade, eles ainda não fazem o mesmo: $xp \ne px $.

O conceito matemático certo para descrever esses objetos não móveis é um operador, que nos casos em que $x $ e $p $ só pode pegar um conjunto discreto de valores coincide com o conceito de uma matriz.
Portanto, para simplificar, vamos pressupor que nosso sistema Quantum é finito para que possa ser descrito usando [vetores e matrizes](xref:microsoft.quantum.concepts.vectors).
Exigimos ainda que essas matrizes sejam Hermitian (o que significa que a transpoção conjugada da matriz é igual à matriz original).
Isso garante que as eigenvalues das matrizes sejam de valor real; uma condição que impõem para garantir que, quando medimos uma quantidade como posição, não vamos fazer um número imaginário.

Assim como os análogos de posição e dinâmica na mecânica quantum precisam ser substituídos por operadores, a função Hamiltonian precisa ser substituída da mesma forma por um operador.
Por exemplo, para uma partícula no espaço livre, temos esse $H (x, p) = p ^ 2/2m $ enquanto na mecânica quantum o operador Hamiltonian $ \hat{H} $ é $ \hat{H} = \hat{p} ^ 2/2m $, em que $ \hat{p} $ é o operador dinâmica.
Dessa perspectiva, ir do clássico para o dinâmica do Quantum simplesmente envolve a substituição das variáveis usadas no Dynamics comum por operadores.
Depois de construirmos o operador Hamiltonian ao traduzir a Hamiltonian clássica comum para a linguagem Quantum, podemos expressar a dinâmica de uma quantidade mecânica arbitrária de Quantum (ou seja, o operador mecânico Quantum) $ \hat{f} (t) $ via \begin{ align} \frac{d}{dt} \hat{f} = \partial_t \hat{f} + [\hat{f}, \hat{H}], \end{Align}, em que $ [f, H] = fH-HF $ é conhecido como Commutator.
Essa expressão é exatamente como a expressão clássica fornecida acima com a diferença de que o colchete Poisson $\\{f, H\\} $ sendo substituído pelo Commutator entre $f $ e $H $.
Esse processo de pegar um Hamiltonian clássico e usá-lo para encontrar uma Hamiltonian Quantum é conhecido no jargão do Quantum como quantificação canônica.

Em que operadores $f $ estamos mais interessados?  A resposta a isso depende do problema que desejamos resolver.
Talvez a quantidade mais útil a ser encontrada seja o operador de estado Quantum, que, como discutido na documentação conceitual anterior, pode ser usado para extrair tudo o que gostaríamos de saber sobre o Dynamics.
Depois de fazer isso (e simplificar o resultado para o caso em que um tem um estado puro), a equação Schrödinger para o estado Quantum é encontrada \begin{align} i\partial_t \ket{\psi (t)} = \hat{H} (t) \ket{\psi (t)}.
\end{align}

Essa equação, embora talvez menos intuitiva do que aquela fornecida acima, produz, talvez, a expressão mais simples para entender como simular a dinâmica da Quantum em um computador Quantum ou clássico.
Isso ocorre porque a solução para a equação diferencial pode ser expressa na seguinte forma (para o caso em que Hamiltonian é constante em $t $) \begin{align} \ket{\psi (t)} = e ^ {-iHt} \ket{\psi (0)}.
\end{align} aqui $e ^ {-iHt} $ é uma matriz unitário.
Isso significa que existe um circuito Quantum que pode ser projetado para realizá-lo porque os computadores Quantum podem aproximar bastante qualquer matriz de unitário.
Esse ato de encontrar um circuito Quantum para implementar o operador de evolução de tempo Quantum $e ^ {-iHt} $ é o que costuma ser chamado de simulação de Quantum ou em uma simulação de Quantum dinâmico específica.
