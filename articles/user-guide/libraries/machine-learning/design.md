---
title: Desenhe o seu próprio classificador com o QDK
description: Aprenda os conceitos básicos de design de modelos de circuito para o classificador centrado em circuito quântico.
author: geduardo
ms.author: v-edsanc
ms.date: 02/17/2020
ms.topic: conceptual
uid: microsoft.quantum.libraries.machine-learning.design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2100fe120ba3b5fce5d06e77d7f3f5174bc04adb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858804"
---
# <a name="design-your-own-classifier"></a>Desenhe o seu próprio classificador

Neste guia você vai aprender os conceitos básicos por trás do design de modelos de circuito para o classificador centrado em circuito quântico.

Tal como na aprendizagem profunda clássica, não existe uma regra geral para escolher uma arquitetura específica. Dependendo do problema, algumas arquiteturas terão um desempenho melhor do que outras. Mas, há alguns conceitos que podem ser úteis ao projetar o circuito:

- Um grande número de parâmetros implica um modelo mais flexível, que pode ser adequado para desenhar limites de classificação complicados, mas que também pode ser mais suscetível a excesso de adaptação.

- Os portões de enredar entre os qubits são essenciais para capturar as correlações entre as características quânticas.

## <a name="how-to-build-a-classifier-with-q"></a>Como construir um classificador com Q\#

Para construir um classificador vamos concatenar rotações controladas parametricadas no nosso modelo de circuito. Para fazê-lo podemos usar o tipo [`ControlledRotation`](xref:Microsoft.Quantum.MachineLearning.ControlledRotation) definido na biblioteca Quantum Machine Learning. Este tipo aceita quatro argumentos que determinam: o índice do qubit-alvo, a matriz de índices dos qubits de controlo, o eixo de rotação e o índice do parâmetro associado na matriz de parâmetros que definem o modelo.

Vamos ver um exemplo de um classificador. Na [amostra de meias-luas, podemos](https://github.com/microsoft/Quantum/tree/main/samples/machine-learning/half-moons)encontrar o seguinte classificador definido no ficheiro `Training.qs` .

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

O que estamos definindo aqui é uma função que devolve uma variedade de `ControlledRotation` elementos, que juntamente com uma variedade de parâmetros e um enviesamento definirão o nosso [`SequentialModel`](xref:Microsoft.Quantum.MachineLearning.SequentialModel) . Este tipo é fundamental na biblioteca Quantum Machine Learning e define o classificador. O circuito definido na função acima faz parte de um classificador no qual cada amostra do conjunto de dados contém duas características. Portanto, só precisamos de dois qubits. A representação gráfica do circuito é:

 ![Exemplo de modelo de circuito](~/media/circuit_model_1.PNG)

Note que, por defeito, as operações da biblioteca Quantum Machine Learning medem o último qubit do registo para estimar as probabilidades de classificação. Deve ter em mente este facto ao desenhar o seu circuito.

## <a name="use-the-library-functions-to-write-layers-of-gates"></a>Use as funções da biblioteca para escrever camadas de portões

Suponha que temos um conjunto de dados com 784 funcionalidades por exemplo, por exemplo, imagens de 28×28 pixels como o conjunto de dados do MNIST. Neste caso, a largura do circuito torna-se grande o suficiente para que a escrita à mão cada portão individual se torne uma tarefa possível, mas impraticável. É por isso que a biblioteca Quantum Machine Learning fornece um conjunto de ferramentas para gerar automaticamente camadas de rotações parametrizadas. Por exemplo, a função devolve uma série de rotações de [`LocalRotationsLayer`](xref:Microsoft.Quantum.MachineLearning.LocalRotationsLayer) um único qubit descontrolado ao longo de um determinado eixo, com uma rotação para cada qubit no registo, cada parametrizado por um parâmetro de modelo diferente. Por exemplo, `LocalRotationsLayer(4, X)` devolve o seguinte conjunto de portões:

 ![Camada de rotações locais](~/media/local_rotations_layer.PNG)

Recomendamos que explore a [referência API da biblioteca Quantum Machine Learning](xref:Microsoft.Quantum.MachineLearning) para descobrir todas as ferramentas disponíveis para agilizar o design do circuito.

## <a name="next-steps"></a>Próximos passos

 Experimente diferentes estruturas nos exemplos fornecidos pelas amostras. Vê alguma alteração no desempenho do modelo? No próximo tutorial, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) aprenderá a carregar conjuntos de dados para tentar explorar novas arquiteturas de classificadores.
