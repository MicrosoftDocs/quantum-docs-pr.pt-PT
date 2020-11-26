---
uid: Microsoft.Quantum.Preparation._PrepareAmplitudesFromZeroState
title: operação _PrepareAmplitudesFromZeroState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: _PrepareAmplitudesFromZeroState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register of unentangled qubits, all of which are in zero state, prepares a state on that register described by the given coefficients. Uses state emulation if supported by the target.
ms.openlocfilehash: 3d90b455bace7b0de1c8c01a5b9b007d719df950
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226592"
---
# <a name="_prepareamplitudesfromzerostate-operation"></a><span data-ttu-id="9b3bc-102">operação _PrepareAmplitudesFromZeroState</span><span class="sxs-lookup"><span data-stu-id="9b3bc-102">_PrepareAmplitudesFromZeroState operation</span></span>

<span data-ttu-id="9b3bc-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="9b3bc-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="9b3bc-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9b3bc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9b3bc-105">Dado um conjunto de coeficientes e um pequeno registo quântico codificado de qubits não emaranhados, todos em estado zero, prepara um estado nesse registo descrito pelos coeficientes determinados.</span><span class="sxs-lookup"><span data-stu-id="9b3bc-105">Given a set of coefficients and a little-endian encoded quantum register of unentangled qubits, all of which are in zero state, prepares a state on that register described by the given coefficients.</span></span> <span data-ttu-id="9b3bc-106">Usa a emulação do estado se for apoiada pelo alvo.</span><span class="sxs-lookup"><span data-stu-id="9b3bc-106">Uses state emulation if supported by the target.</span></span>

```qsharp
operation _PrepareAmplitudesFromZeroState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="9b3bc-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="9b3bc-107">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="9b3bc-108">coeficientes : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="9b3bc-108">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>




### <a name="qubits--littleendian"></a><span data-ttu-id="9b3bc-109">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="9b3bc-109">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="9b3bc-110">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b3bc-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

