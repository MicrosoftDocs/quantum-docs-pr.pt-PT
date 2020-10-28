---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: Função QuantumROM
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 8ba5c6fab4abcfaee7233df9535f22eea5f68c28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722960"
---
# <a name="quantumrom-function"></a>Função QuantumROM

Espaço de nome: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)

Pacote: [](https://nuget.org/packages/)


Usa a técnica de ROM quântica para representar uma determinada matriz de densidade.

Dada a lista de coeficientes de $N$ $\alpha_j$, isto devolve uma $U$ unitária que usa a técnica Quantum-ROM para preparar uma aproximação $\tilde\rho\rho\rho\sum_{j=0}{N-1}p_j\ket{j}bra{j}$ da purificação da matriz de densidade $\rho=\sum_{j=0}{N-1 alpha_j} {\sum_k [\alpha_k]} \ket{j}\bra{j}$. Nesta aproximação, o erro $\epsilon$ é tal que $/p_j-\frac{[alpha_j]. {\sum_k [\alpha_k]. \le \epsilon / N$ e $ \| \tilde\rho - \rho \| \le \epsilon$. Por outras palavras, $$ \start{align} U\ket {0} ^{\lceil\log_2 N\rceil}\ket {0} ^{m}={sum_ j=0}^{N-1}\sqrt{p_j} \ket{j}ket{ket{\ket{\text{garbage}_j}.
\end{align} $$

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a>Entrada

### <a name="targeterror--double"></a>targetError : [Duplo](xref:microsoft.quantum.lang-ref.double)

O erro do alvo $\epsilon$.


### <a name="coefficients--double"></a>coeficientes : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Conjunto de coeficientes de $N$ especificando a probabilidade dos estados de base.
Números negativos $-\alpha_j$ serão tratados como positivos $\alpha_j.$.



## <a name="output--intintintdoublelittleendianqubit--unit-adj--ctl"></a>Saída :[(Int (Int](xref:microsoft.quantum.lang-ref.int),[Int),](xref:microsoft.quantum.lang-ref.int)[Double](xref:microsoft.quantum.lang-ref.double)[(LittleEndian,](xref:Microsoft.Quantum.Arithmetic.LittleEndian)[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)[Int](xref:microsoft.quantum.lang-ref.int)

## <a name="first-parameter"></a>Primeiro parâmetro

Um tuple `(x,(y,z))` onde está o número total de `x = y + z` qubits atribuídos, `y` é o número de qubits para o `LittleEndian` registo, e é o número de `z` qubits de lixo.

## <a name="second-parameter"></a>Segundo parâmetro

A norma única $\sum_j [\alpha_j] do conjunto de coeficientes.

## <a name="third-parameter"></a>Terceiro parâmetro

O $U unitário.

## <a name="references"></a>Referências

- Codificação de Espectros Eletrónicos em Circuitos Quânticos com Complexidade Linear T Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662