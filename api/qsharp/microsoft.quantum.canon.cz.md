---
uid: Microsoft.Quantum.Canon.CZ
title: Operação CZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: cef1544fb76d561cfd0949c84c487550d523bb85
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840696"
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