---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: Função SteaneCodeRecoveryX
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 0f6b987ca23bd9ff2076080d60f1ca756b36848e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712134"
---
# <a name="steanecoderecoveryx-function"></a>Função SteaneCodeRecoveryX

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [](https://nuget.org/packages/)


Descodificador para a parte X do grupo estabilizador do código quântico ⟦ 1, 3⟧ Steane.

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a>Entrada

### <a name="syndrome--syndrome"></a>síndrome : [Síndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

Uma matriz de síndrome obtida a partir da medição da parte X do estabilizador.



## <a name="output--pauli"></a>Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Um conjunto de operações de Pauli que, quando aplicadas ao sistema quântico codificado, corrige o erro correspondente a `syndrome` .

## <a name="remarks"></a>Observações

O descodificador escolhido utiliza a propriedade de código CSS do código ⟦7, 1, 3⟧ código Steane, ou seja, corrige erros X e Z separadamente. Uma propriedade do código é que a localização do X, respectivamente, a correção Z a aplicar é a codificação de 3 bits do X, respectivamente, síndrome de Z quando considerada um inteiro.

## <a name="references"></a>Referências

- D. Gottesman, "Códigos estabilizadores e Correção de Erros Quânticos", Tese de Doutoramento, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)