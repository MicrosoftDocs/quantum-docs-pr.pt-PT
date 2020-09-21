---
title: Introdução aos Quantum Katas
description: Saiba mais sobre os katas (exercícios de preparação) fornecidos com o Microsoft Quantum Development Kit (QDK)
author: bradben
ms.author: bradben
ms.date: 06/02/2020
ms.topic: overview
uid: microsoft.quantum.overview.katas
no-loc:
- Q#
- $$v
ms.openlocfilehash: 780f04aa941d416032ea3e50b05769f93fae769f
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759396"
---
# <a name="learn-quantum-computing-with-the-quantum-katas"></a>Aprender computação quântica com os Quantum Katas

[Os Katas Quânticos](https://github.com/Microsoft/QuantumKatas/) são tutoriais de código aberto, auto-pace e exercícios de programação destinados a ensinar os elementos da computação quântica e Q# da programação ao mesmo tempo.

## <a name="learning-by-doing"></a>Aprendizagem pela prática

Os tutoriais e os exercícios reunidos neste projeto realçam a aprendizagem pela prática. Disponibilizam tarefas de programação que abrangem determinados tópicos que avançam desde muito simples a bastante desafiantes. Cada tarefa requer que preencha algum código; as primeiras tarefas podem precisar de apenas uma linha e a última pode exigir um fragmento considerável de código.

Mais importante ainda, as katas incluem quadros de testes que configuram, executam e validam as soluções para as tarefas. Tal permite-lhe obter feedback imediato sobre a sua solução e reconsiderar a abordagem, caso esteja incorreta.

Você pode usar as katas para aprender no seu ambiente de eleição:

* Jupyter Notebooks online no ambiente de Enlaçamento
* Jupyter Notebooks em execução no computador local
* Visual Studio
* Visual Studio Code

## <a name="what-can-i-learn-with-the-quantum-katas"></a>O que posso aprender com os Quantum Katas?

Explore os fundamentos e fundamentos da computação quântica ou mergulhe mais profundamente em algoritmos e protocolos quânticos. Recomendamos que siga este percurso de aprendizagem no início para assegurar que tem uma noção sólida sobre os conceitos fundamentais da computação quântica. Como é óbvio, pode ignorar os tópicos com os quais está familiarizado, como aritmética complexa, e aprender os algoritmos em qualquer ordem que pretender.

### <a name="introduction-to-quantum-computing-concepts"></a>Introdução aos conceitos de computação quântica

| Rio Kata | Descrição |
|:-----|-------------|
|[Aritmética complexa](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ComplexArithmetic)|Este tutorial explica alguns dos antecedentes matemáticos necessários para trabalhar com a computação quântica, como números imaginários e complexos.|
|[Álgebra linear](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/LinearAlgebra)|A álgebra linear é usada para representar estados quânticos e operações na computação quântica. Este tutorial cobre o básico, incluindo matrizes e vetores.|
|[Conceito de qubit](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/Qubit)|Saiba mais sobre qubits - um dos conceitos fundamentais da computação quântica. |
|[Portas quânticas com um único qubit](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/SingleQubitGates)|Este tutorial introduz portas quânticas de um único qubit, que funcionam como blocos de construção de algoritmos quânticos e transformam estados quânticos quânticos de várias maneiras.|
|[Sistemas multiqubit](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/MultiQubitSystems)|Este tutorial introduz sistemas multi-qubit, a sua representação na notação matemática e em Q# código, e o conceito de emaranhado.|
|[Portas quânticas multi-qubit](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/MultiQubitGates)|Este tutorial segue o tutorial [de portas quânticas single-qubit, e foca-se](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/SingleQubitGates) na aplicação de portões quânticos em sistemas multi-qubit.|

### <a name="quantum-computing-fundamentals"></a>Noções básicas de computação quântica

| Rio Kata | Descrição |
|:-----|-------------|
|[Reconhecer portas quânticas](https://github.com/microsoft/QuantumKatas/tree/main/BasicGates)|Uma série de exercícios concebidos para o familiarizar com os portões quânticos básicos em Q# . Inclui exercícios para portões básicos de um único qubit e multi-qubit, portões adjacentes e controlados, e como usar portões para modificar o estado de um qubit.|
|[Criar sobreposição quântica](https://github.com/microsoft/QuantumKatas/tree/main/Superposition)|Utilize estes exercícios para se familiarizar com o conceito de superposição e programação em Q# . Inclui exercícios para portões básicos de um único qubit e multi-qubit, superposição e controlo de fluxo e recursão em Q# .|
|[Distinguir estados quânticos com medições](https://github.com/microsoft/QuantumKatas/tree/main/Measurements)|Resolva estes exercícios enquanto aprende sobre a medição quântica e estados orthogonais e não orthogonais. |
|[Associar medições](https://github.com/microsoft/QuantumKatas/tree/main/JointMeasurements)|Saiba mais sobre as medições de paridade conjunta e como utilizar a operação [medida](xref:microsoft.quantum.intrinsic.measure) para distinguir estados quânticos.|

### <a name="algorithms"></a>Algoritmos

| Rio Kata | Descrição |
|:-----|-------------|
|[Quantum teleportation](https://github.com/microsoft/QuantumKatas/tree/main/Teleportation) (Teletransporte quântico)|Esta kata explora a teleportação quântica - um protocolo que permite comunicar um estado quântico usando apenas a comunicação clássica e o emaranhado quântico anteriormente partilhado.|
|[Superdense coding](https://github.com/microsoft/QuantumKatas/tree/main/SuperdenseCoding) (Codificação superdensa)|A codificação superdense é um protocolo que permite a transmissão de dois bits de informação clássica enviando apenas um qubit usando o emaranhado quântico anteriormente partilhado.  |
|[Algoritmo Deutsch–Jozsa](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ExploringDeutschJozsaAlgorithm)|Este algoritmo é famoso por ser um dos primeiros exemplos de um algoritmo quântico que é exponencialmente mais rápido do que qualquer algoritmo clássico determinístico.|
|[Explorar as propriedades de alto nível do algoritmo de pesquisa de Grover](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ExploringGroversAlgorithm)|Uma introdução de alto nível a um dos algoritmos mais famosos da computação quântica. Resolve o problema de encontrar uma entrada para uma caixa preta (oráculo) que produz uma determinada saída. |
|[Implementar o algoritmo de pesquisa de Grover](https://github.com/microsoft/QuantumKatas/tree/main/GroversAlgorithm)|Esta kata mergulha mais profundamente no algoritmo de pesquisa de Grover, e cobre a escrita de oráculos, executando passos do algoritmo, e finalmente juntando tudo.|
|[Resolver problemas reais usando o algoritmo de Grover: problemas de SAT](https://github.com/microsoft/QuantumKatas/tree/main/SolveSATWithGrover)|Uma série de exercícios que usam o algoritmo de Grover para resolver problemas realistas, usando [problemas de satisfibilidade booleana](https://en.wikipedia.org/wiki/Boolean_satisfiability_problem) (SAT) como exemplo.  |
|[Resolver problemas reais usando o algoritmo de Grover: Problemas de coloração de gráficos](https://github.com/microsoft/QuantumKatas/tree/main/GraphColoring)| Este kata explora ainda o algoritmo de Grover, desta vez para resolver problemas de [satisfação de restrição](https://en.wikipedia.org/wiki/Constraint_satisfaction_problem), usando um problema de coloração de gráfico como exemplo. |

### <a name="protocols-and-libraries"></a>Protocolos e bibliotecas

| Rio Kata | Descrição |
|:-----|-------------|
|[Protocolo BB84 para distribuição de chaves quânticas](https://github.com/microsoft/QuantumKatas/tree/main/KeyDistribution_BB84)|Saiba e implemente um protocolo de distribuição de chaves quânticas, [BB84,](https://en.wikipedia.org/wiki/BB84)usando qubits para trocar chaves criptográficas. |
|[Código de correção de erro de bit-flip](https://github.com/microsoft/QuantumKatas/tree/main/QEC_BitFlipCode)|Explore a correção de erros quânticos com o mais simples dos códigos de correção de erros quânticos (QEC) - o código bit-flip de três qubits.|
|[Estimativa de fases](https://github.com/microsoft/QuantumKatas/blob/main/PhaseEstimation)|Os algoritmos de estimativa de fase são alguns dos blocos de construção mais fundamentais da computação quântica. Saiba mais sobre a estimativa de fase com estes exercícios que cobrem a estimativa da fase quântica e como preparar e executar rotinas de estimativa de fase em Q# .|
|[Aritmética quântica: Aditeiros de porta-ondas de construção](https://github.com/microsoft/QuantumKatas/blob/main/RippleCarryAdder)|Uma série aprofundada de exercícios que explora [a ondulação carregam](https://en.wikipedia.org/wiki/Adder_(electronics)#Ripple-carry_adder) a adição num computador quântico. Construa um adder quântico no local, expanda-o com um algoritmo diferente e, finalmente, construa um subtrator quântico no local.   |

### <a name="entanglement-games"></a>Jogos de entrelaçamento

| Rio Kata | Descrição |
|:-----|-------------|
|[Jogo CHSH](https://github.com/microsoft/QuantumKatas/tree/main/CHSHGame)|Explore o emaranhado quântico com uma implementação do jogo [CHSH.](https://en.wikipedia.org/wiki/CHSH_inequality) Este jogo [não local](https://en.wikipedia.org/wiki/Quantum_refereed_game) mostra como o emaranhado quântico pode ser usado para aumentar as hipóteses dos jogadores de ganhar para além do que seria possível com uma estratégia puramente clássica.|
|[Jogo GHZ](https://github.com/microsoft/QuantumKatas/tree/main/GHZGame)|O jogo ghz é outro jogo não local, mas envolve três jogadores.|
|[Jogo quadrado mágico Mermin-Peres](https://github.com/microsoft/QuantumKatas/tree/main/MagicSquareGame)|Uma série de exercícios que explora a [pseudo-telepatia quântica](https://en.wikipedia.org/wiki/Quantum_pseudo-telepathy#The_Mermin%E2%80%93Peres_magic_square_game) para resolver um jogo quadrado mágico.  |

## <a name="resources"></a>Recursos

Veja a série completa de [Quantum Katas](https://github.com/microsoft/QuantumKatas)

[Executar katas online](https://aka.ms/try-quantum-katas)
