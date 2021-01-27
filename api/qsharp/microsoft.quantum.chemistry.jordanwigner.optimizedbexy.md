---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEXY
title: Operação OPTIMIZadaBEXY
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEXY
qsharp.summary: A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$. That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$
ms.openlocfilehash: 28a7c7877a3d48fd5ba50384d7996017e7cdb14f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837255"
---
# <a name="optimizedbexy-operation"></a><span data-ttu-id="aab08-102">Operação OPTIMIZadaBEXY</span><span class="sxs-lookup"><span data-stu-id="aab08-102">OptimizedBEXY operation</span></span>

<span data-ttu-id="aab08-103">Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="aab08-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="aab08-104">Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="aab08-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="aab08-105">Um $U$ unitário que aplica a corda Pauli em $(X^{z+1} \_ pY^{z} \_ p)Z \_ {p-1}... Z_0$ em qubits $0.p$ condicionados a um índice $z\em \{ 0,1$ \} e $p$.</span><span class="sxs-lookup"><span data-stu-id="aab08-105">A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$.</span></span> <span data-ttu-id="aab08-106">Ou seja, $$ \start{align} U\ket{z}\ket{p}\ket{\\ket{\psi} = \ket{z}\ket{p}(X^{z+1} \_ pY^{z} \_ p)Z \_ {p-1}... Z_0\ket{\psi} \end{align} $$</span><span class="sxs-lookup"><span data-stu-id="aab08-106">That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$</span></span>

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="aab08-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="aab08-107">Input</span></span>

### <a name="paulibasis--qubit"></a><span data-ttu-id="aab08-108">pauliBasis : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="aab08-108">pauliBasis : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="aab08-109">Quando este qubit estiver no estado $\ket {0} $,, $X$ é aplicado.</span><span class="sxs-lookup"><span data-stu-id="aab08-109">When this qubit is in state $\ket{0}$, $X$ is applied.</span></span> <span data-ttu-id="aab08-110">Quando está no estado $\ket {1} $,, $Y$ é aplicado.</span><span class="sxs-lookup"><span data-stu-id="aab08-110">When it is in state $\ket{1}$, $Y$ is applied.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="aab08-111">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="aab08-111">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="aab08-112">O estado $\ket{p}$ deste registo determina o qubit em que $X$ ou $Y$ é aplicado.</span><span class="sxs-lookup"><span data-stu-id="aab08-112">The state $\ket{p}$ of this register determines the qubit on which $X$ or $Y$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="aab08-113">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="aab08-113">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="aab08-114">Registo de qubits em que são aplicados os operadores Pauli.</span><span class="sxs-lookup"><span data-stu-id="aab08-114">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aab08-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aab08-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="aab08-116">Referências</span><span class="sxs-lookup"><span data-stu-id="aab08-116">References</span></span>

- <span data-ttu-id="aab08-117">Codificação de Espectros Eletrónicos em Circuitos Quânticos com Complexidade Linear T Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="aab08-117">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>