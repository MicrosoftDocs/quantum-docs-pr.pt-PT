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
# <a name="assertoperationsequalreferenced-operation"></a><span data-ttu-id="797cb-102">AssertOperaçãoOperationsEqualReferenced operação</span><span class="sxs-lookup"><span data-stu-id="797cb-102">AssertOperationsEqualReferenced operation</span></span>

<span data-ttu-id="797cb-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="797cb-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="797cb-104">Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="797cb-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="797cb-105">Tendo em conta duas operações, afirma que agem de forma idêntica para todos os estados de entrada.</span><span class="sxs-lookup"><span data-stu-id="797cb-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="797cb-106">Esta afirmação é implementada usando o isomorfismo Choi-Jamiołkowski para reduzir a afirmação a uma afirmação de estado qubit em dois registos emaranhados.</span><span class="sxs-lookup"><span data-stu-id="797cb-106">This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers.</span></span>
<span data-ttu-id="797cb-107">Assim, esta operação necessita apenas de uma única chamada para cada operação que está a ser testada, mas requer o dobro dos qubits a serem atribuídos.</span><span class="sxs-lookup"><span data-stu-id="797cb-107">Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated.</span></span>
<span data-ttu-id="797cb-108">Esta afirmação pode ser usada para garantir, por exemplo, que uma versão otimizada de uma operação age de forma idêntica à sua implementação ingénua, ou que uma operação que atua numa série de entradas não quânticas concorda com casos conhecidos.</span><span class="sxs-lookup"><span data-stu-id="797cb-108">This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.</span></span>

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="797cb-109">Entrada</span><span class="sxs-lookup"><span data-stu-id="797cb-109">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="797cb-110">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="797cb-110">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="797cb-111">Número de qubits para passar para cada operação.</span><span class="sxs-lookup"><span data-stu-id="797cb-111">Number of qubits to pass to each operation.</span></span>


### <a name="actual--qubit--unit"></a><span data-ttu-id="797cb-112">real : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Unidade](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="797cb-112">actual : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="797cb-113">Operação a ser testada.</span><span class="sxs-lookup"><span data-stu-id="797cb-113">Operation to be tested.</span></span>


### <a name="expected--qubit--unit--is-adj"></a><span data-ttu-id="797cb-114">esperado : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unidade](xref:microsoft.quantum.lang-ref.unit) > é Adj</span><span class="sxs-lookup"><span data-stu-id="797cb-114">expected : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="797cb-115">Operação que define o comportamento esperado para a operação em teste.</span><span class="sxs-lookup"><span data-stu-id="797cb-115">Operation defining the expected behavior for the operation under test.</span></span>



## <a name="output--unit"></a><span data-ttu-id="797cb-116">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="797cb-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="797cb-117">Observações</span><span class="sxs-lookup"><span data-stu-id="797cb-117">Remarks</span></span>

<span data-ttu-id="797cb-118">Esta operação requer que a operação que modela o comportamento esperado seja adjacente, de modo a que o inverso possa ser realizado apenas no registo-alvo.</span><span class="sxs-lookup"><span data-stu-id="797cb-118">This operation requires that the operation modeling the expected behavior is adjointable, so that the inverse can be performed on the target register alone.</span></span>
<span data-ttu-id="797cb-119">Formalmente, pode especificar uma operação transposta, que relaxa este requisito, mas a operação de transposição não é fisicamente realizável para operações quânticas arbitrárias e, portanto, não está incluída aqui como uma opção.</span><span class="sxs-lookup"><span data-stu-id="797cb-119">Formally, one can specify a transpose operation, which relaxes this requirement, but the transpose operation is not in general physically realizable for arbitrary quantum operations and thus is not included here as an option.</span></span>