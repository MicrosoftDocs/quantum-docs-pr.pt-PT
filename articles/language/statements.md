---
title: Q# declarações / Microsoft Docs
description: Q# declarações
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 9a6f5d53ec21090d0c13f4369e0270d264cd1e9b
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036496"
---
# <a name="statements-and-other-constructs"></a>Declarações e Outras Construções

## <a name="comments"></a>Comentários

Os comentários começam com dois cortes dianteiros, `//`, e continuam até ao fim da linha.
Um comentário pode aparecer em qualquer lugar num ficheiro de origem Q#.

### <a name="documentation-comments"></a>Comentários de Documentação

Os comentários que começam com três cortes dianteiros, `///`, são tratados especialmente pelo compilador quando aparecem imediatamente antes de um espaço de nome, operação, especialização, função ou definição de tipo.
Nesse caso, os seus conteúdos são tomados como documentação para o tipo definido de callable ou definido pelo utilizador, como para outros idiomas .NET.

No `///` comentários, o texto a aparecer como parte da documentação da API é formatado como [Markdown](https://daringfireball.net/projects/markdown/syntax), com diferentes partes da documentação a serem indicadas por cabeçalhos especialmente nomeados.
Como extensão ao Markdown, as referências cruzadas a operações, funções e tipos definidos pelo utilizador em Q# podem ser incluídas utilizando o `@"<ref target>"`, onde `<ref target>` é substituído pelo nome totalmente qualificado do objeto de código que está a ser referenciado.
Opcionalmente, um motor de documentação também pode suportar extensões de Markdown adicionais.

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
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

Os seguintes nomes são reconhecidos como cabeçalhos de comentário documentais.

- **Resumo**: Um resumo curto do comportamento de uma função ou operação, ou do propósito de um tipo. O primeiro parágrafo do resumo é utilizado para informações sobre pairar. Deve ser um texto simples.
- **Descrição**: Uma descrição do comportamento de uma função ou operação, ou do propósito de um tipo. O resumo e a descrição são concatenados para formar o ficheiro de documentação gerado para a função, operação ou tipo.
  A descrição pode conter símbolos e equações formatados em linha LaTeX.
- **Entrada**: Uma descrição do tuple de entrada para uma operação ou função.
  Pode conter subsecções de Markdown adicionais indicando cada elemento individual da tuple de entrada.
- **Saída**: Uma descrição do tuple devolvido por uma operação ou função.
- **Parâmetros do tipo**: Uma secção vazia que contém uma subsecção adicional para cada parâmetro genérico do tipo.
- **Exemplo**: Um pequeno exemplo do funcionamento, função ou tipo de utilização.
- **Observações**: Prosa diversa que descreve algum aspeto da operação, função ou tipo.
- **Ver Também:** Uma lista de nomes totalmente qualificados que indicam funções, operações ou tipos definidos pelo utilizador.
- **Referências**: Uma lista de referências e citações para o artigo que está a ser documentado.

## <a name="namespaces"></a>Espaços de nomes

Cada operação, função e tipo definido pelo utilizador é definido dentro de um espaço de nome.
Q# segue as mesmas regras para nomear outras línguas .NET.
No entanto, Q# não suporta referências relativas a espaços de nome.
Ou seja, se o espaço de nome`a.b` tiver sido aberto, uma referência a uma operação nomea `c.d` não será resolvida a uma operação com o nome completo `a.b.c.d`.

Dentro de um bloco de espaço-nome, a diretiva `open` pode ser utilizada para importar todos os tipos e calíveis declarados num determinado espaço de nome e encaminhá-los pelo seu nome não qualificado. Opcionalmente, pode ser definido um nome curto para o espaço de nome aberto de modo a que todos os elementos desse espaço de nome possam (e precisam) ser qualificados pelo nome curto definido. A diretiva `open` aplica-se a todo o bloco de espaço de nome dentro de um ficheiro.

Um tipo ou callable definido em outro espaço de nome que não esteja aberto no espaço de nome atual deve ser referenciado pelo seu nome totalmente qualificado.
Por exemplo, uma operação denominada `Op` no espaço de nome `X.Y` deve ser referenciada pelo seu nome totalmente qualificado `X.Y.Op`, a menos que o espaço de nome `X.Y` tenha sido aberto mais cedo no bloco atual. Como mencionado acima, mesmo que tenha sido aberto o espaço de nome `X`, não é possível fazer referência à operação como `Y.Op`.
Se um nome curto `Z` para `X.Y` tiver sido definido nesse espaço de nome e arquivo, então `Op` deve ser referido como `Z.Op`. 

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

Normalmente, é melhor incluir um espaço de nome através de uma diretiva `open`.
É necessário utilizar um nome totalmente qualificado se dois espaços de nome definirem construções com o mesmo nome, e a fonte atual utiliza construções de ambos.

## <a name="formatting"></a>Formatação

A maioria das declarações e diretivas q# terminam com um ponto evígula terminando, `;`.
Declarações e declarações como `for` e `operation` que terminam com um bloco de declaração não requerem um ponto e vírgula terminando.
Cada descrição da declaração observa se o ponto evículo terminando é necessário.

Declarações, como expressões, declarações e diretivas, podem ser quebradas em várias linhas.
Deve evitar-se várias declarações numa única linha.

## <a name="statement-blocks"></a>Blocos de Declaração

As declarações de Q# são agruparadas em blocos de declaração.
Um bloco de declaração começa com uma abertura `{` e termina com um fecho `}`.

Um bloco de declaração que seja lexicamente fechado dentro de outro bloco é considerado um subbloco do bloco contendo; contendo e subblocos também são chamados blocos exteriores e internos.

## <a name="symbol-binding-and-assignment"></a>Ligação e atribuição de símbolos

Q# distingue entre símbolos mutáveis e imutáveis.
Em geral, o uso de símbolos imutáveis é encorajado porque permite ao compilador realizar mais otimizações.

O lado esquerdo da ligação consiste num símbolo tuple, e no lado direito de uma expressão.

Uma vez que todos os tipos de Q# são tipos de valor - com os qubits a assumirem um papel um pouco especial - formalmente é criada uma "cópia" quando um valor está ligado a um símbolo, ou quando um símbolo é recuperado. Ou seja, o comportamento do Q# é o mesmo que se uma cópia fosse criada na atribuição. Isto, em particular, também inclui matrizes. É claro que, na prática, apenas as peças relevantes são recriadas, se necessário. 

### <a name="tuple-deconstruction"></a>Desconstrução de Tuple

Se o lado direito da ligação for uma tuple, então essa tuple pode ser desconstruída após a atribuição.
Tais desconstruções podem envolver tuples aninhados, e qualquer desconstrução total ou parcial é válida desde que a forma da tuple no lado direito seja compatível com a forma do símbolo tuple.
A desconstrução de Tuple pode, em particular, ser usada quando o lado direito do `=` é uma expressão de valor tuple.

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a>Símbolos imutáveis

Os símbolos imutáveis são ligados usando a declaração `let`.
Isto equivale aproximadamente à declaração variável e C#à inicialização em línguas como, exceto que os símbolos Q#, uma vez ligados, não podem ser alterados; `let` encadernações são imutáveis.

Uma ligação imutável consiste na palavra-chave `let`, seguida de um símbolo ou túnica de símbolo, um sinal igual `=`, uma expressão para ligar o símbolo(s) a, e um ponto evícito terminando.
O tipo de símbolo s de atado é inferido com base na expressão do lado direito.

### <a name="mutable-symbols"></a>Símbolos mutáveis

Os símbolos mutáveis são definidos e inicializados utilizando a declaração `mutable`.
Os símbolos declarados e vinculados como parte de uma declaração `mutable` podem ser recuperados para um valor diferente mais tarde no código. 

Uma declaração de ligação mutável consiste na palavra-chave `mutable`, seguida de um símbolo ou símbolo, um sinal igual `=`, uma expressão para ligar o símbolo(s) e um ponto evículo terminante.
O tipo de símbolo s de atado é inferido com base na expressão do lado direito. Se um símbolo for recuperado mais tarde no código, o seu tipo não muda, e o valor vinculado tem de ser compatível com esse tipo.

### <a name="rebinding-of-mutable-symbols"></a>Reenção de símbolos mutáveis

Uma variável mutável pode ser recuperada usando uma declaração `set`.
Tal reencência consiste na palavra-chave `set`, seguida de um símbolo ou símbolo, um sinal igual `=`, uma expressão para religar o símbolo(s) a, e um ponto evículo terminante.
O valor deve ser compatível com o ou os tipos do símbolo a que está ligado.

#### <a name="apply-and-reassign-statement"></a>Declaração de Candidatura e Reatribuição

Um tipo particular de declaração de set a que nos referimos como uma declaração de aplicação e reatribuição fornece uma forma conveniente de concatenação se o lado direito consistir na aplicação de um operador binário e o resultado é ser ressaltado para o argumento esquerdo para o operador. Por exemplo,
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
incrementa o valor do contador `counter` em cada iteração do ciclo `for`. O código acima é equivalente a 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
Estão disponíveis declarações semelhantes para todos os operadores binários em que o tipo do lado esquerdo corresponde ao tipo de expressão. Isto fornece, por exemplo, uma forma conveniente de acumular valores:
```qsharp
mutable results = new Result[0];
for (qubit in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a>Declaração de atualização e reatribuição

Existe uma concatenação semelhante para expressões de cópia e atualização no lado direito. Consequentemente, existem declarações de atualização e reatribuição para itens nomeados em tipos definidos pelo utilizador, bem como para itens de matriz.  

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

No caso das matrizes, as nossas bibliotecas padrão contêm as ferramentas necessárias para muitas necessidades comuns de inicialização e manipulação de matrizes, ajudando assim a evitar ter de atualizar itens de matriz em primeiro lugar. As declarações de atualização e reatribuição fornecem uma alternativa, se necessário:

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

> [!TIP]   
> Evite a utilização desnecessária de declarações de atualização e reatribuição, aproveitando as ferramentas fornecidas em <xref:microsoft.quantum.arrays>.

A função
```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];
    for (index in 0 .. length - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
por exemplo, pode simplesmente ser simplificado utilizando a função `ConstantArray` em `Microsoft.Quantum.Arrays`, e devolvendo uma expressão de cópia e atualização:

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

### <a name="binding-scopes"></a>Âmbitos vinculativos

Em geral, as ligações dos símbolos desbloqueiam o seu alcance e tornam-se inoperantes no final do bloco de declaração em que ocorrem.
Há duas exceções a esta regra:

- A ligação da variável de ciclo de um ciclo de `for` está no âmbito do corpo do laço para o loop, mas não após o fim do laço.
- Todas as três porções de um `repeat`/`until` loop (o corpo, o teste e a fixação) são tratadas como um único âmbito, pelo que os símbolos que estão ligados no corpo estão disponíveis no teste e na fixação.

Para ambos os tipos de loops, cada passe através do loop executa no seu próprio âmbito, pelo que as encadernações de um passe anterior não estão disponíveis num passe posterior.

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

## <a name="control-flow"></a>Fluxo de Controlo

### <a name="for-loop"></a>Para Loop

A declaração de `for` suporta a iteração sobre uma gama de inteiros ou sobre uma matriz.
A declaração consiste na palavra-chave `for`, um parêntese aberto `(`, seguido de um símbolo ou símbolo, a palavra-chave `in`, uma expressão de tipo `Range` ou matriz, um parêntese próximo `)`, e um bloco de declaração.

O bloco de declaração (o corpo do laço) é executado repetidamente, com os símbolos definidos (a variável do laço(s)ligadoa a cada valor na gama ou matriz.
Note que se a expressão de alcance avaliar para um alcance ou matriz vazio, o corpo não será executado de todo.
A expressão é totalmente avaliada antes de entrar no loop, e não mudará enquanto o loop estiver executando.

A ligação dos símbolos declarados é imutável e segue as mesmas regras que outras encadernações variáveis. Em particular, é possível destruir, por exemplo, itens de matriz para uma iteração sobre uma matriz aquando da atribuição à variável de loop.

Por exemplo,

```qsharp
// ...
for (qubit in qubits) { // qubits contains a Qubit[]
    H(qubit);
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

A variável do loop é ligada a cada entrada do corpo em loop, e desamarrada na extremidade do corpo.
Em particular, a variável de loop não está ligada após a conclusão do ciclo para o loop.

### <a name="repeat-until-success-loop"></a>Loop de repetição até ao sucesso

A declaração `repeat` apoia o padrão quântico de "repetir até ao sucesso".
Consiste na palavra-chave `repeat`, seguida de um bloco de declaração (o corpo _de loop),_ a palavra-chave `until`, uma expressão booleana, e ou um ponto evículo terminando ou a palavra-chave `fixup` seguido de outro bloco de declaração (a _fixação)._
O corpo, a condição e a fixação do laço são considerados um único âmbito, pelo que os símbolos ligados ao corpo estão disponíveis na condição e fixação.

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

O corpo do loop é executado, e então a condição é avaliada.
Se a condição for verdadeira, então a declaração é completada; caso contrário, a correção é executada, e a declaração é reexecutada a partir do corpo do loop.
Note que a conclusão da execução da fixação termina o âmbito da declaração, de modo a que as ligações de símbolos efetuadas durante o corpo ou a fixação não estejam disponíveis em repetições subsequentes.

Por exemplo, o seguinte código é um circuito probabilístico que implementa um importante portão de rotação $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ utilizando os portões Hadamard e T.
O loop termina em $\frac{8}{5}repetições de $, em média.
Ver [*Repeat-Until-Success: Decomposição não-determinística de unitários monoqubit*](https://arxiv.org/abs/1311.1074) (Paetznick e Svore, 2014) para mais detalhes.

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

> [!TIP]   
> Evite utilizar laços de repetição até ao sucesso dentro das funções. A funcionalidade correspondente é fornecida através de loops nas funções. 

### <a name="while-loop"></a>Enquanto Loop

Os padrões de repetição até ao sucesso têm uma conotação muito quântica específica. Eles são amplamente usados em classes particulares de algoritmos quânticos - daí a construção de linguagem dedicada em Q#. No entanto, os laços que se rompem com base numa condição e cujo comprimento de execução é, portanto, desconhecido no tempo de compilação precisam de ser tratados com especial cuidado num tempo de execução quântico. A sua utilização dentro de funções, por outro lado, não é problemática, uma vez que estas contêm apenas código que será executado em hardware convencional (não quântico). 

Q# apoia, portanto, a utilização de laços enquanto as funções apenas. Uma declaração `while` consiste na palavra-chave `while`, um `(`de parênteses abertas , uma condição (isto é, uma expressão booleana), um parêntese próximo `)`, e um bloco de declaração.
O bloco de declaração (o corpo do laço) é executado desde que a condição avalie para `true`.

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a>Declaração Condicional

A declaração `if` apoia a execução condicional.
Consiste na palavra-chave `if`, um parêntese aberto `(`, uma expressão booleana, um parêntese próximo `)`, e um bloco de declaração (o _bloco de então)._
Isto pode ser seguido por qualquer número de cláusulas se, cada uma das quais consiste na palavra-chave `elif`, um parêntese aberto `(`, uma expressão booleana, um parêntese próximo `)`, e um bloco de declaração (o _bloco de outra sea)._
Finalmente, a declaração pode terminar opcionalmente com uma outra cláusula, que consiste na palavra-chave `else` seguida de outro bloco de declaração (o _bloco de outra_ si).
A condição é avaliada, e se for verdade, o bloco de então é executado.
Se a condição for falsa, então a condição de outra pessoa é avaliada; se for verdade, que o bloco mais se for executado.
Caso contrário, o segundo bloco se for testado, e depois o terceiro, e assim por diante, até que seja encontrada uma cláusula com uma condição real ou não haja mais cláusulas se.
Se a condição original e todas as cláusulas se forem avaliadas como falsas, o outro bloco é executado se um for fornecido.

Note que qualquer bloco executado é executado no seu próprio âmbito.
As encadernações feitas dentro de um bloco então, se, ou então, não são visíveis após o fim da declaração se.

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

### <a name="return"></a>Devolução

A declaração de devolução termina a execução de uma operação ou função e devolve um valor ao chamador.
Consiste na palavra-chave `return`, seguida de uma expressão do tipo apropriado, e de um ponto evíomina terminando.

Um insensível que devolve uma tuple vazia, `()`, não requer uma declaração de devolução.
Se for desejada uma saída antecipada, `return ()` podem ser utilizados neste caso.
Os callables que devolvem qualquer outro tipo requerem uma declaração final de devolução.

Não há um número máximo de declarações de devolução dentro de uma operação.
O compilador pode emitir um aviso se as declarações seguirem uma declaração de devolução dentro de um bloco.

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

### <a name="fail"></a>Falha

A declaração de falha termina a execução de uma operação e devolve um valor de erro ao chamador.
Consiste na palavra-chave `fail`, seguida de uma corda e de um ponto evío minado.
A corda é devolvida ao condutor clássico como mensagem de erro.

Não existe qualquer restrição ao número de declarações falhadas no âmbito de uma operação.
O compilador pode emitir um aviso se as declarações seguirem uma declaração de falha dentro de um bloco.

Por exemplo,

```qsharp
fail $"Impossible state reached";
```

ou

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a>Gestão qubit

Note que nenhuma destas declarações é permitida dentro do corpo de uma função.
Só são válidos dentro das operações.

### <a name="clean-qubits"></a>Qubits limpos

A declaração `using` é utilizada para adquirir novos qubits para utilização durante um bloco de declaração.
Os qubits são garantidos para serem inicializados para o estado computacional `Zero`.
Os qubits devem estar no estado de `Zero` computacional no final do bloco de declaração; simuladores são encorajados a impor isto.

A declaração consiste na palavra-chave `using`, seguida de um parêntese aberto `(`, uma ligação, um parêntese próximo `)`, e o bloco de declaração dentro do qual estarão disponíveis os qubits.
A ligação segue o mesmo padrão que as declarações `let`: um único símbolo ou uma tuple de símbolos, seguido de um sinal igual `=`, e um único valor ou uma túnica correspondente de iniciais.
Os iniciais estão disponíveis para um único qubit, indicado como `Qubit()`, ou um conjunto de qubits, indicados por `Qubit[`, uma expressão `Int` e `]`.

Por exemplo,

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="borrowed-qubits"></a>Qubits emprestados

A declaração `borrowing` é utilizada para obter qubits para uso temporário. A declaração consiste na palavra-chave `borrowing`, seguida de um parêntese aberto `(`, uma ligação, um parêntese próximo `)`, e o bloco de declaração dentro do qual estarão disponíveis os qubits.
A encadernação segue o mesmo padrão e regras que a de uma declaração `using`.

Por exemplo,

```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

Os qubits emprestados estão num estado desconhecido e saem do âmbito no final do bloco de declaração.
O mutuário compromete-se a deixar os qubits no mesmo estado em que estavam quando foram emprestados, ou seja, o seu estado no início e no final do bloco de declaração deverá ser o mesmo.
Este Estado, em particular, não é necessariamente um estado clássico, de tal forma que, na maioria dos casos, os âmbitos de empréstimo não devem conter medições. 

Consulte [*factoring usando 2n+2 qubits com multiplicação modular baseada em Toffoli*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler e Svore 2017) como um exemplo de utilização de qubit emprestado.

Ao pedir qubits emprestados, o sistema tentará primeiro preencher o pedido de qubits que estão em uso, mas que não são acedidos durante o corpo da declaração de `borrowing`.
Se não houver qubits suficientes, então irá alocar novos qubits para completar o pedido.

## <a name="conjugations"></a>Conjugações

Em contraste com as partes clássicas, a libertação da memória quântica é um pouco mais envolvida, uma vez que os qubits de reposição cega podem ter efeitos indesejados no restante cálculo se os qubits ainda estiverem emaranhados. Isto pode ser evitado por "desfazer" corretamente as computações realizadas antes de libertar a memória. Um padrão comum na computação quântica é, portanto, o seguinte: 

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

:novo: A partir do nosso lançamento 0.9, apoiamos uma declaração de conjugação que implementa a transformação acima. Utilizando esta declaração, a operação `ApplyWith` pode ser implementada da seguinte forma:

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
Tal declaração de conjugação torna-se obviamente muito mais útil se a transformação exterior e interior não estiver prontamente disponível como operações, mas em vez disso são mais convenientes para descrever por um bloco composto por várias declarações. 

A transformação inversa para as declarações definidas no bloco interior é automaticamente gerada pelo compilador e executada após a conclusão do bloco de aplicação. Uma vez que quaisquer variáveis mutáveis utilizadas como parte do bloco interior não podem ser recuperadas no bloco de aplicação, a transformação gerada é garantidamente a adjoint do cálculo no bloco interior. 

## <a name="expression-evaluation-statements"></a>Declarações de avaliação de expressão

Qualquer expressão de chamada de `Unit` pode ser usada como uma declaração.
Isto é principalmente útil quando se ligam operações sobre qubits que devolvem `Unit` porque o objetivo da declaração é modificar o estado quântico implícito.
As declarações de avaliação da expressão requerem um ponto e vírgula terminando.

Por exemplo,

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
