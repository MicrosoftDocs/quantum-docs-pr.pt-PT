---
uid: Microsoft.Quantum.Canon.RAll1
title: Operação RAll1
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: 45892f9811faf56d7b9a0eb34e4bde0a32d5586d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715623"
---
# <a name="rall1-operation"></a><span data-ttu-id="88ab6-102">Operação RAll1</span><span class="sxs-lookup"><span data-stu-id="88ab6-102">RAll1 operation</span></span>

<span data-ttu-id="88ab6-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="88ab6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="88ab6-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="88ab6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="88ab6-105">Realiza uma operação de mudança de fase.</span><span class="sxs-lookup"><span data-stu-id="88ab6-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="88ab6-106">$R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.</span><span class="sxs-lookup"><span data-stu-id="88ab6-106">$R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="88ab6-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="88ab6-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="88ab6-108">fase : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="88ab6-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="88ab6-109">A fase $\phi$ aplicada ao estado $\ket{1\cdots 1}\bra{1\cdots 1}$.</span><span class="sxs-lookup"><span data-stu-id="88ab6-109">The phase $\phi$ applied to state $\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="88ab6-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="88ab6-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="88ab6-111">O registo cujo estado deve ser rodado por $R dólares.</span><span class="sxs-lookup"><span data-stu-id="88ab6-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="88ab6-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="88ab6-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

