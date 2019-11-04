---
title: 'Técnicas de Q #-variáveis locais | Microsoft Docs'
description: 'Técnicas de Q #-variáveis locais'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4f5eff1ee8482fa5e5fee9dff421efab93fc0c5a
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183289"
---
# <a name="local-variables"></a><span data-ttu-id="add59-103">Variáveis locais</span><span class="sxs-lookup"><span data-stu-id="add59-103">Local Variables</span></span> #

<span data-ttu-id="add59-104">Um valor de qualquer tipo em Q # pode ser atribuído a uma variável para reutilização em uma operação ou função usando a palavra-chave `let`.</span><span class="sxs-lookup"><span data-stu-id="add59-104">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>
<span data-ttu-id="add59-105">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="add59-105">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="add59-106">Isso atribui uma determinada matriz de operadores de Pauli a uma variável chamada `measurementOperator`.</span><span class="sxs-lookup"><span data-stu-id="add59-106">This assigns a particular array of Pauli operators to a variable called `measurementOperator`.</span></span>

> [!TIP]
> <span data-ttu-id="add59-107">Observe que não precisamos especificar explicitamente o tipo da nossa nova variável, pois a expressão no lado direito da instrução de `let` não é ambígua e o tipo é inferido pelo compilador.</span><span class="sxs-lookup"><span data-stu-id="add59-107">Note that we did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="add59-108">As variáveis em Q # são *imutáveis*, o que significa que, depois que uma variável tiver sido definida dessa forma, ela não poderá mais ser alterada de forma alguma.</span><span class="sxs-lookup"><span data-stu-id="add59-108">Variables in Q# are *immutable*, meaning that once a variable has been defined in this way, it can no longer be changed in any way.</span></span>
<span data-ttu-id="add59-109">Isso permite várias otimizações úteis, incluindo a otimização da lógica clássica que atua em variáveis a serem reordenadas para aplicar a `Adjoint` variante de uma operação.</span><span class="sxs-lookup"><span data-stu-id="add59-109">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

<span data-ttu-id="add59-110">As variáveis definidas usando a associação de `let` como acima são locais para um escopo específico, como o corpo de uma operação ou o conteúdo de um loop de `for`.</span><span class="sxs-lookup"><span data-stu-id="add59-110">Variables defined using the `let` binding as above are local to a particular scope, such as the body of an operation or the contents of a `for` loop.</span></span>


## <a name="mutability"></a><span data-ttu-id="add59-111">Imutabilidade</span><span class="sxs-lookup"><span data-stu-id="add59-111">Mutability</span></span> ##

<span data-ttu-id="add59-112">Como uma alternativa para criar uma variável com `let`, a palavra-chave `mutable` criará uma variável mutável especial que pode ser reassociada após ser criada inicialmente usando a palavra-chave `set`.</span><span class="sxs-lookup"><span data-stu-id="add59-112">As an alternative to creating a variable with `let`, the `mutable` keyword will create a special mutable variable that can be re-bound after it is initially created by using the `set` keyword.</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

<span data-ttu-id="add59-113">Todos os tipos em Q #, incluindo matrizes, seguem a semântica de valor.</span><span class="sxs-lookup"><span data-stu-id="add59-113">All types in Q#, including arrays, follow value semantics.</span></span> <span data-ttu-id="add59-114">Em particular, não é possível atualizar itens de matriz.</span><span class="sxs-lookup"><span data-stu-id="add59-114">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="add59-115">Para modificar uma matriz existente, é necessário aproveitar um mecanismo de cópia e atualização como aquele para registros no F#.</span><span class="sxs-lookup"><span data-stu-id="add59-115">To modify an existing array requires leveraging a copy-and-update mechanism much like the one for records in F#.</span></span> <span data-ttu-id="add59-116">Usando as ferramentas de biblioteca para matrizes fornecidas no [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), podemos, por exemplo, definir facilmente uma função que retorna uma matriz de Paulis em que o Pauli no índice `i` usa o valor determinado e todas as outras entradas são a identidade:</span><span class="sxs-lookup"><span data-stu-id="add59-116">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can e.g. easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity:</span></span> 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

<span data-ttu-id="add59-117">Falaremos mais sobre como trabalhar com matrizes ao abordar as instruções e expressões de Q #.</span><span class="sxs-lookup"><span data-stu-id="add59-117">We will elaborate more on how to work with arrays when discussing Q# statements and expressions.</span></span> 

<span data-ttu-id="add59-118">A imutabilidade em Q # é um conceito que se aplica a um *símbolo* em vez de um tipo ou valor.</span><span class="sxs-lookup"><span data-stu-id="add59-118">Mutability within Q# is a concept that applies to a *symbol* rather than a type or value.</span></span> <span data-ttu-id="add59-119">Especificamente, ele não tem uma representação no sistema de tipos, implicitamente ou explicitamente, e se uma associação é mutável (conforme indicado pela palavra-chave `mutable`) ou imutável (conforme indicado pelo `let`) não altera o tipo de variável (s) associada.</span><span class="sxs-lookup"><span data-stu-id="add59-119">Specifically, it does not have a representation in the type system, implicitly or explicitly, and whether or not a binding is mutable (as indicated by the `mutable` keyword) or immutable (as indicated by `let`) does not change the type of the bound variable(s).</span></span> <span data-ttu-id="add59-120">Isso fornece uma maneira importante de isolar a imutabilidade dentro de funções e operações especializadas.</span><span class="sxs-lookup"><span data-stu-id="add59-120">This provides an important way to isolate mutability inside specialized functions and operations.</span></span>
<span data-ttu-id="add59-121">Em particular, embora uma especialização adjacente para uma operação que usa uma variável mutável não possa ser gerada automaticamente, a geração automática funciona bem para uma operação que chama uma função que usa a imutabilidade.</span><span class="sxs-lookup"><span data-stu-id="add59-121">In particular, even though an adjoint specialization for an operation which uses a mutable variable cannot be auto-generated, auto-generation works fine for an operation calling a function which uses mutability.</span></span>
<span data-ttu-id="add59-122">Por esse motivo, é uma boa prática fazer funções e operações que usam a imutabilidade o mais curto possível e compacto possível, para que o restante do programa Quantum possa ser escrito usando variáveis imutáveis comuns.</span><span class="sxs-lookup"><span data-stu-id="add59-122">For this reason, it is a good practice to make functions and operations which use mutability as short and compact as possible, so that the rest of the quantum program can be written using ordinary immutable variables.</span></span>


## <a name="deconstruction"></a><span data-ttu-id="add59-123">Desconstrução</span><span class="sxs-lookup"><span data-stu-id="add59-123">Deconstruction</span></span> ##

<span data-ttu-id="add59-124">Além de atribuir uma única variável, as palavras-chave `let` e `mutable`-ou na verdade qualquer outra construção de associação-também permite desempacotar o conteúdo de um [tipo de tupla](xref:microsoft.quantum.language.type-model#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="add59-124">In addition to assigning a single variable, the `let` and `mutable` keywords - or in fact any other binding construct - also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.language.type-model#tuple-types).</span></span>
<span data-ttu-id="add59-125">Uma atribuição desse formulário é mencionada para *desconstruir* os elementos dessa tupla.</span><span class="sxs-lookup"><span data-stu-id="add59-125">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>
<span data-ttu-id="add59-126">Por exemplo, se modelarmos um termo em um Hamiltonian por uma tupla, podemos usar a desconstrução para acessar os dados diferentes que precisamos simular sob esse termo:</span><span class="sxs-lookup"><span data-stu-id="add59-126">For instance, if we model a term in a Hamiltonian by a tuple, then we can use deconstruction to access the different data that we need to simulate under that term:</span></span>

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


