---
uid: Microsoft.Quantum.ErrorCorrection._ExtractLogicalQubitFromSteaneCode
title: operação _ExtractLogicalQubitFromSteaneCode
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: _ExtractLogicalQubitFromSteaneCode
qsharp.summary: >-
  Syndrome measurement and the inverse of embedding.

  $X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit. This asymmetry leads to a different syndrome extraction routine. One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.
ms.openlocfilehash: 71390feb84660cc9bf7bb12b64eac6d3ca512387
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712557"
---
# <a name="_extractlogicalqubitfromsteanecode-operation"></a><span data-ttu-id="0fc5a-102">operação _ExtractLogicalQubitFromSteaneCode</span><span class="sxs-lookup"><span data-stu-id="0fc5a-102">_ExtractLogicalQubitFromSteaneCode operation</span></span>

<span data-ttu-id="0fc5a-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="0fc5a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="0fc5a-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0fc5a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0fc5a-105">Medição da síndrome e o inverso da incorporação.</span><span class="sxs-lookup"><span data-stu-id="0fc5a-105">Syndrome measurement and the inverse of embedding.</span></span>

<span data-ttu-id="0fc5a-106">$X os estabilizadores de $- e $Z não são tratados de forma igual, o que se deve à escolha particular do circuito de codificação.</span><span class="sxs-lookup"><span data-stu-id="0fc5a-106">$X$- and $Z$-stabilizers are not treated equally, which is due to the particular choice of the encoding circuit.</span></span>
<span data-ttu-id="0fc5a-107">Esta assimetria leva a uma rotina de extração de síndrome diferente.</span><span class="sxs-lookup"><span data-stu-id="0fc5a-107">This asymmetry leads to a different syndrome extraction routine.</span></span>
<span data-ttu-id="0fc5a-108">Pode-se medir a síndrome medindo o operador pauli multi-qubit diretamente no estado de código, mas para o propósito de destilação o qubit lógico é devolvido a um único qubit, no decurso do qual as medições da síndrome podem ser feitas sem mais ancillas.</span><span class="sxs-lookup"><span data-stu-id="0fc5a-108">One could measure the syndrome by measuring multi-qubit Pauli operator directly on the code state, but for the distillation purpose the logical qubit is returned into a single qubit, in course of which the syndrome measurements can be done without further ancillas.</span></span>

```qsharp
operation _ExtractLogicalQubitFromSteaneCode (code : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit, Int, Int)
```


## <a name="input"></a><span data-ttu-id="0fc5a-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="0fc5a-109">Input</span></span>

### <a name="code--logicalregister"></a><span data-ttu-id="0fc5a-110">código : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="0fc5a-110">code : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>





## <a name="output--qubitintint"></a><span data-ttu-id="0fc5a-111">Saída :[(Qubit,](xref:microsoft.quantum.lang-ref.qubit)[Int,](xref:microsoft.quantum.lang-ref.int)[Int)](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0fc5a-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

<span data-ttu-id="0fc5a-112">O qubit lógico e um par de inteiros para $X síndrome de $-síndrome e $Z de $-síndrome.</span><span class="sxs-lookup"><span data-stu-id="0fc5a-112">The logical qubit and a pair of integers for $X$-syndrome and $Z$-syndrome.</span></span>
<span data-ttu-id="0fc5a-113">Representam o índice do qubit de código no qual um único $X$- ou $Z$-error teria causado a síndrome medida.</span><span class="sxs-lookup"><span data-stu-id="0fc5a-113">They represent the index of the code qubit on which a single $X$- or $Z$-error would have caused the measured syndrome.</span></span>

## <a name="remarks"></a><span data-ttu-id="0fc5a-114">Observações</span><span class="sxs-lookup"><span data-stu-id="0fc5a-114">Remarks</span></span>

<span data-ttu-id="0fc5a-115">Note que esta operação não está marcada como , uma vez que `internal` os testes unitários dependem diretamente desta operação.</span><span class="sxs-lookup"><span data-stu-id="0fc5a-115">Note that this operation is not marked as `internal`, as unit tests directly depend on this operation.</span></span> <span data-ttu-id="0fc5a-116">Como melhoria futura, os testes unitários devem ser refaccionados para depender apenas de chamadas públicas diretamente.</span><span class="sxs-lookup"><span data-stu-id="0fc5a-116">As a future improvement, unit tests should be refactored to depend only on public callables directly.</span></span>

> [!WARNING]
> <span data-ttu-id="0fc5a-117">Esta rotina é adaptada a um circuito de codificação específico para o código 7 qubit da Steane; se o circuito de codificação for modificado, então o resultado da síndrome pode ter de ser interpretado de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="0fc5a-117">This routine is tailored to a particular encoding circuit for Steane's 7 qubit code; if the encoding circuit is modified then the syndrome outcome might have to be interpreted differently.</span></span>