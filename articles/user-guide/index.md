---
title: Guia de Utilizador Q#
description: Descrição geral da finalidade e índice do Guia de Utilizador
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: c5611f3e2907791f2dfc1644be0a45515d50dfd7
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415374"
---
# <a name="the-q-user-guide"></a>Guia de Utilizador Q#

Bem-vindo ao Guia de Utilizador Q#! 

Nos diferentes tópicos deste guia, apresentamos em detalhe os conceitos fundamentais da linguagem Q# e toda a informação de que precisa para escrever programas quânticos.

## <a name="user-guide-contents"></a>Índice do Guia de Utilizador

- [Noções Básicas de Q#](xref:microsoft.quantum.guide.basics): descrição geral introdutória da finalidade e funcionalidade da linguagem de programação Q#. 

### <a name="q-language"></a>Linguagem Q#

- [Tipos em Q#](xref:microsoft.quantum.guide.types): destaca o modelo de tipos em Q# e descreve a sintaxe para especificar e trabalhar com tipos.

- [Expressões de Tipos](xref:microsoft.quantum.guide.expressions): detalha como especificar, referenciar, combinar e operar nos valores de cada tipo em Q#. 

### <a name="using-q"></a>Utilizar o Q#

- [Estrutura de Ficheiros Q#](xref:microsoft.quantum.guide.filestructure): descreve a estrutura e a sintaxe de um ficheiro Q# `*.qs`.

- [Operações e Funções](xref:microsoft.quantum.guide.operationsfunctions): detalha os dois tipos chamáveis da linguagem Q#: as *operações*, que incluem ações em registos qubit, e as *funções*, que funcionam estritamente com informação clássica. 
    Aqui, pode ver como defini-los e chamá-los, incluindo as versões conjuntas e controladas das operações quânticas.

- [Variáveis](xref:microsoft.quantum.guide.variables): descreve a função das variáveis nos programas de Q# e como tirar partido das mesmas eficazmente. 
    Por exemplo, pode encontrar informações sobre âmbitos de enlace, bem como a diferença entre variáveis imutáveis e mutáveis e como as atribuir ou reatribuir.

- [Trabalhar com qubits](xref:microsoft.quantum.guide.qubits): descreve as funcionalidades de Q# que pode utilizar para trabalhar com qubits individuais e sistemas de qubits, em particular, para os alocar, realizar operações nos mesmos e medi-los. 

- [Fluxo de Controlo](xref:microsoft.quantum.guide.controlflow): detalha os padrões do fluxo de controlo de programação disponíveis em Q#, o que inclui muitas técnicas padrão (tais como execução condicional, para ciclos, durante ciclos), bem como o padrão "Repeat-Until-Success" (RUS) quântico específico.

- [Teste e depuração](xref:microsoft.quantum.guide.testingdebugging): pormenoriza algumas técnicas para confirmar que o código está a fazer o que é suposto. 
    Devido à opacidade geral da informação quântica, a depuração de programas quânticos pode exigir técnicas especializadas. 
    Felizmente, o Q# suporta muitas das técnicas de depuração clássicas a que os programadores estão habituados, bem como aquelas que são específicas da tecnologia quântica. Entre essas técnicas incluem-se a criação e execução de testes de unidades em Q#, a incorporação de *asserções* de valores e probabilidades no seu código e as funções `Dump`, as quais produzem o estado dos computadores de destino. 
    Estas últimas podem ser utilizadas juntamente com o nosso simulador de estado completo para depurar determinadas partes das computações ao contornar algumas limitações quânticas como, por exemplo, o [teorema da não clonagem](xref:microsoft.quantum.concepts.pauli).

### <a name="quantum-simulators-and-resource-estimators"></a>Simuladores Quânticos e Avaliadores de Recursos

- [Simuladores quânticos e aplicações anfitriãs](xref:microsoft.quantum.machines): descrição geral dos diferentes simuladores disponíveis, bem como do modelo de execução geral entre programas anfitriões e os computadores de destino.

- [Simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator): o computador de destino que simula o estado quântico completo. Útil para executar ou depurar totalmente programas de menor escala (menos do que poucas dezenas de qubits)

- [Avaliador de recursos](xref:microsoft.quantum.machines.resources-estimator): calcula os recursos necessários para executar uma determinada instância de uma operação Q# num computador quântico.

- [Simulador de rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro): executa um programa quântico sem simular verdadeiramente o estado de um computador quântico e, por conseguinte, consegue executar programas quânticos que utilizam milhares de qubits. Útil para depurar código clássico num programa quântico, bem como estimar os recursos necessários.

- [Simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): simulador quântico com uma finalidade especial que pode ser utilizado com milhões de qubits, mas apenas para programas com um conjunto restrito de operações quânticas: X, CNOT e X com vários controladores.

### <a name="quick-reference-pages"></a>Páginas de Referência Rápida

- [Comandos Magic do IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): página de referência rápida para comandos Magic do IQ# em Blocos de Notas do Jupyter em Q#.
