---
title: Desenhe o seu próprio classificador com o QDK
description: Aprenda os conceitos básicos de design de modelos de circuito para o classificador centrado em circuito quântico.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
ms.openlocfilehash: b304b9d1a15f164f4dfe758aaed31b7b2369b18c
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630254"
---
# <a name="design-your-own-classifier"></a><span data-ttu-id="d7f99-103">Desenhe o seu próprio classificador</span><span class="sxs-lookup"><span data-stu-id="d7f99-103">Design your own classifier</span></span>

<span data-ttu-id="d7f99-104">Neste guia você vai aprender os conceitos básicos por trás do design de modelos de circuito para o classificador centrado em circuito quântico.</span><span class="sxs-lookup"><span data-stu-id="d7f99-104">In this guide you will learn the basic concepts behind the design of circuit models for the quantum circuit centric classifier.</span></span>

<span data-ttu-id="d7f99-105">Tal como na aprendizagem profunda clássica, não existe uma regra geral para escolher uma arquitetura específica.</span><span class="sxs-lookup"><span data-stu-id="d7f99-105">As in classical deep learning, there is no general rule for choosing a specific architecture.</span></span> <span data-ttu-id="d7f99-106">Dependendo do problema, algumas arquiteturas terão um desempenho melhor do que outras.</span><span class="sxs-lookup"><span data-stu-id="d7f99-106">Depending on the problem some architectures will perform better than others.</span></span> <span data-ttu-id="d7f99-107">Mas, há alguns conceitos que podem ser úteis ao projetar o circuito:</span><span class="sxs-lookup"><span data-stu-id="d7f99-107">But, there are some concepts that might be useful when designing the circuit:</span></span>

- <span data-ttu-id="d7f99-108">Um grande número de parâmetros implica um modelo mais flexível, que pode ser adequado para desenhar limites de classificação complicados, mas que também pode ser mais suscetível a excesso de adaptação.</span><span class="sxs-lookup"><span data-stu-id="d7f99-108">A large number of parameters implies a more flexible model, which may be suitable to draw complicated classification boundaries but which may also be more susceptible to overfitting.</span></span>

- <span data-ttu-id="d7f99-109">Os portões de enredar entre os qubits são essenciais para capturar as correlações entre as características quânticas.</span><span class="sxs-lookup"><span data-stu-id="d7f99-109">Entangling gates between qubits are essential to capture the correlations between the quantum features.</span></span>

## <a name="how-to-build-a-classifier-with-q"></a><span data-ttu-id="d7f99-110">Como construir um classificador com Q\#</span><span class="sxs-lookup"><span data-stu-id="d7f99-110">How to build a classifier with Q\#</span></span>

<span data-ttu-id="d7f99-111">Para construir um classificador vamos concatenar rotações controladas parametricadas no nosso modelo de circuito.</span><span class="sxs-lookup"><span data-stu-id="d7f99-111">To build a classifier we are going to concatenate parametrized controlled rotations in our circuit model.</span></span> <span data-ttu-id="d7f99-112">Para fazê-lo podemos usar o tipo [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) definido na biblioteca Quantum Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="d7f99-112">To do it we can use the type [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) defined in the Quantum Machine Learning library.</span></span> <span data-ttu-id="d7f99-113">Este tipo aceita quatro argumentos que determinam: o índice do qubit-alvo, a matriz de índices dos qubits de controlo, o eixo de rotação e o índice do parâmetro associado na matriz de parâmetros que definem o modelo.</span><span class="sxs-lookup"><span data-stu-id="d7f99-113">This type accepts four arguments that determine: the index of the target qubit, the array of indices of the control qubits, the axis of rotation, and index of the associated parameter in the array of parameters defining the model.</span></span>

<span data-ttu-id="d7f99-114">Vamos ver um exemplo de um classificador.</span><span class="sxs-lookup"><span data-stu-id="d7f99-114">Let's see an example of a classifier.</span></span> <span data-ttu-id="d7f99-115">Na [amostra de meias-luas, podemos](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons)encontrar o seguinte classificador definido no ficheiro `Training.qs` .</span><span class="sxs-lookup"><span data-stu-id="d7f99-115">In the [half-moons sample](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons), we can find the following classifier defined in the file `Training.qs`.</span></span>

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

<span data-ttu-id="d7f99-116">O que estamos definindo aqui é uma função que devolve uma variedade de `ControlledRotation` elementos, que juntamente com uma variedade de parâmetros e um enviesamento definirão o nosso [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel) .</span><span class="sxs-lookup"><span data-stu-id="d7f99-116">What we are defining here is a function that returns an array of `ControlledRotation` elements, that together with an array of parameters and a bias will define our [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel).</span></span> <span data-ttu-id="d7f99-117">Este tipo é fundamental na biblioteca Quantum Machine Learning e define o classificador.</span><span class="sxs-lookup"><span data-stu-id="d7f99-117">This type is fundamental in the Quantum Machine Learning library and defines the classifier.</span></span> <span data-ttu-id="d7f99-118">O circuito definido na função acima faz parte de um classificador no qual cada amostra do conjunto de dados contém duas características.</span><span class="sxs-lookup"><span data-stu-id="d7f99-118">The circuit defined in the function above is part of a classifier in which each sample of the dataset contains two features.</span></span> <span data-ttu-id="d7f99-119">Portanto, só precisamos de dois qubits.</span><span class="sxs-lookup"><span data-stu-id="d7f99-119">Therefore we only need two qubits.</span></span> <span data-ttu-id="d7f99-120">A representação gráfica do circuito é:</span><span class="sxs-lookup"><span data-stu-id="d7f99-120">The graphical representation of the circuit is:</span></span>

 ![Exemplo de modelo de circuito](~/media/circuit_model_1.PNG)

## <a name="use-the-library-functions-to-write-layers-of-gates"></a><span data-ttu-id="d7f99-122">Use as funções da biblioteca para escrever camadas de portões</span><span class="sxs-lookup"><span data-stu-id="d7f99-122">Use the library functions to write layers of gates</span></span>

<span data-ttu-id="d7f99-123">Suponha que temos um conjunto de dados com 784 funcionalidades por exemplo, por exemplo, imagens de 28×28 pixels como o conjunto de dados do MNIST.</span><span class="sxs-lookup"><span data-stu-id="d7f99-123">Suppose we have a dataset with 784 features per instance, e.g. images of 28×28 pixels like the MNIST dataset.</span></span> <span data-ttu-id="d7f99-124">Neste caso, a largura do circuito torna-se grande o suficiente para que a escrita à mão cada portão individual se torne uma tarefa possível, mas impraticável.</span><span class="sxs-lookup"><span data-stu-id="d7f99-124">In this case, the width of the circuit becomes large enough so that writing by hand each individual gate becomes a possible but impractical task.</span></span> <span data-ttu-id="d7f99-125">É por isso que a biblioteca Quantum Machine Learning fornece um conjunto de ferramentas para gerar automaticamente camadas de rotações parametrizadas.</span><span class="sxs-lookup"><span data-stu-id="d7f99-125">This is why the Quantum Machine Learning library provides a set of tools to automatically generate layers of parametrized rotations.</span></span> <span data-ttu-id="d7f99-126">Por exemplo, a função devolve uma série de rotações de [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) um único qubit descontrolado ao longo de um determinado eixo, com uma rotação para cada qubit no registo, cada parametrizado por um parâmetro de modelo diferente.</span><span class="sxs-lookup"><span data-stu-id="d7f99-126">For instance, the function [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) returns an array of uncontrolled single-qubit rotations along a given axis, with one rotation for each qubit in the register, each parametrized by a different model parameter.</span></span> <span data-ttu-id="d7f99-127">Por exemplo, `LocalRotationsLayer(4, X)` devolve o seguinte conjunto de portões:</span><span class="sxs-lookup"><span data-stu-id="d7f99-127">For example, `LocalRotationsLayer(4, X)` returns the following set of gates:</span></span>

 ![Camada de rotações locais](~/media/local_rotations_layer.PNG)

<span data-ttu-id="d7f99-129">Recomendamos que explore a [referência API da biblioteca Quantum Machine Learning](xref:microsoft.quantum.machinelearning) para descobrir todas as ferramentas disponíveis para agilizar o design do circuito.</span><span class="sxs-lookup"><span data-stu-id="d7f99-129">We recommend you explore the [API reference of the Quantum Machine Learning library](xref:microsoft.quantum.machinelearning) to discover all the tools available to streamline the circuit design.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d7f99-130">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="d7f99-130">Next steps</span></span>

 <span data-ttu-id="d7f99-131">Experimente diferentes estruturas nos exemplos fornecidos pelas amostras.</span><span class="sxs-lookup"><span data-stu-id="d7f99-131">Try different structures in the examples provided by the samples.</span></span> <span data-ttu-id="d7f99-132">Vê alguma alteração no desempenho do modelo?</span><span class="sxs-lookup"><span data-stu-id="d7f99-132">Do you see any changes in the performance of the model?</span></span> <span data-ttu-id="d7f99-133">No próximo tutorial, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) aprenderá a carregar conjuntos de dados para tentar explorar novas arquiteturas de classificadores.</span><span class="sxs-lookup"><span data-stu-id="d7f99-133">In the next tutorial, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load), you will learn how to load datasets to try and explore new architectures of classifiers.</span></span>
