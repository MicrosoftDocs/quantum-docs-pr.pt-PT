---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWigner0123Term_
title: _Aplicação Operação JordanWigner0123Term_
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWigner0123Term_
qsharp.summary: Applies time-evolution by a PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: 31105f1adae3c17d409dde7b48a9aac6b87fca39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851755"
---
# <a name="_applyjordanwigner0123term_-operation"></a><span data-ttu-id="15c94-102">_Aplicação Operação JordanWigner0123Term_</span><span class="sxs-lookup"><span data-stu-id="15c94-102">_ApplyJordanWigner0123Term_ operation</span></span>

<span data-ttu-id="15c94-103">Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="15c94-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="15c94-104">Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="15c94-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="15c94-105">Aplica a evolução temporal por um termo PQRS descrito por um `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="15c94-105">Applies time-evolution by a PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWigner0123Term_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="15c94-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="15c94-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="15c94-107">termo : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="15c94-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="15c94-108">`GeneratorIndex` representando um termo PQRS.</span><span class="sxs-lookup"><span data-stu-id="15c94-108">`GeneratorIndex` representing a PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="15c94-109">stepSize : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="15c94-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="15c94-110">Duração da evolução do tempo.</span><span class="sxs-lookup"><span data-stu-id="15c94-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="15c94-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="15c94-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="15c94-112">Qubits de Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="15c94-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="15c94-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15c94-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

