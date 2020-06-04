---
title: 'Fluxo de controlo em Q #'
description: Laços, condicional, etc.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: 1f1b641563fe35879abeee32b4f0aeeb7001b1a0
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84326545"
---
# <a name="control-flow-in-q"></a>Fluxo de controlo em Q #

Dentro de uma operação ou função, cada declaração executa por ordem, semelhante à linguagem clássica mais comum.
No entanto, este fluxo de controlo pode ser modificado de três formas distintas:

- `if`declarações
- `for`loops
- `repeat`-`until`loops

Adiamos a discussão deste último para [mais abaixo.](#repeat-until-success-loop)
O `if` fluxo e o fluxo de `for` controlo, no entanto, procedem num sentido familiar à maioria das linguagens clássicas de programação.

É importante que `for` os loops e `if` as declarações possam ser utilizados em operações para as quais as especializações são geradas automaticamente. Nesse caso, o adjacente de um `for` laço inverte a direção e toma o adjacente de cada iteração.
Isto segue o princípio "sapatos e meias": se quiser desfazer calçar meias e depois sapatos, deve desfazer calçar sapatos e depois desfazer as meias.
Funciona decididamente menos bem para tentar tirar as meias enquanto ainda usa os sapatos!

## <a name="if-else-if-else"></a>Se, Else-if, Else Else

A `if` declaração apoia a execução condicional.
Consiste na palavra-chave `if` , um parênteses `(` aberto, uma expressão booleana, um parênteses `)` próximos, e um bloco de afirmação (o _bloco então)._
Isto pode ser seguido por qualquer número de outras cláusulas, cada uma das quais consiste na palavra-chave `elif` , um parênteses aberto `(` , uma expressão booleana, um parênteses `)` próximos , e um bloco de declaração (o _bloco de outras partes)._
Finalmente, a declaração pode, opcionalmente, terminar com outra cláusula, que consiste na palavra-chave `else` seguida por outro bloco de declaração (o _outro_ bloco).

A `if` condição é avaliada, e se for verdade, o bloco é executado.
Se a condição for falsa, então a primeira condição se for avaliada; se for verdade, o outro bloco é executado.
Caso contrário, o segundo bloco se for testado, e depois o terceiro, e assim por diante, até que uma cláusula com uma condição verdadeira seja encontrada ou não haja mais cláusulas se.
Se a condição original e todas as outras cláusulas avaliarem falsas, o outro bloco é executado se um for fornecido.

Note que qualquer bloco executado é executado no seu próprio âmbito.
As encadernações feitas no interior de um `if` bloco , ou bloco não são `elif` `else` visíveis após o seu fim.

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

## <a name="for-loop"></a>Para Loop

A `for` declaração suporta a iteração sobre um intervalo inteiro ou sobre uma matriz.
A afirmação consiste na palavra-chave `for` , um parênteses `(` aberto, seguido de um símbolo ou tuple de símbolo, a palavra-chave `in` , uma expressão de tipo ou `Range` matriz, um parênteses `)` próximos , e um bloco de declaração.

O bloco de afirmação (o corpo do laço) é executado repetidamente, com o símbolo ou(s) (s) variável de loop(s) ligado a cada valor na gama ou matriz.
Note que se a expressão de alcance avaliar para um alcance ou matriz vazio, o corpo não será executado de todo.
A expressão é totalmente avaliada antes de entrar no loop, e não mudará enquanto o loop estiver a ser executado.

A variável do loop é ligada em cada entrada para o corpo em loop, e desacompida na extremidade do corpo.
Em particular, a variável loop não é ligada após a conclusão do loop.
A ligação dos símbolos declarados é imutável e segue as mesmas regras que outras ligações variáveis. 

Em alguns exemplos, supondo `qubits` ser um registo de qubits (isto é, do `Qubit[]` tipo), 

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
Note que no final utilizamos o operador binário aritmético-esquerdo, `<<<` cujos detalhes podem ser encontrados em [Expressões Numéricas](xref:microsoft.quantum.guide.expressions#numeric-expressions)


## <a name="repeat-until-success-loop"></a>Loop de repetição até ao sucesso

A linguagem Q# permite que o fluxo de controlo clássico dependa dos resultados da medição de qubits.
Esta capacidade, por sua vez, permite implementar poderosos gadgets probabilísticos que podem reduzir o custo computacional para implementar unitárias.
Como exemplo, é fácil implementar os chamados padrões *Repeat-Until-Success* (RUS) em Q#.
Estes padrões RUS são programas probabilísticos que têm um custo baixo *esperado* em termos de portões elementares, mas para os quais o verdadeiro custo depende de uma execução real e de uma interleling real de várias ramificações possíveis.

Para facilitar os padrões de Repetição-Até-Sucesso (RUS), Q# suporta as construções

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
O corpo em loop é executado, e então a condição é avaliada.
Se a condição for verdadeira, então a declaração é completada; caso contrário, a correção é executada, e a declaração é re-executada a partir do corpo do laço.

Todas as três porções de um ciclo de repetição/até loop (o corpo, o teste e a fixação) são tratadas como uma única margem *para cada repetição,* pelo que os símbolos que estão ligados ao corpo estão disponíveis no teste e na fixação.
No entanto, a conclusão da execução da correção termina o âmbito da declaração, de modo a que as ligações de símbolos efetuadas durante o corpo ou a correção não estejam disponíveis em repetições subsequentes.

Além disso, a `fixup` declaração é muitas vezes útil, mas nem sempre necessária.
Nos casos em que não é necessário, a construção
```qsharp
repeat {
    // do stuff
}
until (expression);
```
é também um padrão RUS válido.

Na parte inferior desta página apresentamos [alguns exemplos de loops RUS](#repeat-until-success-examples).

> [!TIP]   
> Evite utilizar laços de repetição até ao sucesso no interior das funções. A funcionalidade correspondente é fornecida por loops em funções. 

## <a name="while-loop"></a>Enquanto Loop

Os padrões de repetição até ao sucesso têm uma conotação muito quântica específica. São amplamente utilizados em classes particulares de algoritmos quânticos, daí a construção dedicada da linguagem em Q#. No entanto, os laços que quebram com base numa condição e cujo comprimento de execução é, portanto, desconhecido no tempo de compilação, precisam de ser tratados com especial cuidado num tempo de execução quântica. A sua utilização dentro de funções, por outro lado, não é problemática, uma vez que estas contêm apenas código que será executado em hardware convencional (não quântico). 

Q# Portanto, suporta a utilização de loops apenas dentro de funções. Uma `while` declaração consiste na palavra-chave , um `while` parênteses `(` aberto, uma condição (ou seja, uma expressão booleana), um parênteses `)` próximos , e um bloco de declaração.
O bloco de declaração (o corpo do laço) é executado desde que a condição avalie a `true` .

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a>Declaração de Devolução

A declaração de devolução termina a execução de uma operação ou função e devolve um valor ao autor da chamada.
Consiste na palavra-chave, `return` seguida de uma expressão do tipo apropriado, e de um ponto de terminação.

Uma chamada que devolve uma tuple vazia, `()` não requer uma declaração de devolução.
Se desejar uma saída antecipada, `return ()` pode ser utilizada neste caso.
Os callables que devolvem qualquer outro tipo requerem uma declaração final de devolução.

Não há um número máximo de declarações de devolução dentro de uma operação.
O compilador pode emitir um aviso se as declarações seguirem uma declaração de retorno dentro de um bloco.

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

## <a name="fail-statement"></a>Declaração de Falha

A declaração de falha termina a execução de uma operação e devolve um valor de erro ao autor da chamada.
Consiste na palavra-chave, `fail` seguida de uma corda e de um ponto de terminação.
A corda é devolvida ao condutor clássico como mensagem de erro.

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

Num caso de uso típico, a seguinte operação Q# implementa uma rotação em torno de um eixo irracional de $(I + 2i Z)/\sqrt {5} $ na esfera Bloch. Isto é conseguido usando um padrão RUS conhecido:

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

### <a name="rus-loop-with-mutable-variable-in-scope"></a>Loop RUS com variável mutável no âmbito

Este exemplo mostra a utilização de uma variável mutável `finished` que está no âmbito de todo o ciclo de repetição até à fixação e que é inicializado antes do loop e atualizado no passo de fixação.

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

### <a name="rus-without-fixup"></a>RUS sem`fixup`

Por exemplo, o seguinte código é um circuito probabilístico que implementa um importante portão de rotação $V_3 = (\boldone + 2 i Z) / \sqrt {5} $ usando o `H` e `T` portões.
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

Finalmente, mostramos um exemplo de um padrão RUS para preparar um estado quântico $\frac {1} {\sqrt {3} }\left(\sqrt {2} \ket {0} +\ket {1} \right)$, a partir do estado de $\ket{+}$.
Consulte também a [amostra de teste de unidade fornecida com a biblioteca padrão:](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
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

Notáveis características programáticas mostradas nesta operação são uma parte mais complexa `fixup` do loop, que envolve operações quânticas, e o uso de `AssertProb` declarações para determinar a probabilidade de medir o estado quântico em certos pontos especificados no programa.
Consulte também [os Testes e depurando](xref:microsoft.quantum.guide.testingdebugging) para obter mais informações sobre o [`Assert`](xref:microsoft.quantum.intrinsic.assert) e [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) operações.


## <a name="next-steps"></a>Próximos passos

Saiba mais [sobre Testes e Debugging](xref:microsoft.quantum.guide.testingdebugging) em Q#.