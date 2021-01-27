---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroA
title: Aplicação OperaçãoIfZeroA
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroA
qsharp.summary: ''
ms.openlocfilehash: 812b7a830d963b4bb73c32ba1c136e506789e997
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854205"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="61bec-102">Aplicação OperaçãoIfZeroA</span><span class="sxs-lookup"><span data-stu-id="61bec-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="61bec-103">Espaço de nome: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="61bec-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="61bec-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="61bec-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfZeroA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="61bec-105">Entrada</span><span class="sxs-lookup"><span data-stu-id="61bec-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="61bec-106">measurementResult : __inválido <Result>__</span><span class="sxs-lookup"><span data-stu-id="61bec-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit--is-adj"></a><span data-ttu-id="61bec-107">onResultZeroOp : 'T = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="61bec-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="61bec-108">zeroArg : 'T</span><span class="sxs-lookup"><span data-stu-id="61bec-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="61bec-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61bec-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="61bec-110">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="61bec-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="61bec-111">'T</span><span class="sxs-lookup"><span data-stu-id="61bec-111">'T</span></span>

