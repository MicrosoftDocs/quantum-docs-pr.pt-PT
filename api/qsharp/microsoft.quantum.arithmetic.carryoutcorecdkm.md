---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: Operação CarryOutCoreCDKM
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 6a292e66f6d9911d2a9075f6397f4f5ba97ec64d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721306"
---
# <a name="carryoutcorecdkm-operation"></a><span data-ttu-id="2fd97-102">Operação CarryOutCoreCDKM</span><span class="sxs-lookup"><span data-stu-id="2fd97-102">CarryOutCoreCDKM operation</span></span>

<span data-ttu-id="2fd97-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="2fd97-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="2fd97-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2fd97-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2fd97-105">A operação principal no RippleCarryAdderCDKM, utilizada com a operação ApplyOuterCDKMAdder, ou seja, conjugada com esta operação para obter o funcionamento interno do RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="2fd97-105">The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM.</span></span> <span data-ttu-id="2fd97-106">Esta operação calcula o qubit e aplica uma sequência de portões NOT por parte da entrada `ys` .</span><span class="sxs-lookup"><span data-stu-id="2fd97-106">This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.</span></span>

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="2fd97-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="2fd97-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="2fd97-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2fd97-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2fd97-109">Primeiro registo de qubits.</span><span class="sxs-lookup"><span data-stu-id="2fd97-109">First qubit register.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="2fd97-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2fd97-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2fd97-111">Segundo registo de qubits.</span><span class="sxs-lookup"><span data-stu-id="2fd97-111">Second qubit register.</span></span>


### <a name="ancilla--qubit"></a><span data-ttu-id="2fd97-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2fd97-112">ancilla : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2fd97-113">O qubit de ancilla usado em RippleCarryAdderCDKM passou para esta operação.</span><span class="sxs-lookup"><span data-stu-id="2fd97-113">The ancilla qubit used in RippleCarryAdderCDKM passed to this operation.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="2fd97-114">transporte : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2fd97-114">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2fd97-115">Efetuar qubit na operação RippleCarryAdderCDKM.</span><span class="sxs-lookup"><span data-stu-id="2fd97-115">Carry out qubit in the RippleCarryAdderCDKM operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2fd97-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2fd97-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="2fd97-117">Referências</span><span class="sxs-lookup"><span data-stu-id="2fd97-117">References</span></span>

- <span data-ttu-id="2fd97-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "Um novo circuito de adição de ondas quânticas", 2004.</span><span class="sxs-lookup"><span data-stu-id="2fd97-118">Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A new quantum ripple-carry addition circuit", 2004.</span></span>
  https://arxiv.org/abs/quant-ph/0410184v1