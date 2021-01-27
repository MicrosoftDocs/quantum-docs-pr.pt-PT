---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: Operação FiveQubitCodeEncoderImpl
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 0a40d9674c011567b2fa9c838f31a0ee115e4268
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826086"
---
# <a name="fivequbitcodeencoderimpl-operation"></a>Operação FiveQubitCodeEncoderImpl

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Operação privada usada para implementar tanto o codificador de 5 qubits como o descodificador.

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Entrada

### <a name="data--qubit"></a>dados : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

uma matriz segurando 1 qubit que é o qubit de entrada.


### <a name="scratch--qubit"></a>risca: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

uma matriz segurando 4 qubits que adicionam redundância.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

O codificador específico escolhido foi retirado do papel V. Kliuchnikov e D. Maslov, "Otimização dos Circuitos Clifford", Phys. Rev. Rev. Rev. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figura 4b) e requer um total de 11 portões.