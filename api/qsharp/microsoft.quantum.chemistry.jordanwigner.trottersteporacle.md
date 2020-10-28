---
uid: Microsoft.Quantum.Chemistry.JordanWigner.TrotterStepOracle
title: Função TrotterStepOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: TrotterStepOracle
qsharp.summary: Returns Trotter step operation and the parameters necessary to run it.
ms.openlocfilehash: f7659616ea39d781137c26965cbf2005c5e634b2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713772"
---
# <a name="trottersteporacle-function"></a><span data-ttu-id="4fb54-102">Função TrotterStepOracle</span><span class="sxs-lookup"><span data-stu-id="4fb54-102">TrotterStepOracle function</span></span>

<span data-ttu-id="4fb54-103">Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="4fb54-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="4fb54-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4fb54-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4fb54-105">Devolve a operação do passo Trotter e os parâmetros necessários para executá-lo.</span><span class="sxs-lookup"><span data-stu-id="4fb54-105">Returns Trotter step operation and the parameters necessary to run it.</span></span>

```qsharp
function TrotterStepOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, trotterStepSize : Double, trotterOrder : Int) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a><span data-ttu-id="4fb54-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="4fb54-106">Input</span></span>

### <a name="qsharpdata--jordanwignerencodingdata"></a><span data-ttu-id="4fb54-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="4fb54-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="4fb54-108">Hamiltonian descrito por `JordanWignerEncodingData` formato.</span><span class="sxs-lookup"><span data-stu-id="4fb54-108">Hamiltonian described by `JordanWignerEncodingData` format.</span></span>


### <a name="trotterstepsize--double"></a><span data-ttu-id="4fb54-109">trotterStepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4fb54-109">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4fb54-110">Tamanho do passo do integrador Trotter.</span><span class="sxs-lookup"><span data-stu-id="4fb54-110">Step size of Trotter integrator.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="4fb54-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4fb54-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4fb54-112">Ordem do integrador Trotter.</span><span class="sxs-lookup"><span data-stu-id="4fb54-112">Order of Trotter integrator.</span></span>



## <a name="output--intdoublequbit--unit-adj--ctl"></a><span data-ttu-id="4fb54-113">Saída : ([Int](xref:microsoft.quantum.lang-ref.int)[(Duplo,](xref:microsoft.quantum.lang-ref.double)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl))</span><span class="sxs-lookup"><span data-stu-id="4fb54-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl))</span></span>

<span data-ttu-id="4fb54-114">Um tuple onde: `Int` é o número de qubits atribuídos, é , e a `Double` `1.0/trotterStepSize` operação é o passo Trotter.</span><span class="sxs-lookup"><span data-stu-id="4fb54-114">A tuple where: `Int` is the number of qubits allocated, `Double` is `1.0/trotterStepSize`, and the operation is the Trotter step.</span></span>