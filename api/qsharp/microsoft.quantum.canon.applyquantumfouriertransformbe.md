---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: Aplicar operaçãoQuantumFourierTransformBE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: d15310298dc138bdffb612895bbf20ca1371db6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717790"
---
# <a name="applyquantumfouriertransformbe-operation"></a>Aplicar operaçãoQuantumFourierTransformBE

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Executa a Transformação Quântica Fourier num registo quântico contendo um número inteiro na representação de grandes pontas.

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a>Entrada

### <a name="qs--bigendian"></a>qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Registo quântico ao qual é aplicada a Transformação Quantum Fourier



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Presume-se que a entrada e a saída estão em grande codificação endiana.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApproximateQFT](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [Microsoft.Quantum.Canon.QFTLE](xref:Microsoft.Quantum.Canon.QFTLE)