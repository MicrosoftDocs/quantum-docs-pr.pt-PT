---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Medidas ComScratch
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 4173aa9daac08a3febdfcbf12dc236f797685436
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854650"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="ed7ba-102">Medidas ComScratch</span><span class="sxs-lookup"><span data-stu-id="ed7ba-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="ed7ba-103">Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="ed7ba-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="ed7ba-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ed7ba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ed7ba-105">Mede o operador pauli dado utilizando um qubit de risco explícito para efetuar a medição.</span><span class="sxs-lookup"><span data-stu-id="ed7ba-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="ed7ba-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ed7ba-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="ed7ba-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="ed7ba-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="ed7ba-108">Um operador de Pauli multi-qubit especificado como uma matriz de operadores pauli de um único qubit.</span><span class="sxs-lookup"><span data-stu-id="ed7ba-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ed7ba-109">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ed7ba-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ed7ba-110">Registo qubit a medir.</span><span class="sxs-lookup"><span data-stu-id="ed7ba-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="ed7ba-111">Saída: __<Result> inválida__</span><span class="sxs-lookup"><span data-stu-id="ed7ba-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="ed7ba-112">O resultado da medição do operador pauli no `target` registo.</span><span class="sxs-lookup"><span data-stu-id="ed7ba-112">The result of measuring the given Pauli operator on the `target` register.</span></span>