---
title: Biblioteca de aprendizagem de máquinas quânticas
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.introduction
ms.openlocfilehash: 4c42612fee3a58e15368677bb2c77a70c5680f45
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909794"
---
# <a name="introduction-to-quantum-machine-learning"></a>Introdução à Aprendizagem automática quântica

## <a name="framework-and-goals"></a>Enquadramento e metas

A codificação quântica e o processamento de informação são uma poderosa alternativa à aprendizagem automática clássica Classificadores quânticos, em particular, codificam dados em registos quânticos que são concisos em relação ao número de funcionalidades, empregam sistematicamente quantum emaranhado como recurso computacional e utilizar a medição quântica para a inferência da classe.
O classificador quântico centrado no circuito é uma solução quântica relativamente simples que combina a codificação de dados com um circuito quântico de engato/dessentido rápido seguido de medição para inferir etiquetas de classe de amostras de dados.
O objetivo é garantir a caracterização clássica e armazenamento de circuitos de matérias, bem como o treino híbrido quântico/clássico dos parâmetros do circuito, mesmo para espaços de características extremamente grandes.

## <a name="classifier-architecture"></a>Arquitetura classifier

A classificação é uma tarefa de aprendizagem automática supervisionada, onde o objetivo é inferir etiquetas de classe $\{y_1,y_2,\ldots,y_d\}$ de certas amostras de dados. O "conjunto de dados de treino" é uma coleção de amostras $\mathcal{D}=\{(x,y)}$ com etiquetas pré-atribuídas conhecidas. Aqui $x$ é uma amostra de dados e $y$ é a sua conhecida etiqueta chamada "etiqueta de treino".
Um pouco semelhante aos métodos tradicionais, a classificação quântica consiste em três etapas:
- codificação de dados
- preparação de um estado classificador
- medição Devido à natureza probabilística da medição, estes três passos devem ser repetidos várias vezes. A medição pode ser vista como um equivalente quântico de ativação não linear.
Tanto a codificação como a computação do estado de classificação são feitas através de *circuitos quânticos.* Embora o circuito de codificação seja geralmente baseado em dados e livre de parâmetros, o circuito de classificação contém um conjunto suficiente de parâmetros aprendíveis. 

Na solução proposta, o circuito de classificação é composto por rotações de qubit único e rotações controladas por dois qubits. Os parâmetros aprendáveis aqui são os ângulos de rotação. Os portões de rotação e rotação controlados são conhecidos por serem *universais* para a computação quântica, o que significa que qualquer matriz de peso unitário pode ser decomposta num circuito suficientemente longo, composto por tais portões.

![Perceptron multicamada vs. Circuit Centric Classifier](~/media/DLvsQCC.png)

Podemos comparar este modelo com um perceptron multicamada para obter uma melhor compreensão da estrutura básica. Na perceção, o preditor $p (y/x, \theta)$ é parametrizado pelo conjunto de pesos $\theta$ que determinam as funções lineares que ligam as funções de ativação não lineares (neurónios). Estes parâmetros podem ser treinados para criar o modelo. Na camada de saída podemos obter a probabilidade de uma amostra pertencente a uma classe usando funções de ativação não lineares como softmax. No classificador centrado no circuito, o preditor é parametrizado pelos ângulos de rotação das rotações controladas por qubit único e dois qubits do circuito do modelo. Da mesma forma, esses parâmetros podem ser treinados por uma versão quântica/clássica híbrida do algoritmo de descida gradiente. Para calcular a saída, em vez de utilizar funções de ativação não lineares, a probabilidade da classe é obtida através da leitura de medições repetidas sobre um qubit específico após as rotações controladas. Para codificar os dados clássicos num estado quântico, usamos um circuito de codificação controlável para a preparação do Estado.

A nossa arquitetura explora circuitos relativamente rasos, que, portanto, devem estar *rapidamente ligados* para capturar todas as correlações entre as características dos dados em todas as gamas. Um exemplo do componente de circuito de enredação mais útil rapidamente é mostrado na figura abaixo. Mesmo que um circuito com esta geometria consista em apenas $3 n+1$ portões, a matriz de peso unitário que calcula garante uma conversa cruzada significativa entre as características de $2^n$.

![Circuito quântico em 5 qubits (com duas camadas cíclicas).](~/media/5-qubit-qccc.png)

O circuito no exemplo acima é composto por 6 portões de um único qubit $(G_1,\ldots,G_5; G_{16})$ e 10 dois qubits portões $(G_6,\ldots,G_{15})$. Assumindo que cada um dos portões é definido com um parâmetro apreciável temos 16 parâmetros aprendentes, enquanto a dimensão do espaço Hilbert de 5 qubits é de 32. Tal geometria do circuito pode ser facilmente generalizada a qualquer registo $n$-qubit, quando $n$ é estranho, produzindo circuitos com parâmetros de $3 n+1$ para $2^n$-dimensional feature space.

## <a name="classifier-training-as-a-supervised-learning-task"></a>Formação de classificação como uma tarefa de aprendizagem supervisionada

A formação de um modelo de classificação envolve encontrar os valores ideais dos seus parâmetros operacionais, de modo a maximizar a probabilidade média de inferir os rótulos de formação corretos nas amostras de formação.
Aqui, preocupamo-nos apenas com a classificação de dois níveis, ou seja, o caso de $d=2$ e apenas duas classes com os rótulos $y_1,y_2$.

> [!NOTE]
> Uma forma de generalizar os nossos métodos para o número arbitrário de classes é substituir qubits por qudits, ou seja, unidades quânticas por $d estados de base de $, e a medição bidirecional com $d medição de usuário.

### <a name="likelihood-as-the-training-goal"></a>Probabilidade de ser o objetivo de treino

Dado um circuito quântico aprendeu $U(\theta)$, onde $\theta$ é um vetor de parâmetros, e denotando a medição final por $M$, a probabilidade média da inferência do rótulo correto é $$ \start{align} \mathcal{L}(\theta)=\frac{1}{\mathcal{D}} \left( \sum_{(x,y_1)\in\mathcal{D}} P(M=y_1] U(\theta) x) + \sum_{(x,y_2)\in\mathcal{D}} P(M=y_2/ U(\theta) x)\right) \end{align} $$ where $P(M=y[z)$ é a probabilidade de medir $y$ em estado quântico $z$.
Aqui, basta entender que a função de probabilidade $\mathcal{L}(\theta)$ é suave em $\theta$ e a sua derivada em qualquer $\theta_j$ pode ser calculada essencialmente pelo mesmo protocolo quântico usado para calcular a função de probabilidade em si. Isto permite otimizar o $\mathcal{L}(\theta)$ por descida gradiente.

### <a name="classifier-bias-and-training-score"></a>Tendência classificação e pontuação de treino

Tendo em conta alguns valores intermédios (ou finais) dos parâmetros em $\theta$, precisamos identificar um único valor real $b$ conhecido como *preconceito de classificação* para fazer a inferência. A regra de inferência do rótulo funciona da seguinte forma: 
- Uma amostra $x$ é atribuída $y_2$ se e apenas se $P(M=y_2 U(\theta) x) + b > 0,5$ (RULE1) (caso contrário, é atribuído rótulo $y_1$)

Claramente $b$ deve estar no intervalo $(-0,5,+0,5)$ para ter significado.

Um caso de treino $(x,y) \in \mathcal{D}$ é considerado uma *classificação errada* dado o enviesamento $b$ se a etiqueta inferida para $x$ conforme rule1 é realmente diferente de $y$. O número global de classificações erradas é a *pontuação* de treino do classificador dado o enviesamento $b$. O viés de classificação *ideal* $b$ minimiza a pontuação do treino. É fácil ver que, dadas as estimativas de probabilidade pré-calculadas $\{ P(M=y_2 U(\theta) x)  (x,*)\in\mathcal{D} \}$, o viés de classificação ideal pode ser encontrado por pesquisa binária em intervalo $(-0,5,+0,5)$ fazendo no máximo $\log_2(\mathcal{D}) Passos de $.

### <a name="reference"></a>Referência

Esta informação deve ser suficiente para começar a jogar com o código. No entanto, se quiser saber mais sobre este modelo, leia a proposta original: [ *"Classificadores quânticos centrados em circuitos", Maria Schuld, Alex Bocharov, Krysta Svore e Nathan Wiebe*](https://arxiv.org/abs/1804.00633)
