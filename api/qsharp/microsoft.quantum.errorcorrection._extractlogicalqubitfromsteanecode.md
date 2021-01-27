---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: operação _ExtractLogicalQubitFromSteaneCode
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: fe64343e30a0a3f0d05382e7812d37d5b13133d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853220"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a>operação _ExtractLogicalQubitFromSteaneCode

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Medição da síndrome e o inverso da incorporação.

$X os estabilizadores de $- e $Z não são tratados de forma igual, o que se deve à escolha particular do circuito de codificação.
Esta assimetria leva a uma rotina de extração de síndrome diferente.
Pode-se medir a síndrome medindo o operador pauli multi-qubit diretamente no estado de código, mas para o propósito de destilação o qubit lógico é devolvido a um único qubit, no decurso do qual as medições da síndrome podem ser feitas sem mais ancillas.

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a>Entrada

### <a name="code--logicalregister"></a>código : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)





## <a name="output--qubitintint"></a>Saída :[(Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Int,](xref:microsoft.quantum.lang-ref.int)[Int)](xref:microsoft.quantum.lang-ref.int)

O qubit lógico e um par de inteiros para $X síndrome de $-síndrome e $Z de $-síndrome.
Representam o índice do qubit de código no qual um único $X$- ou $Z$-error teria causado a síndrome medida.

## <a name="remarks"></a>Observações

Note que esta operação não está marcada como , uma vez que `internal` os testes unitários dependem diretamente desta operação. Como melhoria futura, os testes unitários devem ser refaccionados para depender apenas de chamadas públicas diretamente.

> [!WARNING]
> Esta rotina é adaptada a um circuito de codificação específico para o código 7 qubit da Steane; se o circuito de codificação for modificado, então o resultado da síndrome pode ter de ser interpretado de forma diferente.