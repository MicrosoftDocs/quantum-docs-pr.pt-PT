---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: AplicarOperaçãoMultiControlledC
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: bf6b78cd18a827a9a4fd9d61dfd4d240de3503e9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844873"
---
# <a name="applymulticontrolledc-operation"></a>AplicarOperaçãoMultiControlledC

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Aplica uma versão controlada por multiplicação de uma operação controlada por singingly.
O modificador `C` indica que a operação de um único qubit é controlável.

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Ctl
```


## <a name="input"></a>Entrada

### <a name="singlycontrolledop--qubit--unit"></a>singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit)> 

Uma operação controlada num único qubit.
O primeiro qubit no argumento da operação é assumido como um controlo e os restantes são assumidos como qubits alvo.
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

- [Microsoft.Quantum.Canon.ApplyMultiControlledCA](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)