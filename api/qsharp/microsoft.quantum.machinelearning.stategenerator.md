---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: Estado Modelo de utilizador definido
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: b4f6c3ca28e2976b6a0d58f4ef25ea943de9811e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854883"
---
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="6f4a1-102">Estado Modelo de utilizador definido</span><span class="sxs-lookup"><span data-stu-id="6f4a1-102">StateGenerator user defined type</span></span>

<span data-ttu-id="6f4a1-103">Espaço de nome: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6f4a1-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="6f4a1-104">Pacote: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6f4a1-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="6f4a1-105">Descreve uma operação que prepara uma dada entrada para um classificador sequencial.</span><span class="sxs-lookup"><span data-stu-id="6f4a1-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="6f4a1-106">Itens nomeados</span><span class="sxs-lookup"><span data-stu-id="6f4a1-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="6f4a1-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6f4a1-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6f4a1-108">O número de qubits em que a entrada codificada é definida.</span><span class="sxs-lookup"><span data-stu-id="6f4a1-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="6f4a1-109">Preparar : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="6f4a1-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6f4a1-110">Uma operação que prepara a entrada codificada num pequeno registo de `NQubits` qubits.</span><span class="sxs-lookup"><span data-stu-id="6f4a1-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>