---
title: Matemática nas Q# bibliotecas padrão
description: Conheça as funções matemáticas clássicas nas Q# bibliotecas padrão que são usadas com os tipos de dados incorporados.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4a3747eaa2c91e482ded3af1279a0e40d922bfb3
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868428"
---
# <a name="classical-mathematical-functions"></a>Funções Matemáticas Clássicas #

Estas funções são usadas principalmente para trabalhar com os Q# tipos de dados incorporados, `Int` e `Double` `Range` .

A <xref:microsoft.quantum.intrinsic.random> operação tem `(Double[] => Int)` assinatura.
Requer uma série de duplos como entrada, e devolve um índice selecionado aleatoriamente para a matriz como um `Int` .
A probabilidade de selecionar um índice específico é proporcional ao valor do elemento matriz nesse índice. n Elementos de matriz que são iguais a zero são ignorados e os seus índices nunca são devolvidos.
Se qualquer elemento de matriz for inferior a zero, ou se nenhum elemento de matriz for maior que zero, então a operação falha.
