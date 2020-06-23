---
title: Introdução às bibliotecas padrão de Q# da Microsoft
description: Saiba mais sobre as bibliotecas padrão de Q# da Microsoft que definam as operações, as funções e os tipos de dados que são utilizados em programas quânticos.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
ms.openlocfilehash: 820ad885e7134aa723116d4c9f853d88210a5514
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273815"
---
# <a name="introduction-to-the-q-standard-libraries"></a>Introdução às Bibliotecas Padrão Q# #

A linguagem Q# é suportada por uma série de diferentes operações, funções e tipos definidos pelo utilizador úteis que constituem as *bibliotecas padrão* Q#.
O [pacote NuGet `Microsoft.Quantum.Development.Kit`](https://www.nuget.org/packages/microsoft.quantum.development.kit) instalado durante a [instalação e validação](xref:microsoft.quantum.install) fornece o compilador Q# e partes da biblioteca padrão que são implementadas pelos computadores de destino.
O [pacote `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) fornece a parte das bibliotecas padrão Q# que são portáteis entre computadores de destino.

Os símbolos definidos pelas bibliotecas padrão Q# são definidos com detalhes muito maiores e mais completos na [documentação da API](xref:microsoft.quantum.standardlibsintro).

Nas secções seguintes, vamos descrever as funcionalidades mais relevantes de cada parte da biblioteca padrão e fornecer contexto sobre como cada funcionalidade pode ser utilizada na prática.
