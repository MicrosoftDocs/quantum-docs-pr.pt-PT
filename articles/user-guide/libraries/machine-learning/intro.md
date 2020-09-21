---
title: Biblioteca de machine learning quântica
description: Saiba como é que a aprendizagem automática é usada em sistemas quânticos
author: alexeib2
ms.author: alexeib
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9f7f892fb2b76432942c86163497c22f0c73d51f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833806"
---
# <a name="introduction-to-quantum-machine-learning"></a>Introdução à Aprendizagem de Máquinas Quânticas

## <a name="framework-and-goals"></a>Enquadramento e metas

A codificação quântica e o processamento da informação é uma poderosa alternativa aos classificadores quânticos de aprendizagem de máquinas clássicas. Em particular, permite-nos codificar dados em registos quânticos concisos em relação ao número de funcionalidades, empregando sistematicamente o emaranhamento quântico como recurso computacional e utilizando a medição quântica para a inferência da classe.
O classificador quântico centrado em circuitos é uma solução quântica relativamente simples que combina codificação de dados com um circuito quântico emaranhamento/disentangling rápido seguido de medição para inferir rótulos de classe de amostras de dados.
O objetivo é garantir a caracterização clássica e armazenamento de circuitos sujeitos, bem como o treino quântico/clássico híbrido dos parâmetros do circuito, mesmo para espaços de características extremamente grandes.

## <a name="classifier-architecture"></a>Arquitetura de classificador

A classificação é uma tarefa de aprendizagem automática supervisionada, onde o objetivo é inferir etiquetas de classe $ \{ y_1,y_2,\ldots,y_d \} de $100 de certas amostras de dados. O "conjunto de dados de treino" é uma coleção de amostras $\mathcal{D}= \{ (x,y)}} com etiquetas pré-atribuídas conhecidas. Aqui $x$ é uma amostra de dados e $y$ é a sua conhecida etiqueta chamada "etiqueta de treino".
Um pouco semelhante aos métodos tradicionais, a classificação quântica consiste em três etapas:
- codificação de dados
- preparação de um estado classificador
- medição Devido à natureza probabilística da medição, estes três passos devem ser repetidos várias vezes. Tanto a codificação como a computação do estado classificador são feitas através de *circuitos quânticos.* Embora o circuito de codificação seja normalmente orientado por dados e sem parâmetros, o circuito de classificação contém um conjunto suficiente de parâmetros aprecáveis. 

Na solução proposta, o circuito classificador é composto por rotações de um único qubit e rotações controladas de dois qubits. Os parâmetros apregáveis aqui são os ângulos de rotação. Os portões de rotação e rotação controlados são conhecidos por serem *universais* para a computação quântica, o que significa que qualquer matriz de peso unitário pode ser decomposta num circuito suficientemente longo, composto por tais portões.

Na versão proposta, apenas é suportado um circuito seguido de uma estimativa de frequência única.
Assim, a solução é um analógico quântico de uma máquina vetorial de suporte com um núcleo polinómio de baixo grau.

![Perceptron multicamacro contra o classificador centrado em circuito](~/media/DLvsQCC.png)

Um design de classificador quântico simples pode ser comparado com uma solução tradicional de vetor de suporte (SVM). A inferência para uma amostra de dados $x$ no caso de SVM é feita usando um núcleo ideal $\sum \alpha_j k (x_j,x)$ onde $k$ é uma determinada função de kernel.

Em contraste, um classificador quântico usa o previsão $p(y│x,U(\theta))=〈U(\theta)x/ M. U(\theta)x〉$, que é semelhante em espírito, mas tecnicamente bastante diferente. Assim, quando é utilizada uma codificação simples de amplitude, $p(y│x,U(\theta)$ é uma forma quadrática nas amplitudes de $x$, mas os coeficientes desta forma já não são aprendidos de forma independente; são, em vez disso, agregados a partir dos elementos matricias do circuito $U(\theta)$, que normalmente tem significativamente menos parâmetros apreitáveis $\theta$ do que a dimensão do vetor $x$. O grau polinómico de $p(y│x,U(\theta)$ nas características originais pode ser aumentado para $2^l$ usando um produto quântico codificando $l$ cópias de $x$.

A nossa arquitetura explora circuitos relativamente rasos, que, portanto, devem ser *rapidamente emaranhados* para capturar todas as correlações entre as características dos dados em todas as gamas. Um exemplo do componente de circuito de enredar rápido mais útil é mostrado na figura abaixo. Mesmo que um circuito com esta geometria consista em apenas $3 n+1$ portões, a matriz de peso unitário que calcula garante conversas cruzadas significativas entre as características de $2^n$ .

![Circuito quântico em 5 qubits (com duas camadas cíclicas).](~/media/5-qubit-qccc.png)

O circuito no exemplo acima é composto por 6 portões de um único qubit $(G_1,\ldots,G_5; G_ {16} )$ e 10 portões de dois qubits $(G_6,\ldots,G_ {15} )$. Assumindo que cada um dos portões é definido com um parâmetro aprecável temos 16 parâmetros aprecíveis, enquanto a dimensão do espaço Hilbert de 5 qubits é de 32. Tal geometria de circuito pode ser facilmente generalizada a qualquer registo de $n$-qubit, quando $n$ é estranho, cedendo circuitos com parâmetros de $3 n+1$ para $2^n$-dimensional feature space.

## <a name="classifier-training-as-a-supervised-learning-task"></a>Formação de classificador como tarefa de aprendizagem supervisionada

A formação de um modelo de classificador implica encontrar valores ideais dos seus parâmetros operacionais, de modo a maximizar a probabilidade média de inferir os rótulos de treino corretos através das amostras de treino.
Aqui, preocupamo-nos apenas com a classificação de dois níveis, ou seja, o caso de $d=2$ e apenas duas classes com os rótulos $y_1,y_2$.

> [!NOTE]
> Uma forma de generalizar os nossos métodos para um número arbitrário de classes é substituir qubits por qudits, ou seja, unidades quânticas por estados de base $d$, e a medição bidirecionais com $d medição de $-way.

### <a name="likelihood-as-the-training-goal"></a>Probabilidade como objetivo de treino

Dado um circuito quântico apresuável $U(\theta)$, onde $\theta$ é um vetor de parâmetros, e denotando a medição final por $M$, a probabilidade média da inferência correta da etiqueta é $$ \start{L}} {1} \mathcal{L}}}(\mathcal{D}]} \left\{{D y_1}/* \left\ \sum_{(x,y_1)\in math\cal{D}} U(\theta) x) + \sum_{(x,y_2)\in\mathcal{D}} P(M=y_2/ U(\theta) x)\right) \end{align} $$ onde $P (M=y/z)$ é a probabilidade de medir $y$ em estado quântico $z$.
Aqui, basta entender que a função de probabilidade $\mathcal{L}(\theta)$ é suave em $\theta$ e a sua derivada em qualquer $\theta_j$ pode ser calculada essencialmente pelo mesmo protocolo quântico usado para calcular a função de probabilidade em si. Isto permite otimizar o $\mathcal{L}(\theta)$ por descida de gradiente.

### <a name="classifier-bias-and-training-score"></a>Viés de classificado e pontuação de treino

Tendo em conta alguns valores intermédios (ou finais) dos parâmetros em $\theta$, precisamos identificar um único valor real $b$ conhecido como *viés de classificador* para fazer a inferência. A regra da inferência do rótulo funciona da seguinte forma: 
- Uma amostra $x$ é atribuída etiqueta $y_2$ se e somente se $P (M=y_2/ U(\theta) x) + b > 0,5$ (REGRA1) (caso contrário, é atribuída a etiqueta $y_1$)

É evidente $b$ deve estar no intervalo $(-0,5,0,5)$ para ser significativo.

Um caso de treino $(x,y) \in \mathcal{D}$ é considerado uma *classificação errada* dado o preconceito $b$ se o rótulo inferido por $x$ como por RULE1 é realmente diferente de $y$. O número total de classificações erradas é a *pontuação* de treino do classificador dado o preconceito $b$. O *viés de* classificador ideal $b$ minimiza a pontuação do treino. É fácil ver que, dadas as estimativas de probabilidade pré-computação $ \{ P(M=y_2/ U(\theta) x ! (x,*)\in\mathcal{D} \} $, o viés de classificador ideal pode ser encontrado através de pesquisa binária em intervalos $(-0,5,+0,5)$ fazendo no máximo $\log_2(\mathcal{D}]) Passos de $000.

### <a name="reference"></a>Referência

Esta informação deve ser suficiente para começar a brincar com o código. No entanto, se quiser saber mais sobre este modelo, leia a proposta original: [ *"Classificadores quânticos centrados em circuitos", Maria Schuld, Alex Bocharov, Krysta Svore e Nathan Wiebe*](https://arxiv.org/abs/1804.00633)

Além da amostra de código que você verá nos próximos passos, você também pode começar a explorar a classificação quântica [neste tutorial](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/QuantumClassification) 
