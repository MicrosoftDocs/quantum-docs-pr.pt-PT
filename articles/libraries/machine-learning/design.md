---
title: Desenhe o seu próprio classificador com o QDK
description: Aprenda os conceitos básicos de desenhar modelos de circuitos para o classificador centrado em circuito quântico.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
ms.openlocfilehash: 4899336f437c1b7712a7831b97fd6ec1431b59a2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909726"
---
# <a name="design-your-own-classifier"></a>Desenhe o seu próprio classificador

Neste guia você aprenderá os conceitos básicos por trás do design de modelos de circuito para o classificador centrado em circuito quântico.

Tal como na aprendizagem profunda clássica, não existe regra geral para escolher uma arquitetura específica. Dependendo do problema, algumas arquiteturas terão um desempenho melhor do que outras. Mas, há alguns conceitos que podem ser úteis ao projetar o circuito:

- Um grande número de parâmetros implica um modelo mais flexível, que pode ser adequado para estabelecer limites de classificação complicados, mas que também pode ser mais suscetível a excesso de encaixe.

- Os portões de enredação entre qubits são essenciais para capturar as correlações entre as características quânticas.

## <a name="how-to-build-a-classifier-with-q"></a>Como construir um classificador com Q\#

Para construir um classificador vamos concatenar rotações controladas parametrizadas no nosso modelo de circuito. Para isso podemos usar o tipo [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) definido na biblioteca quantum machine learning. Este tipo aceita quatro argumentos que determinam: o índice do qubit-alvo, a matriz de índices dos qubits de controlo, o eixo de rotação e o índice do parâmetro associado na matriz de parâmetros que definem o modelo.

Vamos ver um exemplo de um classificador. Na [amostra de meia-lua,](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons)podemos encontrar o seguinte classificador definido no ficheiro `Training.qs`.

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

O que estamos aqui a definir é uma função que devolve uma série de elementos `ControlledRotation`, que juntamente com uma série de parâmetros e um enviesamento definirão a nossa [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel). Este tipo é fundamental na biblioteca quantum machine learning e define o classificador. O circuito definido na função acima faz parte de um classificador no qual cada amostra do conjunto de dados contém duas características. Portanto, só precisamos de dois qubits. A representação gráfica do circuito é:

 ![Exemplo de modelo de circuito](~/media/circuit_model_1.PNG)

## <a name="use-the-library-functions-to-write-layers-of-gates"></a>Use as funções da biblioteca para escrever camadas de portões

Suponha que temos um conjunto de dados com 784 funcionalidades por exemplo, por exemplo imagens de 28×28 pixels como o conjunto de dados MNIST. Neste caso, a largura do circuito torna-se suficientemente grande para que a escrita à mão cada portão individual se torne uma tarefa possível, mas impraticável. É por isso que a biblioteca Quantum Machine Learning fornece um conjunto de ferramentas para gerar automaticamente camadas de rotações parametrizadas. Por exemplo, a função [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) devolve uma série de rotações de moqubit descontrolados ao longo de um determinado eixo, com uma rotação para cada qubit no registo, cada uma parametrizada por um parâmetro de modelo diferente. Por exemplo, `LocalRotationsLayer(4, X)` devolve o seguinte conjunto de portões:

 ![Camada de rotações locais](~/media/local_rotations_layer.PNG)

Recomendamos que explore o [referendo da API da biblioteca Quantum Machine Learning](xref:microsoft.quantum.machinelearning) para descobrir todas as ferramentas disponíveis para agilizar o design do circuito.

## <a name="next-steps"></a>Passos seguintes

 Experimente diferentes estruturas nos exemplos fornecidos pelas amostras. Vê alguma mudança no desempenho do modelo? No próximo tutorial, [`Load your own datasets`, ](xref:microsoft.quantum.libraries.machine-learning.load)aprenderá a carregar conjuntos de dados para tentar explorar novas arquiteturas de classificadores.
