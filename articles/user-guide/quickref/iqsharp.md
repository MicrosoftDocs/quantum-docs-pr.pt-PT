---
title: I Q# Comandos Mágicos
description: Página de referência rápida para Q# i comandos mágicos com Q# Cadernos Jupyter
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1d2d092588e1a5c69d12e5d50377e3e26412c094
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863701"
---
# <a name="ino-locq-magic-commands"></a>I Q# Comandos Mágicos

### <a name="general"></a>Geral

- [`%config`](xref:microsoft.quantum.iqsharp.magic-ref.config): Permite opções de configuração de configuração ou consulta.
- [`%estimate`](xref:microsoft.quantum.iqsharp.magic-ref.estimate): Executa uma determinada função ou funcionamento na máquina-alvo ResourcesEstimator.
- [`%lsmagic`](xref:microsoft.quantum.iqsharp.magic-ref.lsmagic): Devolve uma lista de todos os comandos mágicos atualmente disponíveis.
- [`%lsopen`](xref:microsoft.quantum.iqsharp.magic-ref.lsopen)Listas atualmente abertas espaços de nome e seus pseudónimos.
- [`%package`](xref:microsoft.quantum.iqsharp.magic-ref.package): Fornece a capacidade de carregar um pacote NuGet.
- [`%performance`](xref:microsoft.quantum.iqsharp.magic-ref.performance): Relatórios atuais das métricas de desempenho para este núcleo.
- [`%project`](xref:microsoft.quantum.iqsharp.magic-ref.project): Fornece a capacidade de visualizar ou adicionar referências de Q# projeto. 
- [`%simulate`](xref:microsoft.quantum.iqsharp.magic-ref.simulate): Executa uma determinada função ou funcionamento na máquina alvo quantumSimulator.
- [`%toffoli`](xref:microsoft.quantum.iqsharp.magic-ref.toffoli): Executa uma determinada função ou funcionamento na máquina alvo ToffoliSimulator.
- [`%who`](xref:microsoft.quantum.iqsharp.magic-ref.who): Lista as Q# operações disponíveis na sessão em curso.
- [`%workspace`](xref:microsoft.quantum.iqsharp.magic-ref.workspace): Fornece ações relacionadas com o espaço de trabalho atual.

### <a name="azure-quantum-integration"></a>Integração quântica Azure

- [`%azure.connect`](xref:microsoft.quantum.iqsharp.magic-ref.azure.connect): Liga-se a um espaço de trabalho Azure Quantum ou apresenta o estado atual da ligação.
- [`%azure.execute`](xref:microsoft.quantum.iqsharp.magic-ref.azure.execute): Executa um trabalho num espaço de trabalho Azure Quantum.
- [`%azure.jobs`](xref:microsoft.quantum.iqsharp.magic-ref.azure.jobs): Apresenta uma lista de postos de trabalho no atual espaço de trabalho Azure Quantum.
- [`%azure.output`](xref:microsoft.quantum.iqsharp.magic-ref.azure.output): Apresenta resultados para um trabalho no atual espaço de trabalho Azure Quantum.
- [`%azure.status`](xref:microsoft.quantum.iqsharp.magic-ref.azure.status): Apresenta o estado de um trabalho no atual espaço de trabalho Azure Quantum.
- [`%azure.submit`](xref:microsoft.quantum.iqsharp.magic-ref.azure.submit): Submete um emprego a um espaço de trabalho Azure Quantum.
- [`%azure.target`](xref:microsoft.quantum.iqsharp.magic-ref.azure.target): Define ou apresenta o alvo de execução ativo para Q# a submissão de emprego num espaço de trabalho Azure Quantum.

### <a name="chemistry-from-microsoftquantumchemistry-package"></a>Chemistry (do pacote Microsoft.Quantum.Chemistry)

- [`%chemistry.broombridge`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.broombridge): Cargas e devoluções Representação de problemas de estrutura electrónica de Broombridge a partir de um dado ficheiro .yaml.
- [`%chemistry.encode`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.encode): Codifica um fermion Hamiltonian a um formato consumível por Q# .
- [`%chemistry.fh.add_terms`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.add_terms): Adiciona termos a um fermion Hamiltonian.
- [`%chemistry.fh.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.fh.load): Carrega o fermion Hamiltonian para um problema de estrutura electrónica. O problema é carregado a partir de um ficheiro ou transmitido como argumento.
- [`%chemistry.inputstate.load`](xref:microsoft.quantum.iqsharp.magic-ref.chemistry.inputstate.load): Carrega o problema da estrutura electrónica de Broombridge e devolve o estado de entrada selecionado.

### <a name="katas-from-microsoftquantumkatas-package"></a>Katas (do pacote Microsoft.Quantum.Katas)

- [`%kata`](xref:microsoft.quantum.iqsharp.magic-ref.kata): Executa um único teste e informa se o teste passou com sucesso.
- [`%check_kata`](xref:microsoft.quantum.iqsharp.magic-ref.check_kata): Verifica a aplicação de referência para um único teste de kata.
    Especificamente, substitui a implementação de referência para uma única tarefa na célula, e informa se o teste passou com sucesso.
