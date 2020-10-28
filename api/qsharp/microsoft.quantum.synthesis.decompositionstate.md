---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: Decomposição Esclarou o tipo definido pelo utilizador
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: 0547c04828a80b4f696cc17e13c8cc57d0379f96
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725214"
---
# <a name="decompositionstate-user-defined-type"></a>Decomposição Esclarou o tipo definido pelo utilizador

Espaço de nome: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacote: [](https://nuget.org/packages/)


Estado durante a decomposição com base em índices variáveis

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a>Itens nomeados

### <a name="perm--int"></a>Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]


### <a name="lfunctions--bigintint"></a>Funções : ([BigInt,](xref:microsoft.quantum.lang-ref.bigint)[Int](xref:microsoft.quantum.lang-ref.int))[]


### <a name="rfunctions--bigintint"></a>Rfunctions : ([BigInt,](xref:microsoft.quantum.lang-ref.bigint)[Int](xref:microsoft.quantum.lang-ref.int)[]



## <a name="description"></a>Descrição

O Estado detém a permutação atual e as funções atualmente geradas para portões controlados à esquerda, e portões controlados à direita.