---
uid: Microsoft.Quantum.Preparation._PrepareAmplitudesFromZeroState
title: operação _PrepareAmplitudesFromZeroState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: _PrepareAmplitudesFromZeroState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register of unentangled qubits, all of which are in zero state, prepares a state on that register described by the given coefficients. Uses state emulation if supported by the target.
ms.openlocfilehash: 94563632d514f66608b14c264a73bdfcc6f50982
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854451"
---
# <a name="_prepareamplitudesfromzerostate-operation"></a><span data-ttu-id="da85f-102">operação _PrepareAmplitudesFromZeroState</span><span class="sxs-lookup"><span data-stu-id="da85f-102">_PrepareAmplitudesFromZeroState operation</span></span>

<span data-ttu-id="da85f-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="da85f-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="da85f-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="da85f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="da85f-105">Dado um conjunto de coeficientes e um pequeno registo quântico codificado de qubits não emaranhados, todos em estado zero, prepara um estado nesse registo descrito pelos coeficientes determinados.</span><span class="sxs-lookup"><span data-stu-id="da85f-105">Given a set of coefficients and a little-endian encoded quantum register of unentangled qubits, all of which are in zero state, prepares a state on that register described by the given coefficients.</span></span> <span data-ttu-id="da85f-106">Usa a emulação do estado se for apoiada pelo alvo.</span><span class="sxs-lookup"><span data-stu-id="da85f-106">Uses state emulation if supported by the target.</span></span>

```qsharp
operation _PrepareAmplitudesFromZeroState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="da85f-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="da85f-107">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="da85f-108">coeficientes : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="da85f-108">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>




### <a name="qubits--littleendian"></a><span data-ttu-id="da85f-109">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="da85f-109">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>





## <a name="output--unit"></a><span data-ttu-id="da85f-110">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="da85f-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

