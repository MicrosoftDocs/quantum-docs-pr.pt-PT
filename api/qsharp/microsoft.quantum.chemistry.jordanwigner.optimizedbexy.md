---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEXY
title: Operação OPTIMIZadaBEXY
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBEXY
qsharp.summary: A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$. That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$
ms.openlocfilehash: 359d347fc57be46200a218646911a7a400b4a96d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713912"
---
# <a name="optimizedbexy-operation"></a><span data-ttu-id="e2b58-102">Operação OPTIMIZadaBEXY</span><span class="sxs-lookup"><span data-stu-id="e2b58-102">OptimizedBEXY operation</span></span>

<span data-ttu-id="e2b58-103">Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="e2b58-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="e2b58-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e2b58-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e2b58-105">Um $U$ unitário que aplica a corda Pauli em $(X^{z+1} \_ pY^{z} \_ p)Z \_ {p-1}... Z_0$ em qubits $0.p$ condicionados a um índice $z\em \{ 0,1$ \} e $p$.</span><span class="sxs-lookup"><span data-stu-id="e2b58-105">A unitary $U$ that applies the Pauli string on $(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0$ on qubits $0..p$ conditioned on an index $z\in\{0,1\}$ and $p$.</span></span> <span data-ttu-id="e2b58-106">Ou seja, $$ \start{align} U\ket{z}\ket{p}\ket{\\ket{\psi} = \ket{z}\ket{p}(X^{z+1} \_ pY^{z} \_ p)Z \_ {p-1}... Z_0\ket{\psi} \end{align} $$</span><span class="sxs-lookup"><span data-stu-id="e2b58-106">That is, $$ \begin{align} U\ket{z}\ket{p}\ket{\psi} = \ket{z}\ket{p}(X^{z+1}\_pY^{z}\_p)Z\_{p-1}...Z_0\ket{\psi} \end{align} $$</span></span>

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e2b58-107">Entrada</span><span class="sxs-lookup"><span data-stu-id="e2b58-107">Input</span></span>

### <a name="paulibasis--qubit"></a><span data-ttu-id="e2b58-108">pauliBasis : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e2b58-108">pauliBasis : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e2b58-109">Quando este qubit estiver no estado $\ket {0} $,, $X$ é aplicado.</span><span class="sxs-lookup"><span data-stu-id="e2b58-109">When this qubit is in state $\ket{0}$, $X$ is applied.</span></span> <span data-ttu-id="e2b58-110">Quando está no estado $\ket {1} $,, $Y$ é aplicado.</span><span class="sxs-lookup"><span data-stu-id="e2b58-110">When it is in state $\ket{1}$, $Y$ is applied.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="e2b58-111">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e2b58-111">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="e2b58-112">O estado $\ket{p}$ deste registo determina o qubit em que $X$ ou $Y$ é aplicado.</span><span class="sxs-lookup"><span data-stu-id="e2b58-112">The state $\ket{p}$ of this register determines the qubit on which $X$ or $Y$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="e2b58-113">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e2b58-113">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e2b58-114">Registo de qubits em que são aplicados os operadores Pauli.</span><span class="sxs-lookup"><span data-stu-id="e2b58-114">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e2b58-115">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e2b58-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="e2b58-116">Referências</span><span class="sxs-lookup"><span data-stu-id="e2b58-116">References</span></span>

- <span data-ttu-id="e2b58-117">Codificação de Espectros Eletrónicos em Circuitos Quânticos com Complexidade Linear T Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="e2b58-117">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>