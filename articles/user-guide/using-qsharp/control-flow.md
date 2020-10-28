---
title: Fluxo de controlo em Q#
description: Laços, condicional, etc.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: eca37202e5fe9b48dcfdec4eeb4ba6cafaac8723
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691097"
---
# <a name="control-flow-in-no-locq"></a>Fluxo de controlo em Q#

Dentro de uma operação ou função, cada declaração funciona em ordem, semelhante a outras línguas clássicas imperativas comuns.
No entanto, pode modificar o fluxo de controlo de três formas distintas:

* `if` declarações
* `for` loops
* `repeat-until-success` loops
* conjugações `apply-within` (declarações)

As `if` construções de fluxo e `for` controlo prosseguem num sentido familiar à maioria das linguagens clássicas de programação. [`Repeat-until-success`](#repeat-until-success-loop) loops e conjugações são [discutidos](#conjugations) mais tarde neste artigo.

Importante, `for` loops e `if` declarações podem ser usados em operações para as quais [as especializações](xref:microsoft.quantum.guide.operationsfunctions) são geradas automaticamente. Nesse cenário, o adjacente de um `for` loop inverte a direção e toma o adjacente de cada iteração.
Esta ação segue o princípio "sapatos e meias": se quiser desfazer calçar meias e depois sapatos, deve desfazer calçar sapatos e depois desfazer as meias. 

## <a name="if-else-if-else"></a>Se, Else-if, Else Else

A `if` declaração suporta o processamento condicional.
Consiste na palavra-chave, `if` uma expressão booleana em parênteses, e um bloco de declaração (o _bloco então)._
Opcionalmente, qualquer número de outras cláusulas podem seguir- cada uma delas consiste na `elif` palavra-chave , uma expressão booleana em parênteses, e um bloco de declaração (o _bloco de outras partes)._
Finalmente, a declaração pode, opcionalmente, terminar com outra cláusula, que consiste na palavra-chave `else` seguida por outro bloco de declaração (o _outro_ bloco).

A `if` condição é avaliada, e se for *verdade,* o *bloco é* executado.
Se a condição for *falsa,* então a primeira condição se for avaliada; se isso é verdade, então o *outro bloco-se* é executado.
Caso contrário, o segundo bloco se avaliar, e depois o terceiro, e assim por diante, até que uma cláusula com uma condição verdadeira seja encontrada ou não haja mais cláusulas se.
Se o original *se* a condição e todas as cláusulas se avaliarem *falsas,* o *outro* bloco é executado, se fornecido.

Note que qualquer que seja o bloco que corre, funciona dentro do seu próprio âmbito.
As ligações feitas no interior de um `if` bloco , ou bloco não são `elif` `else` visíveis após as extremidades do bloco.

Por exemplo,

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
ou
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a>Ciclos For

A `for` declaração suporta a iteração sobre um intervalo inteiro ou uma matriz.
A afirmação consiste na palavra-chave `for` , seguida de um símbolo ou tuple de símbolo, a palavra-chave , e uma expressão de tipo ou `in` `Range` matriz, tudo em parênteses, e um bloco de declaração.

O bloco de declaração (o corpo do laço) funciona repetidamente, com o símbolo definido (a variável loop) ligado a cada valor na gama ou matriz.
Note que se a expressão de alcance avalia para um alcance ou matriz vazio, o corpo não funciona de todo.
A expressão é totalmente avaliada antes de entrar no loop, e não muda enquanto o loop está em funcionamento.

A variável do loop está ligada em cada entrada do corpo em loop, e é desacompida na extremidade do corpo.
A variável loop não é ligada após o loop for for complete.
A ligação da variável loop é imutável e segue as mesmas regras que outras encadernações variáveis. 

Nestes exemplos, `qubits` encontra-se um registo de qubits (isto é, do `Qubit[]` tipo), 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

Note que no final, utilizamos o operador binário aritmético-esquerdo, `<<<` . Para mais informações, consulte [Expressões Numéricas.](xref:microsoft.quantum.guide.expressions#numeric-expressions)

## <a name="repeat-until-success-loop"></a>Loop de repetição até ao sucesso

A Q# linguagem permite que o fluxo de controlo clássico dependa dos resultados da medição de qubits.
Esta capacidade, por sua vez, permite implementar poderosos gadgets probabilísticos que podem reduzir o custo computacional para implementar unitárias.
Exemplos disso são os padrões *de repetição até ao sucesso* (RUS) em Q# .
Estes padrões RUS são programas probabilísticos que têm um custo baixo *esperado* em termos de portões elementares; o custo incorrido depende da execução real e da interligagem das múltiplas ramificações possíveis.

Para facilitar os padrões de repetição até ao sucesso (RUS), Q# apoia as construções

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

onde `expression` é qualquer expressão válida que avalie a um valor de tipo `Bool` .
O corpo do loop corre, e então a condição é avaliada.
Se a condição for verdadeira, então a declaração é completada; caso contrário, a correção corre, e a declaração corre novamente, começando com o corpo do laço.

Todas as três porções de um laço RUS (o corpo, o teste e a fixação) são tratadas como uma única margem *para cada repetição,* pelo que os símbolos que estão ligados ao corpo estão disponíveis tanto no teste como na fixação.
No entanto, completar o funcionamento da correção termina o âmbito da declaração, de modo que as ligações de símbolos efetuadas durante o corpo ou a correção não estejam disponíveis em repetições subsequentes.

Além disso, a `fixup` declaração é muitas vezes útil, mas nem sempre necessária.
Nos casos em que não é necessário, a construção

```qsharp
repeat {
    // do stuff
}
until (expression);
```

é também um padrão RUS válido.

Para mais exemplos e detalhes, consulte [exemplos de repetição até ao sucesso](#repeat-until-success-examples) neste artigo.

> [!TIP]   
> Evite utilizar laços de repetição até ao sucesso no interior das funções. Utilize *enquanto* os loops fornecem as funções correspondentes no interior. 

## <a name="while-loop"></a>Ciclo While

Os padrões de repetição até ao sucesso têm uma conotação muito quântica específica. São amplamente utilizados em determinadas classes de algoritmos quânticos - daí a construção dedicada da linguagem em Q# . No entanto, os laços que quebram com base numa condição e cujo comprimento de execução é, portanto, desconhecido no tempo de compilação, são tratados com especial cuidado num tempo de execução quântica. No entanto, a sua utilização dentro das funções não é problemática, uma vez que estes loops contêm apenas código que funciona em hardware convencional (não quântico). 

Q#, portanto, suporta a utilização de loops apenas dentro de funções.
Uma `while` declaração consiste na palavra-chave , uma expressão `while` booleana em parênteses, e um bloco de declaração.
O bloco de declaração (o corpo do laço) é executado desde que a condição avalie para `true` .

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="conjugations"></a>Conjugações

Em contraste com os bits clássicos, a libertação da memória quântica é um pouco mais envolvida, uma vez que os qubits de reposição cega podem ter efeitos indesejáveis na computação restante se os qubits ainda estiverem emaranhados. Estes efeitos podem ser evitados "desfazendo" os cálculos realizados corretamente antes de libertar a memória. Um padrão comum na computação quântica é, por conseguinte, o seguinte: 

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

Q# apoia uma declaração de conjugação que implementa a transformação anterior. Utilizando esta declaração, a operação `ApplyWith` pode ser implementada da seguinte forma:

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
Tal declaração de conjugação torna-se útil se as transformações exteriores e interiores não estiverem prontamente disponíveis como operações, mas são mais convenientes para descrever por um bloco composto por várias declarações. 

A transformação inversa para as declarações definidas no bloco interior é gerada automaticamente pelo compilador e executada após o fim do bloco de aplicação.
Uma vez que quaisquer variáveis mutáveis utilizadas como parte do bloco interior não podem ser recuperadas no bloco de aplicação, a transformação gerada é garantidamente o adjacente do cálculo no bloco interior. 

## <a name="return-statement"></a>Declaração de Devolução

A declaração de devolução termina a execução de uma operação ou função e devolve um valor ao autor da chamada.
Consiste na palavra-chave, `return` seguida de uma expressão do tipo apropriado, e de um ponto de terminação.

Por exemplo,
```qsharp
return 1;
```
ou
```qsharp
return (results, qubits);
```

* Uma chamada que devolve uma tuple vazia, `()` não requer uma declaração de devolução.
* Para especificar uma saída antecipada da operação ou função, utilize `return ();` .
Os callables que devolvem qualquer outro tipo requerem uma declaração final de devolução.
* Não há um número máximo de declarações de devolução dentro de uma operação.
O compilador pode emitir um aviso se as declarações seguirem uma declaração de retorno dentro de um bloco.

   
## <a name="fail-statement"></a>Declaração de falha

A declaração de falha termina a execução de uma operação e devolve um valor de erro ao autor da chamada.
Consiste na palavra-chave, `fail` seguida de uma corda e de um ponto de terminação.
A declaração devolve a corda ao condutor clássico como mensagem de erro.

Não existe qualquer restrição ao número de declarações de falha no âmbito de uma operação.
O compilador pode emitir um aviso se as declarações seguirem uma declaração de falha dentro de um bloco.

Por exemplo,

```qsharp
fail $"Impossible state reached";
```
ou, utilizando [cordas interpoladas,](xref:microsoft.quantum.guide.expressions#interpolated-strings)
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a>Exemplos de repetição até ao sucesso

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>Padrão RUS para rotação de um único qubit sobre um eixo irracional 

Num caso de uso típico, a seguinte Q# operação implementa uma rotação em torno de um eixo irracional de $(I + 2i Z)/\sqrt {5} $ na esfera Bloch. A implementação utiliza um padrão RUS conhecido:

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a>Loop RUS com uma variável mutável no âmbito

Este exemplo mostra a utilização de uma variável mutável, `finished` que está no âmbito de todo o ciclo de repetição até-fixup e que é inicializado antes do loop e atualizado no passo de correção.

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

### <a name="rus-without-fixup"></a>RUS sem `fixup`

Este exemplo mostra um loop RUS sem o passo de fixação. O código é um circuito probabilístico que implementa um importante portão de rotação $V_3 = (\boldone + 2 i Z) / \sqrt {5} $ usando o `H` e `T` portões.
O loop termina em repetições de $\frac$ {8} {5} em média.
Ver [*Repeti-Until-Success: Decomposição não determinística de unitários de um único qubit*](https://arxiv.org/abs/1311.1074) (Paetznick e Svore, 2014) para mais detalhes.

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

### <a name="rus-to-prepare-a-quantum-state"></a>RUS para preparar um estado quântico

Finalmente, aqui está um exemplo de um padrão RUS para preparar um estado quântico $\frac {1} {\sqrt {3} }\left(\sqrt {2} \ket {0} +\ket {1} \right)$, a partir do estado de $\ket{+}$.

As notáveis características programáticas mostradas nesta operação são:

* Uma parte mais complexa `fixup` do ciclo, que envolve operações quânticas. 
* O uso de `AssertMeasurementProbability` declarações para determinar a probabilidade de medir o estado quântico em certos pontos especificados no programa.

Para obter mais informações sobre o [`AssertMeasurement`](xref:Microsoft.Quantum.Diagnostics.assertmeasurement) e [`AssertMeasurementProbability`](xref:Microsoft.Quantum.Diagnostics.assertmeasurementprobability) operações, consulte [Testes e depuragem.](xref:microsoft.quantum.guide.testingdebugging)

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

Para obter mais informações, consulte [a amostra de teste de unidade fornecida com a biblioteca padrão:](https://github.com/microsoft/Quantum/blob/main/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)

## <a name="next-steps"></a>Passos seguintes

Saiba mais [sobre testes e depuragem](xref:microsoft.quantum.guide.testingdebugging) em Q# .
