---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: Operação QuantumPhaseEstimation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 7e524477a4b2bcd8d6767441e278fbf501355e0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714948"
---
# <a name="quantumphaseestimation-operation"></a><span data-ttu-id="771ec-102">Operação QuantumPhaseEstimation</span><span class="sxs-lookup"><span data-stu-id="771ec-102">QuantumPhaseEstimation operation</span></span>

<span data-ttu-id="771ec-103">Espaço de nome: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="771ec-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="771ec-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="771ec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="771ec-105">Executa o algoritmo de estimativa da fase quântica para um dado oráculo `U` `targetState` e, lendo a fase num registo quântico de grande ponta.</span><span class="sxs-lookup"><span data-stu-id="771ec-105">Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.</span></span>

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="771ec-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="771ec-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="771ec-107">oráculo : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="771ec-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="771ec-108">Uma operação que implementa $U^m$ para dados poderes inteiros m.</span><span class="sxs-lookup"><span data-stu-id="771ec-108">An operation implementing $U^m$ for given integer powers m.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="771ec-109">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="771ec-109">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="771ec-110">Um registo quântico que representa o estado $\ket{\phi}$ agido por $U$.</span><span class="sxs-lookup"><span data-stu-id="771ec-110">A quantum register representing the state $\ket{\phi}$ acted on by $U$.</span></span> <span data-ttu-id="771ec-111">Se $\ket{\phi}$ é um eigenstate de $U$, $U\ket{\phi} = e^{i\phi} \ket{\phi}$ por $\phi \in [0, 2\pi)$ uma fase desconhecida.</span><span class="sxs-lookup"><span data-stu-id="771ec-111">If $\ket{\phi}$ is an eigenstate of $U$, $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi \in [0, 2\pi)$ an unknown phase.</span></span>


### <a name="controlregister--bigendian"></a><span data-ttu-id="771ec-112">controlRegister : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="771ec-112">controlRegister : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="771ec-113">Um registo inteiro de representação de grande ponta que pode ser usado para controlar o oráculo fornecido, e que conterá a representação de $\phi$ após a aplicação desta operação.</span><span class="sxs-lookup"><span data-stu-id="771ec-113">A big-endian representation integer register that can be used to control the provided oracle, and that will contain the a representation of $\phi$ following the application of this operation.</span></span> <span data-ttu-id="771ec-114">Presume-se que o controlRegister comece no estado inicial $\ket{00\cdots 0}$, onde o comprimento do registo indica a precisão desejada.</span><span class="sxs-lookup"><span data-stu-id="771ec-114">The controlRegister is assumed to start in the initial state $\ket{00\cdots 0}$, where the length of the register indicates the desired precision.</span></span>



## <a name="output--unit"></a><span data-ttu-id="771ec-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="771ec-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

