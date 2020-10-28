---
uid: Microsoft.Quantum.Chemistry.JordanWigner.QubitizationOracle
title: Função qubitizaçãoOo
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: QubitizationOracle
qsharp.summary: Returns Qubitization operation and the parameters necessary to run it.
ms.openlocfilehash: 326bebfc1cfd839082732898167c20ecf105a266
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713814"
---
# <a name="qubitizationoracle-function"></a><span data-ttu-id="1f879-102">Função qubitizaçãoOo</span><span class="sxs-lookup"><span data-stu-id="1f879-102">QubitizationOracle function</span></span>

<span data-ttu-id="1f879-103">Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="1f879-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="1f879-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1f879-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1f879-105">Devolve a operação de qubitização e os parâmetros necessários para executá-la.</span><span class="sxs-lookup"><span data-stu-id="1f879-105">Returns Qubitization operation and the parameters necessary to run it.</span></span>

```qsharp
function QubitizationOracle (qSharpData : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData) : (Int, (Double, (Qubit[] => Unit is Adj + Ctl)))
```


## <a name="input"></a><span data-ttu-id="1f879-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1f879-106">Input</span></span>

### <a name="qsharpdata--jordanwignerencodingdata"></a><span data-ttu-id="1f879-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="1f879-107">qSharpData : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="1f879-108">Hamiltonian descrito por `JordanWignerEncodingData` formato.</span><span class="sxs-lookup"><span data-stu-id="1f879-108">Hamiltonian described by `JordanWignerEncodingData` format.</span></span>



## <a name="output--intdoublequbit--unit-adj--ctl"></a><span data-ttu-id="1f879-109">Saída : ([Int](xref:microsoft.quantum.lang-ref.int)[(Duplo,](xref:microsoft.quantum.lang-ref.double)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unidade](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl))</span><span class="sxs-lookup"><span data-stu-id="1f879-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl))</span></span>

<span data-ttu-id="1f879-110">Um tuple onde: `Int` é o número de qubits atribuídos, é a única norma dos `Double` coeficientes hamiltonianos, e a operação é a caminhada quântica criada pela Qubitização.</span><span class="sxs-lookup"><span data-stu-id="1f879-110">A tuple where: `Int` is the number of qubits allocated, `Double` is the one-norm of Hamiltonian coefficients, and the operation is the Quantum walk created by Qubitization.</span></span>