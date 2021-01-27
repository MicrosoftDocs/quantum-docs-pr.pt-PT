---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: Aplicar operaçãoPauli
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: b3557c6d8b5a90019f6d4cfa7b405475a3ab39fb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844744"
---
# <a name="applypauli-operation"></a><span data-ttu-id="a83c5-102">Aplicar operaçãoPauli</span><span class="sxs-lookup"><span data-stu-id="a83c5-102">ApplyPauli operation</span></span>

<span data-ttu-id="a83c5-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a83c5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a83c5-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a83c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a83c5-105">Dado um operador pauli multi-qubit, aplica a operação correspondente a um registo.</span><span class="sxs-lookup"><span data-stu-id="a83c5-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a83c5-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="a83c5-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="a83c5-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="a83c5-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="a83c5-108">Um operador de Pauli multi-qubit representado como uma variedade de operadores pauli de um único qubit.</span><span class="sxs-lookup"><span data-stu-id="a83c5-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="a83c5-109">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a83c5-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a83c5-110">Registe-se para aplicar a operação pauli dada.</span><span class="sxs-lookup"><span data-stu-id="a83c5-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a83c5-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a83c5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="a83c5-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a83c5-112">Example</span></span>

<span data-ttu-id="a83c5-113">Os seguintes são equivalentes:</span><span class="sxs-lookup"><span data-stu-id="a83c5-113">The following are equivalent:</span></span>

```qsharp
ApplyPauli([PauliY, PauliZ, PauliX], target);
```

<span data-ttu-id="a83c5-114">e</span><span class="sxs-lookup"><span data-stu-id="a83c5-114">and</span></span>

```qsharp
Y(target[0]);
Z(target[1]);
X(target[2]);
```