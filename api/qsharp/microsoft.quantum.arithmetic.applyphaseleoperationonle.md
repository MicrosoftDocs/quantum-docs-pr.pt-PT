---
uid: Microsoft.Quantum.Arithmetic.ApplyPhaseLEOperationOnLE
title: AplicaPhaseLEOperação OperaçãoOnLHA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyPhaseLEOperationOnLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.
ms.openlocfilehash: d94fdb55e051e76dd518eff14b80d1a24516bf8a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843685"
---
# <a name="applyphaseleoperationonle-operation"></a><span data-ttu-id="20a53-102">AplicaPhaseLEOperação OperaçãoOnLHA</span><span class="sxs-lookup"><span data-stu-id="20a53-102">ApplyPhaseLEOperationOnLE operation</span></span>

<span data-ttu-id="20a53-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="20a53-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="20a53-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="20a53-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="20a53-105">Aplica uma operação que toma um <xref:microsoft.quantum.arithmetic.littleendian> registo como entrada num registo-alvo do tipo <xref:microsoft.quantum.arithmetic.phaselittleendian> .</span><span class="sxs-lookup"><span data-stu-id="20a53-105">Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.</span></span>

```qsharp
operation ApplyPhaseLEOperationOnLE (op : (Microsoft.Quantum.Arithmetic.PhaseLittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="20a53-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="20a53-106">Input</span></span>

### <a name="op--phaselittleendian--unit"></a><span data-ttu-id="20a53-107">op : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20a53-107">op : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="20a53-108">A operação a ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="20a53-108">The operation to be applied.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="20a53-109">alvo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="20a53-109">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="20a53-110">O registo a que a operação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="20a53-110">The register to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="20a53-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20a53-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="20a53-112">Observações</span><span class="sxs-lookup"><span data-stu-id="20a53-112">Remarks</span></span>

<span data-ttu-id="20a53-113">O registo é transformado `PhaseLittleEndian` pela utilização <xref:microsoft.quantum.canon.qftle> de e é devolvido à sua representação original após a aplicação de `op` .</span><span class="sxs-lookup"><span data-stu-id="20a53-113">The register is transformed to `PhaseLittleEndian` by the use of <xref:microsoft.quantum.canon.qftle> and is then returned to its original representation after application of `op`.</span></span>

## <a name="see-also"></a><span data-ttu-id="20a53-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="20a53-114">See Also</span></span>

- [<span data-ttu-id="20a53-115">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span><span class="sxs-lookup"><span data-stu-id="20a53-115">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="20a53-116">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span><span class="sxs-lookup"><span data-stu-id="20a53-116">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [<span data-ttu-id="20a53-117">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA</span><span class="sxs-lookup"><span data-stu-id="20a53-117">Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA</span></span>](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA)