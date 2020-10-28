---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: Operação LogicalANDMeasAndFix
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715928"
---
# <a name="logicalandmeasandfix-operation"></a><span data-ttu-id="b2f19-102">Operação LogicalANDMeasAndFix</span><span class="sxs-lookup"><span data-stu-id="b2f19-102">LogicalANDMeasAndFix operation</span></span>

<span data-ttu-id="b2f19-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b2f19-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b2f19-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2f19-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2f19-105">Calcula a lógica e de múltiplos qubits.</span><span class="sxs-lookup"><span data-stu-id="b2f19-105">Computes the logical AND of multiple qubits.</span></span>

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="b2f19-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b2f19-106">Input</span></span>

### <a name="ctrlregister--qubit"></a><span data-ttu-id="b2f19-107">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b2f19-107">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b2f19-108">Qubits entrada para o portão E de entrada múltipla.</span><span class="sxs-lookup"><span data-stu-id="b2f19-108">Qubits input to the multiple-input AND gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b2f19-109">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b2f19-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b2f19-110">Qubit em que saída de E é escrita para.</span><span class="sxs-lookup"><span data-stu-id="b2f19-110">Qubit on which output of AND is written to.</span></span> <span data-ttu-id="b2f19-111">Isto é assumido para sempre começar no estado $\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="b2f19-111">This is assumed to always start in the $\ket{0}$ state.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b2f19-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b2f19-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b2f19-113">Observações</span><span class="sxs-lookup"><span data-stu-id="b2f19-113">Remarks</span></span>

<span data-ttu-id="b2f19-114">Quando `ctrlRegister` tem exatamente $2$ qubits, isto é equivalente à `CCNOT` operação, mas fase com uma fase $e^{i\Pi/2}$ em $\ket {001} $ e $-e^{i\Pi/2}$ em $\ket {101} $ e $\ket {011} $.</span><span class="sxs-lookup"><span data-stu-id="b2f19-114">When `ctrlRegister` has exactly $2$ qubits, this is equivalent to the `CCNOT` operation but phase with a phase $e^{i\Pi/2}$ on $\ket{001}$ and $-e^{i\Pi/2}$ on $\ket{101}$ and $\ket{011}$.</span></span>
<span data-ttu-id="b2f19-115">O Adjacente é também uma abordagem de medida e fixação que é o inverso da operação original apenas em casos especiais (ver referências), mas utiliza menos portas T.</span><span class="sxs-lookup"><span data-stu-id="b2f19-115">The Adjoint is also measure-and-fixup approach that is the inverse of the original operation only in special cases (see references), but uses fewer T-gates.</span></span>

## <a name="references"></a><span data-ttu-id="b2f19-116">Referências</span><span class="sxs-lookup"><span data-stu-id="b2f19-116">References</span></span>

- [<span data-ttu-id="b2f19-117">*Craig Gidney* , 1709.06648</span><span class="sxs-lookup"><span data-stu-id="b2f19-117"> *Craig Gidney* , 1709.06648</span></span>](https://arxiv.org/abs/1709.06648)