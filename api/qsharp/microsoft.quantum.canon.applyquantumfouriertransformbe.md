---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: Aplicar operaçãoQuantumFourierTransformBE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: d15310298dc138bdffb612895bbf20ca1371db6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717790"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="1ffa5-102">Aplicar operaçãoQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="1ffa5-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="1ffa5-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1ffa5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1ffa5-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1ffa5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1ffa5-105">Executa a Transformação Quântica Fourier num registo quântico contendo um número inteiro na representação de grandes pontas.</span><span class="sxs-lookup"><span data-stu-id="1ffa5-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="1ffa5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1ffa5-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="1ffa5-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="1ffa5-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="1ffa5-108">Registo quântico ao qual é aplicada a Transformação Quantum Fourier</span><span class="sxs-lookup"><span data-stu-id="1ffa5-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="1ffa5-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1ffa5-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1ffa5-110">Observações</span><span class="sxs-lookup"><span data-stu-id="1ffa5-110">Remarks</span></span>

<span data-ttu-id="1ffa5-111">Presume-se que a entrada e a saída estão em grande codificação endiana.</span><span class="sxs-lookup"><span data-stu-id="1ffa5-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="1ffa5-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1ffa5-112">See Also</span></span>

- [<span data-ttu-id="1ffa5-113">Microsoft.Quantum.Canon.ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="1ffa5-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="1ffa5-114">Microsoft.Quantum.Canon.QFTLE</span><span class="sxs-lookup"><span data-stu-id="1ffa5-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)