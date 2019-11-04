---
title: 'P # bibliotecas padrão-correção de erros | Microsoft Docs'
description: 'P # bibliotecas padrão-correção de erro'
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 5aac40686ba9b45a51e0274a1828f2ff7cce6fc3
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184445"
---
# <a name="error-correction"></a>Correção de erro #

## <a name="introduction"></a>Introdução ##

Na computação clássica, se alguém quiser proteger um pouco contra erros, muitas vezes poderá representar esse bit por um *bit lógico* repetindo o bit de dados.
Por exemplo, deixe que $ \overline{0} = $0 seja a codificação do bit de dados 0, em que usamos uma linha acima do rótulo 0 para indicar que é uma codificação de um bit no estado 0.
Se, de forma semelhante, permitimos $ \overline{1} = $111, temos um código de repetição simples que protege contra um erro de inversão de um bit.
Ou seja, se qualquer um dos três bits for invertido, podemos recuperar o estado do bit lógico assumindo um voto principal.
Embora a correção de erro clássica seja um assunto muito mais rico que esse exemplo específico (Recomendamos [a introdução de fiapos à teoria de codificação](https://www.springer.com/us/book/9783540641339)), o código de repetição acima já aponta para um possível problema na proteção de informações da Quantum.
Ou seja, o [teorema no-Cloning](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) implica que, se medirmos cada qubit individual e pegarmos um voto de maioria por analogia com o código clássico acima, perdemos as informações precisas que estamos tentando proteger.

Na configuração Quantum, veremos que a medida é problemática. Ainda podemos implementar a codificação acima.
É útil fazer isso para ver como é possível generalizar a correção de erro para o caso Quantum.
Portanto, permita que $ \ket{\overline{0}} = \ket{000} = \ket{0} \otimes \ket{0} \otimes \ket{0}$ e permita que $ \ket{\overline{1}} = \ket{111}$.
Em seguida, por linearidade, definimos nosso código de repetição para todas as entradas; por exemplo, $ \ket{\overline{+}} = (\ket{\overline{0}} + \ket{\overline{1}})/\sqrt{2} = (\ket{000} + \ket{111})/\sqrt{2}$.
Em particular, deixando um erro de inversão $X o _1 $ Act no meio qubit, vemos que a correção necessária em ambas as ramificações é precisamente $X _1 $: $ $ \begin{align} X_1 \ket{\overline{+}} & = \frac{1}{\sqrt{2}} \left (X_1 \ket{000} + X_1 \ket @no__ t_3_ \right) \\\\ & = \frac{1}{\sqrt{2}} \left (\ket{010} + \ket{101} \right).
\end{align} $ $

Para ver como podemos identificar que esse é o caso sem medir o estado que estamos tentando proteger, é útil anotar o que significa cada erro de inversão de bit diferente para nossos Estados lógicos:

| Erro $E $ | $E \ket{\overline{0}} $ | $E \ket{\overline{1}} $ |
| --- | --- | --- |
| US $ \boldone $ | $ \ket{000}$ | $ \ket{111}$ |
| $X _0 $ | $ \ket{100}$ | $ \ket{011}$ |
| $X _1 $ | $ \ket{010}$ | $ \ket{101}$ |
| $X _2 $ | $ \ket{001}$ | $ \ket{110}$ |

Para proteger o estado que estamos codificando, precisamos ser capaz de distinguir os três erros uns dos outros e da identidade $ \boldone $ sem distinção entre $ \ket{\overline{0}} $ e $ \ket{\overline{1}} $.
Por exemplo, se medirmos $Z _0 $, obteremos um resultado diferente para $ \ket{\overline{0}} $ e $ \ket{\overline{1}} $ no caso no-Error, para que recolha o estado codificado.
Por outro lado, considere medir $Z _0 Z_1 $, a paridade dos dois primeiros bits em cada Estado de base computacional.
Lembre-se de que cada medida de um operador Pauli verifica a qual eigenvalue o estado que está sendo medido corresponde a, portanto, para cada Estado $ \ket{\psi} $ na tabela acima, podemos calcular $Z _0 Z_1 \ket{\psi} $ para ver se obtemos $ \pm\ket{\psi} $.
Observe que $Z _0 Z_1 \ket{000} = \ket{000}$ e $Z _0 Z_1 \ket{111} = \ket{111}$, para que possamos concluir que essa medida faz a mesma coisa para ambos os Estados codificados.
Por outro lado, $Z _0 Z_1 \ket{100} =-\ket{100}$ e $Z _0 Z_1 \ket{011} =-\ket{011}$, portanto, o resultado da medição $Z _0 Z_1 $ revela informações úteis sobre o erro ocorrido.

Para enfatizar isso, repetimos a tabela acima, mas adiciono os resultados da medição $Z _0 Z_1 $ e $Z _1 Z_2 $ em cada linha.
Nós denotamos os resultados de cada medição pelo sinal do eigenvalue observado, $ + $ ou $-$, que corresponde aos valores de `Result` Q # de `Zero` e `One`, respectivamente.

| Erro $E $ | $E \ket{\overline{0}} $ | $E \ket{\overline{1}} $ | Resultado de $Z _0 Z_1 $ | Resultado de $Z _1 Z_2 $ |
| --- | --- | --- | --- | --- |
| US $ \boldone $ | $ \ket{000}$ | $ \ket{111}$ | $+$ | $+$ |
| $X _0 $ | $ \ket{100}$ | $ \ket{011}$ | $-$ | $+$ |
| $X _1 $ | $ \ket{010}$ | $ \ket{101}$ | $-$ | $-$ |
| $X _2 $ | $ \ket{001}$ | $ \ket{110}$ | $+$ | $-$ |

Assim, os resultados das duas medições determinam exclusivamente qual erro de inversão de bit ocorreu, mas sem revelar nenhuma informação sobre o estado que codificamos.
Chamamos esses resultados de uma *síndrome*e referimos-se ao processo de mapeamento de uma síndrome de volta para o erro que o causou como *recuperação*.
Em particular, enfatizamos que a recuperação é um procedimento de inferência *clássico* que usa como entrada a síndrome que ocorreu e retorna uma receita para corrigir quaisquer erros que possam ter ocorrido.

> [!NOTE]
> O código de inversão de bits acima só pode corrigir em caso de erros de flip-bit único; ou seja, uma operação `X` atuando em um único qubit.
> A aplicação de `X` a mais de um qubit mapeará $ \ket{\overline{0}} $ para $ \ket{\overline{1}} $ após a recuperação.
> Da mesma forma, aplicar uma operação de inversão de fase `Z` mapeará $ \ket{\overline{1}} $ para $-\ket{\overline{1}} $ e, portanto, mapeará $ \ket{\overline{+}} $ para $ \ket{\overline{-}} $.
> Em geral, os códigos podem ser criados para lidar com um número maior de erros e para manipular $Z $ erros, bem como $X $ erros.

O insight que podemos descrever as medidas na correção de erro Quantum que atuam da mesma forma em todos os Estados de código, é o essense da *forma formal do estabilizador*.
O Q # Canon fornece uma estrutura para descrever a codificação e decodificação de códigos de estabilizador e para descrever como um se recupera de erros.
Nesta seção, descrevemos essa estrutura e seu aplicativo com alguns códigos de correção de erro de Quantum simples.

> [!TIP]
> Uma introdução completa ao informativo do estabilizador está além do escopo desta seção.
> Nós nos referimos aos leitores interessados em aprender mais sobre o [Gottesman 2009](https://arxiv.org/abs/0904.2557).

## <a name="representing-error-correcting-codes-in-q"></a>Representando códigos de correção de erro em Q # ##

Para ajudar a especificar códigos de correção de erro, o Q # Canon fornece vários tipos distintos definidos pelo usuário:

- <xref:microsoft.quantum.errorcorrection.logicalregister> `= Qubit[]`: indica que um registro de qubits deve ser interpretado como o bloco de código de um código de correção de erros.
- <xref:microsoft.quantum.errorcorrection.syndrome> `= Result[]`: indica que uma matriz de resultados de medidas deve ser interpretada como a síndrome medida em um bloco de código.
- <xref:microsoft.quantum.errorcorrection.recoveryfn> `= (Syndrome -> Pauli[])`: indica que uma função *clássica* deve ser usada para interpretar uma síndrome e retornar uma correção que deve ser aplicada.
- <xref:microsoft.quantum.errorcorrection.encodeop> `= ((Qubit[], Qubit[]) => LogicalRegister)`: indica que uma operação usa qubits que representa dados junto com a nova ancilla qubits para produzir um bloco de código de um código de correção de erros.
- <xref:microsoft.quantum.errorcorrection.decodeop> `= (LogicalRegister => (Qubit[], Qubit[]))`: indica que uma operação decompõe um bloco de código de um erro corrigindo o código no qubits de dados e o ancilla qubits usado para representar informações sobre a síndrome.
- <xref:microsoft.quantum.errorcorrection.syndromemeasop> `= (LogicalRegister => Syndrome)`: denota uma operação que deve ser usada para extrair informações de síndrome de um bloco de código, sem perturbar o estado protegido pelo código.

Por fim, a Canon fornece o tipo de <xref:microsoft.quantum.errorcorrection.qecc> para coletar os outros tipos necessários para definir um código de correção de erro Quantum. Associado a cada código Quantum do estabilizador é o tamanho do código $n $, o número $k $ of Logical qubits e a distância mínima $d $, geralmente agrupados em conjunto na notação ⟦ $n $, $k $, $d $ ⟧. Por exemplo, a função <xref:microsoft.quantum.errorcorrection.bitflipcode> define o código de folheio de ⟦ 3, 1, 1 ⟧ de bits:

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

Observe que o tipo de `QECC` *não inclui uma* função de recuperação.
Isso nos permite alterar a função de recuperação que é usada na correção de erros sem alterar a definição do próprio código; Essa capacidade é particularmente útil ao incorporar comentários de medidas de caracterização ao modelo assumido pela recuperação.

Depois que um código é definido dessa forma, podemos usar a operação <xref:microsoft.quantum.errorcorrection.recover> para se recuperar de erros:

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

Exploraremos isso mais detalhadamente na [amostra de código de inversão de bits](https://github.com/Microsoft/Quantum/tree/master/Samples/src/BitFlipCode).

Além do código de inversão de bits, o Q # Canon é fornecido com implementações do [código perfeito de cinco qubit](https://arxiv.org/abs/1305.08)e o [código de sete qubit](https://arxiv.org/abs/quant-ph/9705052), que pode corrigir um erro arbitrário de qubit único.
