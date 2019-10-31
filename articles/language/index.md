---
title: A Linguagem de Programação Q# | Microsoft Docs
description: A Linguagem de Programação Q#
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: d8759b9f043d2e13f4b0c97d54bd824c7e87d6de
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035262"
---
# <a name="the-q-programming-language"></a>A Linguagem de Programação Q#

# <a name="introduction"></a>Introdução

Um modelo natural de computação quântica é tratar o computador quântico como coprocessador, semelhante ao que é utilizado em GPUs, FPGAs e outros processadores adjuntos.
A lógica de controlo primária executa código clássico num computador “anfitrião” clássico.
Quando for pertinente e necessário, o programa anfitrião pode invocar uma sub-rotina que é executada no processador adjunto.
Quando a sub-rotina for concluída, o programa anfitrião obtém acesso aos resultados da mesma.

Q# (Q-Sharp) é uma linguagem de programação específica de domínio, utilizada para expressar algoritmos quânticos.
É utilizada para escrever sub-rotinas que são executadas num processador quântico adjunto, sob o controlo de um computador e programa anfitrião clássico.
Até que os processadores quânticos estejam disponíveis ao público em geral, as sub-rotinas Q# são executadas num simulador.

A Q# fornece um pequeno conjunto de tipos primitivos, juntamente com duas formas (matrizes e cadeias de identificação) para criar novos tipos estruturados.
Suporta um modelo processual básico para escrita de programas, com ciclos e instruções if/when.
As construções de nível superior em Q# são tipos, operações e funções definidos por utilizadores.

As secções a seguir detalham:
- [O Modelo de Tipo](xref:microsoft.quantum.language.type-model)
- [Expressões](xref:microsoft.quantum.language.expressions)
- [Instruções](xref:microsoft.quantum.language.statements)
- [Estrutura de Ficheiros](xref:microsoft.quantum.language.file-structure)

# <a name="conventions"></a>Convenções

Estamos a trabalhar no sentido de garantir que os sinais de pontuação comuns são utilizados de forma consistente em todas as situações.
Esperamos que isso torne a Q# mais fácil de aprender e ler, porque estes sinais têm sempre o mesmo significado, e o mesmo conceito é sempre representado da mesma forma.

Mais concretamente:

- O ponto e vírgula, `;`, é utilizado para terminar uma instrução ou diretiva de uma linha.
  Não é utilizado para outros fins.
- A vírgula, `,`, é utilizada para separar os elementos de uma sequência. É utilizada em cadeias de identificação de literais, literais de matrizes, listas de argumentos, definições de cadeias de identificação e listas de tipos. **Ao contrário das versões anteriores, o `;` já não é suportado como um separador de literais de matrizes.**
- Os dois pontos, `:`, são utilizados para introduzir uma anotação de tipo. São sobretudo utilizados em assinaturas disponíveis.
  Uma vez que os dois pontos introduzem sempre uma assinatura de tipo, o operador condicional ternário, introduzido na versão 0.3, utiliza uma barra vertical, `|`, para separar os valores verdadeiros e falsos; por conseguinte, Q# utiliza `cond ? tval | fval` em vez do separador de dois pontos, tal como em C.
  
