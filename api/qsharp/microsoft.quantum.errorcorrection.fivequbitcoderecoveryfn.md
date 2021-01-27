---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 94b6c12f31b0e6367151d0ebb225cff5f82915e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853135"
---
# <a name="fivequbitcoderecoveryfn-function"></a>FiveQubitCodeRecoveryFn

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retorna a função que mapeia as medições da síndrome de erro para os operadores Pauli que corrigem erros apropriados para a procura de tabela para o código quântico ⟦5, 1, 3⟧.

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a>Saída : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)

Função do tipo `RecoveryFn` que faz uma medição de síndrome e `Result[]` devolve os `Pauli[]` operadores que corrigem o erro detetado.

## <a name="remarks"></a>Observações

Ao iterar todos os erros de peso $1$, obtemos um total de $3\times 5=15$ possíveis síndromes não triviais.
Juntamente com a identidade, uma tabela de erros e síndrome correspondente é construída. Para o código de 5 qubits esta tabela é dada por: $X \_ 1: (0,0,0,1); X \_ 2: (1,0,0,0); X \_ 3: (1,1,0,0); X \_ 4: (0,1,1,0); X \_ 5: (0,0,1,1)$, $Z \_ 1: (1,0,1,0); Z \_ 2: (0,1,0,1); Z \_ 3: (0,0,1,0); Z \_ 4: (1,0,0,1); Z \_ 5: (0,1,0,0)$ com $Y_i$ obtido adicionando as síndromes de $X_i$ e $Z_i$. Note que a encomenda na recuperação de procura da tabela é dada através da conversão dos bitvectors para inteiros (utilizando pouco endian).

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.ErrorCorrection.RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)