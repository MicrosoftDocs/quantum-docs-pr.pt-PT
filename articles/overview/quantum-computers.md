---
title: O que podem fazer os computadores quânticos?
description: Saiba mais sobre o impacto da computação quântica, desde algoritmos quânticos inovadores até à quântica inspirada em algoritmos executados em computadores clássicos.
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.computers
ms.openlocfilehash: d4be970c635ca090e8dcb1b58d5c840eebd4d110
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443839"
---
# <a name="what-can-a-quantum-computer-do"></a>O que pode fazer um computador quântico?

O que podemos fazer com um computador quântico que não possa ser feito com um computador clássico?

Para resolver alguns dos problemas mais desafiantes do mundo, onde os computadores atuais levariam milhares de milhões de anos a encontrar uma solução, um computador quântico poderia fazer o mesmo em dias, horas ou até mesmo minutos. A computação quântica irá permitir que os investigadores desenvolvam catalisadores e materiais novos, melhorem medicamentos, acelerem os avanços na inteligência artificial e respondam a questões fundamentais sobre a origem do nosso universo.

## <a name="quantum-simulation"></a>Simulação quântica

A utilização de programas quânticos para modelar os próprios sistemas quânticos tem um grande potencial para desbloquear informações que levam a inovações em vários setores. Fotossíntese, supercondutores e moléculas complexas são exemplos de sistemas quânticos que podem ser simulados através de programas quânticos.

A simulação de sistemas microscópicos que se comportam de acordo com as leis da mecânica quântica é computacionalmente dispendiosa. Precisamos de ter em consideração todos os estados possíveis que podem estar em sobreposição e o número de estados aumenta exponencialmente com o tamanho do sistema. Num computador quântico, não precisamos de modelar todos os estados do sistema. Em vez disso, incorporamos o estado quântico do sistema que queremos simular nos qubits do próprio computador e executamos a simulação com um conjunto específico de portas quânticas. Por outras palavras, utilizamos um computador quântico para simular um sistema quântico.

As moléculas químicas são sistemas quânticos e, por isso, podem ser analisadas desta forma. Uma dessas substâncias químicas específicas é a enzima _nitrogenase_, que, com uma melhor compreensão das respetivas propriedades, poderia ter o potencial para reduzir o consumo de energia e a emissão de gases com efeito de estufa dos fertilizantes atuais.

## <a name="cryptography"></a>Criptografia

Talvez a aplicação mais famosa de computadores quânticos esteja em criptografia, em que Peter Shor demonstrou em 1994 que um computador quântico dimensionável consegue ultrapassar cada técnica de encriptação amplamente utilizada.  A criptografia clássica depende da dificuldade das operações em números grandes, como a fatorização de números grandes em dois números primos.  A computação quântica torna estas operações teoricamente possíveis (por via do algoritmo de Shor). Embora a implementação deste algoritmo não seja fisicamente possível com o dimensionamento atual do hardware quântico, gerou o desenvolvimento de algoritmos resistentes a ataques quânticos para uma segurança dos dados preparada para o futuro, incluindo algoritmos quânticos inovadores para encriptação e distribuição de chaves criptográficas.  Aqui na Microsoft, temos a equipa líder mundial em criptografia pós-quântica e algoritmos de desenvolvimento de segurança resistentes à quântica. 

## <a name="optimization"></a>Otimização

A otimização é a tarefa de executar uma pesquisa grande num espaço alto-dimensional para uma solução realmente boa que minimize uma determinada função de custo.   Num computador quântico, podemos acelerar os algoritmos de otimização ao encontrar soluções que de outra forma não seriam possíveis. As aplicações variam entre transporte e logística, saúde, diagnóstico e ciência materiais. Pode haver um impacto profundo sobre a forma como estes setores se podem tornar mais eficientes. 

A otimização com a computação quântica permite-nos inovar em termos de transporte e logística de uma forma que não seria possível com os sistemas clássicos atuais. A otimização do fluxo de tráfego pode reduzir o congestionamento.  Além do planeamento de rotas, existe a atribuição de portas aéreas, entrega de pacotes, agendamento de tarefas e muito mais.  Com as inovações na ciência de materiais, existirão novas formas de energia, baterias com maior capacidade, materiais mais leves e mais fortes. 

## <a name="machine-learning"></a>Aprendizagem automática

Grande parte dos cálculos numéricos na computação clássica consiste principalmente em resolver sistemas lineares de equações. Tal acontece sobretudo no campo da aprendizagem automática, onde a maior parte do custo da computação é atribuída ao cálculo do inverso de matrizes enormes.

Felizmente, existe um algoritmo quântico que nos permite solucionar aproximadamente o sistema de forma exponencialmente mais rápida do que um computador clássico, o que abre a porta a grandes acelerações em todos os problemas que precisem da solução para sistemas lineares de equações.

Soluções para problemas nestas áreas ajudarão a resolver a crise energética, as alterações climáticas, a escassez de alimentos e o diagnóstico médico pessoal preciso.

## <a name="quantum-inspired-computing"></a>Computação inspirada na quântica

Os algoritmos inspirados na quântica são implementados com um software clássico, mas utilizam princípios quânticos para aumentar a velocidade e a precisão.

Estão a ser aplicados algoritmos inspirados na quântica à investigação médica. Por exemplo, para melhorar a precisão dos exames de ressonância magnética (IRM). A computação inspirada na quântica está a ser utilizada para otimizar a configuração das máquinas de IRM para identificar doenças específicas.

## <a name="next-steps"></a>Passos seguintes

* [Por que motivo devo aprender computação quântica?](xref:microsoft.quantum.overview.why)
* [Introdução ao Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
