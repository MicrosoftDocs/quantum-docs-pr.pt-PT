---
uid: Microsoft.Quantum.Canon.QFT
title: Operação QFT
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: e5b40be6c86647205fe1c764b6b043272296a354
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715651"
---
# <a name="qft-operation"></a>Operação QFT

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Executa a Transformação Quântica Fourier num registo quântico contendo um número inteiro na representação de grandes pontas.

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a>Entrada

### <a name="qs--bigendian"></a>qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Registo quântico ao qual é aplicada a Transformação Quantum Fourier



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Presume-se que a entrada e a saída estão em grande codificação endiana.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)