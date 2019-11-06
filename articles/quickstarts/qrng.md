---
title: Criar um Gerador de Números Aleatórios Quântico
description: Crie um projeto Q# que demonstre conceitos quânticos básicos, como a sobreposição, ao criar um gerador de números aleatórios quântico.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: c3039b92c4b3235a397d5cf31280ac2673706e9d
ms.sourcegitcommit: 2ca4755d1a63431e3cb2d2918a10ad477ec2e368
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73462833"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="06fe9-103">Início Rápido: Implementar um Gerador de Números Aleatórios Quântico em Q#</span><span class="sxs-lookup"><span data-stu-id="06fe9-103">Quickstart: Implement a Quantum Random Number Generator in Q#</span></span>
<span data-ttu-id="06fe9-104">Um exemplo simples de um algoritmo quântico escrito em Q# é um gerador de números aleatórios quântico.</span><span class="sxs-lookup"><span data-stu-id="06fe9-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="06fe9-105">Este algoritmo tira partido da natureza da mecânica quântica para produzir um número aleatório.</span><span class="sxs-lookup"><span data-stu-id="06fe9-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="06fe9-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="06fe9-106">Prerequisites</span></span>

- <span data-ttu-id="06fe9-107">O Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span><span class="sxs-lookup"><span data-stu-id="06fe9-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="06fe9-108">Criar um Projeto Q#</span><span class="sxs-lookup"><span data-stu-id="06fe9-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a><span data-ttu-id="06fe9-109">Escrever uma operação Q#</span><span class="sxs-lookup"><span data-stu-id="06fe9-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="06fe9-110">Código de operação Q#</span><span class="sxs-lookup"><span data-stu-id="06fe9-110">Q# operation code</span></span>

1. <span data-ttu-id="06fe9-111">Substitua o conteúdo do ficheiro Operation.qs pelo seguinte código:</span><span class="sxs-lookup"><span data-stu-id="06fe9-111">Replace the contents of the Operation.qs file with the following code:</span></span>

    ```qsharp
    namespace Quantum {
        open Microsoft.Quantum.Intrinsic;

        operation QuantumRandomNumberGenerator() : Result {
            using(q = Qubit())  { // Allocate a qubit.
                H(q);             // Put the qubit to superposition. It now has a 50% chance of being 0 or 1.
                let r = M(q);     // Measure the qubit value.
                Reset(q);
                return r;
            }
        }
    }
    ```

<span data-ttu-id="06fe9-112">Conforme mencionado no nosso artigo [O que é a Computação Quântica?](xref:microsoft.quantum.overview.what), um qubit é uma unidade de informações quânticas que pode estar em sobreposição.</span><span class="sxs-lookup"><span data-stu-id="06fe9-112">As mentioned in our [What is Quantum Computing?](xref:microsoft.quantum.overview.what) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="06fe9-113">Quando medido, um qubit só pode ser 0 ou 1.</span><span class="sxs-lookup"><span data-stu-id="06fe9-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="06fe9-114">No entanto, durante a execução, o estado do qubit representa a probabilidade de ler um 0 ou um 1 com uma medição.</span><span class="sxs-lookup"><span data-stu-id="06fe9-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="06fe9-115">Este estado de probabilidade é conhecido como sobreposição.</span><span class="sxs-lookup"><span data-stu-id="06fe9-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="06fe9-116">Podemos utilizar esta probabilidade para gerar números aleatórios.</span><span class="sxs-lookup"><span data-stu-id="06fe9-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="06fe9-117">Na nossa operação de Q#, apresentamos o tipo de dados `Qubit`, nativo do Q#.</span><span class="sxs-lookup"><span data-stu-id="06fe9-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="06fe9-118">Apenas podemos alocar um `Qubit` com uma instrução `using`.</span><span class="sxs-lookup"><span data-stu-id="06fe9-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="06fe9-119">Depois de ser alocado, um qubit está sempre no estado `Zero`.</span><span class="sxs-lookup"><span data-stu-id="06fe9-119">When it gets allocated a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="06fe9-120">Com a operação `H`, podemos colocar o `Qubit` em sobreposição.</span><span class="sxs-lookup"><span data-stu-id="06fe9-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="06fe9-121">Para medir um qubit e ler o seu valor, pode utilizar a operação intrínseca `M`.</span><span class="sxs-lookup"><span data-stu-id="06fe9-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="06fe9-122">Ao colocar o `Qubit` em sobreposição e ao medi-lo, o resultado será um valor diferente sempre que o código for invocado.</span><span class="sxs-lookup"><span data-stu-id="06fe9-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span> 

<span data-ttu-id="06fe9-123">Quando um `Qubit` é desalocado, tem de ser definido explicitamente de volta para o estado `Zero`. Caso contrário, o simulador reportará um erro de runtime.</span><span class="sxs-lookup"><span data-stu-id="06fe9-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="06fe9-124">Uma forma fácil de conseguir isto é ao invocar `Reset`.</span><span class="sxs-lookup"><span data-stu-id="06fe9-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="06fe9-125">Visualizar o código com a Esfera de Bloch</span><span class="sxs-lookup"><span data-stu-id="06fe9-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="06fe9-126">Na Esfera de Bloch, o polo norte representa o valor clássico **0** e o polo sul representa o valor clássico **1**.</span><span class="sxs-lookup"><span data-stu-id="06fe9-126">In the Bloch sphere the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="06fe9-127">Qualquer sobreposição pode ser representada por um ponto na esfera (representada por uma seta).</span><span class="sxs-lookup"><span data-stu-id="06fe9-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="06fe9-128">Quando mais próximo estiver o fim da seta de um polo, maior a probabilidade de o qubit ser incluído no valor clássico atribuído a esse polo quando medido.</span><span class="sxs-lookup"><span data-stu-id="06fe9-128">When the closer the end of the arrow to a pole, the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="06fe9-129">Por exemplo, o estado do qubit representado pela seta vermelha abaixo tem uma probabilidade mais alta de originar o valor **0** se for medido.</span><span class="sxs-lookup"><span data-stu-id="06fe9-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="./Bloch.svg" width="175">

<span data-ttu-id="06fe9-130">Podemos utilizar esta representação para visualizar o que o código está a fazer:</span><span class="sxs-lookup"><span data-stu-id="06fe9-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="06fe9-131">Primeiro, começamos com um qubit inicializado no estado **0** e aplicamos `H` para criar uma sobreposição em que as probabilidades de **0** e **1** são iguais.</span><span class="sxs-lookup"><span data-stu-id="06fe9-131">First we start with a qubit initalizated in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="./H.svg" width="450">

* <span data-ttu-id="06fe9-132">Em seguida, medimos o qubit e guardamos a saída:</span><span class="sxs-lookup"><span data-stu-id="06fe9-132">Then we measure the qubit and save the output:</span></span>

<img src="./Measurement2.svg" width="450">

<span data-ttu-id="06fe9-133">Como o resultado da medição é completamente aleatório, obtivemos um bit aleatório.</span><span class="sxs-lookup"><span data-stu-id="06fe9-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="06fe9-134">Podemos chamar esta operação várias vezes para criar números inteiros.</span><span class="sxs-lookup"><span data-stu-id="06fe9-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="06fe9-135">Por exemplo, se chamarmos a operação três vezes para obter três bits aleatórios, poderemos criar números aleatórios de 3 bits (ou seja, um número aleatório entre 0 e 7).</span><span class="sxs-lookup"><span data-stu-id="06fe9-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>
