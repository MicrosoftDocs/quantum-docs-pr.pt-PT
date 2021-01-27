---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: Aplicar operaçãoQuantumFourierTransformBE
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: a1f4a0a5e94465fc8bf3af344e2e19ee0d1d15e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841571"
---
# <a name="applyquantumfouriertransformbe-operation"></a>Aplicar operaçãoQuantumFourierTransformBE

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Executa a Transformação Quântica Fourier num registo quântico contendo um número inteiro na representação de grandes pontas.

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
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