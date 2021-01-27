---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: Função BlockEncodingToReflection
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: bada0dcc54d2a8d67cf7383d7153c7f46a4a8415
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847263"
---
# <a name="blockencodingtoreflection-function"></a>Função BlockEncodingToReflection

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Converte um `BlockEncoding` em `BLockEncodingReflection` equivalente.

Ou seja, dado um `BlockEncoding` $U$ unitário que codifica algum operador $H de juros, converte-o num `BlockEncodingReflection` $U'$ que codifica o mesmo operador, mas também satisfaz $U'^\dagger = U'$.
Isto aumenta o tamanho do registo auxiliar de $U$ por um qubit.

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a>Entrada

### <a name="blockencoding--blockencoding"></a>blockEncoding : [BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)

Um `BlockEncoding` $U unitário para ser convertido num reflexo.



## <a name="output--blockencodingreflection"></a>Saída : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

Um $U unitário'$ agindo conjuntamente em registos `a` e `s` que codifica $H$, e satisfaz $U'^\dagger = U'$.

## <a name="remarks"></a>Observações

Isto aumenta o tamanho do registo auxiliar de $U$ por um qubit.

## <a name="references"></a>Referências

- Simulação Hamiltonian por Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Simulation.BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft.Quantum.Simulation.BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)