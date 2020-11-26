---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: Função DeintoTimeStepsCA decomposta
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: aa5f09f2e1fde878b523b4efc20b86c26ac738ff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216545"
---
# <a name="decomposedintotimestepsca-function"></a>Função DeintoTimeStepsCA decomposta

Espaço de nome: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)

Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Devolve uma operação de implementação do integrador Trotter-Suzuki para uma determinada operação.

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrada

### <a name="nsteps--int"></a>nSteps : [Int](xref:microsoft.quantum.lang-ref.int)

O número de operações a decompor-se em etapas temporais.


### <a name="op--intdoublet--unit--is-adj--ctl"></a>op :[(Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) = [> Unit](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl

Uma operação que aceita uma entrada de índice `Int` (tipo) e uma entrada de tempo (tipo ) para `Double` decomposição.


### <a name="trotterorder--int"></a>trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)

Selecione a ordem do integrador Trotter-Suzuki a utilizar.
Encomenda 1 e até encomendas 2, 4, 6,... são atualmente apoiados.



## <a name="output--doublet--unit--is-adj--ctl"></a>Saída :[(Duplo](xref:microsoft.quantum.lang-ref.double),'T) = [> Unidade](xref:microsoft.quantum.lang-ref.unit)  é Adj + Ctl

Devolve um integrador unitário de implementação do integrador Trotter-Suzuki, onde o primeiro parâmetro `Double` é o tamanho do passo de integração, e o segundo parâmetro é o alvo acionado.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T

O tipo que cada passo deve ser pisado; tipicamente, ou `Qubit[]` ou `Qubit` . .

## <a name="remarks"></a>Observações

Quando chamado com `order` igual a , esta `1` função devolve uma operação que pode ser simulada pelo integrador Trotter-Suzuki de menor ordem $$ \start{align} S_1(\lambda) = \prod_{j = 1}^{m} e^{{{H_j \lambda}, \end{align}08139 e deixe $\lambda$ ser o tempo de evolução (representado pela primeira entrada da operação devolvida), e deixe $ H_j [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139) \{ \} _{j = 1}^{m}$ seja o conjunto de geradores dinâmicos (skew-Hermitian) sendo integrados de tal forma que `op(j, lambda, _)` é simulado pelo operador unitário $e^{{H_j \lambda$}

Da mesma forma, um `order` dos `2` retornos do integrador simétrico trotter-Suzuki de segunda ordem $$ \start{align} S_2(\lambda) = \prod_{j = 1}^{m} e^{{{H_k \lambda / 2} \prod_{j' = m}^ {1} e^{H_{j'}
\end{align} $$

Valores partivos mais `order` elevados são implementados utilizando a construção recursiva de [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).

## <a name="references"></a>Referências

- [*D. W. Berry, G. Ahokas, R. Cleve, B.C. Sanders*](https://arxiv.org/abs/quant-ph/0508139)