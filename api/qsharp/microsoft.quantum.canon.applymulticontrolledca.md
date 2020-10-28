---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: Aplicam a operação ApplyMultiControlledCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 5662efe0dc6f665206b8773596bf885ce631413c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717961"
---
# <a name="applymulticontrolledca-operation"></a>Aplicam a operação ApplyMultiControlledCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Aplica uma versão controlada por multiplicação de uma operação controlada por singingly.
O modificador `CA` indica que a operação de um único qubit é controlável e adjacente.

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="singlycontrolledop--qubit--unit-adj"></a>singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj

Uma operação controlada num único qubit.
O primeiro qubit no argumento da operação assumido como um controlo e os restantes são assumidos como qubits alvo.
`ApplyMultiControlled` sempre chama `singlyControlledOp` com um argumento de comprimento pelo menos 1.


### <a name="ccnot--ccnotop"></a>ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

O portão NÃO controlado controlado para a construção.


### <a name="controls--qubit"></a>controlos: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Os qubits que `singlyControlledOp` devem ser controlados.
O comprimento `controls` deve ser de, pelo menos, 1.


### <a name="targets--qubit"></a>alvos : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

O alvo qubits que `singlyControlledOp` atua.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Esta operação utiliza apenas qubits de ancilla limpos.

Para a explicação e diagrama do circuito ver Figura 4.10, Secção 4.3 em Nielsen & Chuang

## <a name="references"></a>Referências

- [*Michael A. Nielsen , Isaac L. Chuang,* Quantum Computation e Quantum Information](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyMultiControlledC](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)