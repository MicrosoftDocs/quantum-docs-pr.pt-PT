---
title: Técnicas Q# - Juntar tudo
description: Caminhe por um programa básico de Q# que demonstre teletransporte quântico.
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030570"
---
# <a name="putting-it-all-together-teleportation"></a>Colocando tudo junto: Teleportation #
Voltemos ao exemplo do circuito de teletransporte definido em [Circuitos Quânticos.](xref:microsoft.quantum.concepts.circuits) Vamos usar isto para ilustrar os conceitos que aprendemos até agora. Uma explicação da teleportação quântica é fornecida abaixo para aqueles que não estão familiarizados com a teoria, seguido de uma passagem pela implementação do código em Q#. 

## <a name="quantum-teleportation-theory"></a>Teleportação Quântica: Teoria
A teleportação quântica é uma técnica para o envio de um estado quântico desconhecido (a que nos referiremos como a '__mensagem__') de um qubit em um local para um qubit em outro local (vamos referir-nos a estes qubits como '__aqui__' e '__lá__', respectivamente). Podemos representar a nossa __mensagem__ como um vetor usando a notação de Dirac: 

$$ \ket{\psi} = \alpha\ket{0} +{1} \beta\ket $$

O estado do qubit da __mensagem__ é desconhecido para nós, uma vez que não sabemos os valores de $\alpha$ e $\beta$.

### <a name="step-1-create-an-entangled-state"></a>Passo 1: Criar um estado emaranhado
Para enviar a __mensagem,__ precisamos que o qubit __aqui__ seja enredado com o qubit __lá__. Isto é conseguido aplicando um portão Hadamard, seguido por um portão CNOT. Vamos ver as contas por detrás destas operações do portal.

Começaremos com os qubits __aqui__ e __ali,__ ambos no estado de $\ket$.{0} Depois de envolver estes qubits, estão no estado:

$$ \ket{\phi^+} ={1}\frac{2}{\sqrt{00} }(\ket + \ket{11}) $$

### <a name="step-2-send-the-message"></a>Passo 2: Enviar a mensagem
Para enviar a __mensagem__ aplicamos primeiro um portão CNOT com o qubit da __mensagem__ e __aqui__ qubit como entradas (sendo o qubit da __mensagem__ o controlo e o qubit __aqui__ sendo o qubit alvo, neste caso). Este estado de entrada pode ser escrito:

$$ \ket{\psi}\ket{\phi^+}{0} = (\alpha\ket +{1}\beta\ket )(\frac{1}{\sqrt{11}{2}}(\ket{00} + \ket)) $$

Isto expande-se para:

$${2}\ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{000} }\ket + \frac{\alpha}{{sqrt{2}}\ket \ \cet{2}{100} {2}{111} {011} {{\beta}{\sqrt }\ket + \frac{\beta}{{{{\sqrt

Como lembrete, o portão CNOT inverte o qubit do alvo quando o qubit de controlo é 1. Assim, por exemplo, uma entrada{000}de $\ket $ não resultará em nenhuma alteração, uma vez que o primeiro qubit (o controlo) é 0. No entanto, tome um caso em que o primeiro qubit é 1 - por exemplo, uma entrada de $\ket{100}$. Neste caso, a saída é{110}$\ket $ como o segundo qubit (o alvo) é virado pelo portão CNOT.

Vamos agora considerar a nossa saída uma vez que o portão CNOT tenha agido na nossa entrada acima. O resultado é:

{2}$$ \frac{\alpha}{\sqrt }\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{{{{{{{\sqrt{2}}\ket{101} $$

O próximo passo para enviar a __mensagem__ é aplicar um portão Hadamard ao qubit da __mensagem__ (que é o primeiro qubit de cada termo). 

Como lembrete, o portão hadamard faz o seguinte:

Input | Saída
---------------------------| ---------------------------------------------------------------
$\ket{0}$  | $\frac{1}{\sqrt{2}}(\ket{0} {1}+ \ket )$
$\ket{1}$  | $\frac{1}{\sqrt{2}}(\ket{0} {1}- \ket )$

Se aplicarmos o portão Hadamard ao primeiro qubit de cada termo da nossa saída acima, obtemos o seguinte resultado:

{2}$$ \frac{\alfa}{\sqrt }(\frac{1}{\sqrt{2}{0} }(\ket +{00} \ket))\ket{2}{1}{2}{0} {1}{11} {2}{1}{2}{0} {1}{10} {2}{1}{1}+ \frac{\alpha}{\sqrt (\frac {\sqrt }(\ket + \ket)\ket + \frac{\beta}{\sqrt }(\frac {\sqrt }(\ket - \ket))\ket + \frac{\beta}{\sqrt }(\frac {\sqrt{2}}(\ket{0} - \ket)\ket{1}{01} $$

Note que cada termo tem{1}dois fatores{2}$\frac {\sqrt }$ . Podemos multiplicá-los dando o seguinte resultado:

$${2}\frac{\alpha}{0} (\ket{1}+ \ket )\ket{00} +{2}\frac{\alpha} (\ket{0} + \ket{1}\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$

O fator{1}{2}$\frac $ é comum a cada termo para que possamos agora levá-lo para fora dos suportes:

$${1}{2}\frac{0} \big[\alpha(\ket{1}+ \ket )\ket{00} {0} + \alpha(\ket + \ket{1})\ket{11} + \beta(\ket{0} -{1}\ket )\ket{10} + \beta(\ket{0} - \ket{1})\ket \ket{01}\big] $$

Podemos então multiplicar os suportes para cada termo que dá:

$${1}{2}\frac \big[\alfa\ket{000} +{100} \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} -{110} \beta\ket{001} + \beta\ket + \beta\ket - \beta\ket - \beta\ket{101}\big] $$

### <a name="step-3-measure-the-result"></a>Passo 3: Medir o resultado

Devido a __aqui__ e __ali__ estarem emaranhados, qualquer medição __aqui__ afetará o estado de __lá.__ Se medirmos o primeiro e o segundo qubit __(mensagem__ e __aqui)__ podemos saber em que estado __existe,__ devido a esta propriedade de emaranhado. 

* Se medirmos e conseguirmos um resultado 00, a superposição entra em colapso, deixando apenas termos consistentes com este resultado. São $\alpha\ket{000} +\beta\ket{001}$. Isto pode ser refactored{00}para $\ket{0} (\alpha\ket +\beta\ket{1})$. Portanto, se medirmos o primeiro e o segundo qubit para ser 00, sabemos que o terceiro{0} qubit,{1} __lá,__ está no estado $(\alpha\ket +\beta\ket )$.
* Se medirmos e conseguirmos um resultado 01, a superposição entra em colapso, deixando apenas termos consistentes com este resultado. São $\alpha\ket{011} +\beta\ket{010}$. Isto pode ser refactored{01}para $\ket{1} (\alpha\ket +\beta\ket{0})$. Portanto, se medirmos o primeiro e o segundo qubit para ser 01, sabemos que o terceiro{1} qubit,{0} __lá,__ está no estado $(\alpha\ket +\beta\ket )$.
* Se medirmos e conseguirmos um resultado 10, a superposição entra em colapso, deixando apenas termos consistentes com este resultado. São $\alfa\ket{100} -\beta\ket{101}$. Isto pode ser refactored{10}para $\ket{0} (\alpha\ket -\beta\ket{1})$. Portanto, se medirmos o primeiro e o segundo qubit para ser 10, sabemos que o terceiro{0} qubit,{1} __lá,__ está no estado $(\alpha\ket -\beta\ket )$.
* Se medirmos e conseguirmos um resultado 11, a superposição entra em colapso, deixando apenas termos consistentes com este resultado. São $\alfa\ket{111} -\beta\ket{110}$. Isto pode ser refactored{11}para $\ket{1} (\alpha\ket -\beta\ket{0})$. Portanto, se medirmos o primeiro e o segundo qubit para ser 11, sabemos que o terceiro{1} qubit,{0} __lá,__ está no estado $(\alpha\ket -\beta\ket )$.

### <a name="step-4-interpret-the-result"></a>Passo 4: Interpretar o resultado

Como lembrete, a __mensagem__ original que queríamos enviar era:

$$ \ket{\psi} = \alpha\ket{0} +{1} \beta\ket $$

Precisamos de colocar o qubit __lá__ neste estado, para que o estado recebido seja o pretendido. 

* Se medimos e obtivemos um resultado de 00, então o terceiro qubit, __lá, está__no estado $(\alfa\ket{0} +\beta\ket{1})$. Como esta é a __mensagem__pretendida, não é necessária qualquer alteração.
* Se medimos e obtivemos um resultado de 01, então o terceiro qubit, __lá, está__no estado $(\alfa\ket{1} +\beta\ket{0})$. Isto difere da __mensagem__pretendida, no entanto, aplicar um portão NOT{0} dá-nos{1}o estado desejado $(\alpha\ket +\beta\ket )$.
* Se medimos e obtivemos um resultado de 10, então o terceiro qubit, __lá, está__no estado $(\alpha\ket{0} -\beta\ket{1})$. Isto difere da __mensagem__pretendida, no entanto, aplicar um portão Z{0} dá-nos{1}o estado desejado $(\alpha\ket +\beta\ket )$.
* Se medimos e obtivemos um resultado de 11, então o terceiro qubit, __lá, está__no estado $(\alpha\ket{1} -\beta\ket{0})$. Isto difere da __mensagem__pretendida, no entanto, aplicar um portão NOT seguido por{0} um portão Z{1}dá-nos o estado desejado $(\alpha\ket +\beta\ket )$.

Resumindo, se medirmos e o primeiro qubit for 1, é aplicado um portão Z. Se medirmos e o segundo qubit for 1, aplica-se um portão NOT.

### <a name="summary"></a>Resumo
Abaixo é apresentado um circuito quântico de livro de texto que implementa a teleportação. Movendo-se da esquerda para a direita, pode ver:
- Passo 1: Entrelaçar __aqui__ e __ali__ aplicando um portão Hadamard e portão CNOT.
- Passo 2: Envio da __mensagem__ utilizando um portão CNOT e um portão Hadamard.
- Passo 3: Medição do primeiro e segundo qubits, __mensagem__ e __aqui__.
- Passo 4: Aplicação de um portão NOT ou de um portão Z, dependendo do resultado da medição no passo 3.

![«Teleport (msg: Qubit, ali: Qubit) : Unidade»](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>Teletransporte Quântico: Código

Temos o nosso circuito de teletransporte quântico:

![«Teleport (msg: Qubit, ali: Qubit) : Unidade»](~/media/teleportation.svg)

Podemos agora traduzir cada um dos passos deste circuito quântico em Q#.

### <a name="step-0-definition"></a>Passo 0: Definição
Quando executamos teletransporte, temos de saber a __mensagem__ que queremos enviar, e para onde queremos enviá-la __(lá).__ Por esta razão, começamos por definir uma nova operação teleport que `msg` `there`é dada a dois qubits como argumentos, e:

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

Precisamos também de atribuir `here` um qubit `using` que conseguimos com um bloco:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>Passo 1: Criar um estado emaranhado
Podemos então criar o `here` `there` par emaranhado @"microsoft.quantum.intrinsic.h" @"microsoft.quantum.intrinsic.cnot" entre e usando as e operações:

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>Passo 2: Enviar a mensagem
Em seguida, usamos o próximo nome de $\operador{CNOT}$ e $H$ portões para mover o qubit da nossa mensagem:

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>Passo 3 & 4: Medir e interpretar o resultado
Finalmente, usamos @"microsoft.quantum.intrinsic.m" para realizar as medições e realizar as operações necessárias para `if` obter o estado desejado, conforme denotado por declarações:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a>Passo 5: Reiniciar o registo qubit

No final de cada operação q# precisamos deixar os qubits no estado $\ket{0}$. Podemos @"microsoft.quantum.intrinsic.reset" usar para reiniciar todos os qubits para o estado zero e isso terminará a nossa operação.

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


