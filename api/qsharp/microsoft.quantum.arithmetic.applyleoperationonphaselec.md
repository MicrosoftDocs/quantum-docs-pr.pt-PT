---
uid: Microsoft.Quantum.Arithmetic.ApplyLEOperationOnPhaseLEC
title: AplicaçãoOperaçãoÇãoOnPhaseLEC
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyLEOperationOnPhaseLEC
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.
ms.openlocfilehash: dafe27f66f967fb641a8898672e124c0a51fe687
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190841"
---
# <a name="applyleoperationonphaselec-operation"></a><span data-ttu-id="d3c9d-102">AplicaçãoOperaçãoÇãoOnPhaseLEC</span><span class="sxs-lookup"><span data-stu-id="d3c9d-102">ApplyLEOperationOnPhaseLEC operation</span></span>

<span data-ttu-id="d3c9d-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d3c9d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d3c9d-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3c9d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3c9d-105">Aplica uma operação que toma um <xref:microsoft.quantum.arithmetic.phaselittleendian> registo como entrada num registo-alvo do tipo <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="d3c9d-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.phaselittleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>

```qsharp
operation ApplyLEOperationOnPhaseLEC (op : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Ctl), target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="d3c9d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="d3c9d-106">Input</span></span>

### <a name="op--littleendian--unit--is-ctl"></a><span data-ttu-id="d3c9d-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span><span class="sxs-lookup"><span data-stu-id="d3c9d-107">op : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="d3c9d-108">A operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="d3c9d-108">The operation to be applied.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="d3c9d-109">alvo : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d3c9d-109">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="d3c9d-110">O registo a que a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="d3c9d-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d3c9d-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3c9d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d3c9d-112">Observações</span><span class="sxs-lookup"><span data-stu-id="d3c9d-112">Remarks</span></span>

<span data-ttu-id="d3c9d-113">O registo é transformado `LittleEndian` pela utilização <xref:microsoft.quantum.canon.qftle> de e é devolvido à sua representação original após a aplicação de `op` .</span><span class="sxs-lookup"><span data-stu-id="d3c9d-113">The register is transformed to `LittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3c9d-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d3c9d-114">See Also</span></span>

- [<span data-ttu-id="d3c9d-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE</span><span class="sxs-lookup"><span data-stu-id="d3c9d-115">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLE)
- [<span data-ttu-id="d3c9d-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span><span class="sxs-lookup"><span data-stu-id="d3c9d-116">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLEA)
- [<span data-ttu-id="d3c9d-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span><span class="sxs-lookup"><span data-stu-id="d3c9d-117">Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyLEOperationonPhaseLECA)