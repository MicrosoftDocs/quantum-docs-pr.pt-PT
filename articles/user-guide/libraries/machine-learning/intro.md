---
title: Biblioteca de machine learning quântica
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.intro
ms.openlocfilehash: 4a4ecbb85cc5bbfb1ccb1f111309578bcc5bce3d
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86872655"
---
# <a name="introduction-to-quantum-machine-learning"></a>Introdução à Aprendizagem de Máquinas Quânticas

## <a name="framework-and-goals"></a>Enquadramento e metas

A codificação quântica e o processamento da informação é uma poderosa alternativa à aprendizagem de máquinas clássicas Os classificadores quânticos, em particular, codificam dados em registos quânticos que são concisos em relação ao número de características, empregam sistematicamente o emaranhamento quântico como recurso computacional e empregam a medição quântica para a inferência da classe.
O classificador quântico centrado em circuitos é uma solução quântica relativamente simples que combina codificação de dados com um circuito quântico emaranhamento/disentangling rápido seguido de medição para inferir rótulos de classe de amostras de dados.
O objetivo é garantir a caracterização clássica e armazenamento de circuitos sujeitos, bem como o treino quântico/clássico híbrido dos parâmetros do circuito, mesmo para espaços de características extremamente grandes.

## <a name="classifier-architecture"></a>Arquitetura de classificador

A classificação é uma tarefa de aprendizagem automática supervisionada, onde o objetivo é inferir etiquetas de classe $ \{ y_1,y_2,\ldots,y_d \} de $100 de certas amostras de dados. O "conjunto de dados de treino" é uma coleção de amostras $\mathcal{D}= \{ (x,y)}} com etiquetas pré-atribuídas conhecidas. Aqui $x$ é uma amostra de dados e $y$ é a sua conhecida etiqueta chamada "etiqueta de treino".
Um pouco semelhante aos métodos tradicionais, a classificação quântica consiste em três etapas:
- codificação de dados
- preparação de um estado classificador
- medição Devido à natureza probabilística da medição, estes três passos devem ser repetidos várias vezes. A medição pode ser vista como um equivalente quântico de ativação não linear.
Tanto a codificação como a computação do estado classificador são feitas através de *circuitos quânticos.* Embora o circuito de codificação seja normalmente orientado por dados e sem parâmetros, o circuito de classificação contém um conjunto suficiente de parâmetros aprecáveis. 

Na solução proposta, o circuito classificador é composto por rotações de um único qubit e rotações controladas de dois qubits. Os parâmetros apregáveis aqui são os ângulos de rotação. Os portões de rotação e rotação controlados são conhecidos por serem *universais* para a computação quântica, o que significa que qualquer matriz de peso unitário pode ser decomposta num circuito suficientemente longo, composto por tais portões.

![Perceptron multicamacro contra o classificador centrado em circuito](~/media/DLvsQCC.png)

Podemos comparar este modelo com um perceptron multicama para obter uma melhor compreensão da estrutura básica. No pertron o preditor $p(y/x, \theta)$ é parametrizado pelo conjunto de pesos $\theta$ que determinam as funções lineares que ligam as funções de ativação não linear (neurónios). Estes parâmetros podem ser treinados para criar o modelo. Na camada de saída podemos obter a probabilidade de uma amostra pertencente a uma classe usando funções de ativação não linear como softmax. No classificador centrado no circuito, o preditor é parametrizado pelos ângulos de rotação do monobit e das rotações controladas de dois qubits do circuito modelo. De forma semelhante, esses parâmetros podem ser treinados por uma versão quântica/clássica híbrida do algoritmo de descida de gradiente. Para calcular a saída, em vez de utilizar funções de ativação não lineares, a probabilidade da classe é obtida lendo medições repetidas sobre um qubit específico após as rotações controladas. Para codificar os dados clássicos num estado quântico, usamos um circuito de codificação controlável para a preparação do estado.

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
