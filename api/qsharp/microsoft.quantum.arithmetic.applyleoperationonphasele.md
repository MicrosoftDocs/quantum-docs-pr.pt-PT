---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLE
title: AplicaÇÃOOperaçãoOperaçãoOnPhaseLE operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 8c00890dea67e0beec356245e0794ee5ac697ada
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843799"
---
# <a name="applyleoperationonphasele-operation"></a><span data-ttu-id="b51ef-102">AplicaÇÃOOperaçãoOperaçãoOnPhaseLE operação</span><span class="sxs-lookup"><span data-stu-id="b51ef-102">ApplyLEOperationOnPhaseLE operation</span></span>

<span data-ttu-id="b51ef-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b51ef-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b51ef-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b51ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b51ef-105">Aplica uma operação que toma um <xref:microsoft.quantum.arithmetic.phaselittleendian> registo como entrada num registo-alvo do tipo <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="b51ef-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="b51ef-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="b51ef-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="b51ef-107">op : [Unidade LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b51ef-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b51ef-108">A operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="b51ef-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="b51ef-109">alvo : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b51ef-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="b51ef-110">O registo a que a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="b51ef-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b51ef-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b51ef-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b51ef-112">Observações</span><span class="sxs-lookup"><span data-stu-id="b51ef-112">Remarks</span></span>

<span data-ttu-id="b51ef-113">O registo é transformado `LittleEndian` pela utilização <xref:microsoft.quantum.canon.qftle> de e é devolvido à sua representação original após a aplicação de `op` .</span><span class="sxs-lookup"><span data-stu-id="b51ef-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b51ef-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b51ef-114">See Also</span></span>

- [<span data-ttu-id="b51ef-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span><span class="sxs-lookup"><span data-stu-id="b51ef-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [<span data-ttu-id="b51ef-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span><span class="sxs-lookup"><span data-stu-id="b51ef-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)
- [<span data-ttu-id="b51ef-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span><span class="sxs-lookup"><span data-stu-id="b51ef-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)