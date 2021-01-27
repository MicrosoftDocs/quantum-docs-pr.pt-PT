---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: AssertOperaçãoOperationsEqualReferenced operação
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: 045f00a720e9f4d2e6993c66ace44a81e192ff30
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853469"
---
# <a name="assertoperationsequalreferenced-operation"></a>AssertOperaçãoOperationsEqualReferenced operação

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Tendo em conta duas operações, afirma que agem de forma idêntica para todos os estados de entrada.

Esta afirmação é implementada usando o isomorfismo Choi-Jamiołkowski para reduzir a afirmação a uma afirmação de estado qubit em dois registos emaranhados.
Assim, esta operação necessita apenas de uma única chamada para cada operação que está a ser testada, mas requer o dobro dos qubits a serem atribuídos.
Esta afirmação pode ser usada para garantir, por exemplo, que uma versão otimizada de uma operação age de forma idêntica à sua implementação ingénua, ou que uma operação que atua numa série de entradas não quânticas concorda com casos conhecidos.

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Entrada

### <a name="nqubits--int"></a>nQubits : [Int](xref:microsoft.quantum.lang-ref.int)

Número de qubits para passar para cada operação.


### <a name="actual--qubit--unit"></a>real : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)> 

Operação a ser testada.


### <a name="expected--qubit--unit--is-adj"></a>esperado : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj

Operação que define o comportamento esperado para a operação em teste.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Esta operação requer que a operação que modela o comportamento esperado seja adjacente, de modo a que o inverso possa ser realizado apenas no registo-alvo.
Formalmente, pode especificar uma operação transposta, que relaxa este requisito, mas a operação de transposição não é fisicamente realizável para operações quânticas arbitrárias e, portanto, não está incluída aqui como uma opção.