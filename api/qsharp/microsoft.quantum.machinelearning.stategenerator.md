---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: Estado Modelo de utilizador definido
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: 5c9643f5c917ff3cb25fa8c046856b03cc287edd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211564"
---
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="6bc74-102">Estado Modelo de utilizador definido</span><span class="sxs-lookup"><span data-stu-id="6bc74-102">StateGenerator user defined type</span></span>

<span data-ttu-id="6bc74-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6bc74-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="6bc74-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6bc74-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="6bc74-105">Descreve uma operação que prepara uma dada entrada para um classificador sequencial.</span><span class="sxs-lookup"><span data-stu-id="6bc74-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="6bc74-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="6bc74-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="6bc74-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6bc74-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6bc74-108">O número de qubits em que a entrada codificada é definida.</span><span class="sxs-lookup"><span data-stu-id="6bc74-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="6bc74-109">Preparar : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="6bc74-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6bc74-110">Uma operação que prepara a entrada codificada num pequeno registo de `NQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="6bc74-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>