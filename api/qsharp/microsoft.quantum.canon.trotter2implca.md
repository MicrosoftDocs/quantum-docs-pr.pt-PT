---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Operação Trotter2ImplCA
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 98ba4db45fa7b7e8f442ba166929142aac4fa5a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715312"
---
# <a name="trotter2implca-operation"></a>Operação Trotter2ImplCA

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [](https://nuget.org/packages/)


Implementação do integrador Trotter-Suzuki de segunda ordem.

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit
```


## <a name="input"></a>Entrada

### <a name="nsteps--int"></a>nSteps : [Int](xref:microsoft.quantum.lang-ref.int)

O número de operações a decompor-se em etapas temporais.


### <a name="op--intdoublet--unit-adj--ctl"></a>op :[(Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl

Uma operação que aceita uma entrada de índice `Int` (tipo) e uma entrada de tempo (tipo) e um registo `Double` quântico `'T` (tipo) para decomposição.


### <a name="stepsize--double"></a>stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)

Multiplicador no tamanho de cada passo da simulação.


### <a name="target--t"></a>alvo : 'T

Um registo quântico no qual as operações atuam.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo que cada passo deve ser pisado; tipicamente, ou `Qubit[]` ou `Qubit` . .