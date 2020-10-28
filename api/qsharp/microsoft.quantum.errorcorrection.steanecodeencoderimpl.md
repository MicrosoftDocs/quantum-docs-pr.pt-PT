---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: Operação SteaneCodeEncoderImpl
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: b843422a6007d01de9b57ec659c229b8ab0ad2e6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712190"
---
# <a name="steanecodeencoderimpl-operation"></a><span data-ttu-id="239d0-102">Operação SteaneCodeEncoderImpl</span><span class="sxs-lookup"><span data-stu-id="239d0-102">SteaneCodeEncoderImpl operation</span></span>

<span data-ttu-id="239d0-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="239d0-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="239d0-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="239d0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="239d0-105">Operação privada usada para implementar o codificador de código Steane e o descodificador.</span><span class="sxs-lookup"><span data-stu-id="239d0-105">Private operation used to implement both the Steane code encoder and decoder.</span></span>

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="239d0-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="239d0-106">Input</span></span>

### <a name="data--qubit"></a><span data-ttu-id="239d0-107">dados : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="239d0-107">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="239d0-108">uma matriz segurando 1 qubit que é o qubit de entrada.</span><span class="sxs-lookup"><span data-stu-id="239d0-108">an array holding 1 qubit which is the input qubit.</span></span>


### <a name="scratch--qubit"></a><span data-ttu-id="239d0-109">risca: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="239d0-109">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="239d0-110">uma matriz segurando 6 qubits que adicionam redundância.</span><span class="sxs-lookup"><span data-stu-id="239d0-110">an array holding 6 qubits which add redundancy.</span></span>



## <a name="output--unit"></a><span data-ttu-id="239d0-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="239d0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

