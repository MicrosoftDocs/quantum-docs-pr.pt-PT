---
title: Técnicas de desenvolvimento quântico
description: Aprenda as noções básicas do desenvolvimento de programas Q#, a trabalhar com operações, funções, variáveis e qubits e, ainda, a criar um programa quântico simples.
keywords: Não adicione nem edite as palavras-chave sem consultar o perito em SEO.
author: QuantumWriter
ms.author: MSFT-alias-person-or-DL
ms.date: 9/20/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.techniques.intro
ms.openlocfilehash: e5b7fbde18afbc0333d89f70c5e4596848e30f4f
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907720"
---
# <a name="quantum-development-techniques"></a>Técnicas de Desenvolvimento Quântico

Esta secção da documentação detalha os conceitos principais utilizados para criar programas quânticos em Q# e para interagir com esses programas em programas clássicos.
Partimos do princípio de que já tem *alguns* conhecimentos de conceitos de computação quântica, como os descritos em [Conceitos da computação quântica](xref:microsoft.quantum.concepts.intro). Contudo, para tirar o máximo partido destas secções, não tem de ser especialista em computação quântica.

Os conteúdos das secções são:

- [Descrição geral de programas de Q#](xref:microsoft.quantum.techniques.file-structure), que mostra uma descrição geral da finalidade e da funcionalidade da linguagem de programação Q#. 
    Em particular, esclarece como é que a Q# *não* é uma linguagem para meramente simular mecânicas quânticas, embora essa funcionalidade seja, como é óbvio, fornecida pelo nosso simulador de estado completo. 
    Pelo contrário, a Q# foi concebida tendo em conta o futuro e os respetivos programas descrevem de que forma é que os computadores de controlo clássicos *interagem* com qubits. 

- [Operações e funções](xref:microsoft.quantum.techniques.opsandfunctions), que detalha os dois tipos chamáveis da linguagem Q#, as *operações*, que incluem ações em qubits e em sistemas quânticos, e as *funções*, que funcionam estritamente com informação clássica. 
    Se as informações clássicas e quânticas não funcionarem em conjunto, a computação quântica estaria fora de alcance. 
    Esta secção descreve como definir e utilizar estas operações chamáveis a partir do fluxo de controlo de um programa de Q#.

- [Variáveis locais](xref:microsoft.quantum.techniques.local-variables), que descreve a função das variáveis nos programas de Q# e como tirar partido das mesmas eficazmente. 
    Mais concretamente, vai aprender as diferenças entre as variáveis imutáveis e mutáveis e como as atribuir e reatribuir.

- [Trabalhar com qubits](xref:microsoft.quantum.techniques.qubits), que descreve as funcionalidades da Q# que pode utilizar para trabalhar com qubits individuais e sistemas de qubits. 
    Mais especificamente, implica a respetiva alocação, realizar operações nos mesmos e, por fim, a medição dos mesmos. 
    Além disso, vai aprender algumas técnicas de fluxo de controlo úteis.

- [Juntar tudo](xref:microsoft.quantum.techniques.puttingittogether), em que se vai servir das técnicas das secções anteriores para criar um programa que realiza **teletransporte quântico**, através da utilização de dois bits clássicos para "teletransportar" o estado completo de um qubit para outro.

- [Fazer mais](xref:microsoft.quantum.techniques.going-further), que apresenta técnicas avançadas que se podem revelar importantes à medida que avança para uma programação quântica mais complexa. 
    Em particular, abordamos a utilização de operações *parametrizadas por tipo* e as funções na Q#, que permitem um fluxo de controlo de ordem superior ao se manterem agnósticas em termos dos tipos específicos das respetivas entradas/saídas, bem como o *empréstimo* de qubits. 
    Este último mecanismo difere da alocação básica de qubits no sentido em que uma operação de C# pode utilizar qubits "modificados", ou seja, qubits não necessariamente inicializados num estado conhecido, para auxiliar nas computações.

- [Teste e depuração](xref:microsoft.quantum.techniques.testing-and-debugging), que pormenoriza algumas técnicas para confirmar que o código está a fazer o que é suposto. 
    Devido à opacidade geral da informação quântica, a depuração de programas quânticos pode exigir técnicas especializadas. 
    Felizmente, a Q# suporta muitas das técnicas de depuração clássicas a que os programadores estão habituados, bem como aquelas que são específicas da tecnologia quântica. Entre essas técnicas incluem-se a criação/execução de testes de unidade em Q#, a incorporação de *asserções* em valores e probabilidades do código e as funções `Dump` que produzem o estado da máquina de destino. 
    Estas últimas podem ser utilizadas juntamente com o nosso simulador de estado completo para depurar determinadas partes das computações ao contornar algumas limitações quânticas (por exemplo, o teorema da não clonagem).


![Quântica](~/media/mobius_strip_preview.png)
