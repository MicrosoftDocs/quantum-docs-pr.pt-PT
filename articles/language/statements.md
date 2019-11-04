---
title: 'Instruções Q # | Microsoft Docs'
description: 'Instruções Q #'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5bcbee868c76aaf53d0b7969e6e634da62689aaa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184870"
---
# <a name="statements-and-other-constructs"></a>Instruções e outras construções

## <a name="comments"></a>Comentários

Os comentários começam com duas barras, `//`e continuam até o fim da linha.
Um comentário pode aparecer em qualquer lugar em um arquivo de origem Q #.

### <a name="documentation-comments"></a>Comentários da documentação

Os comentários que começam com três barras "/", `///`, são tratados especialmente pelo compilador quando aparecem imediatamente antes de um namespace, operação, especialização, função ou definição de tipo.
Nesse caso, seu conteúdo é levado como documentação para o tipo definido pelo usuário ou callable, como para outras linguagens .NET.

Em `///` comentários, o texto a ser exibido como parte da documentação da API é formatado como [redução](https://daringfireball.net/projects/markdown/syntax), com partes diferentes da documentação que está sendo indicada por cabeçalhos nomeados especialmente.
Como uma extensão para redução, referências cruzadas a operações, funções e tipos definidos pelo usuário em Q # podem ser incluídas usando o `@"<ref target>"`, onde `<ref target>` é substituído pelo nome totalmente qualificado do objeto de código que está sendo referenciado.
Opcionalmente, um mecanismo de documentação também pode oferecer suporte a extensões de redução adicionais.

Por exemplo:

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit
{
    op(target);
    op(target);
}
```

Os nomes a seguir são reconhecidos como cabeçalhos de comentário da documentação.

- **Resumo**: um breve resumo do comportamento de uma função ou operação, ou da finalidade de um tipo. O primeiro parágrafo do resumo é usado para informações de foco. Ele deve ser texto sem formatação.
- **Descrição**: uma descrição do comportamento de uma função ou operação, ou da finalidade de um tipo. O resumo e a descrição são concatenados para formar o arquivo de documentação gerado para a função, a operação ou o tipo.
  A descrição pode conter símbolos e equações LaTeX e formatados em linha.
- **Entrada**: uma descrição da tupla de entrada para uma operação ou função.
  Pode conter subseções de redução adicionais indicando cada elemento individual da tupla de entrada.
- **Saída**: uma descrição da tupla retornada por uma operação ou função.
- **Parâmetros de tipo**: uma seção vazia que contém uma subseção adicional para cada parâmetro de tipo genérico.
- **Exemplo**: um breve exemplo da operação, função ou tipo em uso.
- **Comentários**: o Proseware variado que descreve algum aspecto da operação, função ou tipo.
- **Consulte também**: uma lista de nomes totalmente qualificados que indica funções relacionadas, operações ou tipos definidos pelo usuário.
- **Referências**: uma lista de referências e citações para o item que está sendo documentado.

## <a name="namespaces"></a>Espaços de nomes

Cada operação de Q #, função e tipo definido pelo usuário é definido em um namespace.
O Q # segue as mesmas regras para nomear como outras linguagens .NET.
No entanto, Q # não oferece suporte a referências relativas a namespaces.
Ou seja, se o namespace `a.b` tiver sido aberto, uma referência a uma operação de nomes `c.d` não será resolvida para uma operação com o nome completo `a.b.c.d`.

Dentro de um bloco de namespace, a diretiva `open` pode ser usada para importar todos os tipos e chamadores declarados em um determinado namespace e consultá-los por seu nome não qualificado. Opcionalmente, um nome curto para o namespace aberto pode ser definido de modo que todos os elementos desse namespace possam (e precisam) ser qualificados pelo nome curto definido. A diretiva `open` se aplica ao bloco de namespace inteiro em um arquivo.

Um tipo ou callable definido em outro namespace que não está aberto no namespace atual deve ser referenciado por seu nome totalmente qualificado.
Por exemplo, uma operação chamada `Op` no namespace `X.Y` deve ser referenciada por seu nome totalmente qualificado `X.Y.Op`, a menos que o namespace `X.Y` tenha sido aberto anteriormente no bloco atual. Conforme mencionado acima, mesmo que o namespace de `X` tenha sido aberto, não é possível fazer referência à operação como `Y.Op`.
Se um nome curto `Z` para `X.Y` tiver sido definido nesse namespace e arquivo, `Op` precisará ser chamado de `Z.Op`. 

```qsharp
namespace NS {

    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

Geralmente, é melhor incluir um namespace usando uma diretiva `open`.
Usar um nome totalmente qualificado é necessário se dois namespaces definem construções com o mesmo nome e a fonte atual usa construções de ambos.

## <a name="formatting"></a>Formatação

A maioria das instruções Q # e diretivas terminam com um ponto e vírgula de terminação, `;`.
Instruções e declarações como `for` e `operation` que terminam com um bloco de instruções não exigem um ponto e vírgula de terminação.
Cada descrição de instrução observa se o ponto e vírgula de terminação é necessário.

Instruções, como expressões, declarações e diretivas, podem ser divididas em várias linhas.
Ter várias instruções em uma única linha deve ser evitada.

## <a name="statement-blocks"></a>Blocos de instrução

As instruções Q # são agrupadas em blocos de instrução.
Um bloco de instruções começa com um `{` de abertura e termina com um `}`de fechamento.

Um bloco de instrução que está delimitado de forma lexical dentro de outro bloco é considerado um subbloco do bloco de contenção; os blocos e os subcontêineres também são chamados de bloco externo e interno.

## <a name="symbol-binding-and-assignment"></a>Atribuição e Associação de símbolo

Q # distingue entre símbolos mutáveis e imutáveis.
Em geral, o uso de símbolos imutáveis é incentivado porque permite que o compilador execute mais otimizações.

O lado esquerdo da Associação consiste em uma tupla de símbolos e no lado direito de uma expressão.

Como todos os tipos de Q # são tipos de valor – com o qubits de uma função especial, formalmente uma "cópia" é criada quando um valor é associado a um símbolo ou quando um símbolo é reassociado. Isso significa que o comportamento de Q # é o mesmo que se uma cópia fosse criada na atribuição. Isso, em particular, também inclui matrizes. É claro que, na prática, apenas as partes relevantes são, na verdade, recriadas, conforme necessário. 

### <a name="tuple-deconstruction"></a>Desconstrução de tupla

Se o lado direito da associação for uma tupla, essa tupla poderá ser desconstruída após a atribuição.
Essas desconstruções podem envolver tuplas aninhadas e qualquer desconstrução completa ou parcial é válida, desde que a forma da tupla no lado direito seja compatível com a forma da tupla de símbolo.
A desconstrução de tupla pode, em particular, também ser usada quando o lado direito da `=` é uma expressão com valor de tupla.

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a>Símbolos imutáveis

Os símbolos imutáveis são associados usando a instrução `let`.
Isso é praticamente equivalente à declaração de variável e à inicialização em idiomas C#como, exceto que os símbolos Q #, uma vez vinculados, não podem ser alterados; associações de `let` são imutáveis.

Uma associação imutável consiste na palavra-chave `let`, seguida por uma tupla de símbolo ou símbolo, um sinal de igual `=`, uma expressão para associar os símbolos a e um ponto e vírgula de terminação.
O tipo de símbolo (s) associado é inferido com base na expressão no lado direito.

### <a name="mutable-symbols"></a>Símbolos mutáveis

Os símbolos mutáveis são definidos e inicializados usando a instrução `mutable`.
Os símbolos declarados e associados como parte de uma instrução `mutable` podem ser reassociados a um valor diferente posteriormente no código. 

Uma instrução de associação mutável consiste na palavra-chave `mutable`, seguida por uma tupla de símbolo ou símbolo, um sinal de igual `=`, uma expressão para associar os símbolos a e um ponto e vírgula de terminação.
O tipo de símbolo (s) associado é inferido com base na expressão no lado direito. Se um símbolo for reassociado posteriormente no código, seu tipo não será alterado e o valor de limite precisará ser compatível com esse tipo.

### <a name="rebinding-of-mutable-symbols"></a>Reassociação de símbolos mutáveis

Uma variável mutável pode ser reassociada usando uma instrução `set`.
Essa reassociação consiste na `set`da palavra-chave, seguida por uma tupla de símbolo ou símbolo, um sinal de igual `=`, uma expressão para reassociar os símbolos a e um ponto e vírgula de terminação.
O valor deve ser compatível com os tipos do (s) símbolo (es) ao qual está associado.

#### <a name="apply-and-reassign-statement"></a>Instrução de aplicação e reatribuição

Um tipo específico de instrução SET-Statement que chamamos de instrução de aplicação e reatribuição fornece uma maneira conveniente de concatenação se o lado direito consistir no aplicativo de um operador binário e o resultado for ser reassociado ao argumento esquerdo para o operador. Por exemplo,
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
incrementa o valor do contador `counter` em cada iteração do loop `for`. O código acima é equivalente a 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
Instruções semelhantes estão disponíveis para todos os operadores binários nos quais o tipo do lado esquerdo corresponde ao tipo de expressão. Isso fornece, por exemplo, uma maneira conveniente de acumular valores:
```qsharp
mutable results = new Result[0];
for (q in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a>Instrução UPDATE-and-REASSIGN

Existe uma concatenação semelhante para expressões de copiar e atualizar no lado direito. De modo correspondente, as instruções UPDATE-and-REASSIGN existem para itens nomeados em tipos definidos pelo usuário, bem como para itens de matriz.  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function AddAll (reals : Double[], ims : Double[]) : Complex[] {
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

No caso de matrizes, nossas bibliotecas padrão contêm as ferramentas necessárias para muitas necessidades comuns de inicialização e manipulação de matriz e, portanto, ajudam a evitar a necessidade de atualizar itens de matriz em primeiro lugar. As instruções UPDATE-and-REASSIGN fornecem uma alternativa, se necessário:

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {

    mutable samples = new Double[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}

operation SampleUniformDistr(nrSamples : Int, prec : Int) : Double[] {

    let normalization = 1. / IntAsDouble(prec);
    mutable samples = RandomInts(prec, nrSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

> [!TIP]   
> Evite o uso desnecessário de instruções UPDATE-and-REASSIGN aproveitando as ferramentas fornecidas no <xref:microsoft.quantum.arrays>.

A função
```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
{
    mutable pauliArray = new Pauli[n];
    for (index in 0 .. n - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
por exemplo, pode simplesmente ser simplificado usando a função `ConstantArray` em `Microsoft.Quantum.Arrays`e retornar uma expressão de copiar e atualizar:

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    return ConstantArray(n, PauliI) w/ i <- pauli;
}
```

### <a name="binding-scopes"></a>Escopos de associação

Em geral, as ligações de símbolo saem do escopo e se tornam inoperantes no final do bloco de instrução em que ocorrem.
Há duas exceções a essa regra:

- A associação da variável de loop de um loop de `for` está no escopo do corpo do loop for, mas não após o final do loop.
- Todas as três partes de um `repeat`/loop de `until` (o corpo, o teste e a correção) são tratados como um único escopo, de modo que os símbolos associados ao corpo estão disponíveis no teste e no conserto.

Para ambos os tipos de loops, cada passagem do loop é executada em seu próprio escopo, portanto, as associações de uma passagem anterior não estarão disponíveis em uma passagem posterior.

Associações de símbolo de blocos externos são herdadas por blocos internos.
Um símbolo só pode ser associado uma vez por bloco; é ilegal definir um símbolo com o mesmo nome de outro símbolo que está dentro do escopo (sem "sombreamento").
As sequências a seguir seriam legais:

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

e em

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
```

Mas isso seria ilegal:

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

como seria:

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a>Fluxo de Controlo

### <a name="for-loop"></a>Loop for

A instrução `for` dá suporte à iteração em um intervalo de inteiros ou em uma matriz.
A instrução consiste na palavra-chave `for`, um parêntese de abertura `(`, seguido por uma tupla de símbolo ou símbolo, a palavra-chave `in`, uma expressão do tipo `Range` ou matriz, um parêntese de fechamento `)`e um bloco de instruções.

O bloco de instrução (o corpo do loop) é executado repetidamente, com os símbolos definidos (as variáveis de loop) associadas a cada valor no intervalo ou na matriz.
Observe que, se a expressão de intervalo for avaliada como um intervalo ou uma matriz vazia, o corpo não será executado.
A expressão é totalmente avaliada antes de entrar no loop e não será alterada enquanto o loop estiver em execução.

A Associação dos símbolos declarados é imutável e segue as mesmas regras que outras associações de variáveis. Em particular, é possível destruir, por exemplo, itens de matriz para uma iteração em uma matriz após a atribuição à (s) variável (ões) de loop.

Por exemplo,

```qsharp
// ...
for (qb in qubits) { // qubits contains a Qubit[]
    H(qb);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

A variável de loop é associada a cada entrada no corpo do loop e desassociada no final do corpo.
Em particular, a variável de loop não é associada depois que o loop for é concluído.

### <a name="repeat-until-success-loop"></a>Repetir-loop Until-êxito

A instrução `repeat` dá suporte ao padrão Quantum "repetir até o sucesso".
Ele consiste na palavra-chave `repeat`, seguida por um bloco de instrução (o corpo do _loop_ ), a palavra-chave `until`, uma expressão booleana e um ponto e vírgula de terminação ou a palavra-chave `fixup` seguido por outro bloco de instrução (a _correção_).
O corpo, a condição e a correção do loop são considerados um único escopo, portanto, os símbolos associados ao corpo estão disponíveis na condição e na correção.

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qs);
    let success = ComputeSuccessIndicator(qs);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qs);
}
```

O corpo do loop é executado e a condição é avaliada.
Se a condição for verdadeira, a instrução será concluída; caso contrário, a correção será executada e a instrução será executada novamente começando com o corpo do loop.
Observe que a conclusão da execução da correção encerra o escopo da instrução, para que as associações de símbolo feitas durante o corpo ou correção não estejam disponíveis em repetições subsequentes.

Por exemplo, o código a seguir é um circuito probabilística que implementa um portão de rotação importante $V _3 = (\boldone + 2 i Z)/\sqrt{5}$ usando o Hadamard e T Gates.
O loop termina em 8/5 repetições em média.
Consulte [*repetir-até-êxito: decomposição não determinística de unidades de qubit único*](https://arxiv.org/abs/1311.1074) (Paetznick e Svore, 2014) para obter detalhes.

```qsharp
using (anc = Qubit()) {
    repeat {
        H(anc);
        T(anc);
        CNOT(target,anc);
        H(anc);
        Adjoint T(anc);
        H(anc);
        T(anc);
        H(anc);
        CNOT(target,anc);
        T(anc);
        Z(target);
        H(anc);
        let result = M(anc);
    } until (result == Zero);
}
```

> [!TIP]   
> Evite usar loops repetir-até-sucesso dentro de funções. A funcionalidade correspondente é fornecida por loops em funções do. 

### <a name="while-loop"></a>Loop while

Os padrões de repetição-até-sucesso têm uma connotação de muito Quantum específica. Eles são amplamente usados em classes específicas de algoritmos Quantum, portanto, a construção de linguagem dedicada em Q #. No entanto, os loops que quebram com base em uma condição e cujo comprimento de execução é, portanto, desconhecido em tempo de compilação precisam ser manipulados com cuidado específico em um tempo de execução do Quantum. Seu uso dentro de funções por outro lado é inproblemático, pois elas contêm apenas o código que será executado em hardware convencional (sem Quantum). 

O Q #, portanto, dá suporte ao uso de loops while apenas dentro de funções. Uma instrução `while` consiste na `while`de palavras-chave, uma `(`de parênteses aberto, uma condição (ou seja, uma expressão booleana), um parêntese de fechamento `)`e um bloco de instruções.
O bloco de instrução (o corpo do loop) é executado contanto que a condição seja avaliada como `true`.

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a>Instrução condicional

A instrução `if` dá suporte à execução condicional.
Ele consiste na palavra-chave `if`, um `(`de parênteses aberto, uma expressão booleana, um parêntese de fechamento `)`e um bloco de instruções (o bloco _then_ ).
Isso pode ser seguido por qualquer número de cláusulas else-if, cada uma das quais consiste na palavra-chave `elif`, um parênteses de abertura `(`, uma expressão booleana, um parêntese de fechamento `)`e um bloco de instrução (o bloco _else-if_ ).
Por fim, a instrução pode, opcionalmente, ser concluída com uma cláusula else, que consiste na palavra-chave `else` seguida por outro bloco de instrução (o bloco _else_ ).
A condição é avaliada e, se for verdadeira, o bloco then será executado.
Se a condição for falsa, a primeira condição IF-IF será avaliada; Se for true, o bloco else if será executado.
Caso contrário, o segundo bloco else é testado e, em seguida, o terceiro, e assim por diante, até que seja encontrada uma cláusula com uma condição true ou que não haja mais cláusulas If-If.
Se a condição if original e todas as cláusulas If forem avaliadas como false, o bloco else será executado se um for fornecido.

Observe que qualquer bloco executado é executado em seu próprio escopo.
Associações feitas dentro de um bloco then, else-if ou else não são visíveis após o final da instrução If.

Por exemplo,

```qsharp
if (result == One) {
    X(target);
} 
```

ou

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a>exibir

A instrução return encerra a execução de uma operação ou função e retorna um valor para o chamador.
Ele consiste na palavra-chave `return`, seguida por uma expressão do tipo apropriado e um ponto e vírgula de terminação.

Um callable que retorna uma tupla vazia, `()`, não requer uma instrução de retorno.
Se uma saída antecipada for desejada, `return ()` poderá ser usada nesse caso.
Os chamadores que retornam qualquer outro tipo exigem uma instrução de retorno final.

Não há um número máximo de instruções de retorno em uma operação.
O compilador pode emitir um aviso se as instruções seguirem uma instrução return dentro de um bloco.

Por exemplo,

```qsharp
return 1;
```

ou

```qsharp
return ();
```

ou

```qsharp
return (results, qubits);
```

### <a name="fail"></a>Recuperação

A instrução Fail encerra a execução de uma operação e retorna um valor de erro para o chamador.
Ela consiste na `fail`de palavras-chave, seguida por uma cadeia de caracteres e um ponto e vírgula de terminação.
A cadeia de caracteres é retornada ao driver clássico como a mensagem de erro.

Não há nenhuma restrição quanto ao número de instruções de falha em uma operação.
O compilador pode emitir um aviso se as instruções seguirem uma instrução Fail dentro de um bloco.

Por exemplo,

```qsharp
fail $"Impossible state reached";
```

ou

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a>Gerenciamento de qubit

Observe que nenhuma dessas instruções é permitida dentro do corpo de uma função.
Eles só são válidos dentro de operações.

### <a name="clean-qubits"></a>Limpar qubits

A instrução `using` é usada para adquirir novas qubits para uso durante um bloco de instruções.
Os qubits têm a garantia de serem inicializados para o estado computacional `Zero`.
O qubits deve estar no estado computacional `Zero` no final do bloco de instrução; os simuladores são incentivados a impor isso.

A instrução consiste na `using`de palavras-chave, seguida por um parêntese de abertura `(`, uma associação, um parêntese de fechamento `)`e o bloco de instruções dentro do qual o qubits estará disponível.
A associação segue o mesmo padrão que `let` instruções: um único símbolo ou uma tupla de símbolos, seguido por um sinal de igual `=`e um único valor ou uma tupla correspondente de inicializadores.
Inicializadores estão disponíveis para um único qubit, indicado como `Qubit()`, ou uma matriz de qubits, indicada por `Qubit[`, uma expressão de `Int` e `]`.

Por exemplo,

```qsharp
using (q = Qubit()) {
    // ...
}
using ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="dirty-qubits"></a>Qubits sujos

A instrução `borrowing` é usada para obter qubits para uso temporário. A instrução consiste na `borrowing`de palavras-chave, seguida por um parêntese de abertura `(`, uma associação, um parêntese de fechamento `)`e o bloco de instruções dentro do qual o qubits estará disponível.
A associação segue o mesmo padrão e regras que uma em uma instrução `using`.

Por exemplo,

```qsharp
borrowing (q = Qubit()) {
    // ...
}
borrowing ((ancilla, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

O qubits emprestado está em um estado desconhecido e sai do escopo no final do bloco de instrução.
O tomador de confirmações para deixar o qubits no mesmo estado em que estavam emprestados, ou seja, seu estado no início e no final do bloco de instrução deve ser o mesmo.
Esse estado em particular não é necessariamente um estado clássico, de modo que, na maioria dos casos, os escopos emprestados não devem conter medidas. 

Esses qubits geralmente são conhecidos como "Dirty ancilla".
Consulte [*fatoração usando 2n + 2 qubits com multiplicação modular baseada em Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler e Svore 2017) para obter um exemplo de uso de ancilla sujos.

Ao emprestar qubits, o sistema primeiro tentará preencher a solicitação de qubits que estão em uso, mas que não são acessadas durante o corpo da instrução `borrowing`.
Se não houver tal qubits suficiente, ele alocará o novo qubits para concluir a solicitação.

## <a name="conjugations"></a>Conjugações

Em contraste com os bits clássicos, liberar memória Quantum é um pouco mais envolvida, uma vez que a redefinição oculta de qubits pode ter efeitos indesejados na computação restante se o qubits ainda for confusas. Isso pode ser evitado com o "desfazendo" adequadamente os cálculos executados antes de liberar a memória. Um padrão comum na computação Quantum é, portanto, o seguinte: 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

: novo: começando com nossa versão 0,9, damos suporte a uma instrução Conjugation que implementa a transformação acima. Usando essa instrução, a operação `ApplyWith` pode ser implementada da seguinte maneira:

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
Uma instrução de conjugação, obviamente, se torna muito mais útil se as transformações externa e interna não estão prontamente disponíveis como operações, mas são mais convenientes de descrever por um bloco que consiste em várias instruções. 

A transformação inversa para as instruções definidas no bloco Within é gerada automaticamente pelo compilador e executada após a conclusão do bloco de aplicação. Como as variáveis mutáveis usadas como parte do bloco Within não podem ser reassociadas no bloco Apply, a transformação gerada é garantida como sendo a adjoin do cálculo no bloco Within. 

## <a name="expression-evaluation-statements"></a>Instruções de avaliação de expressão

Qualquer expressão de chamada do tipo `Unit` pode ser usada como uma instrução.
Isso é basicamente usado ao chamar operações em qubits que retornam `Unit` porque a finalidade da instrução é modificar o estado de Quantum implícito.
As instruções de avaliação de expressão exigem um ponto e vírgula de terminação.

Por exemplo,

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
