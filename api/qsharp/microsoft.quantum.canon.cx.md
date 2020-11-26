---
uid: Microsoft.Quantum.Canon.CX
title: Operação CX
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 4eaecf372f3054de4886b1e42c6b4ce386a22f73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207246"
---
# <a name="cx-operation"></a>Operação CX

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica o portão controlado X (CX) a um par de qubits.

$$ \start{align} \left(\start{matrix} 1 & 0 & 0 & 0 \\ \\ & 1 & 0 & \\ \\ 0 & 0 & 0 & \\ \\ 10 & 0 & 1 & 0\end{matrix) \end{}) \end{}) \end{}) \end{}) \end{}) \end{}) \end{}) \end{}) \end align, {}} $$ onde linhas e colunas são organizadas como no guia de conceitos quânticos.

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit is Adj + Ctl
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