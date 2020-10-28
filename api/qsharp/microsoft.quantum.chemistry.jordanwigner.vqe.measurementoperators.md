---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.MeasurementOperators
title: Função Dos Operadores de Medição
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: MeasurementOperators
qsharp.summary: Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.
ms.openlocfilehash: 24d752c4f198764b6e7c6ea6c49669c020c1a502
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713677"
---
# <a name="measurementoperators-function"></a><span data-ttu-id="b1205-102">Função Dos Operadores de Medição</span><span class="sxs-lookup"><span data-stu-id="b1205-102">MeasurementOperators function</span></span>

<span data-ttu-id="b1205-103">Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="b1205-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="b1205-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b1205-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b1205-105">Calcula todos os operadores de medição necessários para calcular a expectativa de um termo Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="b1205-105">Computes all the measurement operators required to compute the expectation of a Jordan-Wigner term.</span></span>

```qsharp
function MeasurementOperators (nQubits : Int, indices : Int[], termType : Int) : Pauli[][]
```


## <a name="input"></a><span data-ttu-id="b1205-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b1205-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="b1205-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b1205-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b1205-108">O número de qubits necessários para simular o sistema molecular.</span><span class="sxs-lookup"><span data-stu-id="b1205-108">The number of qubits required to simulate the molecular system.</span></span>


### <a name="indices--int"></a><span data-ttu-id="b1205-109">índices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b1205-109">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b1205-110">É aplicada uma matriz contendo os índices do qubit a que cada operador Pauli é aplicado.</span><span class="sxs-lookup"><span data-stu-id="b1205-110">An array containing the indices of the qubit each Pauli operator is applied to.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="b1205-111">termoType : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b1205-111">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b1205-112">O tipo de termo Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="b1205-112">The type of the Jordan-Wigner term.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="b1205-113">Saída : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][ ]</span><span class="sxs-lookup"><span data-stu-id="b1205-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="b1205-114">Uma série de operadores de medição (cada um deles é um conjunto de Pauli).</span><span class="sxs-lookup"><span data-stu-id="b1205-114">An array of measurement operators (each being an array of Pauli).</span></span>