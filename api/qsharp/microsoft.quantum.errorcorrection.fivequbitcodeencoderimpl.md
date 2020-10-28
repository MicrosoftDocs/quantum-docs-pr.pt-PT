---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: Operação FiveQubitCodeEncoderImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 29b0f47ddffeae3ed4dfda4084304427418e02fd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712333"
---
# <a name="fivequbitcodeencoderimpl-operation"></a>Operação FiveQubitCodeEncoderImpl

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [](https://nuget.org/packages/)


Operação privada usada para implementar tanto o codificador de 5 qubits como o descodificador.

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="data--qubit"></a>dados : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

uma matriz segurando 1 qubit que é o qubit de entrada.


### <a name="scratch--qubit"></a>risca: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

uma matriz segurando 4 qubits que adicionam redundância.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

O codificador específico escolhido foi retirado do papel V. Kliuchnikov e D. Maslov, "Otimização dos Circuitos Clifford", Phys. Rev. Rev. Rev. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Figura 4b) e requer um total de 11 portões.