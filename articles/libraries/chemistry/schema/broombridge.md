---
title: Broombridge Quantum Chemistry Schema
description: Visão geral do esquema de química quântica de Broombridge, usado para modelar problemas de química no mundo real com o Kit de Desenvolvimento Quântico da Microsoft.
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: 708c4277080c358cb35a49fbf1dde0394d331043
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/10/2020
ms.locfileid: "79022530"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Broombridge Quantum Chemistry Schema # 

Um poderoso software de química computacional como o [NWChem](http://www.nwchem-sw.org/) permite-lhe modelar uma vasta gama de problemas de química no mundo real. Para aceder aos modelos moleculares NWChem com a biblioteca Microsoft Quantum Chemistry, usa-se um esquema baseado em [YAML](https://en.wikipedia.org/wiki/YAML)chamado **Broombridge**. O nome foi escolhido em referência a um [marco](https://en.wikipedia.org/wiki/Broom_Bridge) que em alguns círculos é celebrado como um berço dos hamiltonianos. 

[NWChem](https://github.com/nwchemgit/nwchem) é um projeto Open Source licenciado sob a licença permissiva da Comunidade Educativa (ECL) 2.0. O [Broombridge Quantum Chemistry Schema](https://docs.microsoft.com/quantum/libraries/chemistry/schema/spec_v_0_2)é um esquema open source que inclui uma [definição](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) seguindo o [RFC 2119](https://tools.ietf.org/html/rfc2119) e um [script validador](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) licenciado sob a licença do MIT. 

Sendo baseado em YAML, Broombridge é uma forma estruturada, legível pelo homem e editável pelo homem de representar problemas de estrutura electrónica. Em especial, podem ser representados os seguintes dados:
- Os Hamiltonianos fermiónicos podem ser representados usando integrales de um e dois eletrões.
- Estados de terra e excitação podem ser apresentados usando sequências de criação.
- Podem ser especificados os limites superiores e inferiores dos níveis de energia.

Os dados podem ser gerados a partir da NWChem usando vários métodos, tais como usar uma instalação completa de NWChem para executar decks de química (por exemplo, os fornecidos na [biblioteca NWChem](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) que output Broombridge como parte da corrida), ou uma imagem de estivador de NWChem que também pode ser usada para gerar Broombridge a partir de decks de química. Para começar com a química computacional rapidamente sem ter de instalar qualquer software de química, pode utilizar a interface visual para a NWChem fornecida por [Setas EMSL](https://arrows.emsl.pnnl.gov/api/qsharp_chem).

A um nível elevado, a interação entre a NWChem e o Microsoft Quantum Development Kit pode ser visualizada da seguinte forma: ![chemistry stack](~/media/broombridge.png) A caixa sombreada azul representa o esquema de Broombridge, as várias caixas cinzentas sombreadas representam outras representações internas de dados que foram escolhidas para representar e processar algoritmos quânticos para química computacional baseada em problemas de química real.

A pasta [Integral/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) no repositório de amostras do kit de desenvolvimento quântico contém múltiplas representações químicas definidas usando o esquema broombridge.
