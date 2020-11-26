---
uid: Microsoft.Quantum.Math.PlusA
title: Função PlusA
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: fe19c5d2e075624516376a5d5fa49014acb295ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194836"
---
# <a name="plusa-function"></a>Função PlusA

Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve a soma (concatenação) de duas entradas.

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a>Entrada

### <a name="a--element"></a>a : «Elemento].

A primeira entrada $a$ a ser resumida.


### <a name="b--element"></a>b : «Elemento].

A segunda entrada $b$ a resumir.



## <a name="output--element"></a>Saída : «Elemento[]

A soma $a + b$.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="element"></a>'Elemento

O tipo de cada elemento em cada uma das duas matrizes de entrada.