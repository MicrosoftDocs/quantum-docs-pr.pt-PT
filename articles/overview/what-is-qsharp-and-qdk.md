---
title: O que é a linguagem de programação Q# e o QDK?
description: Saiba mais sobre o Microsoft Quantum Development kit e a linguagem de programação Q# e aprenda a criar programas quânticos.
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.q-sharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 21adfcc1c5321d87665adb39a3c838bbda0b8861
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834572"
---
# <a name="what-are-the-no-locq-programming-language-and-qdk"></a>O que é a linguagem de programação Q# e o QDK?

O Q# é a linguagem de programação open-source da Microsoft para desenvolver e executar algoritmos quânticos. Faz parte do Quantum Development Kit (QDK), que inclui [bibliotecas Q#](xref:microsoft.quantum.libraries), [simuladores quânticos](xref:microsoft.quantum.machines), [extensões para outros ambientes de programação](xref:microsoft.quantum.install) e [documentação de API](xref:microsoft.quantum.apiref-intro). Além da biblioteca Q# padrão, o QDK inclui bibliotecas de Química, Machine Learning e Numéricas.

Enquanto linguagem de programação, o Q# tem elementos familiares de Python, C# e F# e suporte um modelo procedimental básico para escrever programas com ciclos, instruções if/then e tipos de dados comuns. Também introduz operações e estruturas de dados específicas da computação quântica.

## <a name="what-can-i-do-with-the-qdk"></a>O que posso fazer com o QDK?

O QDK é um development kit completo para Q# que pode ser utilizado com ferramentas e linguagens comuns para o desenvolvimento de aplicações quânticas que pode executar em vários ambientes. Os programas em Q# podem ser executados como aplicação de consola através do Jupyter Notebook ou podem utilizar um programa anfitrião do Python ou .NET.

### <a name="develop-in-common-tools-and-environments"></a>Desenvolver com ferramentas e em ambientes comuns

Integre o seu desenvolvimento quântico no [Visual Studio, no Visual Studio Code](xref:microsoft.quantum.install.standalone) e no [Jupyter Notebook](xref:microsoft.quantum.install.jupyter). Utilize as APIs incorporadas para emparelhar os programas com as linguagens anfitriãs [Python](xref:microsoft.quantum.install.python) e [.NET](xref:microsoft.quantum.install.cs).

### <a name="try-quantum-operations-and-domain-specific-libraries"></a>Experimentar operações quânticas e bibliotecas de domínios específicos

Escreva e teste algoritmos quânticos para explorar a sobreposição, o entrelaçamento e outras operações quânticas. Com as bibliotecas Q#, pode executar operações quânticas complexas sem ter de desenhar sequências de operações de nível inferior.

### <a name="run-programs-in-simulators"></a>Executar programas em simuladores

Execute os seus programas quânticos num simulador quântico de estado completo, um simulador Toffoli de âmbito limitado. ou teste o seu código Q# em avaliadores de recursos diferentes. 

## <a name="where-can-i-learn-more"></a>Onde posso saber mais?

|||
| ---- | ---- |
| **Não estou familiarizado com a computação quântica** | Reveja algumas noções básicas da física quântica e da computação quântica nos [Conceitos-chave](xref:microsoft.quantum.overview.understanding).|
| **Quero perceber melhor a linguagem Q#** | Explore tipos, expressões, variáveis e a estrutura dos programas quânticos no [Guia do Utilizador do Q#](xref:microsoft.quantum.guide).|
| **Quero simplesmente começar a escrever programas quânticos** | Configure o seu ambiente Q# e comece a escrever programas quânticos nos [Inícios Rápidos](xref:microsoft.quantum.install).|

## <a name="how-does-no-locq-work"></a>Como funciona o Q#?

Os programas em Q# podem ser compilados numa aplicação autónoma ou ser chamados por um programa anfitrião escrito nas linguagens Python ou .NET.

Quando compila e executa o programa, o mesmo cria uma instância do simulador quântico e transmite-lhe o código Q#. O simulador utiliza o código Q# para criar qubits (simulações de partículas quânticas) e aplica as transformações para modificar o estado dos mesmos. Os resultados das operações quânticas no simulador são, depois, devolvidos ao programa.  

Isolar o código Q# no simulador garante que os algoritmos seguem as leis da física quântica e que podem ser executados corretamente em computadores quânticos.

![Fluxo de código Qsharp](~/media/qsharp-code-flow.png)

## <a name="how-do-i-use-the-qdk"></a>Como utilizo o QDK?

Tudo aquilo de que precisa para escrever e executar programas em Q#, incluindo o compilador de Q#, as bibliotecas Q# e os simuladores quânticos, pode ser instalado e executado no seu computador local. Chegará o momento em que poderá executar os programas em Q# remotamente num computador quântico real; contudo, até lá, os simuladores quânticos disponibilizados com o QDK dão resultados precisos e fiáveis.

- Desenvolver [ aplicações Q#](xref:microsoft.quantum.install.standalone) é a forma mais rápida de começar.

- Execute o [Jupyter Notebook com o IQ#](xref:microsoft.quantum.install.jupyter), uma extensão do Jupyter para compilar, simular e visualizar programas em Q#.

- Se estiver familiarizado com [Python](xref:microsoft.quantum.install.python), pode utilizá-lo como plataforma de programação anfitriã para começar. O Python é muito utilizado não só entre os programadores, mas também por cientistas, investigadores e professores.

- Se já tiver experiência com [C#, F# ou VB.NET](xref:microsoft.quantum.install.cs) e estiver familiarizado com o ambiente de desenvolvimento do Visual Studio, só precisa de adicionar algumas extensões ao Visual Studio para o preparar para Q#.  

## <a name="summary"></a>Resumo

O Q# é uma linguagem de programação open-source para desenvolver programas quânticos. Tem bibliotecas que lhe permitem criar operações quânticas complexas e simuladores quânticos para executar e testar os seus programas corretamente. Os programas em Q# podem ser executados como aplicações autónomas ou ser chamados a partir de um programa anfitrião Python ou .NET e podem ser escritos, executados e testados no seu computador local.

## <a name="next-steps"></a>Passos Seguintes

[Álgebra linear para computação quântica](xref:microsoft.quantum.overview.algebra)
