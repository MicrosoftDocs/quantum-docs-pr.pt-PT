---
title: Biblioteca de aprendizagem de máquinas quânticas
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 2/27/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.training
ms.openlocfilehash: f9b33a607a892179795d0700ba3080f9a24ab94a
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909777"
---
# <a name="quantum-machine-learning-glossary"></a>Glossário de Aprendizagem de Máquina Quântica

A formação de um classificador quântico centrado em circuitos é um processo com muitas partes móveis que requerem a mesma quantidade (ou ligeiramente maior) de calibração por tentativa e erro como treino dos classificadores tradicionais. Aqui definimos os principais conceitos e ingredientes deste processo de formação.

## <a name="trainingtesting-schedules"></a>Horários de treino/teste

No contexto da formação de classificadores, um *calendário* descreve um subconjunto de amostras de dados num conjunto de treino ou teste global. Um horário é geralmente definido como uma coleção de índices de amostra.

## <a name="parameterbias-scores"></a>Pontuações parametrómetros/enviesamento

Dado um vetor de parâmetros candidato e um enviesamento de *classificação,* a sua pontuação de validação é medida em relação a um calendário de validação escolhido S e é expressa por uma série de classificações erradas contadas sobre todas as amostras na programação S.

## <a name="hyperparameters"></a>Hiperparâmetros

O processo de formação do modelo rege-se por certos valores pré-definidos *chamados hiperparâmetros:*

### <a name="learning-rate"></a>Taxa de aprendizagem

É um dos principais hiperparâmetros. Define a quantidade de estimativa de gradiente estocástico atual que afeta a atualização do parâmetro. O tamanho da atualização de parâmetros delta é proporcional à taxa de aprendizagem. Os valores mais pequenos da taxa de aprendizagem conduzem a uma evolução dos parâmetros mais lento e a uma convergência mais lenta, mas valores excessivamente grandes de LR podem quebrar completamente a convergência, uma vez que a descida do gradiente nunca se compromete com um determinado mínimo local. Embora a taxa de aprendizagem seja ajustada adaptativamente pelo algoritmo de treino em certa medida, selecionar um bom valor inicial para ele é importante. Um valor inicial padrão habitual para a taxa de aprendizagem é de 0,1. Selecionar o melhor valor da taxa de aprendizagem é uma arte de arte (ver, por exemplo, a secção 4.3 de Goodfellow et al."Deep learning", MIT Press, 2017).

### <a name="minibatch-size"></a>Tamanho do minilote

Define quantas amostras de dados são usadas para uma única estimativa de gradiente estocástico. Valores maiores do tamanho do minibatch geralmente conduzem a uma convergência mais robusta e monotónica, mas podem potencialmente abrandar o processo de treino, uma vez que o custo de qualquer estimativa de gradiente é proporcional ao tamanho da minimatch. Um valor padrão habitual para o tamanho do minilote é 10.

### <a name="training-epochs-tolerance-gridlocks"></a>Épocas de treino, tolerância, impasses

"Época" significa um passe completo através dos dados de treino programados.
O número máximo de épocas por fio de treino (ver abaixo) deve ser limitado. O fio de formação é definido para terminar (com os parâmetros candidatos mais conhecidos) quando o número máximo de épocas tiver sido executado. No entanto, essa formação terminaria mais cedo quando a taxa de classificação errada no calendário de validação fica abaixo da tolerância escolhida. Suponhamos, por exemplo, que a tolerância à má classificação é de 0,01 (1%); se no conjunto de validação de 2000 amostras estamos a assistir a menos de 20 classificações erradas, então o nível de tolerância foi atingido. Um fio de formação também termina prematuramente se a pontuação de validação do modelo candidato não tiver mostrado qualquer melhoria ao longo de várias épocas consecutivas (um impasse). A lógica para a rescisão do impasse está atualmente codificada.

### <a name="measurements-count"></a>Contagem de medições

Estimar as pontuações de formação/validação e os componentes do gradiente estocástico num dispositivo quântico equivale a estimar sobreposições do estado quântico que requerem múltiplas medições dos observáveis apropriados. O número de medições deve ser dimensionado como $O(1/\epsilon^2)$ onde $\epsilon$ é o erro de estimativa desejado.
Regra geral, a contagem inicial de medições pode ser de aproximadamente $1/\mbox{tolerância}^2^$$ (ver definição de tolerância no parágrafo anterior). Seria necessário rever a contagem de medidas para cima se a descida do gradiente parecesse demasiado errática e a convergência demasiado difícil de alcançar.

### <a name="training-threads"></a>Linhas de treino

A função de probabilidade que é a utilidade de treino para o classificador é muito raramente convexa, o que significa que geralmente tem uma infinidade de optima local no espaço de parâmetros que podem diferir significativamente pela qualidade. Uma vez que o processo de DSG pode convergir para apenas um ideal específico, é importante explorar múltiplos vetores de parâmetros de partida. A prática comum na aprendizagem automática é inicializar os vetores iniciais aleatoriamente. O treino Q# API aceita uma variedade arbitrária de tais vetores inexistentes, mas o código subjacente explora-os sequencialmente. Num computador multicore ou, de facto, em qualquer arquitetura de computação paralela é aconselhável realizar várias chamadas para API de treino Q# em paralelo com diferentes ininicializações de parâmetros através das chamadas.

#### <a name="how-to-modify-the-hyperparameters"></a>Como modificar os hiperparâmetros

Na biblioteca QML, a melhor maneira de modificar os hiperparâmetros é sobrepondo-se aos valores padrão da [UDT`TrainingOptions`](xref:microsoft.quantum.machinelearning.trainingoptions). Para tal, chamamos-lhe a função [`DefaultTrainingOptions`](xref:microsoft.quantum.machinelearning.defaulttrainingoptions) e aplicamos o `w/` do operador para anular os valores predefinidos. Por exemplo, utilizar 100.000 medições e uma taxa de aprendizagem de 0,01:
 ```qsharp
let options = DefaultTrainingOptions()
w/ LearningRate <- 0.01
w/ NMeasurements <- 100000;
 ```
