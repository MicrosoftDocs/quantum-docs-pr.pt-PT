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
# <a name="local-variables"></a>Variáveis Locais #

Um valor de qualquer tipo em Q# pode ser atribuído a uma variável para reutilização dentro de uma operação ou função utilizando a palavra-chave `let`.
Por exemplo:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Isto atribui um leque particular de operadores Pauli a uma variável chamada `measurementOperator`.

> [!TIP]
> Note que não precisamos especificar explicitamente o tipo da nossa nova variável, uma vez que a expressão no lado direito da declaração `let` é inequívoca e o tipo é inferido pelo compilador. 

As variáveis em Q# são *imutáveis,* o que significa que uma vez definida uma variável desta forma, não pode mais ser alterada de forma alguma.
Isto permite várias otimizações benéficas, incluindo a otimização da lógica clássica agindo sobre variáveis a serem reordenadas para aplicar a variante `Adjoint` de uma operação.

As variáveis definidas utilizando a `let` encadernação como acima são locais para um âmbito específico, como o corpo de uma operação ou o conteúdo de um laço de `for`.


## <a name="mutability"></a>Mutabilidade ##

Como alternativa à criação de uma variável com `let`, a palavra-chave `mutable` criará uma variável mutável especial que pode ser religada depois de inicialmente criada usando a palavra-chave `set`.

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

Todos os tipos em Q#, incluindo matrizes, seguem a semântica de valor. Em particular, não é possível atualizar itens de matriz. Para modificar uma matriz existente requer alavancar um mecanismo de cópia F#e atualização muito semelhante ao dos registos em . Utilizando as ferramentas da biblioteca para matrizes fornecidas em [`Microsoft.Quantum.Arrays`, ](xref:microsoft.quantum.arrays)podemos, por exemplo, definir facilmente uma função que devolve uma matriz de Paulis onde o Pauli no índice `i` assume o valor dado e todas as outras entradas são a identidade: 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

Vamos elaborar mais sobre como trabalhar com matrizes ao discutir declarações e expressões Q# . 

Mutabilidade dentro do Q# é um conceito que se aplica a um *símbolo* em vez de um tipo ou valor. Especificamente, não tem representação no sistema de tipo, implicitamente ou explicitamente, e se uma ligação é ou não mutável (como indicado pela palavra-chave `mutable`) ou imutável (como indicado por `let`) não altera o tipo de variável vinculada. Isto fornece uma forma importante de isolar a mutabilidade dentro de funções e operações especializadas.
Em particular, embora uma especialização adjoint para uma operação que utilize uma variável mutável não possa ser gerada automaticamente, a geração automática funciona bem para uma operação que chama uma função que utiliza mutabilidade.
Por esta razão, é uma boa prática fazer funções e operações que usam a mutabilidade o mais curta e compacta possível, para que o resto do programa quântico possa ser escrito usando variáveis imutáveis ordinárias.


## <a name="deconstruction"></a>Desconstrução ##

Além de atribuir uma única variável, as palavras-chave `let` e `mutable` - ou, na verdade, qualquer outra construção vinculativa - também permitem desembalar o conteúdo de um [tipo de tuple](xref:microsoft.quantum.language.type-model#tuple-types).
Diz-se que uma atribuição deste formulário *desconstrói* os elementos daquela tuple.
Por exemplo, se modelarmos um termo num Hamiltoniano por um tumulto, então podemos usar a desconstrução para aceder aos diferentes dados que precisamos simular nesse termo:

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


