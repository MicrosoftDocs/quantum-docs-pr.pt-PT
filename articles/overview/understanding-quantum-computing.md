---
title: Compreender a computação quântica
description: O que são computadores quânticos e como utilizam os princípios da mecânica quântica?
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.understanding
ms.openlocfilehash: 65fa85a80021124444fd352f9492d03cbefcb859
ms.sourcegitcommit: a03d79ca3f0774161a9f86a15528d36e1291acce
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83433015"
---
# <a name="understanding-quantum-computing"></a>Compreender a computação quântica

A computação quântica utiliza os princípios da mecânica quântica para processar informações. Por esse motivo, exige uma abordagem diferente relativamente à computação clássica.  Um exemplo dessa diferença é o processador utilizado nos computadores quânticos.  Ao passo que os computadores clássicos utilizam os familiares chips de silício, os computadores quânticos utilizam materiais quânticos, como átomos, iões, fotões ou eletrões.  

O material quântico comporta-se de acordo com as leis da mecânica quântica, recorrendo a conceitos como computação probabilística, sobreposição e entrelaçamento. Estes conceitos são a base dos algoritmos quânticos que tiram partido do poder da computação quântica para resolver problemas complexos. Este artigo descreve alguns dos conceitos essenciais da mecânica quântica subjacentes à computação quântica.

## <a name="a-birds-eye-view-of-quantum-mechanics"></a>Uma perspetiva panorâmica da mecânica quântica

A mecânica quântica, também denominada "teoria quântica", é um ramo da física que lida com partículas a nível atómico e subatómico. Contudo, ao nível quântico, muitas das leis da mecânica que tomamos como garantidas não se aplicam. A sobreposição, a medição quântica e o entrelaçamento são três fenómenos centrais na computação quântica.  

### <a name="superposition-vs-binary-computing"></a>sobreposição vs. computação binária

Imagine que está a fazer exercício na sala. Vira-se completamente para a esquerda e depois completamente para a direita. Agora, vire-se para a esquerda e para a direita ao mesmo tempo. É impossível fazê-lo (a não ser que se divida em dois).  Obviamente, não pode estar nestes dois estados ao mesmo tempo; não pode olhar para a esquerda e para a direita em simultâneo.

No entanto, se fosse uma partícula quântica, poderia ter uma determinada probabilidade de *olhar para a esquerda* E uma determinada probabilidade de *olhar para a direita* devido a um fenómeno chamado **sobreposição** (também conhecido como **coerência**).

As partículas quânticas, como os eletrões, têm as suas próprias propriedades de "olhar para a esquerda ou para a direita", por exemplo, o **spin**, referido como para cima ou para baixo ou, para identificar com a clássica computação binária, digamos simplesmente 1 ou 0. Quando uma partícula quântica está no estado de sobreposição, é uma combinação linear de um número infinito de estados entre 1 e 0, mas só saberemos qual será quando olharmos para o mesmo, o que nos leva ao nosso próximo fenómeno, a **medição quântica**.

### <a name="quantum-measurement"></a>Medição quântica

Agora, imaginemos que um amigo vai a sua casa e quer tirar uma fotografia sua a fazer exercício. O mais provável é que acabe com uma fotografia desfocada consigo a virar-se de um lado para o outro.

Contudo, se fosse uma partícula quântica, aconteceria uma coisa interessante. Independentemente do que estivesse a fazer quando o seu amigo tirou a fotografia, apareceria sempre completamente para a esquerda ou para a direita, nunca a meio do movimento.

Isto deve-se ao facto de o ato de observar ou medir uma partícula quântica fazer **colapsar** o estado de sobreposição (também conhecido como **decoerência**) e essa partícula assume um estado binário clássico de 1 ou 0.

Esse estado binário é-nos útil, porque, na computação, podemos fazer imensas coisas com uns e zeros. No entanto, quando uma partícula quântica é medida e colapsada, fica nesse estado para sempre (tal como a sua fotografia) e será sempre 1 ou 0. Como veremos mais adiante, não obstante, na computação quântica existem operações que podem "repor" as partículas para o estado de sobreposição, para que possam ser reutilizadas em cálculos quânticos.

### <a name="entanglement"></a>Entrelaçamento

O fenómeno possivelmente mais interessante da mecânica quântica é a possibilidade de duas ou mais partículas quânticas se **entrelaçarem** entre si. Quando as partículas se entrelaçam, formam um sistema único de tal forma que o estado quântico de qualquer uma das partículas não pode ser descrito de forma independente do estado quântico das demais. Isto significa que, seja qual for a operação ou o processo que aplicar a uma partícula, essa operação ou processo correlaciona-se também com as outras partículas.

Além desta interdependência, as partículas podem manter essa ligação mesmo quando estão separadas por distâncias incrivelmente grandes, inclusive anos-luz. Os efeitos da medição quântica também se aplicam às partículas entrelaçadas, pelo que, quando uma partícula é medida e colapsada, a outra partícula também é colapsada. Uma vez que há uma correlação entre os qubits entrelaçados, medir o estado de um qubit dá informações sobre o estado do outro; esta propriedade em particular é muito útil na computação quântica.

### <a name="qubits-and-probability"></a>Qubits e probabilidade

Os computadores clássicos armazenam e processam informações em bits, que podem ter o estado 1 ou 0, mas nunca ambos. O equivalente na computação quântica é o **qubit**, que representa o estado das partículas quânticas. Devido à sobreposição, os qubits podem ser 1 ou 0 ou qualquer valor entre ambos. Consoante a sua configuração, os qubits têm uma certa *probabilidade* de se colapsarem para 1 ou 0. A probabilidade de os qubits se colapsarem para um lado ou para o outro é determinada pela **interferência quântica**. 

Ainda se lembra do seu amigo que lhe queria tirar uma fotografia? Imagine que a máquina fotográfica dele tem filtros especiais, chamados filtros de *interferência*. Se ele selecionar o filtro *70/30* e começar a tirar fotografias, em 70% das mesmas apanhá-lo-ia virado para a esquerda e, em 30%, para a direita. O filtro interferiu com o estado normal da máquina fotográfica para influenciar a probabilidade do respetivo comportamento.

Do mesmo modo, a interferência quântica afeta o estado de um qubit para influenciar a probabilidade de ocorrer um determinado resultado durante a medição. É neste estado probabilístico que o poder da computação quântica se destaca.

Por exemplo, com dois bits num computador clássico, cada bit pode armazenar 1 ou 0, pelo que, em conjunto, pode armazenar quatro valores possíveis – **00**, **01**, **10** e **11** –, mas apenas um de cada vez. No entanto, com dois qubits em sobreposição, cada qubit pode ser 1, 0 ou *ambos*, o que lhe permite representar os mesmos quatro valores em simultâneo. Com três qubits, pode representar oito valores; com quatro, pode representar 16 valores e assim sucessivamente.

## <a name="summary"></a>Resumo

Estes conceitos apenas abordam a mecânica quântica pela rama, mas são fundamentais para se perceber a computação quântica.

- **Sobreposição** – a capacidade de as partículas quânticas serem uma combinação de todos os estados possíveis.
- **Medição quântica** – o ato de observar uma partícula quântica em sobreposição e resultar num dos estados possíveis.
- **Entrelaçamento** – a capacidade de as partículas quânticas correlacionarem os resultados das respetivas medições entre as mesmas.
- **Qubit** – a unidade básica de informação da computação quântica. O qubit representa uma partícula quântica em sobreposição de todos os estados possíveis.
- **Interferência** – o comportamento intrínseco de um qubit devido à sobreposição para influenciar a probabilidade de se colapsar num sentido ou noutro.

## <a name="next-steps"></a>Passos Seguintes

> [!div class="nextstepaction"]
> [Computadores e simuladores quânticos](xref:microsoft.quantum.overview.simulators)
