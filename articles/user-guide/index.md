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
ms.openlocfilehash: f0680e773c8233d6c4f1acb742b3cc38dbc069d5
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834759"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="53829-103">Guia do Utilizador Q#</span><span class="sxs-lookup"><span data-stu-id="53829-103">The Q# User Guide</span></span>

<span data-ttu-id="53829-104">Bem-vindo ao Guia de Utilizador Q#!</span><span class="sxs-lookup"><span data-stu-id="53829-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="53829-105">Nos diferentes tópicos deste guia, apresentamos em detalhe os conceitos fundamentais da linguagem Q# e toda a informação de que precisa para escrever programas quânticos.</span><span class="sxs-lookup"><span data-stu-id="53829-105">In the different topics of this guide, we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="53829-106">Índice do Guia de Utilizador</span><span class="sxs-lookup"><span data-stu-id="53829-106">User Guide Contents</span></span>

- <span data-ttu-id="53829-107">[Noções básicas de Q#](xref:microsoft.quantum.guide.basics): descrição geral introdutória da finalidade e funcionalidade da linguagem de programação Q#.</span><span class="sxs-lookup"><span data-stu-id="53829-107">[Q# Basics](xref:microsoft.quantum.guide.basics): An introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

- <span data-ttu-id="53829-108">[Formas de executar um programa Q#](xref:microsoft.quantum.guide.host-programs): descreve como um programa Q# é executado e fornece uma descrição geral das várias formas de chamar o programa: a partir da linha de comandos, no Jupyter Notebook Q# ou a partir de um programa anfitrião clássico escrito em Python ou numa linguagem .NET.</span><span class="sxs-lookup"><span data-stu-id="53829-108">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is run, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

### <a name="no-locq-language"></a><span data-ttu-id="53829-109">Linguagem Q#</span><span class="sxs-lookup"><span data-stu-id="53829-109">Q# Language</span></span>

- <span data-ttu-id="53829-110">[Tipos em Q#](xref:microsoft.quantum.guide.types): destaca o modelo de tipos em Q# e descreve a sintaxe para especificar e trabalhar com tipos.</span><span class="sxs-lookup"><span data-stu-id="53829-110">[Types in Q#](xref:microsoft.quantum.guide.types): Lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="53829-111">[Expressões de Tipos](xref:microsoft.quantum.guide.expressions): detalha como especificar, referenciar, combinar e operar nos valores de cada tipo em Q#.</span><span class="sxs-lookup"><span data-stu-id="53829-111">[Type Expressions](xref:microsoft.quantum.guide.expressions): Details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-no-locq"></a><span data-ttu-id="53829-112">Ao utilizar Q#</span><span class="sxs-lookup"><span data-stu-id="53829-112">Using Q#</span></span>

- <span data-ttu-id="53829-113">[Estrutura de Ficheiros Q#](xref:microsoft.quantum.guide.filestructure): descreve a estrutura e a sintaxe de um ficheiro Q# `*.qs`.</span><span class="sxs-lookup"><span data-stu-id="53829-113">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): Describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="53829-114">[Operações e Funções](xref:microsoft.quantum.guide.operationsfunctions): detalha os dois tipos chamáveis da linguagem Q#: as *operações*, que incluem ações em registos qubit, e as *funções*, que funcionam estritamente com informação clássica.</span><span class="sxs-lookup"><span data-stu-id="53829-114">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): Details the two callable types of the Q# language: *operations*, which include action on qubit registers, and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="53829-115">Aqui, pode ver como defini-los e chamá-los, incluindo as versões conjuntas e controladas das operações quânticas.</span><span class="sxs-lookup"><span data-stu-id="53829-115">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="53829-116">[Variáveis](xref:microsoft.quantum.guide.variables): descreve a função das variáveis nos programas de Q# e como tirar partido das mesmas eficazmente.</span><span class="sxs-lookup"><span data-stu-id="53829-116">[Variables](xref:microsoft.quantum.guide.variables): Describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="53829-117">Por exemplo, pode encontrar informações sobre âmbitos de enlace, bem como a diferença entre variáveis imutáveis e mutáveis e como as atribuir ou reatribuir.</span><span class="sxs-lookup"><span data-stu-id="53829-117">For example, you can find information about binding scopes, as well as the difference between immutable and mutable variables and how to assign or re-assign them.</span></span>

- <span data-ttu-id="53829-118">[Trabalhar com qubits](xref:microsoft.quantum.guide.qubits): descreve as funcionalidades de Q# que pode utilizar para trabalhar com qubits individuais e sistemas de qubits, em particular, para os alocar, realizar operações nos mesmos e para os medir.</span><span class="sxs-lookup"><span data-stu-id="53829-118">[Working with qubits](xref:microsoft.quantum.guide.qubits): Describes the features of Q# used to address individual qubits and systems of qubits, specifically, allocating them, performing operations on them, and measuring them.</span></span> 

- <span data-ttu-id="53829-119">[Fluxo de Controlo](xref:microsoft.quantum.guide.controlflow): detalha os padrões do fluxo de controlo de programação disponíveis no Q#, o que inclui muitas técnicas padrão (tais como processamento condicional, ciclos *for*, ciclos *while*), bem como o padrão *Repeat-Until-Success* quântico específico.</span><span class="sxs-lookup"><span data-stu-id="53829-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): Details the programming control flow patterns available in Q#, which includes many standard techniques (such as conditional processing, *for* loops, *while* loops) as well as the quantum-specific *Repeat-Until-Success* pattern.</span></span>

- <span data-ttu-id="53829-120">[Teste e depuração](xref:microsoft.quantum.guide.testingdebugging): pormenoriza algumas técnicas para confirmar que o código está a fazer o que é suposto.</span><span class="sxs-lookup"><span data-stu-id="53829-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="53829-121">Devido à opacidade geral da informação quântica, a depuração de programas quânticos pode exigir técnicas especializadas.</span><span class="sxs-lookup"><span data-stu-id="53829-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="53829-122">Felizmente, o Q# suporta muitas das técnicas de depuração clássicas a que os programadores estão habituados, bem como aquelas que são específicas da tecnologia quântica.</span><span class="sxs-lookup"><span data-stu-id="53829-122">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="53829-123">Entre essas técnicas incluem-se a criação e execução de testes de unidades em Q#, a incorporação de *asserções* de valores e probabilidades no seu código e as funções `Dump`, as quais produzem o estado dos computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="53829-123">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="53829-124">Estas últimas podem ser utilizadas juntamente com o nosso simulador de estado completo para depurar determinadas partes das computações ao contornar algumas limitações quânticas como, por exemplo, o [teorema da não clonagem](xref:microsoft.quantum.concepts.pauli).</span><span class="sxs-lookup"><span data-stu-id="53829-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="53829-125">Simuladores Quânticos e Avaliadores de Recursos</span><span class="sxs-lookup"><span data-stu-id="53829-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="53829-126">[Simuladores quânticos e aplicações anfitriãs](xref:microsoft.quantum.machines): uma descrição geral dos diferentes simuladores disponíveis, bem como do modelo de execução geral entre programas anfitriões e computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="53829-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well as the general run model between host programs and target machines.</span></span>

- <span data-ttu-id="53829-127">[Simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator): o computador de destino que simula o estado quântico completo.</span><span class="sxs-lookup"><span data-stu-id="53829-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="53829-128">Útil para executar ou depurar totalmente programas de menor escala (menos do que algumas dezenas de qubits)</span><span class="sxs-lookup"><span data-stu-id="53829-128">Useful for fully running or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="53829-129">[Avaliador de recursos](xref:microsoft.quantum.machines.resources-estimator): calcula os recursos necessários para executar uma determinada instância de uma operação Q# num computador quântico.</span><span class="sxs-lookup"><span data-stu-id="53829-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="53829-130">[Simulador de rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro): executa um programa quântico sem simular verdadeiramente o estado de um computador quântico e, por conseguinte, consegue executar programas quânticos que utilizam milhares de qubits.</span><span class="sxs-lookup"><span data-stu-id="53829-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Runs a quantum program without actually simulating the state of a quantum computer, and therefore can run quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="53829-131">Útil para depurar código clássico num programa quântico, bem como estimar os recursos necessários.</span><span class="sxs-lookup"><span data-stu-id="53829-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="53829-132">[Simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): simulador quântico com uma finalidade especial que pode ser utilizado com milhões de qubits, mas apenas para programas com um conjunto restrito de operações quânticas: X, CNOT e X com vários controladores.</span><span class="sxs-lookup"><span data-stu-id="53829-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="53829-133">Páginas de Referência Rápida</span><span class="sxs-lookup"><span data-stu-id="53829-133">Quick Reference Pages</span></span>

- <span data-ttu-id="53829-134">[Comandos Magic do IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): página de referência rápida para comandos Magic do IQ# no Jupyter Notebook em Q#.</span><span class="sxs-lookup"><span data-stu-id="53829-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
