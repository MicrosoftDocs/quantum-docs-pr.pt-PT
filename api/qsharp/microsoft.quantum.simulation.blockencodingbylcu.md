---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: Função BlockEncodingByLCU
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 1d7890e96513817c127ef768f49c0b915ea22fa1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858165"
---
# <a name="blockencodingbylcu-function"></a>Função BlockEncodingByLCU

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Codifica um operador de interesse em `BlockEncoding` um .

Isto constrói um `BlockEncoding` $U unitário=P\cdot V\cdot P^\dagger$ que codifica algum operador $H=\sum_{j}|\alpha_j| U_j de juros que é uma combinação linear de unitários. Tipicamente, $P$ é um unitário de preparação de estado tal que $P\ket {0} \_ a=\sum_j\sqrt{\alpha_j/ \| \vec\alpha \| \_ 2}\ket{j} \_ a$, e $V=sum_{j}ket{j}\bra{j} \_ a\otimes U_j$.

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="statepreparation--t--unit--is-adj--ctl"></a>estatalPreparação : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl

Um $P$ unitário que prepara algum estado-alvo.


### <a name="selector--ts--unit--is-adj--ctl"></a>seletor : ('T'S) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl

Um $V$ unitário que codifica as unidades componentes de $H$.



## <a name="output--ts--unit--is-adj--ctl"></a>Saída : ('T'S) = [> Unidade](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl

Um $U$ unitário agindo conjuntamente em registos `a` e `s` que codifica $H$, e satisfaz $U^\dagger = U$.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T


### <a name="s"></a>'S



## <a name="remarks"></a>Observações

Esta `BlockEncoding` implementação confere-lhe as propriedades de um `BlockEncodingReflection` .

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Simulation.BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft.Quantum.Simulation.BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)