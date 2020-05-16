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
# <a name="iq-magic-commands"></a>Comandos Magic do IQ#

### <a name="general"></a>Geral

- `%config`: Define ou obtém preferências de configuração.
- `%estimate`: Executa uma determinada função ou funcionamento na máquina-alvo QuantumSimulator.
- `%lsmagic`: Devolve uma lista de todos os comandos mágicos atualmente disponíveis.
- `%package`: Fornece a capacidade de carregar um pacote Nuget.
- `%performance`: Reporta as métricas de desempenho atuais para este núcleo.
- `%simulate`: Executa uma determinada função ou funcionamento na máquina-alvo QuantumSimulator.
- `%toffoli`: Funciona com uma determinada função ou funcionamento na máquina-alvo do simulador ToffoliSimulator.
- `%who`: Fornece ações relacionadas com o espaço de trabalho atual.
- `%workspace`: Devolve uma lista de todas as operações e funções definidas na sessão atual, interactivamente ou carregadas a partir do atual espaço de trabalho.

### <a name="chemistry"></a>Química

- `%chemistry.broombridge`: Cargas e devoluções Broombridge electronic structure problem representation from a given .yaml file.
- `%chemistry.encode`: Codifica um fermion Hamiltonian a um formato consumível por Q#.
- `%chemistry.fh.add_terms`: Adiciona termos a um fermion Hamiltonian.
- `%chemistry.fh.load`: Carrega o fermion Hamiltonian para um problema de estrutura electrónica. O problema é carregado a partir de um ficheiro ou transmitido como argumento.
- `%chemistry.inputstate.load`: Problema da estrutura electrónica de Broombridge e devoluções selecionados estado de entrada.

### <a name="from-microsoftquantumkatas-package"></a>Do pacote Microsoft.Quantum.Katas

- `%kata`: Executa um único teste e informa se o teste passou com sucesso.
- `%check_kata`: Verifica a aplicação de referência para um único teste de kata.
    Especificamente, substitui a implementação de referência por uma única tarefa na célula, e informa se o teste passou com sucesso.
