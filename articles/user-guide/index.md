---
title: Guia do Utilizador Q#
description: Descrição geral da finalidade e índice do Guia de Utilizador
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231762"
---
# <a name="the-no-locq-user-guide"></a>Guia do Utilizador Q#

Bem-vindo ao Guia de Utilizador Q#! 

Nos diferentes tópicos deste guia, apresentamos algumas das noções básicas de desenvolvimento de programas quânticos com Q#.

Fazemos referência ao [guia da linguagem Q#](xref:microsoft.quantum.qsharp.index) para lhe dar uma especificação completa e documentação da linguagem de programação quântica Q#. 

## <a name="user-guide-contents"></a>Índice do Guia de Utilizador

- [Programas Q#](xref:microsoft.quantum.guide.programs): uma introdução rápida aos programas quânticos em Q#. 

- [Formas de executar um programa Q#](xref:microsoft.quantum.guide.host-programs): descreve como um programa Q# é executado e fornece uma descrição geral das várias formas de chamar o programa: a partir da linha de comandos, no Jupyter Notebook Q# ou a partir de um programa anfitrião clássico escrito em Python ou numa linguagem .NET.

- [Teste e depuração](xref:microsoft.quantum.guide.testingdebugging): pormenoriza algumas técnicas para confirmar que o código está a fazer o que é suposto. 
    Devido à opacidade geral da informação quântica, a depuração de programas quânticos pode exigir técnicas especializadas. 
    Felizmente, o Q# suporta muitas das técnicas de depuração clássicas a que os programadores estão habituados, bem como aquelas que são específicas da tecnologia quântica. Entre essas técnicas incluem-se a criação e execução de testes de unidades em Q#, a incorporação de *asserções* de valores e probabilidades no seu código e as funções `Dump`, as quais produzem o estado dos computadores de destino. 
    Estas últimas podem ser utilizadas juntamente com o nosso simulador de estado completo para depurar determinadas partes das computações ao contornar algumas limitações quânticas como, por exemplo, o [teorema da não clonagem](xref:microsoft.quantum.concepts.pauli).

### <a name="quantum-simulators-and-resource-estimators"></a>Simuladores Quânticos e Avaliadores de Recursos

- [Simuladores quânticos e aplicações anfitriãs](xref:microsoft.quantum.machines): descrição geral dos diferentes simuladores disponíveis, bem como do funcionamento conjunto dos programas anfitriões e computadores de destino para execução de programas Q#.

- [Simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator): o computador de destino que simula o estado quântico completo. Útil para executar ou depurar totalmente programas de menor escala (menos do que algumas dezenas de qubits)

- [Avaliador de recursos](xref:microsoft.quantum.machines.resources-estimator): calcula os recursos necessários para executar uma determinada instância de uma operação Q# num computador quântico.

- [Simulador de rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro): executa um programa quântico sem simular verdadeiramente o estado de um computador quântico e, por conseguinte, consegue executar programas quânticos que utilizam milhares de qubits. Útil para depurar código clássico num programa quântico, bem como estimar os recursos necessários.

- [Simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): simulador quântico com uma finalidade especial que pode ser utilizado com milhões de qubits, mas apenas para programas com um conjunto restrito de operações quânticas: X, CNOT e X com vários controladores.

### <a name="quick-reference-pages"></a>Páginas de Referência Rápida

- [Comandos Magic do IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): página de referência rápida para comandos Magic do IQ# no Jupyter Notebook em Q#.
