---
uid: Microsoft.Quantum.Canon.QFTLE
title: Operação QFTLE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: f28f74d34fb4688739646da3dc12ae6734eb4ad4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715637"
---
# <a name="qftle-operation"></a><span data-ttu-id="3e59d-102">Operação QFTLE</span><span class="sxs-lookup"><span data-stu-id="3e59d-102">QFTLE operation</span></span>

<span data-ttu-id="3e59d-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3e59d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3e59d-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3e59d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3e59d-105">Executa a Transformação Quântica Fourier num registo quântico contendo um número inteiro na representação pouco endiuense.</span><span class="sxs-lookup"><span data-stu-id="3e59d-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="3e59d-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="3e59d-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="3e59d-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3e59d-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3e59d-108">Registo quântico ao qual é aplicada a Transformação Quantum Fourier</span><span class="sxs-lookup"><span data-stu-id="3e59d-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="3e59d-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e59d-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3e59d-110">Observações</span><span class="sxs-lookup"><span data-stu-id="3e59d-110">Remarks</span></span>

<span data-ttu-id="3e59d-111">Presume-se que a entrada e a saída estão em pequena codificação endiana.</span><span class="sxs-lookup"><span data-stu-id="3e59d-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e59d-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3e59d-112">See Also</span></span>

- [<span data-ttu-id="3e59d-113">Microsoft.Quantum.Canon.QFT</span><span class="sxs-lookup"><span data-stu-id="3e59d-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)