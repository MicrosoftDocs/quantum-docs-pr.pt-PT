---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransform
title: Aplicar operaçãoQuantumFourierTransform
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransform
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: d99000c21c79d2ca97b1fe92ad331c7ba8599700
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844765"
---
# <a name="applyquantumfouriertransform-operation"></a><span data-ttu-id="1016b-102">Aplicar operaçãoQuantumFourierTransform</span><span class="sxs-lookup"><span data-stu-id="1016b-102">ApplyQuantumFourierTransform operation</span></span>

<span data-ttu-id="1016b-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1016b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1016b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1016b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1016b-105">Executa a Transformação Quântica Fourier num registo quântico contendo um número inteiro na representação pouco endiuense.</span><span class="sxs-lookup"><span data-stu-id="1016b-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransform (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1016b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1016b-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="1016b-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1016b-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1016b-108">Registo quântico ao qual é aplicada a Transformação Quantum Fourier</span><span class="sxs-lookup"><span data-stu-id="1016b-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="1016b-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1016b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1016b-110">Observações</span><span class="sxs-lookup"><span data-stu-id="1016b-110">Remarks</span></span>

<span data-ttu-id="1016b-111">Presume-se que a entrada e a saída estão em pequena codificação endiana.</span><span class="sxs-lookup"><span data-stu-id="1016b-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="1016b-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1016b-112">See Also</span></span>

- [<span data-ttu-id="1016b-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="1016b-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)