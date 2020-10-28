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
# <a name="optimizedbexy-operation"></a>Operação OPTIMIZadaBEXY

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pacote: [](https://nuget.org/packages/)


Um $U$ unitário que aplica a corda Pauli em $(X^{z+1} \_ pY^{z} \_ p)Z \_ {p-1}... Z_0$ em qubits $0.p$ condicionados a um índice $z\em \{ 0,1$ \} e $p$. Ou seja, $$ \start{align} U\ket{z}\ket{p}\ket{\\ket{\psi} = \ket{z}\ket{p}(X^{z+1} \_ pY^{z} \_ p)Z \_ {p-1}... Z_0\ket{\psi} \end{align} $$

```qsharp
operation OptimizedBEXY (pauliBasis : Qubit, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a>Entrada

### <a name="paulibasis--qubit"></a>pauliBasis : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Quando este qubit estiver no estado $\ket {0} $,, $X$ é aplicado. Quando está no estado $\ket {1} $,, $Y$ é aplicado.


### <a name="indexregister--littleendian"></a>indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

O estado $\ket{p}$ deste registo determina o qubit em que $X$ ou $Y$ é aplicado.


### <a name="targetregister--qubit"></a>targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registo de qubits em que são aplicados os operadores Pauli.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referências

- Codificação de Espectros Eletrónicos em Circuitos Quânticos com Complexidade Linear T Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662