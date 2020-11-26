---
uid: Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator
title: Função multiplexerBruteForceFromGenerator
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexerBruteForceFromGenerator
qsharp.summary: >-
  Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 650e10b92d9f6cee74765adc09132be36af5fba1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206192"
---
# <a name="multiplexerbruteforcefromgenerator-function"></a><span data-ttu-id="de162-102">Função multiplexerBruteForceFromGenerator</span><span class="sxs-lookup"><span data-stu-id="de162-102">MultiplexerBruteForceFromGenerator function</span></span>

<span data-ttu-id="de162-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="de162-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="de162-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="de162-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="de162-105">Devolve uma operação unitária controlada por multiplicões $U$ que aplica uma $V_j$ unitária quando controlada pelo estado do número n-qubit $\ket{j}$.</span><span class="sxs-lookup"><span data-stu-id="de162-105">Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="de162-106">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span><span class="sxs-lookup"><span data-stu-id="de162-106">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
function MultiplexerBruteForceFromGenerator (unitaryGenerator : (Int, (Int -> (Qubit[] => Unit is Adj + Ctl)))) : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="de162-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="de162-107">Input</span></span>

### <a name="unitarygenerator--intint---qubit--unit--is-adj--ctl"></a><span data-ttu-id="de162-108">unitárioGenerator :[(Int,](xref:microsoft.quantum.lang-ref.int)[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [> Unit](xref:microsoft.quantum.lang-ref.unit) is Adj + Ctl)</span><span class="sxs-lookup"><span data-stu-id="de162-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="de162-109">Um tuple onde o primeiro elemento `Int` é o número de unitários $N$, e o segundo elemento é uma `(Int -> ('T => () is Adj + Ctl))` função que leva um inteiro $j$ em $[0,N-1]$ e produz a operação unitária $V_j$.</span><span class="sxs-lookup"><span data-stu-id="de162-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>



## <a name="output--littleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="de162-110">Saída :[(LittleEndian,](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [> Unit](xref:microsoft.quantum.lang-ref.unit) é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="de162-110">Output : ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="de162-111">Uma operação unitária controlada por multiplicásscimento $U$ que aplica unitários descritos por `unitaryGenerator` .</span><span class="sxs-lookup"><span data-stu-id="de162-111">A multiply-controlled unitary operation $U$ that applies unitaries described by `unitaryGenerator`.</span></span>

## <a name="see-also"></a><span data-ttu-id="de162-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="de162-112">See Also</span></span>

- [<span data-ttu-id="de162-113">Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator</span><span class="sxs-lookup"><span data-stu-id="de162-113">Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator</span></span>](xref:Microsoft.Quantum.Canon.MultiplexerBruteForceFromGenerator)