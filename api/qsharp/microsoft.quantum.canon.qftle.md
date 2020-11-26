---
uid: Microsoft.Quantum.Canon.QFTLE
title: Operação QFTLE
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: QFTLE
qsharp.summary: Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.
ms.openlocfilehash: 460e43bc7997e9efad06c58ad14822e28cc45cdd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205580"
---
# <a name="qftle-operation"></a><span data-ttu-id="1577b-102">Operação QFTLE</span><span class="sxs-lookup"><span data-stu-id="1577b-102">QFTLE operation</span></span>

<span data-ttu-id="1577b-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1577b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1577b-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1577b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1577b-105">Executa a Transformação Quântica Fourier num registo quântico contendo um número inteiro na representação pouco endiuense.</span><span class="sxs-lookup"><span data-stu-id="1577b-105">Performs the Quantum Fourier Transform on a quantum register containing an integer in the little-endian representation.</span></span>

```qsharp
operation QFTLE (qs : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1577b-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="1577b-106">Input</span></span>

### <a name="qs--littleendian"></a><span data-ttu-id="1577b-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="1577b-107">qs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="1577b-108">Registo quântico ao qual é aplicada a Transformação Quantum Fourier</span><span class="sxs-lookup"><span data-stu-id="1577b-108">Quantum register to which the Quantum Fourier Transform is applied</span></span>



## <a name="output--unit"></a><span data-ttu-id="1577b-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1577b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1577b-110">Observações</span><span class="sxs-lookup"><span data-stu-id="1577b-110">Remarks</span></span>

<span data-ttu-id="1577b-111">Presume-se que a entrada e a saída estão em pequena codificação endiana.</span><span class="sxs-lookup"><span data-stu-id="1577b-111">The input and output are assumed to be in little endian encoding.</span></span>

## <a name="see-also"></a><span data-ttu-id="1577b-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1577b-112">See Also</span></span>

- [<span data-ttu-id="1577b-113">Microsoft.Quantum.Canon.QFT</span><span class="sxs-lookup"><span data-stu-id="1577b-113">Microsoft.Quantum.Canon.QFT</span></span>](xref:Microsoft.Quantum.Canon.QFT)