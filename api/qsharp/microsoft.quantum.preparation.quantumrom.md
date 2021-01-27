---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: Função QuantumROM
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  > [!WARNING]

  > QuantumROM has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.


  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 64ed9aed7c9d9a4a689c5926f3cd085a2521c4db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856810"
---
# <a name="quantumrom-function"></a>Função QuantumROM

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> A QuantumROM foi depreparada. Por favor, use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> em vez disso.

Usa a técnica de ROM quântica para representar uma determinada matriz de densidade.

Dada a lista de coeficientes de $N$ $\alpha_j$, isto devolve uma $U$ unitária que usa a técnica Quantum-ROM para preparar uma aproximação $\tilde\rho\sum_{j=0}{N-1}p_j\ket{j}bra{j}} da purificação da matriz de densidade $\rho=\sum_{j=0}{N-1}frac{|alpha_j|} {\sum_k |\alpha_k|} \ket{j}\bra{j}$. Nesta aproximação, o erro $\epsilon$ é tal que $|p_j-\frac{|alpha_j|} {\sum_k |\alpha_k|}| \le \epsilon / N$ e $ \| \tilde\rho - \rho \| \le \epsilon$. Por outras palavras, $$ \start{align} U\ket {0} ^{\lceil\log_2 N\rceil}\ket {0} ^{m}={sum_ j=0}^{N-1}\sqrt{p_j} \ket{j}ket{ket{\ket{\text{garbage}_j}.
\end{align} $$

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a>Entrada

### <a name="targeterror--double"></a>targetError : [Duplo](xref:microsoft.quantum.lang-ref.double)

O erro do alvo $\epsilon$.


### <a name="coefficients--double"></a>coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Conjunto de coeficientes de $N$ especificando a probabilidade dos estados de base.
Números negativos $-\alpha_j$ serão tratados como positivos $|alpha_j|$.



## <a name="output--intintintdoublelittleendianqubit--unit--is-adj--ctl"></a>Saída :[(Int](xref:microsoft.quantum.lang-ref.int)[(Int](xref:microsoft.quantum.lang-ref.int),[Int),](xref:microsoft.quantum.lang-ref.int)[Double](xref:microsoft.quantum.lang-ref.double)[(LittleEndian,](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [> Unit](xref:microsoft.quantum.lang-ref.unit) é Adj + Ctl)

## <a name="first-parameter"></a>Primeiro parâmetro

Um tuple `(x,(y,z))` onde está o número total de `x = y + z` qubits atribuídos, `y` é o número de qubits para o `LittleEndian` registo, e é o número de `z` qubits de lixo.

## <a name="second-parameter"></a>Segundo parâmetro

A norma única $\sum_j |\alpha_j|$ da matriz de coeficiente.

## <a name="third-parameter"></a>Terceiro parâmetro

O $U unitário.

## <a name="example"></a>Exemplo

O seguinte corte de código prepara uma purificação do estado $\rho=\rho=\sum_{j=0}^ {4} \frac{|alpha_j|} {\sum_k |\alpha_k|} \ket{j}\bra{j}$, onde $\vec\alpha=(1.0,2,0,3,0,4,0,5,0)$, e o erro é `1e-3` ;

```qsharp
let coefficients = [1.0,2.0,3.0,4.0,5.0];
let targetError = 1e-3;
let ((nTotalQubits, (nIndexQubits, nGarbageQubits)), oneNorm, op) = QuantumROM(targetError, coefficients);
using (indexRegister = Qubit[nIndexQubits]) {
    using (garbageRegister = Qubit[nGarbageQubits]) {
        op(LittleEndian(indexRegister), garbageRegister);
    }
}
```

## <a name="references"></a>Referências

- Codificação de Espectros Eletrónicos em Circuitos Quânticos com Complexidade Linear T Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662