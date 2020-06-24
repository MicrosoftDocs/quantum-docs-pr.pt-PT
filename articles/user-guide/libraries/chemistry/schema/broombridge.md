---
title: Esquema de Química Quântica de Broombridge
description: Visão geral do esquema de química quântica de Broombridge, usado para modelar problemas de química no mundo real com o Microsoft Quantum Development Kit.
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: 708c4277080c358cb35a49fbf1dde0394d331043
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275875"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Esquema de Química Quântica de Broombridge # 

Um poderoso software de química computacional, como [o NWChem,](http://www.nwchem-sw.org/) permite-lhe modelar uma vasta gama de problemas de química no mundo real. Para aceder aos modelos moleculares da NWChem com a biblioteca Microsoft Quantum Chemistry, utiliza-se um esquema baseado em [YAML](https://en.wikipedia.org/wiki/YAML)chamado **Broombridge.** O nome foi escolhido em referência a um [marco](https://en.wikipedia.org/wiki/Broom_Bridge) que em alguns círculos é celebrado como um berço de Hamiltonians. 

[NWChem](https://github.com/nwchemgit/nwchem) é um projeto Open Source licenciado ao abrigo da licença permissiva da Comunidade Educativa (ECL) 2.0. O [Esquema de Química Quântica de Broombridge](https://docs.microsoft.com/quantum/libraries/chemistry/schema/spec_v_0_2)) é um esquema open source que inclui uma [definição](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) a seguir ao [RFC 2119](https://tools.ietf.org/html/rfc2119) e um [script validador](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) licenciado sob a licença DO MIT. 

Sendo baseada em YAML, Broombridge é uma forma estruturada, legível pelo homem e editável pelo homem de representar problemas de estrutura electrónica. Em especial, podem ser representados os seguintes dados:
- Os hamiltonianos fermiónicos podem ser representados usando integrais de um e dois eletrões.
- Estados terrestres e animados podem ser apresentados usando sequências de criação.
- Os limites superiores e inferiores dos níveis de energia podem ser especificados.

Os dados podem ser gerados a partir de NWChem usando vários métodos, tais como usar uma instalação completa de NWChem para executar decks de química (por exemplo, os fornecidos na [biblioteca NWChem](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) que output Broombridge como parte da corrida), ou uma imagem de estiva de NWChem que também pode ser usada para gerar Broombridge a partir de decks de química. Para começar com a química computacional rapidamente sem ter que instalar qualquer software de química, você pode usar a interface visual para NWChem fornecida pela [EMSL Arrows](https://arrows.emsl.pnnl.gov/api/qsharp_chem).

A um nível elevado, a interação entre a NWChem e o Microsoft Quantum Development Kit pode ser visualizada da seguinte forma: ![ Pilha de química A caixa ](~/media/broombridge.png) sombreada azul representa o esquema de Broombridge, as várias caixas cinzentas sombreadas representam outras representações internas de dados que foram escolhidas para representar e processar algoritmos quânticos para química computacional baseada em problemas de química no mundo real.

A pasta [Integral/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) no repositório de amostras de kit de desenvolvimento quântico contém múltiplas representações químicas definidas usando o esquema de Broombridge.
