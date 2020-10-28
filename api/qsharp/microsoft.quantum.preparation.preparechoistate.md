---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: Preparar OperaçãoChoiState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiłkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: 8b2917a7d9414539f2f7c821c4115fc4b21d0373
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723999"
---
# <a name="preparechoistate-operation"></a>Preparar OperaçãoChoiState

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [](https://nuget.org/packages/)


Prepara o estado Choi-Jamiłkowski para uma determinada operação em dados registos de referência e alvo.

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="op--qubit--unit"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Operação $\Lambda$ cujo estado choi-Jamiłkowski $J(\Lambda) / 2^N$ está para ser preparado, onde $N$ é o número de qubits em que `op` atua.


### <a name="reference--qubit"></a>referência: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo de qubits a partir do estado $\ket{00\cdots 0}$ para ser usado como referência para a ação de `op` .


### <a name="target--qubit"></a>alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Um registo de qubits inicialmente no estado $\ket{00\cdots 0}$ em que `op` deve ser aplicado.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

O estado de Choi-Jamiłkowski $J(\Lambda)$ de um processo quântico é definido como $$ \start{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (\boldone\rangle \! \rangle\langle \! \langle\boldone; \end{align} X\rangle \! \rangle$ é a *vectorização* de uma matriz $X$ na convenção de empilhamento de colunas. Aprender uma descrição clássica deste estado fornece informações completas sobre o efeito de $\Lambda$ agindo em estados de entrada arbitrária, e forma a base da tomografia do *processo quântico.*

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Preparation.PrepareChoiStateA](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [Microsoft.Quantum.Preparation.PrepareChoiStateC](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [Microsoft.Quantum.Preparation.PrepareChoiStateCA](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)