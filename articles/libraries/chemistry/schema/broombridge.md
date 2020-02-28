---
title: Broombridge - Quantum Chemistry Schema
description: Visão geral do esquema de química quântica de Broombridge, usado para modelar problemas de química no mundo real com o Kit de Desenvolvimento Quântico da Microsoft.
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: a746b63055bb1b2c1168b89993a7459ca9597f86
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907822"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Broombridge Quantum Chemistry Schema # 

Um poderoso software de química computacional como o [NWChem](http://www.nwchem-sw.org/) permite modelar uma vasta gama de problemas de química no mundo real. Para aceder aos modelos moleculares NWChem com a biblioteca Microsoft Quantum Chemistry, usamos um esquema baseado em [YAML](https://en.wikipedia.org/wiki/YAML)que chamamos **de Broombridge**. O nome foi escolhido em referência a um [marco](https://en.wikipedia.org/wiki/Broom_Bridge) que em alguns círculos é celebrado como um berço dos hamiltonianos. 

[NWChem](https://github.com/nwchemgit/nwchem) é um projeto Open Source licenciado sob a licença permissiva da Comunidade Educativa (ECL) 2.0. Broombridge é um esquema open source que é especificado [aqui](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) e que vem com uma [definição](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) seguindo [rFC 2119](https://tools.ietf.org/html/rfc2119) e [script validador](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) licenciado sob a licença do MIT. 

Sendo baseado em YAML, Broombridge é uma forma estruturada, legível pelo homem e editável pelo homem de representar problemas de estrutura electrónica. Em especial, podem ser representados os seguintes dados: 
- Os Hamiltonianos fermiónicos podem ser representados usando integrales de um e dois eletrões. 
- Estados de terra e excitação podem ser apresentados usando sequências de criação.
- Podem ser especificados os limites superiores e inferiores dos níveis de energia.

O formato de dados pode ser gerado a partir de NWChem com facilidade sem esforço: uma variedade de métodos está disponível que vão desde uma instalação completa de NWChem para executar decks de química, como os fornecidos [aqui](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) e saída Broombridge como parte do run, sobre uma imagem de estivador de NWchem que também pode ser usado para gerar Broombridge a partir de decks de química. Finalmente, um método visual para começar com química computacional rapidamente sem ter que instalar qualquer software de química é fornecido pela interface [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem) para NWChem. 

A um nível elevado, a interação entre a NWChem e o Microsoft Quantum Development Kit pode ser visualizada da seguinte forma: ![chemistry stack](~/media/broombridge.png) A caixa sombreada azul representa o esquema de Broombridge, as várias caixas cinzentas sombreadas representam outras representações internas de dados que foram escolhidas para representar e processar algoritmos quânticos para química computacional baseada em problemas de química real. 

Múltiplas representações químicas definidas usando o esquema broombridge são fornecidas [aqui](https://github.com/microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).
