---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: Preparar operação DesingleQubitIdentity
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: c6c9b5724354d6ee034dd8b6733901ebdd8072d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856875"
---
# <a name="preparesinglequbitidentity-operation"></a>Preparar operação DesingleQubitIdentity

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Prepara um qubit no estado máximo misturado.

Prepara o qubit dado no estado $\boldone / 2$ aplicando o canal despolarizante $$ \start{align} \Omega(\rho) \mathrel{:=} {1} {4} \frac \sum_{\mu \in \{ 0, 1, 2, 3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu}{\\dagger}, \end{align} $$ where $\sigma \_ i$ é o operador de pauli $i$th, e onde $\rho$ é um operador de densidade que representa um estado misto.

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a>Entrada

### <a name="qubit--qubit"></a>qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Um qubit cujo estado deve ser despolarizado da maneira acima descrita.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

O estado misto $\boldone / 2$ descrevendo o resultado da aplicação desta operação a um estado implicitamente descreve um valor de expectativa sobre as escolhas aleatórias feitas nesta operação.
Assim, para qualquer aplicação, esta operação mapeia estados puros para estados puros, mas age como descrito na expectativa.
Em particular, esta operação pode ser utilizada em tomografia de processo para medir os componentes *não unitais* de um canal.