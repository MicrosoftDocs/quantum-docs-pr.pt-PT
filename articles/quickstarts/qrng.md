---
title: Criar um Gerador de Números Aleatórios Quântico
description: Crie um projeto Q# que demonstre conceitos quânticos básicos, como a sobreposição, ao criar um gerador de números aleatórios quântico.
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: a7c077eda3e46430cbe6598cb899adb460451f75
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/02/2019
ms.locfileid: "73443924"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a>Início Rápido: Implementar um Gerador de Números Aleatórios Quântico em Q#
Um exemplo simples de um algoritmo quântico escrito em Q# é um gerador de números aleatórios quântico. Este algoritmo tira partido da natureza da mecânica quântica para produzir um número aleatório. 

## <a name="prerequisites"></a>Pré-requisitos

- O Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Criar um Projeto Q#](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a>Escrever uma operação Q#

### <a name="q-operation-code"></a>Código de operação Q#

1. Substitua o conteúdo do ficheiro Operation.qs pelo seguinte código:

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

Conforme mencionado no nosso artigo [O que é a Computação Quântica?](xref:microsoft.quantum.overview.what), um qubit é uma unidade de informações quânticas que pode estar em sobreposição. Quando medido, um qubit só pode ser 0 ou 1. No entanto, durante a execução, o estado do qubit representa a probabilidade de ler um 0 ou um 1 com uma medição. Este estado de probabilidade é conhecido como sobreposição. Podemos utilizar esta probabilidade para gerar números aleatórios.

Na nossa operação de Q#, apresentamos o tipo de dados `Qubit`, nativo do Q#. Apenas podemos alocar um `Qubit` com uma instrução `using`. Depois de ser alocado, um qubit está sempre no estado `Zero`. 

Com a operação `H`, podemos colocar o `Qubit` em sobreposição. Para medir um qubit e ler o seu valor, pode utilizar a operação intrínseca `M`.

Ao colocar o `Qubit` em sobreposição e ao medi-lo, o resultado será um valor diferente sempre que o código for invocado. 

Quando um `Qubit` é desalocado, tem de ser definido explicitamente de volta para o estado `Zero`. Caso contrário, o simulador reportará um erro de runtime. Uma forma fácil de conseguir isto é ao invocar `Reset`.

### <a name="visualizing-the-code-with-the-bloch-sphere"></a>Visualizar o código com a Esfera de Bloch

Na Esfera de Bloch, o polo norte representa o valor clássico **0** e o polo sul representa o valor clássico **1**. Qualquer sobreposição pode ser representada por um ponto na esfera (representada por uma seta). Quando mais próximo estiver o fim da seta de um polo, maior a probabilidade de o qubit ser incluído no valor clássico atribuído a esse polo quando medido. Por exemplo, o estado do qubit representado pela seta vermelha abaixo tem uma probabilidade mais alta de originar o valor **0** se for medido.

<img src="./Bloch.svg" width="175">

Podemos utilizar esta representação para visualizar o que o código está a fazer:

* Primeiro, começamos com um qubit inicializado no estado **0** e aplicamos `H` para criar uma sobreposição em que as probabilidades de **0** e **1** são iguais.

<img src="./H.svg" width="450">

* Em seguida, medimos o qubit e guardamos a saída:

<img src="./Measurement2.svg" width="450">

Como o resultado da medição é completamente aleatório, obtivemos um bit aleatório. Podemos chamar esta função várias vezes para criar números inteiros. Por exemplo, se chamarmos a função três vezes para obter três bits aleatórios, podemos criar números aleatórios de 3 bits (ou seja, um número aleatório entre 0 e 7).
