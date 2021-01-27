---
uid: Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE
title: Aplicar operaçãoQuantumFourierTransformBE
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyQuantumFourierTransformBE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: a1f4a0a5e94465fc8bf3af344e2e19ee0d1d15e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841571"
---
# <a name="applyquantumfouriertransformbe-operation"></a><span data-ttu-id="3c366-102">Aplicar operaçãoQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="3c366-102">ApplyQuantumFourierTransformBE operation</span></span>

<span data-ttu-id="3c366-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3c366-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3c366-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c366-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3c366-105">Executa a Transformação Quântica Fourier num registo quântico contendo um número inteiro na representação de grandes pontas.</span><span class="sxs-lookup"><span data-stu-id="3c366-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation ApplyQuantumFourierTransformBE (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3c366-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3c366-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="3c366-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="3c366-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="3c366-108">Registo quântico ao qual é aplicada a Transformação Quantum Fourier</span><span class="sxs-lookup"><span data-stu-id="3c366-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="3c366-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3c366-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3c366-110">Observações</span><span class="sxs-lookup"><span data-stu-id="3c366-110">Remarks</span></span>

<span data-ttu-id="3c366-111">Presume-se que a entrada e a saída estão em grande codificação endiana.</span><span class="sxs-lookup"><span data-stu-id="3c366-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c366-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3c366-112">See Also</span></span>

- [<span data-ttu-id="3c366-113">Microsoft.Quantum.Canon.ApproximateQFT</span><span class="sxs-lookup"><span data-stu-id="3c366-113">Microsoft.Quantum.Canon.ApproximateQFT</span></span>](xref:Microsoft.Quantum.Canon.ApproximateQFT)
- [<span data-ttu-id="3c366-114">Microsoft.Quantum.Canon.QFTLE</span><span class="sxs-lookup"><span data-stu-id="3c366-114">Microsoft.Quantum.Canon.QFTLE</span></span>](xref:Microsoft.Quantum.Canon.QFTLE)