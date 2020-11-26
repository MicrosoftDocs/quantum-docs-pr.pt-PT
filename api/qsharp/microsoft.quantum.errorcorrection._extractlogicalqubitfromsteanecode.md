---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: operação _ExtractLogicalQubitFromSteaneCode
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: 273692efa629cb8cc20069ef500c4e0902fbc3ff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201347"
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