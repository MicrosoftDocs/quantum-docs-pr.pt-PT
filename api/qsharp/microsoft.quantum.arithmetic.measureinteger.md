---
uid: Microsoft.Quantum.Arithmetic.MeasureInteger
title: Operação MeasureInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MeasureInteger
qsharp.summary: Measures the content of a quantum register and converts it to an integer. The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.
ms.openlocfilehash: 7cd2d93332eb168c7c2be92a3b910033ca8c10ae
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720970"
---
# <a name="measureinteger-operation"></a><span data-ttu-id="c1156-102">Operação MeasureInteger</span><span class="sxs-lookup"><span data-stu-id="c1156-102">MeasureInteger operation</span></span>

<span data-ttu-id="c1156-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c1156-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c1156-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c1156-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c1156-105">Mede o conteúdo de um registo quântico e converte-o num inteiro.</span><span class="sxs-lookup"><span data-stu-id="c1156-105">Measures the content of a quantum register and converts it to an integer.</span></span> <span data-ttu-id="c1156-106">A medição é efetuada no que diz respeito à base computacional padrão, ou seja, a eigenbasis de `PauliZ` .</span><span class="sxs-lookup"><span data-stu-id="c1156-106">The measurement is performed with respect to the standard computational basis, i.e., the eigenbasis of `PauliZ`.</span></span>

```qsharp
operation MeasureInteger (target : Microsoft.Quantum.Arithmetic.LittleEndian) : Int
```


## <a name="input"></a><span data-ttu-id="c1156-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="c1156-107">Input</span></span>

### <a name="target--littleendian"></a><span data-ttu-id="c1156-108">alvo : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c1156-108">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c1156-109">Um registo quântico na codificação de pequenas extremidades.</span><span class="sxs-lookup"><span data-stu-id="c1156-109">A quantum register in the little-endian encoding.</span></span>



## <a name="output--int"></a><span data-ttu-id="c1156-110">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c1156-110">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c1156-111">Um inteiro não assinado que contém o valor medido de `target` .</span><span class="sxs-lookup"><span data-stu-id="c1156-111">An unsigned integer that contains the measured value of `target`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c1156-112">Observações</span><span class="sxs-lookup"><span data-stu-id="c1156-112">Remarks</span></span>

<span data-ttu-id="c1156-113">Esta operação reinicia o seu registo de entrada no estado $\ket{00\cdots 0}$ adequado para o lançamento de volta para uma máquina-alvo.</span><span class="sxs-lookup"><span data-stu-id="c1156-113">This operation resets its input register to the $\ket{00\cdots 0}$ state, suitable for releasing back to a target machine.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1156-114">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c1156-114">See Also</span></span>

- [<span data-ttu-id="c1156-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span><span class="sxs-lookup"><span data-stu-id="c1156-115">Microsoft.Quantum.Canon.MeasureIntegerBE</span></span>](xref:Microsoft.Quantum.Canon.MeasureIntegerBE)