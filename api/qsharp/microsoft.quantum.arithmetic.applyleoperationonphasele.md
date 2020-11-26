---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLE
title: AplicaÇÃOOperaçãoOperaçãoOnPhaseLE operação
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: 33e6cb81916737bf5db467e10fd2aeebb619116a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190909"
---
# <a name="applyleoperationonphasele-operation"></a><span data-ttu-id="bae5a-102">AplicaÇÃOOperaçãoOperaçãoOnPhaseLE operação</span><span class="sxs-lookup"><span data-stu-id="bae5a-102">ApplyLEOperationOnPhaseLE operation</span></span>

<span data-ttu-id="bae5a-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bae5a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bae5a-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bae5a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bae5a-105">Aplica uma operação que toma um <xref:microsoft.quantum.arithmetic.phaselittleendian> registo como entrada num registo-alvo do tipo <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="bae5a-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLE (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="bae5a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="bae5a-106">Input</span></span>

### <a name="op--littleendian--unit"></a><span data-ttu-id="bae5a-107">op : [Unidade LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bae5a-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="bae5a-108">A operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="bae5a-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="bae5a-109">alvo : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bae5a-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="bae5a-110">O registo a que a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="bae5a-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bae5a-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bae5a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bae5a-112">Observações</span><span class="sxs-lookup"><span data-stu-id="bae5a-112">Remarks</span></span>

<span data-ttu-id="bae5a-113">O registo é transformado `LittleEndian` pela utilização <xref:microsoft.quantum.canon.qftle> de e é devolvido à sua representação original após a aplicação de `op` .</span><span class="sxs-lookup"><span data-stu-id="bae5a-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="bae5a-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="bae5a-114">See Also</span></span>

- [<span data-ttu-id="bae5a-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span><span class="sxs-lookup"><span data-stu-id="bae5a-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [<span data-ttu-id="bae5a-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span><span class="sxs-lookup"><span data-stu-id="bae5a-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEC)
- [<span data-ttu-id="bae5a-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span><span class="sxs-lookup"><span data-stu-id="bae5a-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)