---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: Aplicar E operar
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 5a4e18cb0361708e1fc00e8d62c0a6c2415d6bed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718462"
---
# <a name="applyand-operation"></a>Aplicar E operar

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Inverte um determinado qubit de alvo se e somente se ambos os qubits de controlo estiverem no estado 1, utilizando a medição para efetuar a operação adjacente.

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="description"></a>Descrição

Inverta `target` se e somente se ambos os controlos forem 1, mas assume que `target` está no estado 0.  A operação tem a contagem T 4, a profundidade T 2 e não requer nenhum qubit de ajudante, podendo, portanto, ser preferível a uma operação CCNOT, se `target` se sabe que é 0.  O adjacente desta operação é baseado em medição e não requer portões T.

A aplicação controlada desta operação não requer qubit, `2^c` `Rz` portões e não está otimizado para profundidade, onde `c` está o número de qubits de controlo geral, incluindo os dois controlos da `ApplyAnd` operação.  A aplicação controlada adjacente requer `2^c - 1` `Rz` portões (com um ângulo duas vezes maior do que a operação não adjacente), nenhum qubit de ajudante e não está otimizado para profundidade.

## <a name="input"></a>Entrada

### <a name="control1--qubit"></a>controle1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Primeiro qubit de controlo


### <a name="control2--qubit"></a>controlo2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Segundo qubit de controlo


### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit auxiliar de destino; deve estar no estado 0



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referências

- Cody Jones: "Novas construções para o portão toffoli tolerante a falhas", Phys. Rev. A 87, 022328, 2013 [arXiv:1212.5069](https://arxiv.org/abs/1212.5069) doi:10.1103/PhysRevA.87.022328
- Craig Gidney: "Reduzir para metade o custo da adição quântica", Quantum 2, página 74, 2018 [arXiv:1709.06648](https://arxiv.org/abs/1709.06648) doi:10.1103/PhysRevA.85.044302
- Mathias Soeken: "Circuitos Quânticos do Oráculo e o Padrão da Árvore de Natal", [artigo de blog de 19 de dezembro de 2019](https://msoeken.github.io/blog_qac.html) (nota: explica a construção múltipla controlada)