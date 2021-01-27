---
uid: Microsoft.Quantum.Preparation.PrepareQuantumROMState
title: Preparar OperaçãoQuantumROMState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQuantumROMState
qsharp.summary: ''
ms.openlocfilehash: 10ad24d0772dfa254072368cf42b882ab5158bb8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855866"
---
# <a name="preparequantumromstate-operation"></a><span data-ttu-id="c8530-102">Preparar OperaçãoQuantumROMState</span><span class="sxs-lookup"><span data-stu-id="c8530-102">PrepareQuantumROMState operation</span></span>

<span data-ttu-id="c8530-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="c8530-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="c8530-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c8530-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>




```qsharp
operation PrepareQuantumROMState (nBitsPrecision : Int, nCoeffs : Int, nBitsIndices : Int, keepCoeff : Int[], altIndex : Int[], data : Bool[][], indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, dataQubits : Qubit[], garbageRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c8530-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="c8530-105">Input</span></span>

### <a name="nbitsprecision--int"></a><span data-ttu-id="c8530-106">nBitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c8530-106">nBitsPrecision : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="ncoeffs--int"></a><span data-ttu-id="c8530-107">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c8530-107">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="nbitsindices--int"></a><span data-ttu-id="c8530-108">nBitsIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c8530-108">nBitsIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>




### <a name="keepcoeff--int"></a><span data-ttu-id="c8530-109">keepCoeff : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c8530-109">keepCoeff : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="altindex--int"></a><span data-ttu-id="c8530-110">altIndex : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c8530-110">altIndex : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="data--bool"></a><span data-ttu-id="c8530-111">dados : [Bool](xref:microsoft.quantum.lang-ref.bool)[][ ]</span><span class="sxs-lookup"><span data-stu-id="c8530-111">data : [Bool](xref:microsoft.quantum.lang-ref.bool)[][]</span></span>




### <a name="indexregister--littleendian"></a><span data-ttu-id="c8530-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c8530-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="dataqubits--qubit"></a><span data-ttu-id="c8530-113">dataQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c8530-113">dataQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="garbageregister--qubit"></a><span data-ttu-id="c8530-114">lixoRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c8530-114">garbageRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="c8530-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c8530-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

