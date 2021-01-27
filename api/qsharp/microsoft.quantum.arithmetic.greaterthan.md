---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: Operação GreaterTh
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: 553efb0fc83f24235cb4a77933bd1d547bbd1fed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846637"
---
# <a name="greaterthan-operation"></a><span data-ttu-id="b14da-102">Operação GreaterTh</span><span class="sxs-lookup"><span data-stu-id="b14da-102">GreaterThan operation</span></span>

<span data-ttu-id="b14da-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="b14da-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="b14da-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b14da-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b14da-105">Aplica uma comparação maior do que a comparação entre dois inteiros codificados em registos qubit, lançando um qubit alvo com base no resultado da comparação.</span><span class="sxs-lookup"><span data-stu-id="b14da-105">Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.</span></span>

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="b14da-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="b14da-106">Description</span></span>

<span data-ttu-id="b14da-107">Realiza uma comparação estritamente maior do que a comparação de dois inteiros $x$ e $y$, codificados em qubit registers xs e ys.</span><span class="sxs-lookup"><span data-stu-id="b14da-107">Carries out a strictly greater than comparison of two integers $x$ and $y$, encoded in qubit registers xs and ys.</span></span> <span data-ttu-id="b14da-108">Se $x > y$, então o qubit do resultado será invertido, caso contrário o qubit de resultado manterá o seu estado.</span><span class="sxs-lookup"><span data-stu-id="b14da-108">If $x > y$, then the result qubit will be flipped, otherwise the result qubit will retain its state.</span></span>

## <a name="input"></a><span data-ttu-id="b14da-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="b14da-109">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="b14da-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b14da-110">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b14da-111">Registo de qubit littleEndian codificando o primeiro inteiro $x$.</span><span class="sxs-lookup"><span data-stu-id="b14da-111">LittleEndian qubit register encoding the first integer $x$.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="b14da-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b14da-112">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b14da-113">Registo de qubit littleEndian codificando o segundo número inteiro $y$.</span><span class="sxs-lookup"><span data-stu-id="b14da-113">LittleEndian qubit register encoding the second integer $y$.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="b14da-114">resultado : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b14da-114">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b14da-115">Um único qubit que será virado se $x > y$.</span><span class="sxs-lookup"><span data-stu-id="b14da-115">Single qubit that will be flipped if $x > y$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b14da-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b14da-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b14da-117">Observações</span><span class="sxs-lookup"><span data-stu-id="b14da-117">Remarks</span></span>

<span data-ttu-id="b14da-118">Usa o truque que $x - y = (x'+y)'$,'$, onde ' denota o complemento do outro.</span><span class="sxs-lookup"><span data-stu-id="b14da-118">Uses the trick that $x - y = (x'+y)'$, where ' denotes the one's complement.</span></span>

## <a name="references"></a><span data-ttu-id="b14da-119">Referências</span><span class="sxs-lookup"><span data-stu-id="b14da-119">References</span></span>

- <span data-ttu-id="b14da-120">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "Um novo circuito de adição de ondas quânticas", 2004.</span><span class="sxs-lookup"><span data-stu-id="b14da-120">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1

- <span data-ttu-id="b14da-121">Thomas Haener, Martin Roetteler, Krysta M. Svore: "Factoring using 2n+2 qubits com multiplicação modular baseada em Toffoli", 2016 https://arxiv.org/abs/1611.07995</span><span class="sxs-lookup"><span data-stu-id="b14da-121">Thomas Haener, Martin Roetteler, Krysta M. Svore: "Factoring using 2n+2 qubits with Toffoli based modular multiplication", 2016 https://arxiv.org/abs/1611.07995</span></span>