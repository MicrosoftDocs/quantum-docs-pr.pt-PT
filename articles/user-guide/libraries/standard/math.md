---
title: Matemática nas bibliotecas padrão Q#
description: Conheça as funções de matemática clássicas nas bibliotecas padrão Q# que são usadas com os tipos de dados incorporados.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275659"
---
# <a name="classical-mathematical-functions"></a>Funções Matemáticas Clássicas #

Estas funções são usadas principalmente para trabalhar com os tipos de dados incorporados Q# `Int` `Double` , e `Range` .

A <xref:microsoft.quantum.intrinsic.random> operação tem `(Double[] => Int)` assinatura.
Requer uma série de duplos como entrada, e devolve um índice selecionado aleatoriamente para a matriz como um `Int` .
A probabilidade de selecionar um índice específico é proporcional ao valor do elemento matriz nesse índice. n Elementos de matriz que são iguais a zero são ignorados e os seus índices nunca são devolvidos.
Se qualquer elemento de matriz for inferior a zero, ou se nenhum elemento de matriz for maior que zero, então a operação falha.
