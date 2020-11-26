---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: Preparar OperaçãoChoiState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: ced71c4278f42f577760acd54ae53e7f5e6dae4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210578"
---
# <a name="preparechoistate-operation"></a><span data-ttu-id="494bb-102">Preparar OperaçãoChoiState</span><span class="sxs-lookup"><span data-stu-id="494bb-102">PrepareChoiState operation</span></span>

<span data-ttu-id="494bb-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="494bb-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="494bb-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="494bb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="494bb-105">Prepara o estado Choi-Jamiołkowski para uma determinada operação em dados registos de referência e alvo.</span><span class="sxs-lookup"><span data-stu-id="494bb-105">Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="494bb-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="494bb-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="494bb-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="494bb-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="494bb-108">Operação $\Lambda$ cujo estado choi-Jamiołkowski $J(\Lambda) / 2^N$ está para ser preparado, onde $N$ é o número de qubits em que `op` atua.</span><span class="sxs-lookup"><span data-stu-id="494bb-108">Operation $\Lambda$ whose Choi–Jamiołkowski state $J(\Lambda) / 2^N$ is to be prepared, where $N$ is the number of qubits on which `op` acts.</span></span>


### <a name="reference--qubit"></a><span data-ttu-id="494bb-109">referência: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="494bb-109">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="494bb-110">Um registo de qubits a partir do estado $\ket{00\cdots 0}$ para ser usado como referência para a ação de `op` .</span><span class="sxs-lookup"><span data-stu-id="494bb-110">A register of qubits starting in the $\ket{00\cdots 0}$ state to be used as a reference for the action of `op`.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="494bb-111">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="494bb-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="494bb-112">Um registo de qubits inicialmente no estado $\ket{00\cdots 0}$ em que `op` deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="494bb-112">A register of qubits initially in the $\ket{00\cdots 0}$ state on which `op` is to be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="494bb-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="494bb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="494bb-114">Observações</span><span class="sxs-lookup"><span data-stu-id="494bb-114">Remarks</span></span>

<span data-ttu-id="494bb-115">O estado de Choi-Jamiłkowski $J(\Lambda)$ de um processo quântico é definido como $$ \start{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (\boldone\rangle \! \rangle\langle \! \langle\boldone; \end{align} X\rangle \! \rangle$ é a *vectorização* de uma matriz $X$ na convenção de empilhamento de colunas.</span><span class="sxs-lookup"><span data-stu-id="494bb-115">The Choi–Jamiłkowski state $J(\Lambda)$ of a quantum process is defined as $$ \begin{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (|\boldone\rangle\!\rangle\langle\!\langle\boldone|), \end{align} $$ where $|X\rangle\!\rangle$ is the *vectorization* of a matrix $X$ in the column-stacking convention.</span></span> <span data-ttu-id="494bb-116">Aprender uma descrição clássica deste estado fornece informações completas sobre o efeito de $\Lambda$ agindo em estados de entrada arbitrária, e forma a base da tomografia do *processo quântico.*</span><span class="sxs-lookup"><span data-stu-id="494bb-116">Learning a classical description of this state provides full information about the effect of $\Lambda$ acting on arbitrary input states, and forms the foundation of *quantum process tomography*.</span></span>

## <a name="see-also"></a><span data-ttu-id="494bb-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="494bb-117">See Also</span></span>

- [<span data-ttu-id="494bb-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span><span class="sxs-lookup"><span data-stu-id="494bb-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [<span data-ttu-id="494bb-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span><span class="sxs-lookup"><span data-stu-id="494bb-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [<span data-ttu-id="494bb-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span><span class="sxs-lookup"><span data-stu-id="494bb-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)