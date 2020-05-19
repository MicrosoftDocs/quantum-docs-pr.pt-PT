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
# <a name="the-q-user-guide"></a><span data-ttu-id="68ef1-103">Guia de Utilizador Q#</span><span class="sxs-lookup"><span data-stu-id="68ef1-103">The Q# User Guide</span></span>

<span data-ttu-id="68ef1-104">Bem-vindo ao Guia de Utilizador Q#!</span><span class="sxs-lookup"><span data-stu-id="68ef1-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="68ef1-105">Aqui, detalhamos os conceitos fundamentais da linguagem Q# e toda a informação de que precisa para escrever programas quânticos.</span><span class="sxs-lookup"><span data-stu-id="68ef1-105">Here we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="68ef1-106">Índice do Guia de Utilizador</span><span class="sxs-lookup"><span data-stu-id="68ef1-106">User Guide Contents</span></span>

- <span data-ttu-id="68ef1-107">[Noções Básicas de Q#](xref:microsoft.quantum.guide.basics): descrição geral introdutória da finalidade e funcionalidade da linguagem de programação Q#.</span><span class="sxs-lookup"><span data-stu-id="68ef1-107">[Q# Basics](xref:microsoft.quantum.guide.basics): an introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

### <a name="q-language"></a><span data-ttu-id="68ef1-108">Linguagem Q#</span><span class="sxs-lookup"><span data-stu-id="68ef1-108">Q# Language</span></span>

- <span data-ttu-id="68ef1-109">[Tipos em Q#](xref:microsoft.quantum.guide.types): destaca o modelo de tipos em Q# e descreve a sintaxe para especificar e trabalhar com tipos.</span><span class="sxs-lookup"><span data-stu-id="68ef1-109">[Types in Q#](xref:microsoft.quantum.guide.types): lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="68ef1-110">[Expressões de Tipos](xref:microsoft.quantum.guide.expressions): detalha como especificar, referenciar, combinar e operar nos valores de cada tipo em Q#.</span><span class="sxs-lookup"><span data-stu-id="68ef1-110">[Type Expressions](xref:microsoft.quantum.guide.expressions): details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-q"></a><span data-ttu-id="68ef1-111">Utilizar o Q#</span><span class="sxs-lookup"><span data-stu-id="68ef1-111">Using Q#</span></span>

- <span data-ttu-id="68ef1-112">[Estrutura de Ficheiros Q#](xref:microsoft.quantum.guide.filestructure): descreve a estrutura e a sintaxe de um ficheiro Q# `*.qs`.</span><span class="sxs-lookup"><span data-stu-id="68ef1-112">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="68ef1-113">[Operações e Funções](xref:microsoft.quantum.guide.operationsfunctions): detalha os dois tipos chamáveis da linguagem Q#, as *operações*, que incluem ações em qubits, e as *funções*, que funcionam estritamente com informação clássica.</span><span class="sxs-lookup"><span data-stu-id="68ef1-113">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): details the two callable types of the Q# language: *operations*, which include action on qubit registers and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="68ef1-114">Aqui, pode ver como defini-los e chamá-los, incluindo as versões conjuntas e controladas das operações quânticas.</span><span class="sxs-lookup"><span data-stu-id="68ef1-114">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="68ef1-115">[Variáveis](xref:microsoft.quantum.guide.variables): descreve a função das variáveis nos programas de Q# e como tirar partido das mesmas eficazmente.</span><span class="sxs-lookup"><span data-stu-id="68ef1-115">[Variables](xref:microsoft.quantum.guide.variables): describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="68ef1-116">Por exemplo, pode encontrar informações sobre âmbitos de enlace, bem como a diferença entre variáveis imutáveis/mutáveis e como atribuir/reatribuí-las.</span><span class="sxs-lookup"><span data-stu-id="68ef1-116">For example, you can find information about binding scopes, as well as the difference between immutable/mutable variables and how to assign/re-assign them.</span></span>

- <span data-ttu-id="68ef1-117">[Trabalhar com qubits](xref:microsoft.quantum.guide.qubits): descreve as funcionalidades de Q# que pode utilizar para trabalhar com qubits individuais e sistemas de qubits.</span><span class="sxs-lookup"><span data-stu-id="68ef1-117">[Working with qubits](xref:microsoft.quantum.guide.qubits): describes the features of Q# used to address individual qubits and systems of qubits.</span></span> 
    <span data-ttu-id="68ef1-118">Mais especificamente, implica a respetiva alocação, realizar operações nos mesmos e, por fim, a medição dos mesmos.</span><span class="sxs-lookup"><span data-stu-id="68ef1-118">Specifically, that entails their allocation, performing operations on them, and ultimately their measurement.</span></span> 

- <span data-ttu-id="68ef1-119">[Fluxo de Controlo](xref:microsoft.quantum.guide.controlflow): detalha os padrões do fluxo de controlo de programação disponíveis em Q#, que inclui muitas técnicas padrão (execução condicional, para ciclos, durante ciclos, etc.), bem como o padrão "Repetir-Até-Obter-Êxito" quântico específico.</span><span class="sxs-lookup"><span data-stu-id="68ef1-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): details the programming control flow patterns available in Q#, which includes many standard techniques (conditional execution, for loops, while loops, etc.) as well as the quantum-specific "Repeat-Until-Success" pattern.</span></span>

- <span data-ttu-id="68ef1-120">[Teste e depuração](xref:microsoft.quantum.guide.testingdebugging): pormenoriza algumas técnicas para confirmar que o código está a fazer o que é suposto.</span><span class="sxs-lookup"><span data-stu-id="68ef1-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="68ef1-121">Devido à opacidade geral da informação quântica, a depuração de programas quânticos pode exigir técnicas especializadas.</span><span class="sxs-lookup"><span data-stu-id="68ef1-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="68ef1-122">Felizmente, a Q# suporta muitas das técnicas de depuração clássicas a que os programadores estão habituados, bem como aquelas que são específicas da tecnologia quântica.</span><span class="sxs-lookup"><span data-stu-id="68ef1-122">Fortunately, Q# supports many of the classical debugging techniques programmers are used to, as well as those that are quantum-specific.</span></span> <span data-ttu-id="68ef1-123">Entre essas técnicas incluem-se a criação/execução de testes de unidade em Q#, a incorporação de *asserções* em valores e probabilidades do código e as funções `Dump` que produzem o estado da máquina de destino.</span><span class="sxs-lookup"><span data-stu-id="68ef1-123">These include creating/running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the state of target machine.</span></span> 
    <span data-ttu-id="68ef1-124">Estas últimas podem ser utilizadas juntamente com o nosso simulador de estado completo para depurar determinadas partes das computações ao contornar algumas limitações quânticas (por exemplo, o teorema da não clonagem).</span><span class="sxs-lookup"><span data-stu-id="68ef1-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations (e.g. the no-cloning theorem).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="68ef1-125">Simuladores Quânticos e Avaliadores de Recursos</span><span class="sxs-lookup"><span data-stu-id="68ef1-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="68ef1-126">[Simuladores quânticos e aplicações anfitriãs](xref:microsoft.quantum.machines): descrição geral dos diferentes simuladores disponíveis, bem como o modelo de execução geral entre o programa anfitrião e os computadores de destino.</span><span class="sxs-lookup"><span data-stu-id="68ef1-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): an overview of the different simulators available, as well as the general execution model between host program and target machines.</span></span>

- <span data-ttu-id="68ef1-127">[Simulador de estado completo](xref:microsoft.quantum.machines.full-state-simulator): o computador de destino que simula o estado quântico completo.</span><span class="sxs-lookup"><span data-stu-id="68ef1-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): the target machine which simulates the full quantum state.</span></span> <span data-ttu-id="68ef1-128">Útil para executar ou depurar totalmente programas de menor escala (menos de umas dezenas de qubits)</span><span class="sxs-lookup"><span data-stu-id="68ef1-128">Useful for fully executing or debugging smaller scale programs (less than a couple dozen qubits)</span></span>

- <span data-ttu-id="68ef1-129">[Avaliador de recursos](xref:microsoft.quantum.machines.resources-estimator): estima os recursos necessários para executar uma determinada instância de uma operação Q# num computador quântico.</span><span class="sxs-lookup"><span data-stu-id="68ef1-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="68ef1-130">[Simulador de rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro): executa um programa quântico sem simular verdadeiramente o estado de um computador quântico e, por conseguinte, consegue executar programas quânticos que utilizam milhares de qubits.</span><span class="sxs-lookup"><span data-stu-id="68ef1-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): executes a quantum program without actually simulating the state of a quantum computer, and therefore can execute quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="68ef1-131">Útil para depurar código clássico num programa quântico, bem como estimar os recursos necessários.</span><span class="sxs-lookup"><span data-stu-id="68ef1-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="68ef1-132">[Simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator): simulador quântico com uma finalidade especial que pode ser utilizado com milhões de qubits, mas apenas para programas com um conjunto restrito de operações quânticas (nomeadamente X, CNOT e X multi-controlados).</span><span class="sxs-lookup"><span data-stu-id="68ef1-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): a special purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations (namely X, CNOT, and multi-controlled X).</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="68ef1-133">Páginas de Referência Rápida</span><span class="sxs-lookup"><span data-stu-id="68ef1-133">Quick Reference Pages</span></span>

- <span data-ttu-id="68ef1-134">[Comandos Magic do IQ#](xref:microsoft.quantum.guide.quickref.iqsharp): página de referência rápida para comandos Magic do IQ# em Blocos de Notas do Jupyter em Q#.</span><span class="sxs-lookup"><span data-stu-id="68ef1-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
