---
title: Computadores e simuladores quânticos
description: Saiba mais sobre hardware quântico, simuladores quânticos e como as operações quânticas funcionam.
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.simulators
ms.openlocfilehash: 04f90e9f88cf17259f96532617ef6f092b56b859
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430752"
---
# <a name="quantum-computers-and-quantum-simulators"></a>Computadores e simuladores quânticos

Os computadores quânticos ainda estão numa fase embrionária de desenvolvimento. O hardware e a manutenção são dispendiosos e a maioria dos sistemas estão instalados em universidades e laboratórios de investigação. Ainda assim, a tecnologia está a avançar e já é permitido acesso público a alguns sistemas.

Os simuladores quânticos são programas de software que funcionam em computadores clássicos e que possibilitam a execução e a testagem de programas quânticos num ambiente que prevê a reação dos qubits a diferentes operações.

## <a name="quantum-hardware"></a>Hardware quântico

Os computadores quânticos têm três partes principais: uma área que aloja os qubits, um método para transferir sinais para os qubits e um computador clássico para executar um programa e enviar instruções.

- O material quântico utilizado para os qubits é frágil e altamente sensível a interferências ambientais. Em alguns métodos do armazenamento de qubits, a unidade que os aloja é mantida a uma temperatura ligeiramente acima do zero absoluto, de modo a maximizar a coerência dos qubits. Outros tipos de alojamento de qubits utilizam uma câmara de vácuo para ajudar a minimizar as vibrações e a estabilizá-los.  
- Os sinais podem ser enviados para os qubits através de vários métodos, incluindo micro-ondas, laser e voltagem.

Os computadores quânticos enfrentam uma multiplicidade de desafios para funcionarem corretamente, sendo a correção de erros nos mesmos um problema muito relevante e o dimensionamento (ou seja, a adição de mais qubits) aumenta a taxa de erro. Devido a estas limitações, os computadores quânticos pessoais ainda estão longe de ser uma realidade, embora versões para laboratórios e comercialmente viáveis estejam mais perto.

## <a name="quantum-simulators"></a>Simuladores quânticos

Os simuladores quânticos que são executados em computadores clássicos permitem-lhe simular a execução de algoritmos quânticos num sistema quântico.  O Microsoft Quantum Development Kit (QDK) inclui um simulador de vetor de estado completo, juntamente com outros simuladores quânticos especializados.

## <a name="topological-qubit"></a>Qubit topológico

A Microsoft está a desenvolver um computador quântico baseado em qubits topológicos. Os qubits topológicos serão menos afetados pelas alterações no respetivo ambiente e, consequentemente, reduzem o grau de correção de erros externos necessária.

A funcionalidade dos qubits topológicos aumentou a estabilidade e a resistência ao ruído do ambiente, o que significa que podem ser facilmente dimensionados e mantêm-se fiáveis durante mais tempo.

## <a name="microsoft-and-quantum-hardware-partnerships"></a>Parcerias entre a Microsoft e fabricantes de hardware quântico

A Microsoft está a estabelecer parcerias com os fabricantes de hardware quântico IonQ, Honeywell e QCI para tornar os computadores quânticos acessíveis aos programadores no futuro. Tirando partido da plataforma do Azure Quantum, os programadores poderão utilizar o Microsoft Quantum Development Kit (QDK) e Q# para escrever programas quânticos e executá-los remotamente.

## <a name="quantum-computations"></a>Computações quânticas

A realização de computações num computador ou num simulador quântico obedece a um processo simples:

- Aceder aos qubits
- Inicializar os qubits para o estado pretendido
- Realizar operações para transformar os estados dos qubits
- Medir os estados novos dos qubits

A inicialização e a transformação dos qubits fazem-se com **operações quânticas** (por vezes, denominadas "portas quânticas"). As operações quânticas são semelhantes às operações lógicas na computação clássica, como AND, OR, NOT e XOR. As operações podem ter são básicas como inverter o estado de um qubit de 1 para 0 ou entrelaçar um par de qubits ou como utilizar múltiplas operações em série para afetar a probabilidade de um qubit sobreposto colapsar num sentido ou no outro.

> [!NOTE] 
> As [bibliotecas Q#](xref:microsoft.quantum.libraries) disponibilizam operações incorporadas que definem combinações complexas de operações quânticas de nível inferior. Pode utilizar as operações da biblioteca para transformar os qubits e para criar operações mais complexas definidas pelo utilizador.  

A medição do resultado da computação dá-nos uma resposta; contudo, em alguns algoritmos quânticos, não é necessariamente a resposta certa. Uma vez que o resultado de alguns algoritmos quânticos tem por base a probabilidade que foi configurada pelas operações quânticas, estas computações são executadas várias vezes, de modo a obter uma distribuição da probabilidade e a refinar a precisão dos resultados.  A certeza de que uma operação devolveu uma resposta correta é conhecida como verificação quântica e é um desafio significativo na computação quântica.

## <a name="summary"></a>Resumo

A computação quântica partilha alguns dos conceitos da computação clássica, mas acrescenta algumas novidades. Eis algumas ideias a reter:

- O hardware quântico é caro e frágil, pelo que se utilizam simuladores quânticos para escrever e testar programas.
- Tanto os computações clássicos como quânticos utilizam operações lógicas (ou portas) para preparar as computações.
- As computações quânticas devolvem probabilidades.

Os avanços no hardware e nas técnicas quânticas estão a mudar rapidamente a área. Eis alguns dos [desenvolvimentos atuais](https://phys.org/search/?search=quantum+computer&s=0).

## <a name="next-steps"></a>Passos seguintes

> [!div class="nextstepaction"]
> [O que é a linguagem de programação Q# e o QDK?](xref:microsoft.quantum.overview.q-sharp)