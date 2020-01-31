---
title: Variáveis locais - Técnicas Q# Microsoft Docs
description: Variáveis locais - Técnicas Q#
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.local-variables
ms.openlocfilehash: 8b1de5c096210fb36a81c127a8bbbe1b39522741
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820186"
---
# <a name="local-variables"></a><span data-ttu-id="21713-103">Variáveis Locais</span><span class="sxs-lookup"><span data-stu-id="21713-103">Local Variables</span></span> #

<span data-ttu-id="21713-104">Um valor de qualquer tipo em Q# pode ser atribuído a uma variável para reutilização dentro de uma operação ou função utilizando a palavra-chave `let`.</span><span class="sxs-lookup"><span data-stu-id="21713-104">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>
<span data-ttu-id="21713-105">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="21713-105">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="21713-106">Isto atribui um leque particular de operadores Pauli a uma variável chamada `measurementOperator`.</span><span class="sxs-lookup"><span data-stu-id="21713-106">This assigns a particular array of Pauli operators to a variable called `measurementOperator`.</span></span>

> [!TIP]
> <span data-ttu-id="21713-107">Note que não precisamos especificar explicitamente o tipo da nossa nova variável, uma vez que a expressão no lado direito da declaração `let` é inequívoca e o tipo é inferido pelo compilador.</span><span class="sxs-lookup"><span data-stu-id="21713-107">Note that we did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="21713-108">As variáveis em Q# são *imutáveis,* o que significa que uma vez definida uma variável desta forma, não pode mais ser alterada de forma alguma.</span><span class="sxs-lookup"><span data-stu-id="21713-108">Variables in Q# are *immutable*, meaning that once a variable has been defined in this way, it can no longer be changed in any way.</span></span>
<span data-ttu-id="21713-109">Isto permite várias otimizações benéficas, incluindo a otimização da lógica clássica agindo sobre variáveis a serem reordenadas para aplicar a variante `Adjoint` de uma operação.</span><span class="sxs-lookup"><span data-stu-id="21713-109">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

<span data-ttu-id="21713-110">As variáveis definidas utilizando a `let` encadernação como acima são locais para um âmbito específico, como o corpo de uma operação ou o conteúdo de um laço de `for`.</span><span class="sxs-lookup"><span data-stu-id="21713-110">Variables defined using the `let` binding as above are local to a particular scope, such as the body of an operation or the contents of a `for` loop.</span></span>


## <a name="mutability"></a><span data-ttu-id="21713-111">Mutabilidade</span><span class="sxs-lookup"><span data-stu-id="21713-111">Mutability</span></span> ##

<span data-ttu-id="21713-112">Como alternativa à criação de uma variável com `let`, a palavra-chave `mutable` criará uma variável mutável especial que pode ser religada depois de inicialmente criada usando a palavra-chave `set`.</span><span class="sxs-lookup"><span data-stu-id="21713-112">As an alternative to creating a variable with `let`, the `mutable` keyword will create a special mutable variable that can be re-bound after it is initially created by using the `set` keyword.</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

<span data-ttu-id="21713-113">Todos os tipos em Q#, incluindo matrizes, seguem a semântica de valor.</span><span class="sxs-lookup"><span data-stu-id="21713-113">All types in Q#, including arrays, follow value semantics.</span></span> <span data-ttu-id="21713-114">Em particular, não é possível atualizar itens de matriz.</span><span class="sxs-lookup"><span data-stu-id="21713-114">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="21713-115">Para modificar uma matriz existente requer alavancar um mecanismo de cópia F#e atualização muito semelhante ao dos registos em .</span><span class="sxs-lookup"><span data-stu-id="21713-115">To modify an existing array requires leveraging a copy-and-update mechanism much like the one for records in F#.</span></span> <span data-ttu-id="21713-116">Utilizando as ferramentas da biblioteca para matrizes fornecidas em [`Microsoft.Quantum.Arrays`, ](xref:microsoft.quantum.arrays)podemos, por exemplo, definir facilmente uma função que devolve uma matriz de Paulis onde o Pauli no índice `i` assume o valor dado e todas as outras entradas são a identidade:</span><span class="sxs-lookup"><span data-stu-id="21713-116">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can e.g. easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity:</span></span> 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

<span data-ttu-id="21713-117">Vamos elaborar mais sobre como trabalhar com matrizes ao discutir declarações e expressões Q# .</span><span class="sxs-lookup"><span data-stu-id="21713-117">We will elaborate more on how to work with arrays when discussing Q# statements and expressions.</span></span> 

<span data-ttu-id="21713-118">Mutabilidade dentro do Q# é um conceito que se aplica a um *símbolo* em vez de um tipo ou valor.</span><span class="sxs-lookup"><span data-stu-id="21713-118">Mutability within Q# is a concept that applies to a *symbol* rather than a type or value.</span></span> <span data-ttu-id="21713-119">Especificamente, não tem representação no sistema de tipo, implicitamente ou explicitamente, e se uma ligação é ou não mutável (como indicado pela palavra-chave `mutable`) ou imutável (como indicado por `let`) não altera o tipo de variável vinculada.</span><span class="sxs-lookup"><span data-stu-id="21713-119">Specifically, it does not have a representation in the type system, implicitly or explicitly, and whether or not a binding is mutable (as indicated by the `mutable` keyword) or immutable (as indicated by `let`) does not change the type of the bound variable(s).</span></span> <span data-ttu-id="21713-120">Isto fornece uma forma importante de isolar a mutabilidade dentro de funções e operações especializadas.</span><span class="sxs-lookup"><span data-stu-id="21713-120">This provides an important way to isolate mutability inside specialized functions and operations.</span></span>
<span data-ttu-id="21713-121">Em particular, embora uma especialização adjoint para uma operação que utilize uma variável mutável não possa ser gerada automaticamente, a geração automática funciona bem para uma operação que chama uma função que utiliza mutabilidade.</span><span class="sxs-lookup"><span data-stu-id="21713-121">In particular, even though an adjoint specialization for an operation which uses a mutable variable cannot be auto-generated, auto-generation works fine for an operation calling a function which uses mutability.</span></span>
<span data-ttu-id="21713-122">Por esta razão, é uma boa prática fazer funções e operações que usam a mutabilidade o mais curta e compacta possível, para que o resto do programa quântico possa ser escrito usando variáveis imutáveis ordinárias.</span><span class="sxs-lookup"><span data-stu-id="21713-122">For this reason, it is a good practice to make functions and operations which use mutability as short and compact as possible, so that the rest of the quantum program can be written using ordinary immutable variables.</span></span>


## <a name="deconstruction"></a><span data-ttu-id="21713-123">Desconstrução</span><span class="sxs-lookup"><span data-stu-id="21713-123">Deconstruction</span></span> ##

<span data-ttu-id="21713-124">Além de atribuir uma única variável, as palavras-chave `let` e `mutable` - ou, na verdade, qualquer outra construção vinculativa - também permitem desembalar o conteúdo de um [tipo de tuple](xref:microsoft.quantum.language.type-model#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="21713-124">In addition to assigning a single variable, the `let` and `mutable` keywords - or in fact any other binding construct - also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.language.type-model#tuple-types).</span></span>
<span data-ttu-id="21713-125">Diz-se que uma atribuição deste formulário *desconstrói* os elementos daquela tuple.</span><span class="sxs-lookup"><span data-stu-id="21713-125">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>
<span data-ttu-id="21713-126">Por exemplo, se modelarmos um termo num Hamiltoniano por um tumulto, então podemos usar a desconstrução para aceder aos diferentes dados que precisamos simular nesse termo:</span><span class="sxs-lookup"><span data-stu-id="21713-126">For instance, if we model a term in a Hamiltonian by a tuple, then we can use deconstruction to access the different data that we need to simulate under that term:</span></span>

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


