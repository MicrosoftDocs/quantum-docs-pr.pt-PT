---
title: Guia de Utilizador Q#
description: Descrição geral da finalidade e índice do Guia de Utilizador
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: f535aaedbe6ce181375d48f7023409ad8212c702
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430616"
---
# <a name="the-q-user-guide"></a>Guia de Utilizador Q#

Bem-vindo ao Guia de Utilizador Q#! 

Aqui, detalhamos os conceitos fundamentais da linguagem Q# e toda a informação de que precisa para escrever programas quânticos.

## <a name="user-guide-contents"></a>Índice do Guia de Utilizador

- [Noções Básicas de Q#](xref:microsoft.quantum.guide.basics): descrição geral introdutória da finalidade e funcionalidade da linguagem de programação Q#. 

### <a name="q-language"></a>Linguagem Q#

- [Tipos em Q#](xref:microsoft.quantum.guide.types): destaca o modelo de tipos em Q# e descreve a sintaxe para especificar e trabalhar com tipos.

- [Expressões de Tipos](xref:microsoft.quantum.guide.expressions): detalha como especificar, referenciar, combinar e operar nos valores de cada tipo em Q#. 

### <a name="using-q"></a>Utilizar o Q#

- [Estrutura de Ficheiros Q#](xref:microsoft.quantum.guide.filestructure): descreve a estrutura e a sintaxe de um ficheiro Q# `*.qs`.

- [Operações e Funções](xref:microsoft.quantum.guide.operationsfunctions): detalha os dois tipos chamáveis da linguagem Q#, as *operações*, que incluem ações em qubits, e as *funções*, que funcionam estritamente com informação clássica. 
    Aqui, pode ver como defini-los e chamá-los, incluindo as versões conjuntas e controladas das operações quânticas.

- [Variáveis](xref:microsoft.quantum.guide.variables): descreve a função das variáveis nos programas de Q# e como tirar partido das mesmas eficazmente. 
    Por exemplo, pode encontrar informações sobre âmbitos de enlace, bem como a diferença entre variáveis imutáveis/mutáveis e como atribuir/reatribuí-las.

- [Trabalhar com qubits](xref:microsoft.quantum.guide.qubits): descreve as funcionalidades de Q# que pode utilizar para trabalhar com qubits individuais e sistemas de qubits. 
    Mais especificamente, implica a respetiva alocação, realizar operações nos mesmos e, por fim, a medição dos mesmos. 

- [Fluxo de Controlo](xref:microsoft.quantum.guide.controlflow): detalha os padrões do fluxo de controlo de programação disponíveis em Q#, que inclui muitas técnicas padrão (execução condicional, para ciclos, durante ciclos, etc.), bem como o padrão "Repetir-Até-Obter-Êxito" quântico específico.

- [Teste e depuração](xref:microsoft.quantum.guide.testingdebugging): pormenoriza algumas técnicas para confirmar que o código está a fazer o que é suposto. 
    Devido à opacidade geral da informação quântica, a depuração de programas quânticos pode exigir técnicas especializadas. 
    Felizmente, a Q# suporta muitas das técnicas de depuração clássicas a que os programadores estão habituados, bem como aquelas que são específicas da tecnologia quântica. Entre essas técnicas incluem-se a criação/execução de testes de unidade em Q#, a incorporação de *asserções* em valores e probabilidades do código e as funções `Dump` que produzem o estado da máquina de destino. 
    Estas últimas podem ser utilizadas juntamente com o nosso simulador de estado completo para depurar determinadas partes das computações ao contornar algumas limitações quânticas (por exemplo, o teorema da não clonagem).

### <a name="quantum-simulators-and-resource-estimators"></a>Simuladores Quânticos e Avaliadores de Recursos

- [Simuladores quânticos e aplicações anfitriãs](xref:microsoft.quantum.machines): descrição geral dos diferentes simuladores disponíveis, bem como o modelo de execução geral entre o programa anfitrião e os computadores de destino.

- [Simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator): o computador de destino que simula o estado quântico completo. Útil para executar ou depurar totalmente programas de menor escala (menos de umas dezenas de qubits)

- [Avaliador de recursos](xref:microsoft.quantum.machines.resources-estimator): estima os recursos necessários para executar uma determinada instância de uma operação Q# num computador quântico.

- [Simulador de rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro): executa um programa quântico sem simular verdadeiramente o estado de um computador quântico e, por conseguinte, consegue executar programas quânticos que utilizam milhares de qubits. Útil para depurar código clássico num programa quântico, bem como estimar os recursos necessários.

- [Simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): simulador quântico com uma finalidade especial que pode ser utilizado com milhões de qubits, mas apenas para programas com um conjunto restrito de operações quânticas (nomeadamente X, CNOT e X multi-controlados).

### <a name="quick-reference-pages"></a>Páginas de Referência Rápida

- [Comandos Magic do IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): página de referência rápida para comandos Magic do IQ# em Blocos de Notas do Jupyter em Q#.
