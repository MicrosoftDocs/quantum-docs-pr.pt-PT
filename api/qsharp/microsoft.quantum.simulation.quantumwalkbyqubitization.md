---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: Função QuantumWalkByQubitization
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: 8ffb6eb77a3f910d3064c4a3c90215d5d9a694aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851060"
---
# <a name="quantumwalkbyqubitization-function"></a><span data-ttu-id="3d648-102">Função QuantumWalkByQubitization</span><span class="sxs-lookup"><span data-stu-id="3d648-102">QuantumWalkByQubitization function</span></span>

<span data-ttu-id="3d648-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="3d648-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="3d648-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3d648-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3d648-105">Converte uma reflexão de codificação de blocos numa caminhada quântica.</span><span class="sxs-lookup"><span data-stu-id="3d648-105">Converts a block-encoding reflection into a quantum walk.</span></span>

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="3d648-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="3d648-106">Description</span></span>

<span data-ttu-id="3d648-107">Dado um `BlockEncodingReflection` representado por um $U$ unitário que codifica algum operador $H$ de juros, converte-o numa caminhada quântica $W$ contendo o espectro de $\pm e^\pm i\sin^ {-1} (H)}$.</span><span class="sxs-lookup"><span data-stu-id="3d648-107">Given a `BlockEncodingReflection` represented by a unitary $U$ that encodes some operator $H$ of interest, converts it into a quantum walk $W$ containing the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="input"></a><span data-ttu-id="3d648-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="3d648-108">Input</span></span>

### <a name="blockencoding--blockencodingreflection"></a><span data-ttu-id="3d648-109">blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="3d648-109">blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="3d648-110">Um `BlockEncodingReflection` $U unitário para ser convertido numa caminhada quântica.</span><span class="sxs-lookup"><span data-stu-id="3d648-110">A `BlockEncodingReflection` unitary $U$ to be converted into a Quantum walk.</span></span>



## <a name="output--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="3d648-111">Saída :[(Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="3d648-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="3d648-112">Uma caminhada quântica $W$ agindo conjuntamente em registos `a` e que codifica o `s` $H$, e contém o espectro de $\pm e^{\pm i\sin^ {-1} (H)}$.</span><span class="sxs-lookup"><span data-stu-id="3d648-112">A quantum walk $W$ acting jointly on registers `a` and `s` that block- encodes $H$, and contains the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="references"></a><span data-ttu-id="3d648-113">Referências</span><span class="sxs-lookup"><span data-stu-id="3d648-113">References</span></span>

- <span data-ttu-id="3d648-114">Simulação Hamiltonian por Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="3d648-114">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="3d648-115">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3d648-115">See Also</span></span>

- [<span data-ttu-id="3d648-116">Microsoft.Quantum.Simulation.BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="3d648-116">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="3d648-117">Microsoft.Quantum.Simulation.BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="3d648-117">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)