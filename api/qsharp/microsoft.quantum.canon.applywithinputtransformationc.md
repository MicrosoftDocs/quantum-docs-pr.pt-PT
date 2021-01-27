---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: Aplicação ComInputTransformationC operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: d877fedbc0caa1a9ebc87d80cbce9ab54ca20d88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850360"
---
# <a name="applywithinputtransformationc-operation"></a>Aplicação ComInputTransformationC operação

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dada uma operação que aceita alguma entrada, uma função que devolve uma saída compatível com essa operação, e uma entrada para essa função, aplica a operação utilizando a função para transformar a entrada num formulário esperado pela operação.

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit is Ctl
```


## <a name="input"></a>Entrada

### <a name="fn--u---t"></a>fn : 'U -> 'T

Uma função que transforma a entrada dada num formulário esperado pela operação.


### <a name="op--t--unit--is-ctl"></a>op : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é CTL

A operação a ser aplicada.


### <a name="input--u"></a>entrada : 'U

Uma entrada para a função.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T


### <a name="u"></a>'U



## <a name="example"></a>Exemplo

A chamada a seguir @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" utiliza-se para aplicar uma operação concebida para @"Microsoft.Quantum.Arithmetic.BigEndian" entradas numa entrada do @"Microsoft.Quantum.Arithmetic.LittleEndian" tipo:

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a>Consulte também

- [Microsoft.Quantum.Canon.ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft.Quantum.Canon.ApplyWithInputTransformationa](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [Microsoft.Quantum.Canon.ApplyWithInputTransformationCA](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [Microsoft.Quantum.Canon.TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)