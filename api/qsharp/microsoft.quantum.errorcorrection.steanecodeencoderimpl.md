---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: Operação SteaneCodeEncoderImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: b843422a6007d01de9b57ec659c229b8ab0ad2e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712190"
---
# <a name="steanecodeencoderimpl-operation"></a>Operação SteaneCodeEncoderImpl

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [](https://nuget.org/packages/)


Operação privada usada para implementar o codificador de código Steane e o descodificador.

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="data--qubit"></a>dados : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

uma matriz segurando 1 qubit que é o qubit de entrada.


### <a name="scratch--qubit"></a>risca: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

uma matriz segurando 6 qubits que adicionam redundância.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

