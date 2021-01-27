---
title: Glossário da biblioteca de aprendizagem de máquinas quânticas
description: Glossário dos termos de aprendizagem da máquina quântica
author: alexeib2
ms.author: alexeib
ms.date: 2/27/2020
ms.topic: conceptual
uid: microsoft.quantum.libraries.machine-learning.training
no-loc:
- Q#
- $$v
ms.openlocfilehash: b6133c1f3068dff597f71d2111e5e117131a7fd1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852724"
---
# <a name="quantum-machine-learning-glossary"></a>Glossário de aprendizagem de máquina quântica

O treino de um classificador quântico centrado em circuitos é um processo com muitas partes móveis que requerem a mesma (ou ligeiramente maior) quantidade de calibração por tentativa e erro como formação de classificadores tradicionais. Aqui definimos os principais conceitos e ingredientes deste processo de formação.

## <a name="trainingtesting-schedules"></a>Horários de treino/testes

No contexto da formação de classificados, um *programa* descreve um subconjunto de amostras de dados num conjunto de treino ou testes globais. Um horário é geralmente definido como uma coleção de índices de amostra.

## <a name="parameterbias-scores"></a>Pontuações parâmetro/viés

Dado um vetor de parâmetros candidatos e um viés de classificação, a sua *pontuação de validação* é medida em relação a um calendário de validação escolhido S e é expressa por uma série de classificações erradas contadas em todas as amostras do calendário S.

## <a name="hyperparameters"></a>Hiperparmetros

O processo de formação do modelo rege-se por certos valores pré-definidos chamados *hiperparímetros:*

### <a name="learning-rate"></a>Taxa de aprendizagem

É um dos hiperparímetros chave. Define a quantidade atual de estimativa de gradiente estocástico que impacta a atualização dos parâmetros. O tamanho da atualização dos parâmetros delta é proporcional à taxa de aprendizagem. Valores de taxa de aprendizagem mais pequenos conduzem a uma evolução mais lenta dos parâmetros e a uma convergência mais lenta, mas valores excessivamente grandes de LR podem quebrar completamente a convergência, uma vez que a descida do gradiente nunca se compromete a um mínimo local específico. Embora a taxa de aprendizagem seja ajustada de forma adaptável pelo algoritmo de treino em certa medida, selecionar um bom valor inicial para ele é importante. O valor inicial padrão habitual para a taxa de aprendizagem é de 0,1. Selecionar o melhor valor da taxa de aprendizagem é uma arte fina (ver, por exemplo, secção 4.3 de Goodfellow et al."Deep learning", MIT Press, 2017).

### <a name="minibatch-size"></a>Tamanho de minibatch

Define quantas amostras de dados são usadas para uma única estimativa do gradiente estocástico. Valores maiores de tamanho de minibatch geralmente conduzem a uma convergência mais robusta e mais monótona, mas podem potencialmente abrandar o processo de treino, uma vez que o custo de qualquer estimativa de gradiente é proporcional ao tamanho mini-ajuste. Um valor padrão habitual para o tamanho da minibatch é 10.

### <a name="training-epochs-tolerance-gridlocks"></a>Épocas de treino, tolerância, impasses

"Época" significa uma passagem completa através dos dados de treino programados.
O número máximo de épocas por fio de treino (ver abaixo) deve ser limitado. O fio de treino é definido para terminar (com os parâmetros candidatos mais conhecidos) quando o número máximo de épocas foi executado. No entanto, essa formação terminaria mais cedo quando a taxa de classificação errada no calendário de validação se situasse abaixo de uma tolerância escolhida. Suponhamos, por exemplo, que a tolerância à classificação errada é de 0,01 (1%); se no conjunto de validação de 2000 amostras estamos a assistir a menos de 20 classificações erradas, então o nível de tolerância foi atingido. Um fio de treino também termina prematuramente se a pontuação de validação do modelo candidato não tiver mostrado qualquer melhoria em várias épocas consecutivas (um impasse). A lógica para a rescisão do impasse está atualmente codificada.

### <a name="measurements-count"></a>Contagem de medições

Estimar as pontuações de treino/validação e os componentes do gradiente estocástico num dispositivo quântico equivale a estimar sobreposições de estado quântico que requer várias medições dos observáveis apropriados. O número de medições deve ser escalado como $O (1/\epsilon^2)$ onde $\epsilon$ é o erro de estimativa pretendido.
Em regra do polegar, a contagem inicial de medições pode ser aproximadamente $1/\mbox{tolerância}^2$ (ver definição de tolerância no parágrafo anterior). Seria necessário rever a contagem de medidas para cima se a descida do declive parecesse demasiado errática e a convergência demasiado difícil de alcançar.

### <a name="training-threads"></a>Fios de treino

A função de probabilidade que é a utilidade de treino para o classificador é muito raramente convexa, o que significa que geralmente tem uma infinidade de optima local no espaço de parâmetros que podem diferir significativamente pela qualidade. Uma vez que o processo SGD pode convergir para apenas um ideal específico, é importante explorar vários vetores de parâmetros iniciais. A prática comum na aprendizagem automática é inicializar tais vetores iniciais aleatoriamente. A Q# API de formação aceita uma matriz arbitrária de tais vetores iniciais, mas o código subjacente explora-os sequencialmente. Num computador multicore ou de facto em qualquer arquitetura de computação paralela é aconselhável realizar várias chamadas para Q# a formação de API em paralelo com diferentes inicializações de parâmetros através das chamadas.

#### <a name="how-to-modify-the-hyperparameters"></a>Como modificar os hiperparímetros

Na biblioteca QML, a melhor forma de modificar os hiperparmetros é sobrevam os valores predefinidos da UDT [`TrainingOptions`](xref:Microsoft.Quantum.MachineLearning.TrainingOptions) . Para isso chamamos-lhe com a função [`DefaultTrainingOptions`](xref:Microsoft.Quantum.MachineLearning.DefaultTrainingOptions) e aplicamos o operador `w/` para anular os valores predefinidos. Por exemplo, utilizar 100.000 medições e uma taxa de aprendizagem de 0,01:

```qsharp
let options = DefaultTrainingOptions()
w/ LearningRate <- 0.01
w/ NMeasurements <- 100000;
```
