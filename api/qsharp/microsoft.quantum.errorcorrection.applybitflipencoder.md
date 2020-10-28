---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: Aplicação OperaçãoBitFlipEncoder
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: 4d78cbb5892aabc600321185641bbf217bd4d745
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712515"
---
# <a name="applybitflipencoder-operation"></a>Aplicação OperaçãoBitFlipEncoder

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [](https://nuget.org/packages/)


Operação privada usada para implementar tanto o codificader bit flip como o descodificador.

Note-se que este codificadora pode recorrer a uma recuperação coerente no local, caso em que irá "causar" o erro descrito pelo estado inicial de `auxQubits` .
Em particular, se `auxQubits` estiverem inicialmente no estado $\ket {10} $, isto causará um erro de $X_1$ no qubit codificado.

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="coherentrecovery--bool"></a>coerenteRecovery : [Bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="data--qubit"></a>dados : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="scratch--qubit"></a>risca: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referências

- doi:10.1103/PhysRevA.85.044302