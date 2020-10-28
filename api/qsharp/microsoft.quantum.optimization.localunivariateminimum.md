---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: Função LocalUnivariateMinimum
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: 3b09af88bbed20a392768d005e5e9567b3bb7022
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711017"
---
# <a name="localunivariateminimum-function"></a>Função LocalUnivariateMinimum

Espaço de nome: [Microsoft.Quantum.Otimização](xref:Microsoft.Quantum.Optimization)

Pacote: [](https://nuget.org/packages/)


Devolve o mínimo local para uma função univariada durante um intervalo limitado, utilizando uma busca de intervalo dourado.

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a>Entrada

### <a name="fn--double---double"></a>fn : [Duplo](xref:microsoft.quantum.lang-ref.double) -> [Duplo](xref:microsoft.quantum.lang-ref.double)

A função univariada a ser minimizada.


### <a name="bounds--doubledouble"></a>limites :[(Duplo,](xref:microsoft.quantum.lang-ref.double)[Duplo)](xref:microsoft.quantum.lang-ref.double)

O intervalo em que se encontra o mínimo local.


### <a name="tolerance--double"></a>tolerância : [Duplo](xref:microsoft.quantum.lang-ref.double)

A precisão na entrada da função a ser tolerada.
A procura por optima local continuará até que o intervalo seja menor em largura do que esta tolerância.



## <a name="output--univariateoptimizationresult"></a>Saída : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)

Um optima local da função dada, localizada dentro dos limites dados.