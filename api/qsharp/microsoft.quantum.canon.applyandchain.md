---
uid: Microsoft.Quantum.Canon.ApplyAndChain
title: Aplicar Operação Operação Operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAndChain
qsharp.summary: Computes a chain of AND gates
ms.openlocfilehash: 3991ded1a9c70bf4b58d19b0304a1df3b31896d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842008"
---
# <a name="applyandchain-operation"></a><span data-ttu-id="ec875-102">Aplicar Operação Operação Operação</span><span class="sxs-lookup"><span data-stu-id="ec875-102">ApplyAndChain operation</span></span>

<span data-ttu-id="ec875-103">Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ec875-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ec875-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec875-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec875-105">Calcula uma cadeia de portões E</span><span class="sxs-lookup"><span data-stu-id="ec875-105">Computes a chain of AND gates</span></span>

```qsharp
operation ApplyAndChain (auxRegister : Qubit[], ctrlRegister : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="ec875-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="ec875-106">Description</span></span>

<span data-ttu-id="ec875-107">Os qubits auxiliares para calcular os resultados temporários devem ser explicitamente especificados.</span><span class="sxs-lookup"><span data-stu-id="ec875-107">The auxiliary qubits to compute temporary results must be specified explicitly.</span></span>
<span data-ttu-id="ec875-108">O comprimento desse registo é `Length(ctrlRegister) - 2` , se houver pelo menos dois controlos, caso contrário o comprimento é 0.</span><span class="sxs-lookup"><span data-stu-id="ec875-108">The length of that register is `Length(ctrlRegister) - 2`, if there are at least two controls, otherwise the length is 0.</span></span>

## <a name="input"></a><span data-ttu-id="ec875-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="ec875-109">Input</span></span>

### <a name="auxregister--qubit"></a><span data-ttu-id="ec875-110">auxRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ec875-110">auxRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="ctrlregister--qubit"></a><span data-ttu-id="ec875-111">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ec875-111">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="ec875-112">alvo : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ec875-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="ec875-113">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ec875-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

