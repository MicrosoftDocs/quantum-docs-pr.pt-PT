---
title: Matemática nas Q# bibliotecas padrão
description: Conheça as funções matemáticas clássicas nas Q# bibliotecas padrão que são usadas com os tipos de dados incorporados.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6de1574341d67c569cd2f040ec533e263fdd386e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692052"
---
# <a name="classical-mathematical-functions"></a>Funções Matemáticas Clássicas #

Estas funções são usadas principalmente para trabalhar com os Q# tipos de dados incorporados, `Int` e `Double` `Range` .

A <xref:Microsoft.Quantum.Intrinsic.Random> operação tem `(Double[] => Int)` assinatura.
Requer uma série de duplos como entrada, e devolve um índice selecionado aleatoriamente para a matriz como um `Int` .
A probabilidade de selecionar um índice específico é proporcional ao valor do elemento matriz nesse índice. n Elementos de matriz que são iguais a zero são ignorados e os seus índices nunca são devolvidos.
Se qualquer elemento de matriz for inferior a zero, ou se nenhum elemento de matriz for maior que zero, então a operação falha.
