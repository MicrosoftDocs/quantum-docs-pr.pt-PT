---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: Preparar OperaçãoChoiState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: cb34078c09f8c28b5b9bbda1bae6936d13ffcc78
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854408"
---
# <a name="preparechoistate-operation"></a><span data-ttu-id="c41b1-102">Preparar OperaçãoChoiState</span><span class="sxs-lookup"><span data-stu-id="c41b1-102">PrepareChoiState operation</span></span>

<span data-ttu-id="c41b1-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="c41b1-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="c41b1-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c41b1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c41b1-105">Prepara o estado Choi-Jamiołkowski para uma determinada operação em dados registos de referência e alvo.</span><span class="sxs-lookup"><span data-stu-id="c41b1-105">Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.</span></span>

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c41b1-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c41b1-106">Input</span></span>

### <a name="op--qubit--unit"></a><span data-ttu-id="c41b1-107">op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="c41b1-107">op : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c41b1-108">Operação $\Lambda$ cujo estado choi-Jamiołkowski $J(\Lambda) / 2^N$ está para ser preparado, onde $N$ é o número de qubits em que `op` atua.</span><span class="sxs-lookup"><span data-stu-id="c41b1-108">Operation $\Lambda$ whose Choi–Jamiołkowski state $J(\Lambda) / 2^N$ is to be prepared, where $N$ is the number of qubits on which `op` acts.</span></span>


### <a name="reference--qubit"></a><span data-ttu-id="c41b1-109">referência: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c41b1-109">reference : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c41b1-110">Um registo de qubits a partir do estado $\ket{00\cdots 0}$ para ser usado como referência para a ação de `op` .</span><span class="sxs-lookup"><span data-stu-id="c41b1-110">A register of qubits starting in the $\ket{00\cdots 0}$ state to be used as a reference for the action of `op`.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c41b1-111">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c41b1-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c41b1-112">Um registo de qubits inicialmente no estado $\ket{00\cdots 0}$ em que `op` deve ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="c41b1-112">A register of qubits initially in the $\ket{00\cdots 0}$ state on which `op` is to be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c41b1-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c41b1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c41b1-114">Observações</span><span class="sxs-lookup"><span data-stu-id="c41b1-114">Remarks</span></span>

<span data-ttu-id="c41b1-115">O estado de Choi-Jamiłkowski $J(\Lambda)$ de um processo quântico é definido como $$ \start{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (|\boldone\rangle \! \rangle\langle \! \langle\boldone|), \end{align |$ X\rangle \! \rangle$ é a *vectorização* de uma matriz $X$ na convenção de empilhamento de colunas.</span><span class="sxs-lookup"><span data-stu-id="c41b1-115">The Choi–Jamiłkowski state $J(\Lambda)$ of a quantum process is defined as $$ \begin{align} J(\Lambda) \mathrel{:=} (\boldone \otimes \Lambda) (|\boldone\rangle\!\rangle\langle\!\langle\boldone|), \end{align} $$ where $|X\rangle\!\rangle$ is the *vectorization* of a matrix $X$ in the column-stacking convention.</span></span> <span data-ttu-id="c41b1-116">Aprender uma descrição clássica deste estado fornece informações completas sobre o efeito de $\Lambda$ agindo em estados de entrada arbitrária, e forma a base da tomografia do *processo quântico.*</span><span class="sxs-lookup"><span data-stu-id="c41b1-116">Learning a classical description of this state provides full information about the effect of $\Lambda$ acting on arbitrary input states, and forms the foundation of *quantum process tomography*.</span></span>

## <a name="see-also"></a><span data-ttu-id="c41b1-117">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c41b1-117">See Also</span></span>

- [<span data-ttu-id="c41b1-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span><span class="sxs-lookup"><span data-stu-id="c41b1-118">Microsoft.Quantum.Preparation.PrepareChoiStateA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [<span data-ttu-id="c41b1-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span><span class="sxs-lookup"><span data-stu-id="c41b1-119">Microsoft.Quantum.Preparation.PrepareChoiStateC</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [<span data-ttu-id="c41b1-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span><span class="sxs-lookup"><span data-stu-id="c41b1-120">Microsoft.Quantum.Preparation.PrepareChoiStateCA</span></span>](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)