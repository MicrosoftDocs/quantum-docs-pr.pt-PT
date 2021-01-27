---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: Aplicar operaçãoQuantumFourierTransform
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: d99000c21c79d2ca97b1fe92ad331c7ba8599700
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844765"
---
# <a name="applyquantumfouriertransform-operation"></a>Aplicar operaçãoQuantumFourierTransform

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Executa a Transformação Quântica Fourier num registo quântico contendo um número inteiro na representação pouco endiuense.

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="qs--littleendian"></a>qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registo quântico ao qual é aplicada a Transformação Quantum Fourier



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Presume-se que a entrada e a saída estão em pequena codificação endiana.

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)