---
uid: Microsoft.Quantum.Canon.CX
title: Operação CX
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: c430525b71ad4ef0812d90a8ff20c41a5d5b8708
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716376"
---
# <a name="cx-operation"></a>Operação CX

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Aplica o portão controlado X (CX) a um par de qubits.

$$ \start{align} \left(\start{matrix} 1 & 0 & 0 & 0 \\ \\ & 1 & 0 & \\ \\ 0 & 0 & 0 & \\ \\ 10 & 0 & 1 & 0\end{matrix) \end{}) \end{}) \end{}) \end{}) \end{}) \end{}) \end{}) \end{}) \end align, {}} $$ onde linhas e colunas são organizadas como no guia de conceitos quânticos.

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="control--qubit"></a>controlo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Controlo do qubit para o portão CX.


### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit de alvo para o portão CX.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Equivalente a:

```qsharp
Controlled X([control], target);
```

e:

```qsharp
CNOT(control, target);
```