---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: Função BlockEncodingByLCU
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 04738aa54ce8b719b05954824e3553388a995df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724864"
---
# <a name="blockencodingbylcu-function"></a>Função BlockEncodingByLCU

Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)

Pacote: [](https://nuget.org/packages/)


Codifica um operador de interesse em `BlockEncoding` um .

Isto constrói um `BlockEncoding` $U unitário=P\cdot V\cdot P^\dagger$ que codifica algum operador $H=\sum_{j}/\alpha_j/ U_j de juros que é uma combinação linear de unitários. Tipicamente, $P$ é um unitário de preparação de estado tal que $P\ket {0} \_ a=\sum_j\sqrt{\alpha_j/ \| \vec\alpha \| \_ 2}\ket{j} \_ a$, e $V=sum_{j}ket{j}\bra{j} \_ a\otimes U_j$.

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="statepreparation--t--unit-adj--ctl"></a>estatalPreparação : 'T = [Unit](xref:microsoft.quantum.lang-ref.unit) unidade> Adj + Ctl

Um $P$ unitário que prepara algum estado-alvo.


### <a name="selector--ts--unit-adj--ctl"></a>seletor : ('T'S) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl

Um $V$ unitário que codifica as unidades componentes de $H$.



## <a name="output--ts--unit-adj--ctl"></a>Saída : ('T'S) => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl

Um $U$ unitário agindo conjuntamente em registos `a` e `s` que codifica $H$, e satisfaz $U^\dagger = U$.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T


### <a name="s"></a>'S



## <a name="remarks"></a>Observações

Esta `BlockEncoding` implementação confere-lhe as propriedades de um `BlockEncodingReflection` .

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Simulation.BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft.Quantum.Simulation.BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)