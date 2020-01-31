---
title: Glossário de computação quântica Microsoft Docs
description: Glossário de termos quânticos
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: 5c7f2c4a572f6194ee846f056016a25b8c5303a2
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820764"
---
# <a name="quantum-computing-glossary"></a>Glossário de computação quântica

|Duração|Definição|
|-------------|----------|
|Adjoint|O complexo conjugado transposição da operação. Para operações que implementem um operador unitário, o adjoint é o inverso da operação.|
|Callable|As operações e funções são coletivamente conhecidas como *callables*.|
|Padrão|Operações e funções definidas em Q# baseando-se na lógica definida no prelúdio. A implementação padrão da biblioteca é agnóstica no que diz respeito às máquinas-alvo.|
|Grupo Clifford|O conjunto de operações que ocupam os octantes da esfera bloch. Estes incluem: `X`, `Y`, `Z`, `H` e `S`|
|Controlado|Uma operação quântica que toma um ou mais qubits como facilitadores para a operação alvo.|
|Notação Dirac|Uma representação abreviada do Estado quântico. Consulte a secção [de Notação Dirac](xref:microsoft.quantum.concepts.dirac) para mais detalhes.|
|Eigenvalues e Eigenvectors|Consulte a [secção Advanced Matrix](xref:microsoft.quantum.concepts.matrix-advanced) para obter mais detalhes.|
|Par de EPR|Também conhecido como [Bell State](https://en.wikipedia.org/wiki/Bell_state)|
|Evolução|Como o estado muda com o tempo. Consulte a secção em <xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials>, por exemplo. |
|Função|Rotinas puramente clássicas na língua Q#|
| <a id="global-phase"></a>Fase global | Dois estados que são idênticos a um número complexo $e^{i\phi}$ diferem até uma fase global. Ao contrário das fases locais, as fases globais não podem ser observadas através de qualquer medição. Consulte [as medidas de Pauli](xref:microsoft.quantum.concepts.pauli) para mais detalhes. |
|Medida|Obtenção de uma broca clássica a partir de um qubit (ou conjunto de qubits). Consulte a secção [Qubit Concepts](xref:microsoft.quantum.concepts.qubit) para mais detalhes.|
|Mutável|Uma variável cujo valor pode ser alterado após a sua criação.|
|Espaço de Nomes|Uma etiqueta para uma coleção de nomes relacionados (normalmente operações, funções e tipos). Por exemplo, o espaço de nome [`Microsoft.Quantum.Preparation`](xref:microsoft.quantum.preparation) rotula todos os símbolos definidos na biblioteca padrão que ajudam na preparação dos estados iniciais.|
|Operação|A unidade básica de execução quântica em Q#. É aproximadamente equivalente à função C, C++ ou Python ou a um método estático em C# ou Java.|
|Pedido do Operador|A fazer uma operação quântica. Isto aplica tipicamente uma matriz unitária ao vetor de estado atual. Consulte [a Introdução aos Conceitos Quânticos](xref:microsoft.quantum.concepts.intro) para obter mais detalhes.|
|Oracle|Uma subrotina que fornece informações dependentes de dados a um algoritmo quântico no tempo de execução. Tipicamente, o objetivo é fornecer uma superposição de saídas correspondentes a inputs que estão em superposição.   |
|Aplicação parcial|Chamar uma função ou operação sem todos os parâmetros necessários. O retorna um novo callable que só precisa dos parâmetros em falta fornecidos durante uma futura aplicação.|
|Operadores Pauli|O `X`, `Y` e `Z` portões quânticos.|
|Prelúdio|O conjunto de operações e funções primitivas e clássicas definidas por cada máquina-alvo individual, em vez de ao nível Q#.|
|Circuito Quântico|A representação de um programa para um computador quântico. Consulte a secção <xref:microsoft.quantum.concepts.circuits> para mais detalhes.|
|Estado Quântico|Uma representação dos qubits no sistema. Isto é geralmente denotado como um vetor de coluna complexa. Para mais informações, consulte <xref:microsoft.quantum.concepts.vectors>. |
|Qubit|Unidade de armazenamento quântico. Consulte a secção <xref:microsoft.quantum.concepts.qubit> para mais detalhes.|
|Repetir até ao sucesso|Um algoritmo quântico que probabilisticamente sucede. Após o fracasso, a rotina voltará a tentar até que tenha sido atingido um limite (ou um limite tenha sido atingido). |
|Máquina-alvo|Um alvo de compilação que reduz um programa quântico abstrato para hardware ou simulação. Isto normalmente inclui re-writes para muitos fins, incluindo a substituição do portão, codificação para correção de erros, layout geométrico e outros.|
|Rio Tuple|Os tipos separados da vírem agruparam-se através de parênteses. |
|Tipo definido pelo utilizador|Recolha de tipos incorporados ou previamente definidos que possam ser referidos como uma única unidade.|

