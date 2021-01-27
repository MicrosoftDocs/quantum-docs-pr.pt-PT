---
uid: Microsoft.Quantum.Math.PlusA
title: Função PlusA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 14e9bfdbe4b70b4730e5bfc64a0ee81ab3cecaaf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842707"
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