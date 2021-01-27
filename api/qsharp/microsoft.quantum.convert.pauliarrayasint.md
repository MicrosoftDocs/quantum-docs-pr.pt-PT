---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: Função PauliArrayAsInt
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 4c3c51813ef509fdc52773b15a956c0a99500603
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832712"
---
# <a name="pauliarrayasint-function"></a><span data-ttu-id="e1b06-102">Função PauliArrayAsInt</span><span class="sxs-lookup"><span data-stu-id="e1b06-102">PauliArrayAsInt function</span></span>

<span data-ttu-id="e1b06-103">Espaço de nome: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="e1b06-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="e1b06-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e1b06-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e1b06-105">Codifica um operador pauli multi-qubit representado como uma matriz de operadores pauli de um único qubit em um inteiro.</span><span class="sxs-lookup"><span data-stu-id="e1b06-105">Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.</span></span>

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a><span data-ttu-id="e1b06-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e1b06-106">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="e1b06-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="e1b06-107">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="e1b06-108">Uma série de, no máximo, 31 operadores de Pauli de um único qubit.</span><span class="sxs-lookup"><span data-stu-id="e1b06-108">An array of at most 31 single-qubit Pauli operators.</span></span>



## <a name="output--int"></a><span data-ttu-id="e1b06-109">Saída : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e1b06-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e1b06-110">Um inteiro identificando `paulis` exclusivamente, como descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="e1b06-110">An integer uniquely identifying `paulis`, as described below.</span></span>

## <a name="remarks"></a><span data-ttu-id="e1b06-111">Observações</span><span class="sxs-lookup"><span data-stu-id="e1b06-111">Remarks</span></span>

<span data-ttu-id="e1b06-112">Cada operador Pauli pode ser codificado usando dois bits: $$ \start{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span><span class="sxs-lookup"><span data-stu-id="e1b06-112">Each Pauli operator can be encoded using two bits: $$ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.</span></span>
<span data-ttu-id="e1b06-113">\end{align} $$</span><span class="sxs-lookup"><span data-stu-id="e1b06-113">\end{align} $$</span></span>

<span data-ttu-id="e1b06-114">Dada uma série de operadores `[P0, ..., Pn]` Pauli, esta função devolve um inteiro com expansão binária formada pela concatenação dos mapeamentos de cada operador Pauli em ordem de grande `bits(Pn) ... bits(P0)` ponta.</span><span class="sxs-lookup"><span data-stu-id="e1b06-114">Given an array of Pauli operators `[P0, ..., Pn]`, this function returns an integer with binary expansion formed by concatenating the mappings of each Pauli operator in big-endian order `bits(Pn) ... bits(P0)`.</span></span>