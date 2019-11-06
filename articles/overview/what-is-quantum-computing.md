---
title: O que é a computação quântica?
description: Saiba o que é a computação quântica e o que um computador quântico pode fazer
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.what
ms.openlocfilehash: 2f3b64b00a0a9552e52e34cb1e3652810b266eab
ms.sourcegitcommit: edcf15044d7bdf4f8b21fb8f6af4bde475eb13a0
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/04/2019
ms.locfileid: "73529939"
---
# <a name="what-is-quantum-computing"></a>O que é a computação quântica?

Existem alguns problemas tão difíceis, tão incrivelmente vastos, que mesmo se todos os supercomputadores do mundo trabalhassem no problema, ainda assim levaria mais tempo do que o tempo de vida do universo para resolver.

Os computadores quânticos prometem resolver alguns dos maiores desafios do nosso planeta – no ambiente, na agricultura, na saúde, na energia, na ciência dos materiais e problemas que ainda nem imaginamos. O impacto dos computadores quânticos será abrangente e terá um impacto tão grande como a criação do transístor em 1947, que preparou o caminho para a economia digital atual.

A computação quântica tira partido do comportamento único da física quântica para fornecer um modelo novo e poderoso de computação. A teoria da física quântica pressupõe que a matéria, num nível quântico, pode estar numa sobreposição de vários estados clássicos. E, esses vários estados interferem uns com os outros, como ondas numa poça de maré.  O estado da matéria depois de uma medição “colapsar” num dos estados clássicos. 

Depois disso, repetir a mesma medição produzirá o mesmo resultado clássico.  O entrelaçamento quântico ocorre quando as partículas interagem de modo a que o estado quântico de cada uma não possa ser descrito de forma independente das restantes, mesmo que as partículas estejam fisicamente distantes.  

A computação quântica armazena informações em estados quânticos de matéria e utiliza a sua natureza quântica de sobreposição e entrelaçamento para realizar operações quânticas que calculam com base nessas informações, ao tirar partido e ao aprender a programar interferência quântica.

A computação quântica pode parecer assustadora, mas com os recursos certos pode começar a criar aplicações quânticas ainda hoje.

## <a name="the-qubit"></a>O qubit

A computação quântica define os conceitos de computação que refletem o comportamento quântico.  A computação quântica começa com a noção de qubit.  Na computação quântica, um bit quântico (**qubit**) é uma unidade de informação quântica, como um bit clássico. Enquanto os bits clássicos contêm um único valor binário como 0 ou 1, o estado de um qubit pode estar numa **sobreposição** de 0 e 1 simultaneamente.  

O ato de medir um qubit altera o estado de um qubit. Com a medição, o qubit vai do estado de sobreposição até um dos estados clássicos.  

Também é possível **entrelaçar** vários qubits. Quando fazemos a medição de um qubit entrelaçado, o nosso conhecimento do estado do(s) outro(s) também é atualizado.

## <a name="quantum-algorithms"></a>Algoritmos quânticos

Os algoritmos quânticos são concebidos para tirar partido da natureza quântica e do comportamento para acelerar os algoritmos clássicos ou para fornecer formas completamente novas de modelar os sistemas físicos.  Estes algoritmos exploram a forma como os qubits codificam as informações e a natureza paralela de operar em vários qubits entrelaçados em sobreposição.  

Os computadores clássicos codificam as informações em bits, sendo que cada bit codifica dois valores possíveis, 0 ou 1.  Um qubit codifica dois valores simultaneamente, 0 e 1.  Dois bits clássicos codificam um de quatro valores possíveis, (00, 01, 10, 11), enquanto que dois qubits codificam qualquer sobreposição dos quatro estados simultaneamente, embora possamos obter apenas um desses valores na medição. Quatro qubits codificam qualquer sobreposição de 16 valores simultaneamente, e assim por diante, exponencialmente.  100 qubits podem codificar mais informações do que as disponíveis nos maiores sistemas de computador atualmente.  

Além disso, quando vários qubits entrelaçados atuam de forma coerente, podem processar várias opções em simultâneo. Os qubits entrelaçados conseguem processar informações numa pequena fração do tempo que demorariam até os sistemas não quânticos mais rápidos.

Tirar partido destes atributos quânticos tem sido o objetivo de várias décadas de investigação de algoritmos quânticos e foram encontradas inúmeras técnicas inovadoras que resolvem problemas numa fração do tempo necessário para resolver de forma clássica.  

Um dos algoritmos quânticos mais conhecidos é o _algoritmo de Shor_ para fatorizar, que transforma o problema classicamente difícil da fatorização de um número grande em dois números primos rápido o suficiente para desafiar a criptografia tradicional.

No lado mais construtivo, os algoritmos para a distribuição segura de chaves de criptografia tornam-se possíveis através da sobreposição, do entrelaçamento quântico e da propriedade de **não clonagem** dos qubits, o que significa que os qubits não podem ser copiados sem deteção.

O _algoritmo de Grover_ realça uma técnica de algoritmos quânticos que fornece uma velocidade quadrática para pesquisar dados não estruturados.

## <a name="quantum-hardware"></a>Hardware quântico

Nos computadores clássicos, os bits correspondem a níveis de tensão em circuitos integrados de silício. O hardware de computação quântica pode ser implementado por muitas realizações físicas diferentes de qubits: qubits de iões capturados, qubits supercondutores, qubits de átomos neutros, qubits de spin de eletrões, qubits de polarização da luz. O hardware quântico é uma tecnologia emergente. Os qubits são frágeis por natureza e tornam-se menos coerentes à medida que interagem com o ambiente. É necessário equilibrar a fidelidade do sistema com a escalabilidade. Quanto maior o dimensionamento (ou seja, o número de qubits), maior a taxa de erros.

A Microsoft está a desenvolver um computador quântico baseado em qubits topológicos. Acreditamos que um qubit topológico será menos afetado pelas alterações no respetivo ambiente e, consequentemente, reduzem o grau de correção de erros externos. A funcionalidade dos qubits topológicos aumentou a estabilidade e a resistência ao ruído do ambiente, o que significa que podem ser facilmente dimensionados e mantêm-se fiáveis durante mais tempo.

## <a name="quantum-computing--a-full-hardware-and-software-stack"></a>Computação quântica – uma pilha completa de hardware e software

O programa quântico da Microsoft é exclusivo na forma como nos concentramos no dimensionamento de cada componente do sistema para causar um impacto quântico real. Esta abordagem abrangente envolve:

* Compilar um computador quântico com qubits topológicos fiáveis, dimensionáveis e com tolerância a falhas. 
* Criar um plano de controlo criogénico exclusivo com energia baixa e dissipação de calor. 
* Desenvolver uma pilha de software completa para permitir a programação do computador quântico e controlar o sistema em escala.

O Microsoft Quantum Development Kit (QDK) open source foi introduzido para facilitar o acesso à programação quântica e ao desenvolvimento de algoritmos. A nossa linguagem de programação de alto nível, Q#, aborda os desafios da programação quântica.  Criámos o Q# como uma linguagem de programação quântica de alto nível concentrada no desenvolvimento de algoritmos e aplicações. O compilador Q# está integrado numa pilha de software que permite que um algoritmo quântico seja compilado para as operações primitivas de um computador quântico.  A computação quântica pode ser simulada num computador clássico até um determinado dimensionamento (número de qubits). Ao utilizar a simulação, pode começar a escrever programas quânticos ainda hoje, para serem executados em hardware quântico no futuro.  Também integrámos o Q# em exemplos, bibliotecas e exercícios de aprendizagem para facilitar o início da programação quântica atualmente. 

## <a name="next-steps"></a>Passos seguintes

* [O que podem fazer os computadores quânticos?](xref:microsoft.quantum.overview.computers)
* [Introdução ao Microsoft Quantum Development Kit](xref:microsoft.quantum.welcome)
* Saiba mais sobre os [Conceitos da computação quântica](xref:microsoft.quantum.concepts.intro)
