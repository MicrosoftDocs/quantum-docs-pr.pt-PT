---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: Medida OperaçãoPaulis
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 1bc14ec8e7c608d1195a03a354c71e870594f86d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853774"
---
# <a name="measurepaulis-operation"></a><span data-ttu-id="f3196-102">Medida OperaçãoPaulis</span><span class="sxs-lookup"><span data-stu-id="f3196-102">MeasurePaulis operation</span></span>

<span data-ttu-id="f3196-103">Espaço de nome: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="f3196-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="f3196-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f3196-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f3196-105">Dada uma série de operadores de Pauli multi-qubit, mede cada um usando um dispositivo de medição especificado e, em seguida, devolve a matriz de resultados.</span><span class="sxs-lookup"><span data-stu-id="f3196-105">Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.</span></span>

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a><span data-ttu-id="f3196-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f3196-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="f3196-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][ ]</span><span class="sxs-lookup"><span data-stu-id="f3196-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="f3196-108">Conjunto de operadores de Pauli multi-qubit para medir.</span><span class="sxs-lookup"><span data-stu-id="f3196-108">Array of multi-qubit Pauli operators to measure.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="f3196-109">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f3196-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f3196-110">Registe-se sobre os quais medir os operadores em determinadas empresas.</span><span class="sxs-lookup"><span data-stu-id="f3196-110">Register on which to measure the given operators.</span></span>


### <a name="gadget--pauliqubit--__invalidresult__"></a><span data-ttu-id="f3196-111">gadget :[(Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __inválidos <Result>__</span><span class="sxs-lookup"><span data-stu-id="f3196-111">gadget : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __invalid<Result>__</span></span> 

<span data-ttu-id="f3196-112">Funcionamento que efetua a medição de um determinado operador multi-qubit.</span><span class="sxs-lookup"><span data-stu-id="f3196-112">Operation which performs the measurement of a given multi-qubit operator.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="f3196-113">Saída: __<Result> inválido__[]</span><span class="sxs-lookup"><span data-stu-id="f3196-113">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="f3196-114">A matriz de resultados obtidos a partir da medição de cada elemento de `paulis` `target` .</span><span class="sxs-lookup"><span data-stu-id="f3196-114">The array of results obtained from measuring each element of `paulis` on `target`.</span></span>