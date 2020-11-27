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
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="ee02a-103">Guia do Utilizador Q#</span><span class="sxs-lookup"><span data-stu-id="ee02a-103">The Q# User Guide</span></span>

<span data-ttu-id="ee02a-104">Bem-vindo ao Guia de Utilizador Q#!</span><span class="sxs-lookup"><span data-stu-id="ee02a-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="ee02a-105">Nos diferentes tópicos deste guia, apresentamos algumas das noções básicas de desenvolvimento de programas quânticos com Q#.</span><span class="sxs-lookup"><span data-stu-id="ee02a-105">In the different topics of this guide, we introduce some of the basics for developing quantum programs using Q#.</span></span>

<span data-ttu-id="ee02a-106">Fazemos referência ao [guia da linguagem Q#](xref:microsoft.quantum.qsharp.index) para lhe dar uma especificação completa e documentação da linguagem de programação quântica Q#.</span><span class="sxs-lookup"><span data-stu-id="ee02a-106">We refer to the [Q# language guide](xref:microsoft.quantum.qsharp.index) for a full specification and documentation of the Q# quantum programming language.</span></span> 

## <a name="user-guide-contents"></a><span data-ttu-id="ee02a-107">Índice do Guia de Utilizador</span><span class="sxs-lookup"><span data-stu-id="ee02a-107">User Guide Contents</span></span>

- <span data-ttu-id="ee02a-108">[Programas Q#](xref:microsoft.quantum.guide.programs): uma introdução rápida aos programas quânticos em Q#.</span><span class="sxs-lookup"><span data-stu-id="ee02a-108">[Q# programs](xref:microsoft.quantum.guide.programs): An quick introduction to quantum programs in Q#.</span></span> 

- <span data-ttu-id="ee02a-109">[Formas de executar um programa Q#](xref:microsoft.quantum.guide.host-programs): descreve como um programa Q# é executado e fornece uma descrição geral das várias formas de chamar o programa: a partir da linha de comandos, no Jupyter Notebook Q# ou a partir de um programa anfitrião clássico escrito em Python ou numa linguagem .NET.</span><span class="sxs-lookup"><span data-stu-id="ee02a-109">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is run, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

- <span data-ttu-id="ee02a-110">[Teste e depuração](xref:microsoft.quantum.guide.testingdebugging): pormenoriza algumas técnicas para confirmar que o código está a fazer o que é suposto.</span><span class="sxs-lookup"><span data-stu-id="ee02a-110">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="ee02a-111">Devido à opacidade geral da informação quântica, a depuração de programas quânticos pode exigir técnicas especializadas.</span><span class="sxs-lookup"><span data-stu-id="ee02a-111">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="ee02a-112">Felizmente, o Q# suporta muitas das técnicas de depuração clássicas a que os programadores estão habituados, bem como aquelas que são específicas da tecnologia quântica.</span><span class="sxs-lookup"><span data-stu-id="ee02a-112">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="ee02a-113">Entre essas técnicas incluem-se a criação e execução de testes de unidades em Q#, a incorporação de *asserções* de valores e probabilidades no seu código e as funções `Dump`, as quais produzem o estado dos computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="ee02a-113">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="ee02a-114">Estas últimas podem ser utilizadas juntamente com o nosso simulador de estado completo para depurar determinadas partes das computações ao contornar algumas limitações quânticas como, por exemplo, o [teorema da não clonagem](xref:microsoft.quantum.concepts.pauli).</span><span class="sxs-lookup"><span data-stu-id="ee02a-114">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="ee02a-115">Simuladores Quânticos e Avaliadores de Recursos</span><span class="sxs-lookup"><span data-stu-id="ee02a-115">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="ee02a-116">[Simuladores quânticos e aplicações anfitriãs](xref:microsoft.quantum.machines): descrição geral dos diferentes simuladores disponíveis, bem como do funcionamento conjunto dos programas anfitriões e computadores de destino para execução de programas Q#.</span><span class="sxs-lookup"><span data-stu-id="ee02a-116">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well of how host programs and target machines work together to run Q# programs.</span></span>

- <span data-ttu-id="ee02a-117">[Simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator): o computador de destino que simula o estado quântico completo.</span><span class="sxs-lookup"><span data-stu-id="ee02a-117">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="ee02a-118">Útil para executar ou depurar totalmente programas de menor escala (menos do que algumas dezenas de qubits)</span><span class="sxs-lookup"><span data-stu-id="ee02a-118">Useful for fully running or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="ee02a-119">[Avaliador de recursos](xref:microsoft.quantum.machines.resources-estimator): calcula os recursos necessários para executar uma determinada instância de uma operação Q# num computador quântico.</span><span class="sxs-lookup"><span data-stu-id="ee02a-119">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="ee02a-120">[Simulador de rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro): executa um programa quântico sem simular verdadeiramente o estado de um computador quântico e, por conseguinte, consegue executar programas quânticos que utilizam milhares de qubits.</span><span class="sxs-lookup"><span data-stu-id="ee02a-120">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Runs a quantum program without actually simulating the state of a quantum computer, and therefore can run quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="ee02a-121">Útil para depurar código clássico num programa quântico, bem como estimar os recursos necessários.</span><span class="sxs-lookup"><span data-stu-id="ee02a-121">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="ee02a-122">[Simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): simulador quântico com uma finalidade especial que pode ser utilizado com milhões de qubits, mas apenas para programas com um conjunto restrito de operações quânticas: X, CNOT e X com vários controladores.</span><span class="sxs-lookup"><span data-stu-id="ee02a-122">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="ee02a-123">Páginas de Referência Rápida</span><span class="sxs-lookup"><span data-stu-id="ee02a-123">Quick Reference Pages</span></span>

- <span data-ttu-id="ee02a-124">[Comandos Magic do IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): página de referência rápida para comandos Magic do IQ# no Jupyter Notebook em Q#.</span><span class="sxs-lookup"><span data-stu-id="ee02a-124">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
