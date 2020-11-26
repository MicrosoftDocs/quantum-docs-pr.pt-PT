---
uid: Microsoft.Quantum.Canon.CZ
title: Operação CZ
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 419082dbf8f96a9fe2dfabeab77e1823cb59a8f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207212"
---
# <a name="cz-operation"></a>Operação CZ

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica o portão controlado-Z (CZ) a um par de qubits.

$$ \start{align} 1 & 0 & 0 & \\ \\ 0 & 0 & 0 & \\ \\ 0 & 0 & 1 & \\ \\ 0 & 0 & 0 & -1 \end{}, $$ onde as linhas e colunas são organizadas como guia no conceito quântico.

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="control--qubit"></a>controlo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Controlo qubit para o portão CZ.


### <a name="target--qubit"></a>alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit de alvo para o portão CZ.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Equivalente a:

```qsharp
Controlled Z([control], target);
```