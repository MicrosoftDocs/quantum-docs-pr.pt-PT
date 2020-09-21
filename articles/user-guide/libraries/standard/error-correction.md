---
title: Correção de erros nas Q# bibliotecas padrão
description: Aprenda a usar códigos de correção de erros nos seus Q# programas enquanto protege o estado dos qubits.
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: dad0db4d2aab27e5ae46d4df10ee050f785d8bb8
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835558"
---
# <a name="error-correction"></a>Correção de Erros #

## <a name="introduction"></a>Introdução ##

Na computação clássica, se se quer proteger um pouco contra erros, muitas vezes pode ser suficiente para representar isso um pouco por um *pouco lógico* repetindo a parte dos dados.
Por exemplo, deixe $\overline {0} = 000$ ser a codificação do bit de dados 0, onde usamos a linha acima da etiqueta 0 para indicar que é uma codificação de um pouco no estado 0.
Se também deixarmos $\\overline {1} = 111$, então temos um simples código de repetição que protege contra qualquer erro de lançamento de um bit.
Ou seja, se alguma das três partes for virada, então podemos recuperar o estado da parte lógica, votando por maioria.
Embora a correção clássica de erros seja um assunto muito mais rico que este exemplo em particular (recomendamos [a introdução de Lint à teoria da codificação),](https://www.springer.com/us/book/9783540641339)o código de repetição acima já aponta para um possível problema na proteção da informação quântica.
Ou seja, o [teorema da não clonagem](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) implica que, se medirmos cada qubit individual e tivermos uma votação maioritária por analogia ao código clássico acima, perdemos a informação precisa que estamos a tentar proteger.

No cenário quântico, veremos que a medição é problemática. Ainda podemos implementar a codificação acima.
É útil fazê-lo para ver como podemos generalizar a correção de erros no caso quântico.
Assim, deixe $\ket{\overline {0} } = \ket {000} = \ket {0} \otimes \ket {0} \otimes \ket \ket {0} \ket $, e let $\ket{\overline {1} } = \ket {111} $.
Então, por linearidade, definimos o nosso código de repetição para todas as entradas; por exemplo, $\ket{\overline{+}} = (\ket{\overline {0} } + \ket{\overline {1} }) / \sqrt {2} = {000} (\ket + \ket) {111} / \sqrt {2} $.
Em particular, deixando um erro de flip-flip $X_1$ agir no qubit médio, vemos que a correção necessária em ambos os ramos é precisamente $X_1$: $$ \start{align} X_1 \ket{\overline{+}} & = \frac {1} {\sqrt {2} } \X_1 \ket {000} + X_1 \ket {111} \ket \right) \\ \\ & = \frac {1} {sqrt {2} } \\ket {010} {101}
\end{align} $$

Para ver como podemos identificar que este é o caso sem medir o próprio estado que estamos a tentar proteger, é útil escrever o que cada erro de viragem de bits diferentes faz aos nossos estados lógicos:

| Erro $E$ | $E\ket{\overline {0} }$ | $E\ket{\overline {1} }$ |
| --- | --- | --- |
| $\boldone$ | $\ket {000} $ | $\ket {111} $ |
| $X_0$ | $\ket {100} $ | $\ket {011} $ |
| $X_1$ | $\ket {010} $ | $\ket {101} $ |
| $X_2$ | $\ket {001} $ | $\ket {110} $ |

Para proteger o estado que estamos codificando, precisamos ser capazes de distinguir os três erros uns dos outros e da identidade $\boldone$ sem distinguir entre $\ket\overline {0} }$ e $\ket{\overline {1} }$.
Por exemplo, se medirmos $Z_0$, obtemos um resultado diferente por $\ket{\overline {0} }$ e $\ket{\overline {1} }$ na caixa sem erro, de modo que colapsa o estado codificado.
Por outro lado, considere medir $Z_0 Z_1$, a paridade dos dois primeiros bits em cada estado de base computacional.
Lembre-se que cada medição de um operador Pauli verifica qual o valor do estado que está a ser medido corresponde, de modo que para cada estado $\ket{\psi}$ na tabela acima, podemos calcular $Z_0 Z_1 \ket{\psi}$ para ver se recebemos $\pm\ket\psi}$.
Note que $Z_0 Z_1 {000} \ket = \ket {000} $ e que $Z_0 Z_1 \ket {111} = \ket {111} $, de modo a concluir que esta medição faz o mesmo a ambos os estados codificados.
Por outro lado, $Z_0 Z_1 \ket {100} = - \ket {100} $ e $Z_0 Z_1 \ket {011} = -\ket {011} $, pelo que o resultado da medição de $Z_0 Z_1$ revela informações úteis sobre que erro ocorreu.

Para enfatizar isto, repetimos a tabela acima, mas adicionamos os resultados da medição $Z_0 Z_1$ e $Z_1 Z_2$ em cada linha.
Denotamos os resultados de cada medição pelo sinal do valor eigen que é observado, ou $+$ ou $-$, correspondente aos Q# `Result` valores de `Zero` `One` e, respectivamente.

| Erro $E$ | $E\ket{\overline {0} }$ | $E\ket{\overline {1} }$ | Resultado de $Z_0 Z_1$ | Resultado de $Z_1 Z_2$ |
| --- | --- | --- | --- | --- |
| $\boldone$ | $\ket {000} $ | $\ket {111} $ | $+$ | $+$ |
| $X_0$ | $\ket {100} $ | $\ket {011} $ | $-$ | $+$ |
| $X_1$ | $\ket {010} $ | $\ket {101} $ | $-$ | $-$ |
| $X_2$ | $\ket {001} $ | $\ket {110} $ | $+$ | $-$ |

Assim, os resultados das duas medições determinam exclusivamente qual o erro bit-flip ocorrido, mas sem revelar qualquer informação sobre o estado que codificamos.
Chamamos a estes resultados uma *síndrome,* e referimo-nos ao processo de mapear uma síndrome de volta ao erro que a causou como *recuperação*.
Em particular, salientamos que a recuperação é um procedimento de inferência *clássica* que toma como entrada a síndrome que ocorreu, e devolve uma receita para como corrigir quaisquer erros que possam ter ocorrido.

> [!NOTE]
> O código bit-flip acima só pode corrigir contra erros simples de bit-flip; isto é, uma `X` operação agindo num único qubit.
> `X`Aplicar-se a mais de um qubit irá mapear $\ket{\overline {0} }$ para $\ket{\overline {1} }$ após a recuperação.
> Da mesma forma, a aplicação de uma operação de lançamento de fase `Z` irá mapear $\ket{\overline {1} }$ para $-\ket{\overline {1} }$, e, portanto, mapeará $\ket{\overline{+}} para $\ket{\overline {-} }$.
> De uma forma mais geral, podem ser criados códigos para lidar com um maior número de erros e para lidar com erros de $Z$, bem como $X$ erros.

A perceção de que podemos descrever medições na correção de erros quânticos que atuam da mesma forma em todos os estados de código, é a essência do *formalismo estabilizador.*
O Q# cânone fornece um quadro para descrever a codificação e descodificamento dos códigos estabilizadores, e para descrever como se recupera de erros.
Nesta secção, descrevemos este quadro e a sua aplicação a alguns simples códigos de correção de erros quânticos.

> [!TIP]
> Uma introdução completa ao formalismo estabilizador está fora do âmbito desta secção.
> Referimos leitores interessados em aprender mais com [Gottesman 2009.](https://arxiv.org/abs/0904.2557)

## <a name="representing-error-correcting-codes-in-no-locq"></a>Representando códigos de correção de erros em Q# ##

Para ajudar a especificar códigos de correção de erros, o Q# cânone fornece vários tipos distintos definidos pelo utilizador:

- <xref:microsoft.quantum.errorcorrection.logicalregister>`= Qubit[]`: Denota que um registo de qubits deve ser interpretado como o bloco de código de um código de correção de erros.
- <xref:microsoft.quantum.errorcorrection.syndrome>`= Result[]`: Denota que uma série de resultados de medição deve ser interpretada como a síndrome medida num bloco de código.
- <xref:microsoft.quantum.errorcorrection.recoveryfn>`= (Syndrome -> Pauli[])`: Denota que uma função *clássica* deve ser usada para interpretar uma síndrome e devolver uma correção que deve ser aplicada.
- <xref:microsoft.quantum.errorcorrection.encodeop>`= ((Qubit[], Qubit[]) => LogicalRegister)`: Denota que uma operação requer qubits que representam dados juntamente com novos qubits de ancilla, a fim de produzir um bloco de código de um código de correção de erros.
- <xref:microsoft.quantum.errorcorrection.decodeop>`= (LogicalRegister => (Qubit[], Qubit[]))`: Denota que uma operação decompõe um bloco de código de um código de correção de erros nos qubits de dados e nos qubits de ancilla utilizados para representar informações de síndrome.
- <xref:microsoft.quantum.errorcorrection.syndromemeasop>`= (LogicalRegister => Syndrome)`: Denota uma operação que deve ser utilizada para extrair informações de síndrome de um bloco de código, sem perturbar o estado protegido pelo código.

Finalmente, o cânone fornece o <xref:microsoft.quantum.errorcorrection.qecc> tipo de recolha dos outros tipos necessários para definir um código de correção de erros quânticos. Associado a cada código quântico estabilizador está o comprimento do código $n$, o número $k$ de qubits lógicos, e a distância mínima $d$, muitas vezes convenientemente agrupados na notação ⟦$n$, $k$, $d$⟧. Por exemplo, a <xref:microsoft.quantum.errorcorrection.bitflipcode> função define o código flip ⟦3, 1, 1⟧ bit:

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

Note que o `QECC` tipo *não* inclui uma função de recuperação.
Isto permite-nos alterar a função de recuperação que é utilizada na correção de erros sem alterar a definição do próprio código; esta capacidade é particularmente útil ao incorporar feedback das medições de caracterização no modelo assumido pela recuperação.

Uma vez que um código é definido desta forma, podemos usar a <xref:microsoft.quantum.errorcorrection.recover> operação para recuperar de erros:

```qsharp
let code = BitFlipCode();
let fn = BitFlipRecoveryFn();
let X0 = ApplyPauli([PauliX, PauliI, PauliI], _);
using (scratch = Qubit[nScratch]) {
    let logicalRegister = encode(data, scratch);
    // Cause an error.
    X0(logicalRegister);
    Recover(code, fn, logicalRegister);
    let (decodedData, decodedScratch) = decode(logicalRegister);
    ApplyToEach(Reset, decodedScratch);
}
```

Exploramos isto mais detalhadamente na amostra de [código bit flip.](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code)

Além do código bit-flip, o Q# cânone é fornecido com implementações do [código perfeito de cinco qubits](https://arxiv.org/abs/quant-ph/9602019), e o código de sete [qubits](https://arxiv.org/abs/quant-ph/9705052), ambos podem corrigir um erro arbitar de um único qubit.
