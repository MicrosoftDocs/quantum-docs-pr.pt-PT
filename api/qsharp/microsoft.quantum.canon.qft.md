---
uid: Microsoft.Quantum.Canon.QFT
title: Operação QFT
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFT
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.
ms.openlocfilehash: 8f1aa8c3680a068e500503ca25afa9a49e4ef5bf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205545"
---
# <a name="qft-operation"></a><span data-ttu-id="c0f69-102">Operação QFT</span><span class="sxs-lookup"><span data-stu-id="c0f69-102">QFT operation</span></span>

<span data-ttu-id="c0f69-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c0f69-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c0f69-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c0f69-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c0f69-105">Executa a Transformação Quântica Fourier num registo quântico contendo um número inteiro na representação de grandes pontas.</span><span class="sxs-lookup"><span data-stu-id="c0f69-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the big-endian representation.</span></span>

```qsharp
operation QFT (qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c0f69-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="c0f69-106">Input</span></span>

### <a name="qs--bigendian"></a><span data-ttu-id="c0f69-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="c0f69-107">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="c0f69-108">Registo quântico ao qual é aplicada a Transformação Quantum Fourier</span><span class="sxs-lookup"><span data-stu-id="c0f69-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="c0f69-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c0f69-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c0f69-110">Observações</span><span class="sxs-lookup"><span data-stu-id="c0f69-110">Remarks</span></span>

<span data-ttu-id="c0f69-111">Presume-se que a entrada e a saída estão em grande codificação endiana.</span><span class="sxs-lookup"><span data-stu-id="c0f69-111">The input and output are assumed to be in big endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0f69-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c0f69-112">See Also</span></span>

- [<span data-ttu-id="c0f69-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span><span class="sxs-lookup"><span data-stu-id="c0f69-113">Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE</span></span>](xref:Microsoft.Quantum.Canon.ApplyQuantumFourierTransformBE)