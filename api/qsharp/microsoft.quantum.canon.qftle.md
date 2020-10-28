---
uid: Microsoft.Quantum.Canon.QFTLE
title: Operação QFTLE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: f28f74d34fb4688739646da3dc12ae6734eb4ad4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715637"
---
# <a name="qftle-operation"></a>Operação QFTLE

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Executa a Transformação Quântica Fourier num registo quântico contendo um número inteiro na representação pouco endiuense.

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Entrada

### <a name="qs--littleendian"></a>qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registo quântico ao qual é aplicada a Transformação Quantum Fourier



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Presume-se que a entrada e a saída estão em pequena codificação endiana.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.QFT](xref:Microsoft.Quantum.Canon.QFT)