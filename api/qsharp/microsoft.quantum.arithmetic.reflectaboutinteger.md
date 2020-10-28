---
uid: Microsoft.Quantum.Arithmetic.ReflectAboutInteger
title: Refletir Sobre a operação Deinteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ReflectAboutInteger
qsharp.summary: Reflects a quantum register about a given classical integer.
ms.openlocfilehash: e034f0a24d5c2f0465ebd1914b28cb8c695d978c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719711"
---
# <a name="reflectaboutinteger-operation"></a><span data-ttu-id="d41b2-102">Refletir Sobre a operação Deinteger</span><span class="sxs-lookup"><span data-stu-id="d41b2-102">ReflectAboutInteger operation</span></span>

<span data-ttu-id="d41b2-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d41b2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d41b2-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d41b2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d41b2-105">Reflete um registo quântico sobre um dado número inteiro clássico.</span><span class="sxs-lookup"><span data-stu-id="d41b2-105">Reflects a quantum register about a given classical integer.</span></span>

```qsharp
operation ReflectAboutInteger (index : Int, reg : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="d41b2-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="d41b2-106">Description</span></span>

<span data-ttu-id="d41b2-107">Dado um registo quântico inicialmente no estado $\sum_i \alpha_i \ket{i}$, onde cada $\ket{i}$ é um estado de base que representa um número inteiro $i$, reflete o estado do registo sobre o estado de base para um dado inteiro $\ket{j}$, $$ \sum_i (-1)^{\ \delta_{ij} } \alpha_i \ket{i} $$</span><span class="sxs-lookup"><span data-stu-id="d41b2-107">Given a quantum register initially in the state $\sum_i \alpha_i \ket{i}$, where each $\ket{i}$ is a basis state representing an integer $i$, reflects the state of the register about the basis state for a given integer $\ket{j}$, $$ \sum_i (-1)^{ \delta_{ij} } \alpha_i \ket{i} $$</span></span>

## <a name="input"></a><span data-ttu-id="d41b2-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="d41b2-108">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="d41b2-109">índice : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d41b2-109">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d41b2-110">O inteiro clássico indexando o estado de base sobre o qual refletir.</span><span class="sxs-lookup"><span data-stu-id="d41b2-110">The classical integer indexing the basis state about which to reflect.</span></span>


### <a name="reg--littleendian"></a><span data-ttu-id="d41b2-111">reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d41b2-111">reg : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="d41b2-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d41b2-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d41b2-113">Observações</span><span class="sxs-lookup"><span data-stu-id="d41b2-113">Remarks</span></span>

<span data-ttu-id="d41b2-114">Esta operação é implementada no local, sem atribuição explícita de qubits auxiliares adicionais.</span><span class="sxs-lookup"><span data-stu-id="d41b2-114">This operation is implemented in-place, without explicit allocation of additional auxiliary qubits.</span></span>