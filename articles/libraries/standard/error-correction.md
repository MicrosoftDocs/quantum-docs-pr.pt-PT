---
title: Correção de erros nas bibliotecas padrão Q#
description: Aprenda a usar códigos de correção de erros nos seus programas Q# enquanto protege o estado dos qubits.
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 514fe68f603b9a3a0b4607390719b08a43fe4967
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907771"
---
# <a name="error-correction"></a>Correção de Erros #

## <a name="introduction"></a>Introdução ##

Na computação clássica, se alguém quer proteger um pouco contra erros, muitas vezes pode ser suficiente para representar esse bit por uma *parte lógica* repetindo a bit de dados.
Por exemplo, deixe $\overline{0} = 000$ seja a codificação da bit de dados 0, onde usamos a linha acima da etiqueta 0 para indicar que se trata de uma codificação de um pouco no estado 0.
Se também deixarmos $\overline{1} = 111$, então temos um simples código de repetição que protege contra qualquer erro de viragem de um bit.
Isto é, se algum dos três pedaços for virado, então podemos recuperar o estado da parte lógica, obtendo uma votação por maioria.
Embora a correção de erros clássicas seja um assunto muito mais rico que este exemplo em particular (recomendamos [a introdução de Lint à teoria da codificação),](https://www.springer.com/us/book/9783540641339)o código de repetição acima já aponta para um possível problema na proteção da informação quântica.
Ou seja, o [teorema](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) de não clonagem implica que, se medirmos cada qubit individual e fizermos uma votação maioritária por analogia ao código clássico acima, perdemos a informação exata que estamos a tentar proteger.

Na configuração quântica, veremos que a medição é problemática. Ainda podemos implementar a codificação acima.
É útil fazê-lo para ver como podemos generalizar a correção de erros ao caso quântico.
Assim, deixe $\ket{\overline{0}} = \ket{000} = \ket{0} \otimes \ket{0} \otimes \ket{0}$, e deixe $\ket{\overline{1}} = \ket{111}$.
Então, por linearidade, definimos o nosso código de repetição para todos os inputs; por exemplo, $\ket{\overline{+}} = (\ket{\overline{0}} + \ket{\overline{1}}) / \sqrt{2} = (\ket{000} + \ket{111}) / \sqrt{2}$.
Em particular, deixar um erro de viragem $X_1$ agir no qubit médio, vemos que a correção necessária em ambos os ramos é precisamente $X_1$: $$ \start{align} X_1 \ket{\overline{+}} & = \frac{1}{\sqrt{2}} \left, X_1{000} + X_1 \ket{111} \right) \\\\ & = \frac{1}{\sqrt{2}} \ket{010} + \ + \{101}
\end{align} $$

Para ver como podemos identificar que este é o caso sem medir o estado que estamos a tentar proteger, é útil escrever o que cada erro de flip bit diferente faz aos nossos estados lógicos:

| Erro $E$ | $E\ket{\overline{0}}$ | $E\ket{\overline{1}}$ |
| --- | --- | --- |
| $\boldone$ | $\ket{000}$ | $\ket{111}$ |
| $X_0$ | $\ket{100}$ | $\ket{011}$ |
| $X_1$ | $\ket{010}$ | $\ket{101}$ |
| $X_2$ | $\ket{001}$ | $\ket{110}$ |

Para proteger o estado que estamos a codificar, precisamos de ser capazes de distinguir os três erros uns dos outros e da identidade $\boldone$ sem distinguir entre $\ket{\overline{0}$$ e $\ket{\overline{1}}$.
Por exemplo, se medirmos $Z_0$, obtemos um resultado diferente para $\ket{\overline{0}}$ e $\ket{\overline{1}}$ no caso sem erros, de modo que colapsa o estado codificado.
Por outro lado, considere medir $Z_0 Z_1$, a paridade dos dois primeiros bits em cada estado de base computacional.
Recorde-se que cada medição de um operador Pauli verifica a que eigenvalue o estado que está a ser medido corresponde, por isso, para cada estado $\ket{\psi}$ na tabela acima, podemos calcular $Z_0 Z_1 \ket{\psi}$ para ver se obtemos $\pm\ket{\psi}$.
Note que $Z_0 Z_1 \ket{000} = \ket{000}$ e que $Z_0 Z_1 \ket{111} = \ket{111}$, de modo que concluímos que esta medida faz a mesma coisa a ambos os estados codificados.
Por outro lado, $Z_0 Z_1 \ket{100} = - \ket{100}$ e $Z_0 Z_1 \ket{011} = -\ket{011}$, pelo que o resultado da medição $Z_0 Z_1$ revela informações úteis sobre o erro ocorrido.

Para enfatizar isto, repetimos a tabela acima, mas adicionamos os resultados de medir $Z_0 Z_1$ e $Z_1 Z_2$ em cada linha.
Denotamos os resultados de cada medição pelo sinal do eigenvalue que é observado, seja $+$ ou $-$, correspondente sig `Result` valores de `Zero` e `One`, respectivamente.

| Erro $E$ | $E\ket{\overline{0}}$ | $E\ket{\overline{1}}$ | Resultado de $Z_0 Z_1$ | Resultado de $Z_1 Z_2$ |
| --- | --- | --- | --- | --- |
| $\boldone$ | $\ket{000}$ | $\ket{111}$ | $+$ | $+$ |
| $X_0$ | $\ket{100}$ | $\ket{011}$ | $-$ | $+$ |
| $X_1$ | $\ket{010}$ | $\ket{101}$ | $-$ | $-$ |
| $X_2$ | $\ket{001}$ | $\ket{110}$ | $+$ | $-$ |

Assim, os resultados das duas medições determinam exclusivamente qual o erro de flip bit-flip ocorreu, mas sem revelar qualquer informação sobre o estado que codificamos.
Chamamos a estes resultados uma *síndrome*, e remetemos para o processo de mapear uma síndrome de volta ao erro que a causou como *recuperação*.
Em particular, salientamos que a recuperação é um procedimento de inferência *clássica* que toma como sua entrada a síndrome que ocorreu, e devolve uma receita para como corrigir quaisquer erros que possam ter ocorrido.

> [!NOTE]
> O código de lançamento de bit-flip acima só pode corrigir contra erros de flip simples; isto é, uma operação `X` agindo num único qubit.
> Aplicar `X` a mais de um qubit irá mapear $\ket{\overline{0}}$ para $\ket{\overline{1}}$ após a recuperação.
> Da mesma forma, a aplicação de uma operação de lançamento de fase `Z` irá mapear $\ket{\overline{1}}$ para $-\ket{\overline{1}}$, e, portanto, irá mapear $\ket{\overline{+}}$ para $\ket{\overline{-}}$.
> De uma forma mais geral, podem ser criados códigos para lidar com um maior número de erros e lidar com erros $Z$, bem como erros $X$.

A perceção de que podemos descrever medições na correção de erros quânticos que atuam da mesma forma em todos os estados de código, é a essência do *formalismo estabilizador.*
O cânone Q# fornece um quadro para descrever a codificação e descodificação dos códigos estabilizadores, e para descrever como se recupera de erros.
Nesta secção, descrevemos esta estrutura e a sua aplicação a alguns códigos simples de correção de erros quânticos.

> [!TIP]
> Uma introdução completa ao formalismo estabilizador está fora do âmbito desta secção.
> Referimos leitores interessados em aprender mais ao [Gottesman 2009.](https://arxiv.org/abs/0904.2557)

## <a name="representing-error-correcting-codes-in-q"></a>Representando códigos de correção de erros em Q # ##

Para ajudar a especificar códigos de correção de erros, o cânocon Q# fornece vários tipos definidos pelo utilizador:

- <xref:microsoft.quantum.errorcorrection.logicalregister> `= Qubit[]`: Denota que um registo de qubits deve ser interpretado como o bloco de código de um código de correção de erros.
- <xref:microsoft.quantum.errorcorrection.syndrome> `= Result[]`: Denota que um conjunto de resultados de medição deve ser interpretado como a síndrome medida num bloco de código.
- <xref:microsoft.quantum.errorcorrection.recoveryfn> `= (Syndrome -> Pauli[])`: Denota que deve ser utilizada uma função *clássica* para interpretar uma síndrome e devolver uma correção que deve ser aplicada.
- <xref:microsoft.quantum.errorcorrection.encodeop> `= ((Qubit[], Qubit[]) => LogicalRegister)`: Denota que uma operação requer qubits que representam dados juntamente com novos qubits de oscilação para produzir um bloco de código de um código de correção de erros.
- <xref:microsoft.quantum.errorcorrection.decodeop> `= (LogicalRegister => (Qubit[], Qubit[]))`: Denota do que uma operação decompõe um bloco de código de um código de erro corrigindo código nos qubits de dados e nos qubits de oscilação utilizados para representar informações sobre síndrome.
- <xref:microsoft.quantum.errorcorrection.syndromemeasop> `= (LogicalRegister => Syndrome)`: Denota uma operação que deve ser utilizada para extrair informações de síndrome de um bloco de código, sem perturbar o Estado protegido pelo código.

Finalmente, o cânon fornece o <xref:microsoft.quantum.errorcorrection.qecc> tipo de recolha dos outros tipos necessários para definir um código de correção de erros quânticos. Associado a cada código quântico estabilizador está o comprimento de código $n$, o número $k$ de qubits lógicos, e a distância mínima $d$, muitas vezes convenientemente agruparados na notação de $n$, $k$, $d$. Por exemplo, a função <xref:microsoft.quantum.errorcorrection.bitflipcode> define o código de lançamento de 3, 1, 10 bits:

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

Note que o tipo `QECC` *não* inclui uma função de recuperação.
Isto permite-nos alterar a função de recuperação que é usada na correção de erros sem alterar a definição do código em si; esta capacidade é particularmente útil ao incorporar feedback a partir de medições de caracterização no modelo assumido pela recuperação.

Uma vez definido um código desta forma, podemos usar a operação <xref:microsoft.quantum.errorcorrection.recover> para recuperar de erros:

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

Exploramos isto mais detalhadamente na amostra de [código flip bit](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code).

Além do código bit-flip, o cânão Q# é fornecido com implementações do [código perfeito de cinco qubits](https://arxiv.org/abs/quant-ph/9602019), e o código de sete [qubits](https://arxiv.org/abs/quant-ph/9705052), ambos os quais podem corrigir um erro de um único qubit arbit.
