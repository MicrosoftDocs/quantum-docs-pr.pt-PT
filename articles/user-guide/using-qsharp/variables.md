---
title: 'Variáveis em Q #'
description: preencher descrição
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.variables
ms.openlocfilehash: 407b4ff3570816eb7bdc323a5c5b77dac2d951af
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430905"
---
# <a name="variables-in-q"></a>Variáveis em Q #

Q# distingue entre símbolos mutáveis e imutáveis, ou "variáveis", que são ligados/atribuídos a expressões.
Em geral, o uso de símbolos imutáveis é encorajado porque permite ao compilador realizar mais otimizações.

O lado esquerdo de uma ligação consiste num símbolo tuple, e no lado direito de uma expressão.

## <a name="immutable-variables"></a>Variáveis imutáveis

Um valor de qualquer tipo em Q# pode ser atribuído a uma variável para reutilização dentro de uma operação ou função utilizando a `let` palavra-chave.

Uma ligação imutável consiste na palavra-chave, `let` seguida de um símbolo ou símbolo, um sinal `=` igual, uma expressão para ligar o símbolo(s) a, e um ponto evículo terminante.

Por exemplo:

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

Isto atribui uma determinada gama de operadores Pauli ao nome variável (ou "símbolo"), `measurementOperator` .

> [!NOTE]
> Não precisamos de especificar explicitamente o tipo da nossa nova variável, uma vez que a expressão do lado direito da `let` declaração é inequívoca e o tipo é inferido pelo compilador. 

As variáveis definidas usando `let` são *imutáveis,* o que significa que uma vez definida, não pode mais ser alterada de forma alguma.
Isto permite várias otimizações benéficas, incluindo a otimização da lógica clássica agindo sobre variáveis a serem reordenadas para aplicar a `Adjoint` variante de uma operação.

## <a name="mutable-variables"></a>Variáveis Mutáveis

Como alternativa à criação de uma variável `let` com, a `mutable` palavra-chave criará uma variável mutável que *pode* ser religada depois de inicialmente criada usando a `set` palavra-chave.

Os símbolos declarados e vinculados como parte de uma `mutable` declaração podem ser recuperados para um valor diferente mais tarde no código. Se um símbolo for recuperado mais tarde no código, o seu tipo não muda, e o valor recém-vinculado precisa de ser compatível com esse tipo.

### <a name="rebinding-of-mutable-symbols"></a>Reenção de símbolos mutáveis

Uma variável mutável pode ser recuperada usando uma `set` declaração.
Tal reencência consiste na palavra-chave, `set` seguida de um símbolo ou símbolo, de um sinal `=` igual, de uma expressão para religar o símbolo(s) e de um ponto evículo terminante.

Aqui, fornecemos alguns exemplos possíveis de técnicas de declaração de reentoamento

### <a name="apply-and-reassign-statements"></a>Declarações de aplicação e reatribuição

Um tipo particular de declaração a que nos referimos como uma declaração de `set` *aplicação e reatribuição* fornece uma forma conveniente de concatenação se o lado direito consistir na aplicação de um operador binário e o resultado é ser uma recuperação para o argumento esquerdo para o operador. Por exemplo,
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
incrementa o valor do contador `counter` em cada iteração do `for` loop. O código acima é equivalente a 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```

Estão disponíveis declarações semelhantes para todos os operadores binários em que o tipo do lado esquerdo corresponde ao tipo de expressão. Isto fornece, por exemplo, uma forma conveniente de acumular valores.

Por exemplo, supor `qubits` é um regsiter de qubits:
```qsharp
mutable results = new Result[0];   // results is an empty array of type Result[]
for (q in qubits) {
    set results += [M(q)];         // concatenate the outcome from measuring q to the existing array
    // ...
}
...                                // results contains the measurement outcomes from the whole register
```

### <a name="update-and-reassign-statements"></a>Declarações de atualização e reatribuição

Existe uma concatenação semelhante para [expressões de cópia e atualização](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) no lado direito.
Consequentemente, existem declarações *de atualização e reatribuição* para *itens nomeados* em tipos definidos pelo utilizador, bem como para itens de *matriz*.  

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

No caso das matrizes, [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) nas nossas bibliotecas padrão fornece as ferramentas necessárias para muitas necessidades comuns de inicialização e manipulação de matrizes, ajudando assim a evitar ter que atualizar itens de matriz em primeiro lugar. 

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

Utilizando as ferramentas da biblioteca para matrizes [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) fornecidas, podemos, por exemplo, definir facilmente uma função que devolve uma matriz de Paulis onde o Pauli no índice `i` leva o valor dado e todas as outras entradas são a identidade.

Aqui estão duas definições de tal função, com a segunda a tirar partido das ferramentas à nossa disposição.

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];             // initialize pauliArray of given length
    for (index in 0 .. length - 1) {                    // iterate over the integers in the length range
        set pauliArray w/= index <-                     // change the value at index to input pauli or PauliI
            index == location ? pauli | PauliI;         // cond. expression evaluating to pauli or PauliI dep. on whether index==location
    }    
    return pauliArray;
}
```

Em vez de iterar sobre cada índice da matriz, e defini-lo condicionalmente para `PauliI` `Pauli` ou, em vez disso, podemos usar `ConstantArray` para criar uma variedade de [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays) `PauliI` 's' e, em seguida, simplesmente devolver uma expressão de cópia e atualização em que mudamos o valor especifc no `location` índice:

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

## <a name="tuple-deconstruction"></a>Desconstrução de Tuple

Além de atribuir uma única variável, as `let` palavras-chave e as `mutable` palavras-chave---ou de facto qualquer outra construção vinculativa, como `set` (descrito abaixo)---também permitir desembalar o conteúdo de um tipo de [tuple](xref:microsoft.quantum.guide.types#tuple-types).
Diz-se que uma atribuição deste formulário *desconstrói* os elementos daquela tuple.

Se o lado direito da ligação for uma tuple, então essa tuple pode ser desconstruída após a atribuição.
Tais desconstruções podem envolver tuples aninhados, e qualquer desconstrução total ou parcial é válida desde que a forma da tuple no lado direito seja compatível com a forma do símbolo tuple.

Por exemplo:

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

## <a name="binding-scopes"></a>Âmbitos vinculativos

Em geral, as ligações dos símbolos desbloqueiam o seu alcance e tornam-se inoperantes no final do bloco de declaração em que ocorrem.
Há duas exceções a esta regra:

- A ligação da variável do laço de um `for` laço está no âmbito do corpo do laço, mas não após o fim do laço.
- Todas as três porções de um `repeat` / `until` laço (o corpo, o teste e a fixação) são tratadas como um único âmbito, pelo que os símbolos que estão ligados no corpo estão disponíveis no teste e na fixação.

Para ambos os tipos de loops, cada passe através do loop executa no seu próprio âmbito, pelo que as encadernações de um passe anterior não estão disponíveis num passe posterior.
Os detalhes sobre estes circuitos podem ser encontrados no [Control Flow](xref:microsoft.quantum.guide.controlflow).

As ligações dos símbolos dos blocos exteriores são herdadas por blocos internos.
Um símbolo só pode ser ligado uma vez por bloco; é ilegal definir um símbolo com o mesmo nome que outro símbolo que está dentro do âmbito (sem "sombra").
As seguintes sequências seriam legais:

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

Mas isto seria ilegal.

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

## <a name="whats-next"></a>O que se segue?
Saiba trabalhar [com qubits](xref:microsoft.quantum.guide.qubits) em Q#.