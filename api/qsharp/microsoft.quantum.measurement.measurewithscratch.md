---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: Medidas ComScratch
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 1ee25dbccd5bddde406cf8ed84dff77d96d7804e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720323"
---
# <a name="measurewithscratch-operation"></a><span data-ttu-id="e5c18-102">Medidas ComScratch</span><span class="sxs-lookup"><span data-stu-id="e5c18-102">MeasureWithScratch operation</span></span>

<span data-ttu-id="e5c18-103">Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="e5c18-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="e5c18-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e5c18-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e5c18-105">Mede o operador pauli dado utilizando um qubit de risco explícito para efetuar a medição.</span><span class="sxs-lookup"><span data-stu-id="e5c18-105">Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.</span></span>

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a><span data-ttu-id="e5c18-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e5c18-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="e5c18-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="e5c18-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="e5c18-108">Um operador de Pauli multi-qubit especificado como uma matriz de operadores pauli de um único qubit.</span><span class="sxs-lookup"><span data-stu-id="e5c18-108">A multi-qubit Pauli operator specified as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e5c18-109">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e5c18-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e5c18-110">Registo qubit a medir.</span><span class="sxs-lookup"><span data-stu-id="e5c18-110">Qubit register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="e5c18-111">Saída: __<Result> inválida__</span><span class="sxs-lookup"><span data-stu-id="e5c18-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="e5c18-112">O resultado da medição do operador pauli no `target` registo.</span><span class="sxs-lookup"><span data-stu-id="e5c18-112">The result of measuring the given Pauli operator on the `target` register.</span></span>