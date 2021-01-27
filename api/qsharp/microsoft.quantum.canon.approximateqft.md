---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: Operação AproximadaQFT
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 31fd87c0f61292142c7493cc29cad1082a9a2d67
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850329"
---
# <a name="approximateqft-operation"></a>Operação AproximadaQFT

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplique a Transformação Quântica Aproximada (AQFT) num registo quântico.

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="a--int"></a>a : [Int](xref:microsoft.quantum.lang-ref.int)

parâmetro de aproximação que determina a que nível são podadas as rotações Z controladas que ocorrem no circuito QFT.

O parâmetro de aproximação a determina o nível de poda das rotações Z, ou seja, um ∈ {0.n} e todas as rotações Z 2π/2k onde k>a são removidas do circuito QFT. Sabe-se que por k >= log2(n)+log2(1/ε)+3 pode-se ligar || QFT-AQFT||<ε.


### <a name="qs--bigendian"></a>qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

registo quântico de n qubits aos quais é aplicada a Transformação Aproximada De QuatroS quânticos.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

AQFT requer portões de rotação Z dos portões formulário 2π/2k e Hadamard.

Presume-se que a entrada e a saída estão codificadas na codificação de grandes endians.

## <a name="references"></a>Referências

- [*M. Roetteler, Th. Beth,* Appl. Álgebra Eng. Commun. Computação. 19(3): 177-193 (2008)](http://doi.org/10.1007/s00200-008-0072-2)
- [*D. Coppersmith* arXiv:quant-ph/0201067v1](https://arxiv.org/abs/quant-ph/0201067)