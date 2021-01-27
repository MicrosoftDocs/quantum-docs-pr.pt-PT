---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: Aplicação OperaçãoBitFlipEncoder
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: cc70cc409cb472a747899838d3a9ad2d78f6b5ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827701"
---
# <a name="applybitflipencoder-operation"></a><span data-ttu-id="85d60-102">Aplicação OperaçãoBitFlipEncoder</span><span class="sxs-lookup"><span data-stu-id="85d60-102">ApplyBitFlipEncoder operation</span></span>

<span data-ttu-id="85d60-103">Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="85d60-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="85d60-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="85d60-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="85d60-105">Operação privada usada para implementar tanto o codificader bit flip como o descodificador.</span><span class="sxs-lookup"><span data-stu-id="85d60-105">Private operation used to implement both the bit flip encoder and decoder.</span></span>

<span data-ttu-id="85d60-106">Note-se que este codificadora pode recorrer a uma recuperação coerente no local, caso em que irá "causar" o erro descrito pelo estado inicial de `auxQubits` .</span><span class="sxs-lookup"><span data-stu-id="85d60-106">Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`.</span></span>
<span data-ttu-id="85d60-107">Em particular, se `auxQubits` estiverem inicialmente no estado $\ket {10} $, isto causará um erro de $X_1$ no qubit codificado.</span><span class="sxs-lookup"><span data-stu-id="85d60-107">In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.</span></span>

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="85d60-108">Entrada</span><span class="sxs-lookup"><span data-stu-id="85d60-108">Input</span></span>

### <a name="coherentrecovery--bool"></a><span data-ttu-id="85d60-109">coerenteRecovery : [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="85d60-109">coherentRecovery : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="data--qubit"></a><span data-ttu-id="85d60-110">dados : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="85d60-110">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="scratch--qubit"></a><span data-ttu-id="85d60-111">risca: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="85d60-111">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="85d60-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="85d60-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="85d60-113">Referências</span><span class="sxs-lookup"><span data-stu-id="85d60-113">References</span></span>

- <span data-ttu-id="85d60-114">doi:10.1103/PhysRevA.85.044302</span><span class="sxs-lookup"><span data-stu-id="85d60-114">doi:10.1103/PhysRevA.85.044302</span></span>