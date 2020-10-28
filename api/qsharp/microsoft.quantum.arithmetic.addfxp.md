---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: Operação AddFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: cf1f1379b7e1c32aefb0fccb55f4d13c95c78d8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721702"
---
# <a name="addfxp-operation"></a>Operação AddFxP

Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)

Pacote: [](https://nuget.org/packages/)


Adiciona dois números de ponto fixo armazenados em registos quânticos.

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="description"></a>Descrição

Tendo em conta dois registos de ponto fixo, respectivamente nos estados $\ket{f_1}$ e $\ket{f_2},, executa a operação $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.

## <a name="input"></a>Entrada

### <a name="fp1--fixedpoint"></a>FP1 : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Primeiro número de ponto fixo


### <a name="fp2--fixedpoint"></a>FP2 : [Ponto Fixo](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

O segundo número de ponto fixo será atualizado para conter a soma das duas entradas.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

A implementação atual requer que os dois números de ponto fixo tenham a mesma posição de ponto contando a partir da parte menos significativa, ou seja, $n_i$ e $p_i$ devem ser iguais.