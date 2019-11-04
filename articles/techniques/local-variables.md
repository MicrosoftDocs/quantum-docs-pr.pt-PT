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
# <a name="local-variables"></a>Variáveis locais #

Um valor de qualquer tipo em Q # pode ser atribuído a uma variável para reutilização em uma operação ou função usando a palavra-chave `let`.
Por exemplo:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Isso atribui uma determinada matriz de operadores de Pauli a uma variável chamada `measurementOperator`.

> [!TIP]
> Observe que não precisamos especificar explicitamente o tipo da nossa nova variável, pois a expressão no lado direito da instrução de `let` não é ambígua e o tipo é inferido pelo compilador. 

As variáveis em Q # são *imutáveis*, o que significa que, depois que uma variável tiver sido definida dessa forma, ela não poderá mais ser alterada de forma alguma.
Isso permite várias otimizações úteis, incluindo a otimização da lógica clássica que atua em variáveis a serem reordenadas para aplicar a `Adjoint` variante de uma operação.

As variáveis definidas usando a associação de `let` como acima são locais para um escopo específico, como o corpo de uma operação ou o conteúdo de um loop de `for`.


## <a name="mutability"></a>Imutabilidade ##

Como uma alternativa para criar uma variável com `let`, a palavra-chave `mutable` criará uma variável mutável especial que pode ser reassociada após ser criada inicialmente usando a palavra-chave `set`.

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

Todos os tipos em Q #, incluindo matrizes, seguem a semântica de valor. Em particular, não é possível atualizar itens de matriz. Para modificar uma matriz existente, é necessário aproveitar um mecanismo de cópia e atualização como aquele para registros no F#. Usando as ferramentas de biblioteca para matrizes fornecidas no [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), podemos, por exemplo, definir facilmente uma função que retorna uma matriz de Paulis em que o Pauli no índice `i` usa o valor determinado e todas as outras entradas são a identidade: 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

Falaremos mais sobre como trabalhar com matrizes ao abordar as instruções e expressões de Q #. 

A imutabilidade em Q # é um conceito que se aplica a um *símbolo* em vez de um tipo ou valor. Especificamente, ele não tem uma representação no sistema de tipos, implicitamente ou explicitamente, e se uma associação é mutável (conforme indicado pela palavra-chave `mutable`) ou imutável (conforme indicado pelo `let`) não altera o tipo de variável (s) associada. Isso fornece uma maneira importante de isolar a imutabilidade dentro de funções e operações especializadas.
Em particular, embora uma especialização adjacente para uma operação que usa uma variável mutável não possa ser gerada automaticamente, a geração automática funciona bem para uma operação que chama uma função que usa a imutabilidade.
Por esse motivo, é uma boa prática fazer funções e operações que usam a imutabilidade o mais curto possível e compacto possível, para que o restante do programa Quantum possa ser escrito usando variáveis imutáveis comuns.


## <a name="deconstruction"></a>Desconstrução ##

Além de atribuir uma única variável, as palavras-chave `let` e `mutable`-ou na verdade qualquer outra construção de associação-também permite desempacotar o conteúdo de um [tipo de tupla](xref:microsoft.quantum.language.type-model#tuple-types).
Uma atribuição desse formulário é mencionada para *desconstruir* os elementos dessa tupla.
Por exemplo, se modelarmos um termo em um Hamiltonian por uma tupla, podemos usar a desconstrução para acessar os dados diferentes que precisamos simular sob esse termo:

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


