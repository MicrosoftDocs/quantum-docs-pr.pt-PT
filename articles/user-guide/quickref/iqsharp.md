---
title: Comandos Magic do IQ#
description: Página de referência rápida para comandos mágicos IQ# com Cadernos Q# Jupyter
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431024"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="090b3-103">Comandos Magic do IQ#</span><span class="sxs-lookup"><span data-stu-id="090b3-103">IQ# Magic Commands</span></span>

### <a name="general"></a><span data-ttu-id="090b3-104">Geral</span><span class="sxs-lookup"><span data-stu-id="090b3-104">General</span></span>

- <span data-ttu-id="090b3-105">`%config`: Define ou obtém preferências de configuração.</span><span class="sxs-lookup"><span data-stu-id="090b3-105">`%config`: Sets or gets configuration preferences.</span></span>
- <span data-ttu-id="090b3-106">`%estimate`: Executa uma determinada função ou funcionamento na máquina-alvo QuantumSimulator.</span><span class="sxs-lookup"><span data-stu-id="090b3-106">`%estimate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="090b3-107">`%lsmagic`: Devolve uma lista de todos os comandos mágicos atualmente disponíveis.</span><span class="sxs-lookup"><span data-stu-id="090b3-107">`%lsmagic`: Returns a list of all currently available magic commands.</span></span>
- <span data-ttu-id="090b3-108">`%package`: Fornece a capacidade de carregar um pacote Nuget.</span><span class="sxs-lookup"><span data-stu-id="090b3-108">`%package`: Provides the ability to load a Nuget package.</span></span>
- <span data-ttu-id="090b3-109">`%performance`: Reporta as métricas de desempenho atuais para este núcleo.</span><span class="sxs-lookup"><span data-stu-id="090b3-109">`%performance`: Reports current performance metrics for this kernel.</span></span>
- <span data-ttu-id="090b3-110">`%simulate`: Executa uma determinada função ou funcionamento na máquina-alvo QuantumSimulator.</span><span class="sxs-lookup"><span data-stu-id="090b3-110">`%simulate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="090b3-111">`%toffoli`: Funciona com uma determinada função ou funcionamento na máquina-alvo do simulador ToffoliSimulator.</span><span class="sxs-lookup"><span data-stu-id="090b3-111">`%toffoli`: Runs a given function or operation on the ToffoliSimulator simulator target machine.</span></span>
- <span data-ttu-id="090b3-112">`%who`: Fornece ações relacionadas com o espaço de trabalho atual.</span><span class="sxs-lookup"><span data-stu-id="090b3-112">`%who`: Provides actions related to the current workspace.</span></span>
- <span data-ttu-id="090b3-113">`%workspace`: Devolve uma lista de todas as operações e funções definidas na sessão atual, interactivamente ou carregadas a partir do atual espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="090b3-113">`%workspace`: Returns a list of all operations and functions defined in the current session, either interactively or loaded from the current workspace.</span></span>

### <a name="chemistry"></a><span data-ttu-id="090b3-114">Química</span><span class="sxs-lookup"><span data-stu-id="090b3-114">Chemistry</span></span>

- <span data-ttu-id="090b3-115">`%chemistry.broombridge`: Cargas e devoluções Broombridge electronic structure problem representation from a given .yaml file.</span><span class="sxs-lookup"><span data-stu-id="090b3-115">`%chemistry.broombridge`: Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span>
- <span data-ttu-id="090b3-116">`%chemistry.encode`: Codifica um fermion Hamiltonian a um formato consumível por Q#.</span><span class="sxs-lookup"><span data-stu-id="090b3-116">`%chemistry.encode`: Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span>
- <span data-ttu-id="090b3-117">`%chemistry.fh.add_terms`: Adiciona termos a um fermion Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="090b3-117">`%chemistry.fh.add_terms`: Adds terms to a fermion Hamiltonian.</span></span>
- <span data-ttu-id="090b3-118">`%chemistry.fh.load`: Carrega o fermion Hamiltonian para um problema de estrutura electrónica.</span><span class="sxs-lookup"><span data-stu-id="090b3-118">`%chemistry.fh.load`: Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="090b3-119">O problema é carregado a partir de um ficheiro ou transmitido como argumento.</span><span class="sxs-lookup"><span data-stu-id="090b3-119">The problem is loaded from a file or passed as an argument.</span></span>
- <span data-ttu-id="090b3-120">`%chemistry.inputstate.load`: Problema da estrutura electrónica de Broombridge e devoluções selecionados estado de entrada.</span><span class="sxs-lookup"><span data-stu-id="090b3-120">`%chemistry.inputstate.load`: Loads Broombridge electronic structure problem and returns selected input state.</span></span>

### <a name="from-microsoftquantumkatas-package"></a><span data-ttu-id="090b3-121">Do pacote Microsoft.Quantum.Katas</span><span class="sxs-lookup"><span data-stu-id="090b3-121">From Microsoft.Quantum.Katas package</span></span>

- <span data-ttu-id="090b3-122">`%kata`: Executa um único teste e informa se o teste passou com sucesso.</span><span class="sxs-lookup"><span data-stu-id="090b3-122">`%kata`: Executes a single test, and reports whether the test passed successfully.</span></span>
- <span data-ttu-id="090b3-123">`%check_kata`: Verifica a aplicação de referência para um único teste de kata.</span><span class="sxs-lookup"><span data-stu-id="090b3-123">`%check_kata`: Checks the reference implementation for a single kata's test.</span></span>
    <span data-ttu-id="090b3-124">Especificamente, substitui a implementação de referência por uma única tarefa na célula, e informa se o teste passou com sucesso.</span><span class="sxs-lookup"><span data-stu-id="090b3-124">Specifically, it substitutes the reference implementation for a single task into the cell, and reports whether the test passed successfully.</span></span>
