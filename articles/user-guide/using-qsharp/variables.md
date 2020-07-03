---
title: 'Variáveis em Q #'
description: preencher descrição
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 08301f408dcb2211ba25c582a5e5aa43310b714a
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885285"
---
# <a name="variables-in-q"></a>Variáveis em Q #

Q# distingue entre símbolos mutáveis e imutáveis, ou variáveis, que estão *ligadas/atribuídas*a expressões.
Em geral, o uso de símbolos imutáveis é encorajado porque permite que o compilador execute mais otimizações.

O lado esquerdo de uma ligação consiste de um tuple de símbolo e do lado direito de uma expressão.

## <a name="immutable-variables"></a>Variáveis Imutáveis

Pode atribuir um valor de qualquer tipo em Q# a uma variável para reutilização dentro de uma operação ou função utilizando a `let` palavra-chave. 

Uma ligação imutável consiste na palavra-chave, `let` seguida de um símbolo ou tuple de símbolo, um sinal `=` igual, uma expressão para ligar o símbolo(s) e um semicolon de terminante.

Por exemplo:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Isto atribui uma matriz específica de operadores Pauli ao nome variável (ou "símbolo"), `measurementOperator` .

> [!NOTE]
> No exemplo anterior, não há necessidade de especificar explicitamente o tipo da nova variável, uma vez que a expressão no lado direito da `let` declaração é inequívoca, e o compilador infere o tipo correto. 

As variáveis definidas usando `let` são *imutáveis,* o que significa que uma vez que você defini-lo, você não pode mais mudá-lo de qualquer forma.
Isto permite várias otimizações benéficas, incluindo a otimização da lógica clássica que atua sobre variáveis a serem reordenadas para aplicar a `Adjoint` variante de uma operação.

## <a name="mutable-variables"></a>Variáveis Mutáveis

Como alternativa à criação de uma variável com `let` , a `mutable` palavra-chave cria uma variável mutável que *pode* ser recuperada após a sua criação inicialmente utilizando a `set` palavra-chave.

Pode reencambinar os símbolos declarados e vinculados como parte de uma `mutable` declaração a um valor diferente mais tarde no código. Se um símbolo for recuperado mais tarde no código, o seu tipo não muda e o valor recém-vinculado deve ser compatível com esse tipo.

### <a name="rebinding-of-mutable-symbols"></a>Reencambraming de símbolos mutáveis

Pode reencambá-la uma variável mutável usando uma `set` declaração.
Tal reencaminhamento consiste na palavra-chave, `set` seguida de um símbolo ou tuple de símbolo, um sinal `=` igual, uma expressão para reencaminhar o símbolo(s) para, e um semicolon de terminante.

Seguem-se alguns exemplos de técnicas de afirmação de revindagem.

#### <a name="apply-and-reassign-statements"></a>Aplicar e reatribuir declarações

Um tipo particular de `set` declaração, a declaração *de aplicação e reatribuição,* proporciona uma forma conveniente de concatenação se o lado direito consistir na aplicação de um operador binário, e o resultado é ser recuperado para o operador o argumento da esquerda. Por exemplo,

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
incrementa o valor do contador `counter` em cada iteração do `for` laço. O código anterior é equivalente a 

```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

Estão disponíveis declarações semelhantes para todos os operadores binários em que o tipo do lado esquerdo corresponde ao tipo de expressão. Estas declarações fornecem uma forma conveniente de acumular valores.

Por exemplo, supondo `qubits` ser um registo de qubits:
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

#### <a name="update-and-reassign-statements"></a>Atualizações e reatribuições

Existe uma concatenação semelhante para [expressões de cópia e atualização](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) no lado direito.
Consequentemente, existem declarações *de atualização e reatribuição* para *itens nomeados* em tipos definidos pelo utilizador, bem como para *itens de matriz*.  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

No caso das matrizes, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) na biblioteca padrão Q# fornece as ferramentas necessárias para muitas necessidades comuns de inicialização e manipulação de matrizes, ajudando assim a evitar ter de atualizar os itens de matriz em primeiro lugar. 

As declarações de atualização e reatribuição fornecem uma alternativa, se necessário:

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

Utilizando as ferramentas da biblioteca para matrizes fornecidas, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) pode, por exemplo, definir facilmente uma função que devolve uma série de `Pauli` tipos onde o elemento no índice tem um determinado `i` `Pauli` valor, e todas as outras entradas são a identidade ( `PauliI` ).

Aqui estão duas definições de tal função, com a segunda a tirar partido das ferramentas à nossa disposição.

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli if index==location and PauliI if not
    }    
    return pauliArray;
}
```

Em vez de iterar sobre cada índice na matriz, e defini-lo condicionalmente para `PauliI` ou o `pauli` dado, você pode em vez de `ConstantArray` criar uma variedade de [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) `PauliI` tipos, e em seguida, simplesmente devolver uma expressão de cópia e atualização em que você alterou o valor específico no índice `location` :

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>Desconstrução de Tuple

Além de atribuir uma única variável, pode utilizar as `let` `mutable` palavras-chave - ou qualquer outra construção vinculativa, como `set` - para desempacotar o conteúdo de um [tipo de tuple](xref:microsoft.quantum.guide.types#tuple-types).
Diz-se que uma atribuição deste formulário *desconstrui* os elementos dessa tuple.

Se o lado direito da ligação for uma tuple, então pode desconstruir isso após a atribuição.
Tais desconstruções podem envolver tuples aninhados, e qualquer desconstrução total ou parcial é válida desde que a forma do tuple no lado direito seja compatível com a forma do tuple símbolo.

Por exemplo:

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a>Âmbitos de encadernação

Em geral, as ligações dos símbolos ficam fora de alcance e tornam-se inoperantes no final do bloco de declaração em que ocorrem.
Há duas exceções a esta regra:

- A ligação da variável de laço de um `for` laço está no âmbito do corpo do laço, mas não após o fim do loop.
- Todas as três porções de um `repeat` / `until` laço (o corpo, o teste e a fixação) funcionam como um único âmbito, de modo que os símbolos que estão ligados no corpo estão disponíveis no teste e na fixação.

Para ambos os tipos de loops, cada passagem através do loop corre no seu próprio âmbito, de modo que as encadernações de um passe anterior não estão disponíveis num passe posterior.
Para obter mais informações sobre estes ciclos, consulte [o Control Flow](xref:microsoft.quantum.guide.controlflow).

Os blocos internos herdam as ligações dos símbolos dos blocos exteriores.
Só se pode ligar um símbolo uma vez por bloco; é ilegal definir um símbolo com o mesmo nome que outro símbolo que está dentro do âmbito (sem "sombra").
As seguintes sequências são legais:

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

e

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
...                 // n is not bound to a value
```

Mas isto seria ilegal:

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

como:

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="next-steps"></a>Passos seguintes

Saiba mais [sobre trabalhar com qubits](xref:microsoft.quantum.guide.qubits) em Q#.