---
title: Álgebra linear para computação quântica
description: Saiba que conceitos de álgebra linear básicos são necessários para compreender a computação quântica
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.algebra
no-loc:
- Q#
- $$v
ms.openlocfilehash: d7a8dff8d491a9ce6451148d2d27121f1c190ed0
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759327"
---
# <a name="linear-algebra-for-quantum-computing"></a>Álgebra linear para computação quântica

A álgebra linear é a linguagem da computação quântica. Embora não a tenha de dominar para implementar ou escrever programas quânticos, esta linguagem é amplamente utiliza para descrever estados de qubits, operações quânticas, e para prever o que um computador quântico fará como resposta a uma sequência de instruções.

Da mesma forma que conhecer os [conceitos básicos da física quântica](xref:microsoft.quantum.overview.understanding) pode ajudar a compreender a computação quântica, também saber um mínimo de álgebra linear pode esclarecer o modo de funcionamento dos algoritmos quânticos. Deverá, pelo menos, familiarizar-se com os **vetores** e a **multiplicação de matrizes**. Se precisar de rever os seus conhecimentos destes conceitos de álgebra, pode ver estes tutoriais, que abordam as noções básicas:

- [Tutorial do Jupyter Notebook sobre álgebra linear](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/LinearAlgebra)
- [Tutorial do Jupyter Notebook sobre aritmética complexa](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/ComplexArithmetic)
- [Álgebra Linear para Computação Quântica](https://cds.cern.ch/record/1522001/files/978-1-4614-6336-8_BookBackMatter.pdf)
- [Introdução à Álgebra Linear](https://www.math.ubc.ca/~carrell/NB.pdf)
- [Instruções Básicas da Computação Quântica ](https://www.codeproject.com/Articles/5155638/Quantum-Computation-Primer-Part-1#exploring-quantum-superposition)

## <a name="vectors-and-matrices-in-quantum-computing"></a>Vetores e matrizes em computação quântica

No tópico [Compreender a computação quântica](xref:microsoft.quantum.overview.understanding), aprendeu que um qubit pode ter o estado 1 ou 0 ou uma superposição de ambos. Utilizando a álgebra linear, o estado de um qubit é descrito como um vetor e é representado por uma **matrix** de coluna única $\begin{bmatrix} a \\\\  b \end{bmatrix}$. Também é conhecido como **vetor de estado quântico** e tem de cumprir o requisito em que $|a|^2 + |b|^2 = 1$.  

Os elementos da matriz representam a probabilidade de o qubit colapsar de uma forma ou outra, sendo $|a|^2$ a probabilidade de colapsar para zero e $|b|^2$ para um. Todas as matrizes seguintes representam vetores de estado quântico válidos:

$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}, \begin{bmatrix} 0 \\\\  1 \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix} \text{ e }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}.$$

Em [Computadores quânticos e simuladores quânticos](xref:microsoft.quantum.overview.simulators), também aprendeu que as operações quânticas são utilizadas para modificar o estado de um qubit.  As operações quânticas também podem ser representadas por uma matriz. Quando uma operação quântica é aplicada a um qubit, as duas matrizes que os representam são multiplicadas e a resposta resultante representa o estado novo do qubit depois da operação.  

Abaixo estão duas operações quânticas comuns, representadas com a multiplicação de matriz.


A [operação `X`](xref:microsoft.quantum.intrinsic.x) é representada pela matriz de Pauli $X$,

$$X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix},$$
    
e é utilizado para mudar o estado de um qubit de 0 para 1 (ou vice-versa); por exemplo:

$$\begin{bmatrix}0 &1\\\\ 1 &0\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}.$$

A [operação "H"](xref:microsoft.quantum.intrinsic.h) é representada pela transformação de Hadamard $H$,

$$H = \dfrac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix},$$

 e põe o qubit num estado de superposição, em que a probabilidade de colapsar para um dos lados é igual, conforme mostrado aqui

$$\frac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix}=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=\left(\frac{1}{\sqrt{2}}\right)^2=\frac{1}{2}.$$

Uma matriz que represente uma operação quântica tem um requisito, tem de ser uma matriz **unitária**. Uma matriz é unitária se o seu **inverso** for igual ao seu **transposto conjugado**.

## <a name="representing-two-qubit-states"></a>Representar estados de dois qubits

Nos exemplos anteriores, o estado de um qubit foi descrito com uma matriz de coluna única $\begin{bmatrix} a \\\\  b \end{bmatrix}$ e a aplicação de uma operação ao mesmo foi descrita ao multiplicar as duas matrizes. No entanto, os computadores quânticos utilizam mais de um qubit. Então, como é que descrevemos o estado combinado de dois qubits? 

Lembre-se de que cada qubit é um espaço de vetor, pelo que não podem ser simplesmente multiplicados. Em vez disso, vai utilizar um **produto tensorial**, que é uma operação associada que cria um espaço de vetor novo a partir de espaços de vetores individuais e é representado pelo símbolo $\otimes$. Por exemplo, o produto tensorial do estado de dois qubits $\begin{bmatrix} a \\\\  b \end{bmatrix}$ e $\begin{bmatrix} c \\\\  d \end{bmatrix}$ é calculado

$$ \begin{bmatrix} a \\\\  b \end{bmatrix} \otimes \begin{bmatrix} c \\\\  d \end{bmatrix} =\begin{bmatrix} a \begin{bmatrix} c \\\\  d \end{bmatrix} \\\\ b \begin{bmatrix}c \\\\  d \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}. $$

O resultado é uma matriz quadridimensional, em que cada elemento representa uma probabilidade. Por exemplo, $ac$ é a probabilidade de ambos os qubits colapsarem para 0 e 0, $ad$ é a probabilidade de 0 e 1, e assim sucessivamente. 

Tal como um estado de qubit único $\begin{bmatrix} a \\\\  b \end{bmatrix}$ tem de cumprir o requisito em que $|a|^2 + |b|^2 = 1$ de modo a representar um estado quântico, um estado de dois qubits $\begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}$ tem de cumprir o requisito em que $|ac|^2 + |ad|^2 + |bc|^2+ |bd|^2 = 1$.

## <a name="summary"></a>Resumo

A álgebra linear é a linguagem padrão para a descrição de computação quântica e de física quântica. Embora as [bibliotecas](xref:microsoft.quantum.libraries) incluídas no Microsoft Quantum Development Kit ajudem a executar algoritmos quânticos avançados sem ter de dominar a matemática subjacente, saber os conceitos básicos permitirá começar mais depressa e constituirá uma base sólida sobre a qual progredir.

## <a name="next-steps"></a>Passos seguintes

[Instalar o QDK](xref:microsoft.quantum.install)
