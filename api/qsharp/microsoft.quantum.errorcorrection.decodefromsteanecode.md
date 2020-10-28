---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: Descodificar OperaçãoFromSteaneCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: e6831a8630c0a80c2abe7c4a720263f0de03edc4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712417"
---
# <a name="decodefromsteanecode-operation"></a>Descodificar OperaçãoFromSteaneCode

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [](https://nuget.org/packages/)


Uma operação de codificação inversa que mapeia um registo quântico não codificado para um registo quântico codificado sob o código quântico de ⟦7, 1, 3⟧ Steane.

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a>Entrada

### <a name="logicalregister--logicalregister"></a>LogicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Uma série de qubits que representam o estado lógico codificado do código 5-qubit.



## <a name="output--qubitqubit"></a>Saída :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])

Uma matriz qubit de comprimento 1 representando o estado não codificado no primeiro parâmetro, juntamente com qubits auxiliares no segundo parâmetro.

## <a name="remarks"></a>Observações

O descodificador escolhido utiliza a propriedade de código CSS do código ⟦7, 1, 3⟧ código Steane, ou seja, corrige erros X e Z separadamente. Uma propriedade do código é que a localização do X, respectivamente, a correção Z a aplicar é a codificação de 3 bits do X, respectivamente, síndrome de Z quando considerada um inteiro.

## <a name="references"></a>Referências

- D. Gottesman, "Códigos estabilizadores e Correção de Erros Quânticos", Tese de Doutoramento, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [Microsoft.Quantum.ErrorCorrection.LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)