---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: Aplicar operaçãoPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: ccf8e1b3dbe5d4cd916a581aeab190ab0cff2021
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717818"
---
# <a name="applypauli-operation"></a><span data-ttu-id="13856-102">Aplicar operaçãoPauli</span><span class="sxs-lookup"><span data-stu-id="13856-102">ApplyPauli operation</span></span>

<span data-ttu-id="13856-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="13856-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="13856-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="13856-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="13856-105">Dado um operador pauli multi-qubit, aplica a operação correspondente a um registo.</span><span class="sxs-lookup"><span data-stu-id="13856-105">Given a multi-qubit Pauli operator, applies the corresponding operation to a register.</span></span>

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="13856-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="13856-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="13856-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="13856-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="13856-108">Um operador de Pauli multi-qubit representado como uma variedade de operadores pauli de um único qubit.</span><span class="sxs-lookup"><span data-stu-id="13856-108">A multi-qubit Pauli operator represented as an array of single-qubit Pauli operators.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="13856-109">alvo: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="13856-109">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="13856-110">Registe-se para aplicar a operação pauli dada.</span><span class="sxs-lookup"><span data-stu-id="13856-110">Register to apply the given Pauli operation on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="13856-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="13856-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

