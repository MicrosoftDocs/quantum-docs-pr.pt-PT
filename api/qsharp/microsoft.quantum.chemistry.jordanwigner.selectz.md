---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: Operação SelectZ
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 2b38be5c196d81635daa8b478f6e727fdf378c62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850245"
---
# <a name="selectz-operation"></a><span data-ttu-id="79799-102">Operação SelectZ</span><span class="sxs-lookup"><span data-stu-id="79799-102">SelectZ operation</span></span>

<span data-ttu-id="79799-103">Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="79799-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="79799-104">Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="79799-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="79799-105">Um $U$ unitário que aplica o portão Pauli $Z$ em um qubits $p$ condicionados em um estado de índice $\ket{p}$.</span><span class="sxs-lookup"><span data-stu-id="79799-105">A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$.</span></span> <span data-ttu-id="79799-106">Ou seja, $$ \start{align} U\ket{p}\ket{\psi} = \ket{p}Z \_ p\ket{\psi} \end{align} $$</span><span class="sxs-lookup"><span data-stu-id="79799-106">That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$</span></span>

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="79799-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="79799-107">Input</span></span>

### <a name="indexregister--littleendian"></a><span data-ttu-id="79799-108">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="79799-108">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="79799-109">O estado $\ket{p}$ deste registo determina o qubit em que $Z$ é aplicado.</span><span class="sxs-lookup"><span data-stu-id="79799-109">The state $\ket{p}$ of this register determines the qubit on which $Z$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="79799-110">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="79799-110">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="79799-111">Registo de qubits em que são aplicados os operadores Pauli.</span><span class="sxs-lookup"><span data-stu-id="79799-111">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="79799-112">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="79799-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

