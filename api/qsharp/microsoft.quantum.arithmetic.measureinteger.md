---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Operação MeasureInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 288aee24e0ae6425db35312b560630a6bb9bfc80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843111"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="36e12-102">Operação MeasureInteger</span><span class="sxs-lookup"><span data-stu-id="36e12-102">MeasureInteger operation</span></span>

<span data-ttu-id="36e12-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="36e12-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="36e12-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="36e12-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="36e12-105">Mede o conteúdo de um registo quântico e converte-o num inteiro.</span><span class="sxs-lookup"><span data-stu-id="36e12-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="36e12-106">A medição é efetuada no que diz respeito à base computacional padrão, ou seja, a eigenbasis de `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="36e12-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="36e12-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="36e12-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="36e12-108">alvo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="36e12-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="36e12-109">Um registo quântico na codificação de pequenas extremidades.</span><span class="sxs-lookup"><span data-stu-id="36e12-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="36e12-110">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="36e12-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="36e12-111">Um inteiro não assinado que contém o valor medido de `target` .</span><span class="sxs-lookup"><span data-stu-id="36e12-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="36e12-112">Observações</span><span class="sxs-lookup"><span data-stu-id="36e12-112">Remarks</span></span>

<span data-ttu-id="36e12-113">Esta operação reinicia o seu registo de entrada no estado $\ket{00\cdots 0}$ adequado para o lançamento de volta para uma máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="36e12-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="36e12-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="36e12-114">See Also</span></span>

- [<span data-ttu-id="36e12-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span><span class="sxs-lookup"><span data-stu-id="36e12-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)