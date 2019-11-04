---
title: Glossário da computação Quantum | Microsoft Docs
description: Glossário de termos do Quantum
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: ce15fee2be68d41f0b806be50320b562a749c3b7
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442551"
---
# <a name="quantum-computing-glossary"></a>Glossário da computação Quantum

|Termo|Definição|
|-------------|----------|
|Adjacente|A transpoção conjugada complexa da operação. Para operações que implementam um operador unitário, o adjacente é o inverso da operação.|
|Acessível|Operações e funções são conhecidas coletivamente como *callablefiles*.|
|Padrão|Operações e funções definidas em Q # compilando na lógica definida no prelúdio. A implementação da biblioteca padrão é independente em relação aos computadores de destino.|
|Grupo de Clifford|O conjunto de operações que ocupam o octants da esfera de Bloch. Eles incluem: `X`, `Y`, `Z`, `H` e `S`|
|Controlado|Uma operação Quantum que usa um ou mais qubits como habilitadores para a operação de destino.|
|Notação de Dirac|Uma representação abreviada do estado Quantum. Consulte a seção [notação de Dirac](xref:microsoft.quantum.concepts.dirac) para obter mais detalhes.|
|Eigenvalues e eigenvectors|Consulte a [seção matriz avançada](xref:microsoft.quantum.concepts.matrix-advanced) para obter detalhes.|
|Par de EPR|Também conhecido como [estado de sino](https://en.wikipedia.org/wiki/Bell_state)|
|Evolucionário|Como o estado muda ao longo do tempo. Consulte a seção em <xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials> para obter um exemplo. |
|Função|Rotinas puramente clássicas na linguagem Q #|
| <a id="global-phase"></a>Fase global | Dois Estados que são idênticos até um múltiplo de um número complexo $e ^ {i\phi} $ são considerados diferentes para uma fase global. Ao contrário das fases locais, as fases globais não podem ser observadas em nenhuma medida. Consulte [Pauli medições](xref:microsoft.quantum.concepts.pauli) para obter mais detalhes. |
|Medida|Obtendo um bit clássico de um qubit (ou conjunto de qubits). Consulte a seção [conceitos do qubit](xref:microsoft.quantum.concepts.qubit) para obter mais detalhes.|
|Mutável|Uma variável cujo valor pode ser alterado após ser criada.|
|Namespace|Um rótulo para uma coleção de nomes relacionados (normalmente, operações, funções e tipos). Por exemplo, o namespace [`Microsoft.Quantum.Preparation`](xref:microsoft.quantum.preparation) rotula todos os símbolos definidos na biblioteca padrão que ajudam na preparação de Estados iniciais.|
|Operação|A unidade básica de execução Quantum em Q #. É aproximadamente equivalente à função C, C++ ou Python ou a um método estático em C# ou Java.|
|Aplicativo do operador|Executando uma operação Quantum. Isso normalmente aplica uma matriz unitário ao vetor de estado atual. Consulte [introdução aos conceitos do Quantum](xref:microsoft.quantum.concepts.intro) para obter mais detalhes.|
|Oracle|Uma sub-rotina que fornece informações dependentes de dados para um algoritmo Quantum em tempo de execução. Normalmente, o objetivo é fornecer uma superposição de saídas correspondentes às entradas que estão em superposição.   |
|Aplicativo parcial|Chamar uma função ou operação sem todos os parâmetros necessários. O retorna um novo callable que precisa apenas dos parâmetros ausentes fornecidos durante um aplicativo futuro.|
|Operadores Pauli|O `X`, `Y` e `Z` de Gates da Quantum.|
|Prelúdio|O conjunto de operações e funções primitivas e clássicas definidas por cada computador de destino individual, em vez de no nível Q #.|
|Circuito Quantum|A representação de um programa para um computador Quantum. Consulte a seção <xref:microsoft.quantum.concepts.circuits> para obter mais detalhes.|
|Estado do Quantum|Uma representação do qubits no sistema. Isso geralmente é indicado como um vetor de coluna complexa. Para obter mais informações, consulte <xref:microsoft.quantum.concepts.vectors>. |
|qubit|Unidade de armazenamento Quantum. Consulte a seção <xref:microsoft.quantum.concepts.qubit> para obter mais detalhes.|
|Repetir-até-êxito|Um algoritmo Quantum que Probabilistic teve sucesso. Após a falha, a rotina tentará novamente até que tenha êxito (ou um limite tenha sido atingido). |
|Pilha de software|O conjunto completo de software clássico e Quantum, bem como os compiladores, simuladores e tempos de execução necessários para operar um computador Quantum. Consulte a seção <xref:microsoft.quantum.concepts.software-stack> para obter mais detalhes. |
|Computador de destino|Um destino de compilação que reduz um programa Quantum abstrato em direção a hardware ou simulação. Isso normalmente inclui regravações para muitas finalidades, incluindo substituição de portão, codificação para correção de erros, layout geométrico e outros.|
|Serem|Tipos separados por vírgulas agrupados por parênteses. |
|Tipo definido pelo usuário|Coleção de tipos internos ou definidos anteriormente que podem ser referidos como uma única unidade.|

