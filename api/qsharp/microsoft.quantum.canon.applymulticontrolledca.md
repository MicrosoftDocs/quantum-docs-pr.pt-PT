---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: Aplicam a operação ApplyMultiControlledCA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: a6549084b1c2fda885823f451d17f9c2ebbb4600
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841686"
---
# <a name="applymulticontrolledca-operation"></a>Aplicam a operação ApplyMultiControlledCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma versão controlada por multiplicação de uma operação controlada por singingly.
O modificador `CA` indica que a operação de um único qubit é controlável e adjacente.

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrada

### <a name="singlycontrolledop--qubit--unit--is-adj"></a>singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [> Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj

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