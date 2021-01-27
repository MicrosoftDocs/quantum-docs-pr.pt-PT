---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingByLCU
title: Aplicação OperaçãoBlockEncodingByLCU
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingByLCU
qsharp.summary: Implementation of `BlockEncodingByLCU`.
ms.openlocfilehash: a9a9e3bbd598453719f49f78392f3a92c9401b36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852816"
---
# <a name="applyblockencodingbylcu-operation"></a><span data-ttu-id="5074c-102">Aplicação OperaçãoBlockEncodingByLCU</span><span class="sxs-lookup"><span data-stu-id="5074c-102">ApplyBlockEncodingByLCU operation</span></span>

<span data-ttu-id="5074c-103">Espaço de nome: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="5074c-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="5074c-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5074c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5074c-105">Implementação de `BlockEncodingByLCU` .</span><span class="sxs-lookup"><span data-stu-id="5074c-105">Implementation of `BlockEncodingByLCU`.</span></span>

```qsharp
operation ApplyBlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl), auxiliary : 'T, system : 'S) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5074c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="5074c-106">Input</span></span>

### <a name="statepreparation--t--unit--is-adj--ctl"></a><span data-ttu-id="5074c-107">estatalPreparação : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="5074c-107">statePreparation : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="selector--ts--unit--is-adj--ctl"></a><span data-ttu-id="5074c-108">seletor : ('T'S) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl</span><span class="sxs-lookup"><span data-stu-id="5074c-108">selector : ('T,'S) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="auxiliary--t"></a><span data-ttu-id="5074c-109">auxiliar : 'T</span><span class="sxs-lookup"><span data-stu-id="5074c-109">auxiliary : 'T</span></span>




### <a name="system--s"></a><span data-ttu-id="5074c-110">sistema : 'S</span><span class="sxs-lookup"><span data-stu-id="5074c-110">system : 'S</span></span>





## <a name="output--unit"></a><span data-ttu-id="5074c-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5074c-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5074c-112">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="5074c-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5074c-113">'T</span><span class="sxs-lookup"><span data-stu-id="5074c-113">'T</span></span>


### <a name="s"></a><span data-ttu-id="5074c-114">'S</span><span class="sxs-lookup"><span data-stu-id="5074c-114">'S</span></span>

