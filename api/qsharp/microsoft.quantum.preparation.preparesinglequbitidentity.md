---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: Preparar operação DesingleQubitIdentity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 12a650568aa5682e8fb6498808d188b154527acb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724881"
---
# <a name="preparesinglequbitidentity-operation"></a><span data-ttu-id="5c6b0-102">Preparar operação DesingleQubitIdentity</span><span class="sxs-lookup"><span data-stu-id="5c6b0-102">PrepareSingleQubitIdentity operation</span></span>

<span data-ttu-id="5c6b0-103">Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="5c6b0-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="5c6b0-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5c6b0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5c6b0-105">Prepara um qubit no estado máximo misturado.</span><span class="sxs-lookup"><span data-stu-id="5c6b0-105">Prepares a qubit in the maximally mixed state.</span></span>

<span data-ttu-id="5c6b0-106">Prepara o qubit dado no estado $\boldone / 2$ aplicando o canal despolarizante $$ \start{align} \Omega(\rho) \mathrel{:=} {1} {4} \frac \sum_{\mu \in \{ 0, 1, 2, 3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu}{\\dagger}, \end{align} $$ where $\sigma \_ i$ é o operador de pauli $i$th, e onde $\rho$ é um operador de densidade que representa um estado misto.</span><span class="sxs-lookup"><span data-stu-id="5c6b0-106">It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.</span></span>

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="5c6b0-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="5c6b0-107">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="5c6b0-108">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5c6b0-108">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="5c6b0-109">Um qubit cujo estado deve ser despolarizado da maneira acima descrita.</span><span class="sxs-lookup"><span data-stu-id="5c6b0-109">A qubit whose state is to be depolarized in the manner described above.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5c6b0-110">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5c6b0-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5c6b0-111">Observações</span><span class="sxs-lookup"><span data-stu-id="5c6b0-111">Remarks</span></span>

<span data-ttu-id="5c6b0-112">O estado misto $\boldone / 2$ descrevendo o resultado da aplicação desta operação a um estado implicitamente descreve um valor de expectativa sobre as escolhas aleatórias feitas nesta operação.</span><span class="sxs-lookup"><span data-stu-id="5c6b0-112">The mixed state $\boldone / 2$ describing the result of applying this operation to a state implicitly describes an expectation value over random choices made in this operation.</span></span>
<span data-ttu-id="5c6b0-113">Assim, para qualquer aplicação, esta operação mapeia estados puros para estados puros, mas age como descrito na expectativa.</span><span class="sxs-lookup"><span data-stu-id="5c6b0-113">Thus, for any single application, this operation maps pure states to pure states, but it acts as described in expectation.</span></span>
<span data-ttu-id="5c6b0-114">Em particular, esta operação pode ser utilizada em tomografia de processo para medir os componentes *não unitais* de um canal.</span><span class="sxs-lookup"><span data-stu-id="5c6b0-114">In particular, this operation can be used in process tomography to measure the *non-unital* components of a channel.</span></span>