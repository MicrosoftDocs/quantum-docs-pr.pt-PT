---
title: 'Técnicas de Q # – reunindo todas elas | Microsoft Docs'
description: 'Técnicas de Q #-reunindo tudo'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f65b3e260f98a7a90da13b62edd6cc63d200f5af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183272"
---
# <a name="putting-it-all-together-teleportation"></a>Juntando tudo: Teleportation #
Vamos retornar ao exemplo do circuito de Teleportation definido em [circuitos Quantum](xref:microsoft.quantum.concepts.circuits). Vamos usar isso para ilustrar os conceitos que aprendemos até agora. Uma explicação sobre a teleportação Quantum é fornecida abaixo para aqueles que não estão familiarizados com a teoria, seguidos por uma explicação da implementação do código em Q #. 

## <a name="quantum-teleportation-theory"></a>Portabilidade Quantum: teoria
A teleportabilidade Quantum é uma técnica para enviar um estado de Quantum desconhecido (que iremos nos referir como "__Message__") de um qubit em um local para um qubit em outro local (vamos nos referir a esses qubits como "__aqui__" e "__lá__", respectivamente). Podemos representar nossa __mensagem__ como um vetor usando a notação Dirac: 

$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $

O estado da __mensagem__ qubit é desconhecido para nós, pois não sabemos os valores de $ \alpha $ e $ \beta $.

### <a name="step-1-create-an-entangled-state"></a>Etapa 1: criar um estado de confusas
Para enviar a __mensagem__ , precisamos que o qubit __aqui__ seja confusas com o qubit __lá__. Isso é obtido com a aplicação de um portão Hadamard, seguido por um portão CNOT. Vamos examinar a matemática por trás dessas operações de portão.

Começaremos com o qubits __aqui__ e __lá__ no estado $ \ket{0}$. Depois de Entangling esses qubits, eles estão no estado:

$ $ \ket{\phi ^ +} = \frac{1}{\sqrt{2}} (\ket{00} + \ket{11}) $ $

### <a name="step-2-send-the-message"></a>Etapa 2: enviar a mensagem
Para enviar a __mensagem__ , primeiro aplicamos um portão CNOT com a __mensagem__ qubit e __aqui__ qubit como entradas (a __mensagem__ qubit sendo o controle e __aqui__ qubit sendo a qubit de destino, nesta instância). Esse estado de entrada pode ser escrito:

$ $ \ket{\psi}\ket{\phi ^ +} = (\alpha\ket{0} + \beta\ket{1}) (\frac{1}{\sqrt{2}} (\ket{00} + \ket{11})) $ $

Isso expande para:

$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} + \frac{\beta}{\sqrt{2}} \ket{111} $ $

Como lembrete, a porta CNOT inverte o qubit de destino quando o qubit de controle é 1. Por exemplo, uma entrada de $ \ket{000}$ não resultará em nenhuma alteração, pois o primeiro qubit (o controle) é 0. No entanto, faça um caso em que a primeira qubit é 1, por exemplo, uma entrada de $ \ket{100}$. Nessa instância, a saída é $ \ket{110}$, pois o segundo qubit (o destino) é invertido pelo portão CNOT.

Agora, vamos considerar nossa saída depois que a porta CNOT tiver atuado em nossa entrada acima. O resultado é:

$ $ \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $

A próxima etapa para enviar a __mensagem__ é aplicar um portão Hadamard à __mensagem__ qubit (que é a primeira qubit de cada termo). 

Como lembrete, o portão Hadamard faz o seguinte:

Input | Saída
---------------------------| ---------------------------------------------------------------
$ \ket{0}$  | $ \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) $
$ \ket{1}$  | $ \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}) $

Se aplicarmos o portão Hadamard à primeira qubit de cada termo de nossa saída acima, obteremos o seguinte resultado:

$ $ \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{00} + \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{11} + \frac{\beta}{ \sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{10} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{01} $ $

Observe que cada termo tem $2 \frac{1}{\sqrt{2}} $ fatores. Podemos multiplicar esses resultados dando o seguinte resultado:

$ $ \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{11} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{10} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{01} $ $

A{1}$ \frac {2}$ factor é comum a cada termo, portanto, agora podemos levá-lo para fora dos colchetes:

$ $ \frac{1}{2}\big [\alpha (\ket{0} + \ket{1}) \ket{00} + \alpha (\ket{0} + \ket{1}) \ket{11} + \beta (\ket{0}-\ket{1}) \ket{10} + \beta (\ket{0}-\ket{1}) \ket{01}\big] $ $

Em seguida, podemos multiplicar os colchetes para cada termo, fornecendo:

$ $ \frac{1}{2}\big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001}-\beta\ket{101}\big] $ $

### <a name="step-3-measure-the-result"></a>Etapa 3: medir o resultado

Devido a __aqui__ e __confusas__ , qualquer medida __aqui__ afetará o estado de __lá__. Se medirmos a primeira e a segunda qubit (__mensagem__ e __aqui__), podemos saber em que estado __há__ , devido a essa propriedade de Entanglement. 

* Se medirmos e obtivermos um resultado 00, a superposição recolherá, deixando apenas os termos consistentes com esse resultado. Isso é $ \alpha\ket{000} + \beta\ket{001}$. Isso pode ser refatorado para $ \ket{00}(\alpha\ket{0} + \beta\ket{1}) $. Portanto, se medirmos o primeiro e o segundo qubit como 00, sabemos que o terceiro qubit, __lá__, está no estado $ (\alpha\ket{0} + \beta\ket{1}) $.
* Se medirmos e obtivermos um resultado 01, a superposição recolherá, deixando apenas os termos consistentes com esse resultado. Isso é $ \alpha\ket{011} + \beta\ket{010}$. Isso pode ser refatorado para $ \ket{01}(\alpha\ket{1} + \beta\ket{0}) $. Portanto, se medirmos o primeiro e o segundo qubit como 01, sabemos que o terceiro qubit, __lá__, está no estado $ (\alpha\ket{1} + \beta\ket{0}) $.
* Se medirmos e obtivermos um resultado 10, a superposição recolherá, deixando apenas os termos consistentes com esse resultado. Isso é $ \alpha\ket{100}-\beta\ket{101}$. Isso pode ser refatorado para $ \ket{10}(\alpha\ket{0}-\beta\ket{1}) $. Portanto, se medirmos o primeiro e o segundo qubit como 10, sabemos que o terceiro qubit, __lá__, está no estado $ (\alpha\ket{0}-\beta\ket{1}) $.
* Se medirmos e obtivermos um resultado 11, a superposição recolherá, deixando apenas os termos consistentes com esse resultado. Isso é $ \alpha\ket{111}-\beta\ket{110}$. Isso pode ser refatorado para $ \ket{11}(\alpha\ket{1}-\beta\ket{0}) $. Portanto, se medirmos o primeiro e o segundo qubit como 11, sabemos que o terceiro qubit, __lá__, está no estado $ (\alpha\ket{1}-\beta\ket{0}) $.

### <a name="step-4-interpret-the-result"></a>Etapa 4: interpretar o resultado

Como lembrete, a __mensagem__ original que queríamos enviar foi:

$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $

Precisamos colocar o qubit nesse estado para __que o estado__ recebido seja aquele que foi pretendido. 

* Se medimos e obtivemos um resultado de 00, o terceiro qubit, __lá__, está no estado $ (\alpha\ket{0} + \beta\ket{1}) $. Como essa é a __mensagem__pretendida, nenhuma alteração é necessária.
* Se medimos e obtivemos um resultado de 01, o terceiro qubit, __lá__, está no estado $ (\alpha\ket{1} + \beta\ket{0}) $. Isso difere da __mensagem__pretendida. no entanto, aplicar uma porta not nos oferece o estado desejado $ (\alpha\ket{0} + \beta\ket{1}) $.
* Se medimos e obtivemos um resultado de 10, o terceiro qubit, __lá__, está no estado $ (\alpha\ket{0}-\beta\ket{1}) $. Isso difere da __mensagem__pretendida. no entanto, aplicar uma porta Z nos dá o estado desejado $ (\alpha\ket{0} + \beta\ket{1}) $.
* Se medimos e obtivemos um resultado de 11, o terceiro qubit, __lá__, está no estado $ (\alpha\ket{1}-\beta\ket{0}) $. Isso difere da __mensagem__pretendida, no entanto, aplicar uma porta not seguida por um portão Z nos dá o estado desejado $ (\alpha\ket{0} + \beta\ket{1}) $.

Para resumir, se medirmos e o primeiro qubit for 1, um portão Z será aplicado. Se medirmos e o segundo qubit for 1, uma porta NOT será aplicada.

### <a name="summary"></a>Resumo
Mostrado abaixo está um circuito do quantum de livro de texto que implementa a teleportação. Mudando da esquerda para a direita você pode ver:
- Etapa 1: Entangling __aqui__ e __lá__ aplicando um portão Hadamard e CNOT Gate.
- Etapa 2: enviando a __mensagem__ usando um portão CNOT e um portão Hadamard.
- Etapa 3: fazendo uma medida do primeiro e segundo qubits, __mensagem__ e __aqui__.
- Etapa 4: aplicando uma portão NOT ou Z, dependendo do resultado da medida na etapa 3.

![' Teleport (msg: qubit, ali: qubit): Unit '](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>Portabilidade Quantum: código

Temos nosso circuito para a portadora Quantum:

![' Teleport (msg: qubit, ali: qubit): Unit '](~/media/teleportation.svg)

Agora podemos converter cada uma das etapas neste circuito Quantum em Q #.

### <a name="step-0-definition"></a>Etapa 0: definição
Quando executamos a teleportação, devemos saber a __mensagem__ que desejamos enviar e onde desejamos enviá-la (__lá__). Por esse motivo, começamos definindo uma nova operação teleport que recebe dois qubits como argumentos, `msg` e `there`:

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

Também precisamos alocar um `here` qubit que realizamos com um bloco de `using`:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>Etapa 1: criar um estado de confusas
Em seguida, podemos criar o par confusas entre `here` e `there` usando as operações @"microsoft.quantum.primitive.h" e @"microsoft.quantum.primitive.cnot":

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>Etapa 2: enviar a mensagem
Em seguida, usamos as próximas $ \operatorname{CNOT} $ e $H $ Gates para mover nossa qubit de mensagem:

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>Etapa 3 & 4: medindo e interpretando o resultado
Por fim, usamos @"microsoft.quantum.primitive.m" para executar as medidas e executar as operações de portão necessárias para obter o estado desejado, conforme indicado pelas instruções `if`:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

Isso conclui a definição do nosso operador de Teleportation, para que possamos desalocar `here`, terminar o corpo e terminar a operação.

```qsharp
    }
}
```
