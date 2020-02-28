---
title: Técnicas Q# - Juntar tudo
description: Caminhe por um programa básico de Q# que demonstre teletransporte quântico.
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 6c988f77ef6e433945dbf21dfb41204c74bdda3e
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906836"
---
# <a name="putting-it-all-together-teleportation"></a>Colocando tudo junto: Teleportation #
Voltemos ao exemplo do circuito de teletransporte definido em [Circuitos Quânticos.](xref:microsoft.quantum.concepts.circuits) Vamos usar isto para ilustrar os conceitos que aprendemos até agora. Uma explicação da teleportação quântica é fornecida abaixo para aqueles que não estão familiarizados com a teoria, seguido de uma passagem pela implementação do código em Q#. 

## <a name="quantum-teleportation-theory"></a>Teleportação Quântica: Teoria
A teleportação quântica é uma técnica para o envio de um estado quântico desconhecido (a que nos referiremos como a '__mensagem__') de um qubit em um local para um qubit em outro local (vamos referir-nos a estes qubits como '__aqui__' e '__lá__', respectivamente). Podemos representar a nossa __mensagem__ como um vetor usando a notação de Dirac: 

$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$

O estado do qubit da __mensagem__ é desconhecido para nós, uma vez que não sabemos os valores de $\alpha$ e $\beta$.

### <a name="step-1-create-an-entangled-state"></a>Passo 1: Criar um estado emaranhado
Para enviar a __mensagem,__ precisamos que o qubit __aqui__ seja enredado com o qubit __lá__. Isto é conseguido aplicando um portão Hadamard, seguido por um portão CNOT. Vamos ver as contas por detrás destas operações do portal.

Começaremos com os qubits __aqui__ e __ali,__ ambos no estado de $\ket{0}$. Depois de envolver estes qubits, estão no estado:

$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$

### <a name="step-2-send-the-message"></a>Passo 2: Enviar a mensagem
Para enviar a __mensagem__ aplicamos primeiro um portão CNOT com o qubit da __mensagem__ e __aqui__ qubit como entradas (sendo o qubit da __mensagem__ o controlo e o qubit __aqui__ sendo o qubit alvo, neste caso). Este estado de entrada pode ser escrito:

$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$

Isto expande-se para:

$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sq{2}rt }}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{{{2}{\{\ket{100} + \frac{\beta}{\sqrt{2}\&{111} ket

Como lembrete, o portão CNOT inverte o qubit do alvo quando o qubit de controlo é 1. Assim, por exemplo, uma entrada de $\ket{000}$ não resultará em nenhuma alteração, uma vez que o primeiro qubit (o controlo) é 0. No entanto, tome um caso em que o primeiro qubit é 1 - por exemplo, uma entrada de $\ket{100}$. Neste caso, a saída é de $\ket{110}$, uma vez que o segundo qubit (o alvo) é virado pelo portão CNOT.

Vamos agora considerar a nossa saída uma vez que o portão CNOT tenha agido na nossa entrada acima. O resultado é:

$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha{}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}\\ket{101} $$

O próximo passo para enviar a __mensagem__ é aplicar um portão Hadamard ao qubit da __mensagem__ (que é o primeiro qubit de cada termo). 

Como lembrete, o portão hadamard faz o seguinte:

Input | Saída
---------------------------| ---------------------------------------------------------------
$\ket{0}$  | $\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$
$\ket{1}$  | $\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$

Se aplicarmos o portão Hadamard ao primeiro qubit de cada termo da nossa saída acima, obtemos o seguinte resultado:

$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})\ket{10} + \frac{{{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})\ket{01} $-

Note que cada termo tem dois fatores de{1}de $\frac {\sqrt{2}fatores de $$. Podemos multiplicá-los dando o seguinte resultado:

$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{01}{1}

O fator{1}de $\frac {2}$ é comum a cada termo para que possamos agora levá-lo para fora dos suportes:

$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $go$

Podemos então multiplicar os suportes para cada termo que dá:

$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $big

### <a name="step-3-measure-the-result"></a>Passo 3: Medir o resultado

Devido a __aqui__ e __ali__ estarem emaranhados, qualquer medição __aqui__ afetará o estado de __lá.__ Se medirmos o primeiro e o segundo qubit __(mensagem__ e __aqui)__ podemos saber em que estado __existe,__ devido a esta propriedade de emaranhado. 

* Se medirmos e conseguirmos um resultado 00, a superposição entra em colapso, deixando apenas termos consistentes com este resultado. É $\alfa\ket{000} +\beta\ket{001}$. Isto pode ser refactored para $\ket{00}(\alpha\ket{0} +\beta\ket{1})$. Portanto, se medirmos o primeiro e o segundo qubit para ser 00, sabemos que o terceiro qubit, __lá, está__no estado $(\alpha\ket{0} +\beta\ket{1})$.
* Se medirmos e conseguirmos um resultado 01, a superposição entra em colapso, deixando apenas termos consistentes com este resultado. É $\alfa\ket{011} +\beta\ket{010}$. Isto pode ser refactored para $\ket{01}(\alpha\ket{1} +\beta\ket{0})$. Portanto, se medirmos o primeiro e o segundo qubit para ser 01, sabemos que o terceiro qubit, __lá, está__no estado $(\alpha\ket{1} +\beta\ket{0})$.
* Se medirmos e conseguirmos um resultado 10, a superposição entra em colapso, deixando apenas termos consistentes com este resultado. É $\alfa\ket{100} -\beta\ket{101}$. Isto pode ser refactored para $\ket{10}(\alpha\ket{0} -\beta\ket{1})$. Portanto, se medirmos o primeiro e o segundo qubit para ser 10, sabemos que o terceiro qubit, __lá, está__no estado $(\alpha\ket{0} -\beta\ket{1})$.
* Se medirmos e conseguirmos um resultado 11, a superposição entra em colapso, deixando apenas termos consistentes com este resultado. É $\alfa\ket{111} -\beta\ket{110}$. Isto pode ser refactored para $\ket{11}(\alpha\ket{1} -\beta\ket{0})$. Portanto, se medirmos o primeiro e o segundo qubit para ser 11, sabemos que o terceiro qubit, __lá, está__no estado $(\alpha\ket{1} -\beta\ket{0})$.

### <a name="step-4-interpret-the-result"></a>Passo 4: Interpretar o resultado

Como lembrete, a __mensagem__ original que queríamos enviar era:

$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$

Precisamos de colocar o qubit __lá__ neste estado, para que o estado recebido seja o pretendido. 

* Se medimos e obtivemos um resultado de 00, então o terceiro qubit, __lá, está__no estado $(\alpha\ket{0} +\beta\ket{1})$. Como esta é a __mensagem__pretendida, não é necessária qualquer alteração.
* Se medimos e obtivemos um resultado de 01, então o terceiro qubit, __lá, está__no estado $(\alpha\ket{1} +\beta\ket{0})$. Isto difere da __mensagem__pretendida, no entanto, aplicar um portão NOT dá-nos o estado desejado $(\alpha\ket{0} +\beta\ket{1})$.
* Se medimos e obtivemos um resultado de 10, então o terceiro qubit, __lá, está__no estado $(\alpha\ket{0} -\beta\ket{1})$. Isto difere da __mensagem__pretendida, no entanto, aplicar um portão Z dá-nos o estado desejado $(\alpha\ket{0} +\beta\ket{1})$.
* Se medimos e obtivemos um resultado de 11, então o terceiro qubit, __lá, está__no estado $(\alpha\ket{1} -\beta\ket{0})$. Isto difere da __mensagem__pretendida , no entanto, aplicar um portão NOT seguido por um portão Z dá-nos o estado desejado $(\alpha\ket{0} +\beta\ket{1})$.

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
Quando executamos teletransporte, temos de saber a __mensagem__ que queremos enviar, e para onde queremos enviá-la __(lá).__ Por esta razão, começamos por definir uma nova operação teleport que é dada a dois qubits como argumentos, `msg` e `there`:

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

Precisamos também de atribuir um `here` qubit que conseguimos com um bloco `using`:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>Passo 1: Criar um estado emaranhado
Podemos então criar o par emaranhado entre `here` e `there` utilizando as operações @"microsoft.quantum.intrinsic.h" e @"microsoft.quantum.intrinsic.cnot":

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

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>Passo 3 e 4: Medir e interpretar o resultado
Finalmente, utilizamos @"microsoft.quantum.intrinsic.m" para efetuar as medições e realizar as operações necessárias para obter o estado desejado, conforme denotado por declarações `if`:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

Isto termina a definição do nosso operador de teletransporte, para que possamos desalocar `here`, acabar com o corpo e terminar a operação.

```qsharp
    }
}
```
