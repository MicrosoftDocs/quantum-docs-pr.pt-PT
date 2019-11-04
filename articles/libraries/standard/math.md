---
title: 'P # bibliotecas padrão-matemática | Microsoft Docs'
description: 'P # bibliotecas padrão-matemática'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 7ac9d321f59f7cc95ad8939a4cf7c36e0c5e0491
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184462"
---
# <a name="classical-mathematical-functions"></a>Funções matemáticas clássicas #

Essas funções são usadas principalmente para trabalhar com os tipos de dados internos Q # `Int`, `Double`e `Range`.

A operação de <xref:microsoft.quantum.intrinsic.random> tem `(Double[] => Int)`de assinatura.
Ele usa uma matriz de duplicatas como entrada e retorna um índice selecionado aleatoriamente para a matriz como um `Int`.
A probabilidade de selecionar um índice específico é proporcional ao valor do elemento de matriz nesse índice. n elementos da matriz que são iguais a zero são ignorados e seus índices nunca são retornados.
Se qualquer elemento de matriz for menor que zero, ou se nenhum elemento de matriz for maior que zero, a operação falhará.