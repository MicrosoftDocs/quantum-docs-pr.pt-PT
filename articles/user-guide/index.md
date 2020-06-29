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
# <a name="the-q-user-guide"></a><span data-ttu-id="718ce-103">Guia de Utilizador Q#</span><span class="sxs-lookup"><span data-stu-id="718ce-103">The Q# User Guide</span></span>

<span data-ttu-id="718ce-104">Bem-vindo ao Guia de Utilizador Q#!</span><span class="sxs-lookup"><span data-stu-id="718ce-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="718ce-105">Nos diferentes tópicos deste guia, apresentamos em detalhe os conceitos fundamentais da linguagem Q# e toda a informação de que precisa para escrever programas quânticos.</span><span class="sxs-lookup"><span data-stu-id="718ce-105">In the different topics of this guide, we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="718ce-106">Índice do Guia de Utilizador</span><span class="sxs-lookup"><span data-stu-id="718ce-106">User Guide Contents</span></span>

- <span data-ttu-id="718ce-107">[Noções Básicas de Q#](xref:microsoft.quantum.guide.basics): descrição geral introdutória da finalidade e funcionalidade da linguagem de programação Q#.</span><span class="sxs-lookup"><span data-stu-id="718ce-107">[Q# Basics](xref:microsoft.quantum.guide.basics): An introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

### <a name="q-language"></a><span data-ttu-id="718ce-108">Linguagem Q#</span><span class="sxs-lookup"><span data-stu-id="718ce-108">Q# Language</span></span>

- <span data-ttu-id="718ce-109">[Tipos em Q#](xref:microsoft.quantum.guide.types): destaca o modelo de tipos em Q# e descreve a sintaxe para especificar e trabalhar com tipos.</span><span class="sxs-lookup"><span data-stu-id="718ce-109">[Types in Q#](xref:microsoft.quantum.guide.types): Lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="718ce-110">[Expressões de Tipos](xref:microsoft.quantum.guide.expressions): detalha como especificar, referenciar, combinar e operar nos valores de cada tipo em Q#.</span><span class="sxs-lookup"><span data-stu-id="718ce-110">[Type Expressions](xref:microsoft.quantum.guide.expressions): Details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-q"></a><span data-ttu-id="718ce-111">Utilizar o Q#</span><span class="sxs-lookup"><span data-stu-id="718ce-111">Using Q#</span></span>

- <span data-ttu-id="718ce-112">[Estrutura de Ficheiros Q#](xref:microsoft.quantum.guide.filestructure): descreve a estrutura e a sintaxe de um ficheiro Q# `*.qs`.</span><span class="sxs-lookup"><span data-stu-id="718ce-112">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): Describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="718ce-113">[Operações e Funções](xref:microsoft.quantum.guide.operationsfunctions): detalha os dois tipos chamáveis da linguagem Q#: as *operações*, que incluem ações em registos qubit, e as *funções*, que funcionam estritamente com informação clássica.</span><span class="sxs-lookup"><span data-stu-id="718ce-113">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): Details the two callable types of the Q# language: *operations*, which include action on qubit registers, and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="718ce-114">Aqui, pode ver como defini-los e chamá-los, incluindo as versões conjuntas e controladas das operações quânticas.</span><span class="sxs-lookup"><span data-stu-id="718ce-114">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="718ce-115">[Variáveis](xref:microsoft.quantum.guide.variables): descreve a função das variáveis nos programas de Q# e como tirar partido das mesmas eficazmente.</span><span class="sxs-lookup"><span data-stu-id="718ce-115">[Variables](xref:microsoft.quantum.guide.variables): Describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="718ce-116">Por exemplo, pode encontrar informações sobre âmbitos de enlace, bem como a diferença entre variáveis imutáveis e mutáveis e como as atribuir ou reatribuir.</span><span class="sxs-lookup"><span data-stu-id="718ce-116">For example, you can find information about binding scopes, as well as the difference between immutable and mutable variables and how to assign or re-assign them.</span></span>

- <span data-ttu-id="718ce-117">[Trabalhar com qubits](xref:microsoft.quantum.guide.qubits): descreve as funcionalidades de Q# que pode utilizar para trabalhar com qubits individuais e sistemas de qubits, em particular, para os alocar, realizar operações nos mesmos e medi-los.</span><span class="sxs-lookup"><span data-stu-id="718ce-117">[Working with qubits](xref:microsoft.quantum.guide.qubits): Describes the features of Q# used to address individual qubits and systems of qubits, specifically, allocating them, performing operations on them, and measuring them.</span></span> 

- <span data-ttu-id="718ce-118">[Fluxo de Controlo](xref:microsoft.quantum.guide.controlflow): detalha os padrões do fluxo de controlo de programação disponíveis em Q#, o que inclui muitas técnicas padrão (tais como execução condicional, para ciclos, durante ciclos), bem como o padrão "Repeat-Until-Success" (RUS) quântico específico.</span><span class="sxs-lookup"><span data-stu-id="718ce-118">[Control Flow](xref:microsoft.quantum.guide.controlflow): Details the programming control flow patterns available in Q#, which includes many standard techniques (such as conditional execution, for loops, while loops) as well as the quantum-specific "Repeat-Until-Success" pattern.</span></span>

- <span data-ttu-id="718ce-119">[Teste e depuração](xref:microsoft.quantum.guide.testingdebugging): pormenoriza algumas técnicas para confirmar que o código está a fazer o que é suposto.</span><span class="sxs-lookup"><span data-stu-id="718ce-119">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="718ce-120">Devido à opacidade geral da informação quântica, a depuração de programas quânticos pode exigir técnicas especializadas.</span><span class="sxs-lookup"><span data-stu-id="718ce-120">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="718ce-121">Felizmente, o Q# suporta muitas das técnicas de depuração clássicas a que os programadores estão habituados, bem como aquelas que são específicas da tecnologia quântica.</span><span class="sxs-lookup"><span data-stu-id="718ce-121">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="718ce-122">Entre essas técnicas incluem-se a criação e execução de testes de unidades em Q#, a incorporação de *asserções* de valores e probabilidades no seu código e as funções `Dump`, as quais produzem o estado dos computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="718ce-122">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="718ce-123">Estas últimas podem ser utilizadas juntamente com o nosso simulador de estado completo para depurar determinadas partes das computações ao contornar algumas limitações quânticas como, por exemplo, o [teorema da não clonagem](xref:microsoft.quantum.concepts.pauli).</span><span class="sxs-lookup"><span data-stu-id="718ce-123">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="718ce-124">Simuladores Quânticos e Avaliadores de Recursos</span><span class="sxs-lookup"><span data-stu-id="718ce-124">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="718ce-125">[Simuladores quânticos e aplicações anfitriãs](xref:microsoft.quantum.machines): descrição geral dos diferentes simuladores disponíveis, bem como do modelo de execução geral entre programas anfitriões e os computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="718ce-125">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well as the general execution model between host programs and target machines.</span></span>

- <span data-ttu-id="718ce-126">[Simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator): o computador de destino que simula o estado quântico completo.</span><span class="sxs-lookup"><span data-stu-id="718ce-126">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="718ce-127">Útil para executar ou depurar totalmente programas de menor escala (menos do que poucas dezenas de qubits)</span><span class="sxs-lookup"><span data-stu-id="718ce-127">Useful for fully executing or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="718ce-128">[Avaliador de recursos](xref:microsoft.quantum.machines.resources-estimator): calcula os recursos necessários para executar uma determinada instância de uma operação Q# num computador quântico.</span><span class="sxs-lookup"><span data-stu-id="718ce-128">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="718ce-129">[Simulador de rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro): executa um programa quântico sem simular verdadeiramente o estado de um computador quântico e, por conseguinte, consegue executar programas quânticos que utilizam milhares de qubits.</span><span class="sxs-lookup"><span data-stu-id="718ce-129">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Executes a quantum program without actually simulating the state of a quantum computer, and therefore can execute quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="718ce-130">Útil para depurar código clássico num programa quântico, bem como estimar os recursos necessários.</span><span class="sxs-lookup"><span data-stu-id="718ce-130">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="718ce-131">[Simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): simulador quântico com uma finalidade especial que pode ser utilizado com milhões de qubits, mas apenas para programas com um conjunto restrito de operações quânticas: X, CNOT e X com vários controladores.</span><span class="sxs-lookup"><span data-stu-id="718ce-131">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="718ce-132">Páginas de Referência Rápida</span><span class="sxs-lookup"><span data-stu-id="718ce-132">Quick Reference Pages</span></span>

- <span data-ttu-id="718ce-133">[Comandos Magic do IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): página de referência rápida para comandos Magic do IQ# em Blocos de Notas do Jupyter em Q#.</span><span class="sxs-lookup"><span data-stu-id="718ce-133">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
