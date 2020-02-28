---
title: Matemática nas bibliotecas padrão Q#
description: Conheça as funções matemáticaclássicas nas bibliotecas padrão Q# que são usadas com os tipos de dados incorporados.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906156"
---
# <a name="classical-mathematical-functions"></a>Funções Matemáticas Clássicas #

Estas funções são usadas principalmente para trabalhar com os tipos de dados incorporados Q# `Int`, `Double`e `Range`.

A operação <xref:microsoft.quantum.intrinsic.random> tem `(Double[] => Int)`de assinatura.
Leva uma série de duplos como entrada, e devolve um índice selecionado aleatoriamente na matriz como um `Int`.
A probabilidade de selecionar um índice específico é proporcional ao valor do elemento matriz nesse índice. n Elementos matrizes que são iguais a zero são ignorados e os seus índices nunca são devolvidos.
Se qualquer elemento de matriz for inferior a zero, ou se nenhum elemento de matriz for superior a zero, então a operação falha.
