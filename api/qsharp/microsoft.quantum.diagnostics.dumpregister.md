---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: Função DespesoRegista
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: 835c7a9edb22b4be630ebfc04587c12b3ff668b2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829221"
---
# <a name="dumpregister-function"></a>Função DespesoRegista

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Despeja o estado atual da máquina-alvo associada aos qubits dados.

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="location--t"></a>localização : 'T

Fornece informações sobre onde gerar o lixo do estado.


### <a name="qubits--qubit"></a>qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A lista de qubits a relatar.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

Nenhum.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="remarks"></a>Observações

Este método permite-lhe despejar as informações associadas ao estado dos qubits dados num ficheiro ou em qualquer outro local.
A informação real gerada e a semântica `location` são específicas de cada máquina alvo. No entanto, fornecer um tuple vazio como uma localização `()` () normalmente significa gerar a saída para a consola.

Para o simulador de estado completo local distribuído como parte do Kit de Desenvolvimento Quântico, este método espera uma cadeia com o caminho para um ficheiro no qual escreverá o estado dos qubits dados (isto é, a função de onda do subsistema correspondente) como uma matriz unidimensional de números complexos, em que cada elemento representa as amplitudes da probabilidade de medir o estado correspondente.
Se os qubits dados estiverem emaranhados com outro qubit e o seu estado não puder ser separado, apenas relata que os qubits estão emaranhados.