---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: Função TableLookupRecovery
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: 9f957155e42bb6b5163521171fcba5897f290335
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824403"
---
# <a name="tablelookuprecovery-function"></a>Função TableLookupRecovery

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Para uma dada tabela de operações da Pauli num dado registo de qubits, esta função devolve um objeto de tipo `RecoveryFn` que contém todas as informações necessárias para a realização de uma desacoplamento de mesa no que diz respeito à determinada gama de operações da Pauli.

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a>Entrada

### <a name="table--pauli"></a>tabela : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][ ]

Tabela de operações da Pauli que operam num dado registo qubit



## <a name="output--recoveryfn"></a>Saída : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Um objeto do tipo `RecoveryFn` , isto é, um mapa `Syndrome -> Pauli[]` que associa a uma determinada matriz de síndrome uma operação de correção de Pauli correspondente.