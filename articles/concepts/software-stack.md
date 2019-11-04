---
title: Pilha de software | Microsoft Docs
description: Pilha de software
author: QuantumWriter
uid: microsoft.quantum.concepts.software-stack
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f97dfacf6cde5fa92e1f368efaae36554a5c944d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184734"
---
# <a name="software-stack-for-quantum-computing"></a>Pilha de software para computação Quantum
Normalmente, quando pensamos em um computador, prevemos um único dispositivo executando um aplicativo, mas os ambientes de computação modernos são muito mais complexos e avançados. O aplicativo que interagimos normalmente reside em várias camadas de software que fornecem a execução do aplicativo para o nível de hardware. Essas camadas de software são necessárias para abstrair o desenvolvimento de uma solução de aplicativo da complexidade subjacente do sistema de computação completo. Se um desenvolvedor tivesse de pensar em barramento, arquiteturas de cache, protocolos de comunicação e muito mais durante a gravação de um aplicativo de smartphone simples, a tarefa seria muito mais complexa.  O conceito de uma *pilha de software* foi desenvolvido na computação clássica para resolver esses problemas.  Com o empréstimo do conceito clássico, uma pilha de software também é uma parte fundamental da visão por trás da computação Quantum com Q #.

## <a name="conventional-stack"></a>Pilha convencional
A ideia principal por trás de uma pilha de software é a recursão.  Ele consiste em várias camadas aninhadas de interfaces que abstraim os detalhes dos níveis inferiores do dispositivo para fora do desenvolvedor.  Por exemplo, uma pilha de software comumente usada envolve a execução de ASP.NET (uma linguagem de programação), além do SQL Server (um sistema de gerenciamento de banco de dados relacional), que é executado sobre o Serviços de Informações da Internet (um servidor Web), que é executado no Windows Server (um sistema operacional), que orienta o hardware do computador.  Examinando o software como uma hierarquia, é possível escrever software em ASP.NET sem a necessidade de entender os detalhes de baixo nível de todo o software abaixo dele.

## <a name="quantum-stack"></a>Pilha Quantum

A pilha de software na computação Quantum não é diferente em princípio e, na prática, opera em um nível mais baixo do que as pilhas tradicionais.  Como é a aparência de uma pilha Quantum?  Um computador Quantum não é uma substituição para computadores tradicionais (geralmente chamados de clássico).  Na verdade, os computadores Quantum quase certamente funcionarão em conjunto com computadores clássicos para resolver problemas computacionais.  Em parte, isso ocorre devido ao fragilidade de dados Quantum.  Os dados Quantum são tão frágeis que, se você olhar até mesmo, certamente danificará as informações que estão sendo observadas.  Os computadores Quantum, portanto, precisarão ser projetados com a correção de erro Quantum em mente para que as interações isoladas de seu ambiente físico não danifiquem inadvertidamente as informações e a computação. Por esse motivo, um destino natural para Q # é um computador Quantum corrigido por erro (geralmente chamado de computador Quantum *tolerante a falhas* ) que aceita uma lista de instruções Quantum (chamadas de operações de Gates ou de entrada) e aplica essas instruções à Quantum dados armazenados nele.  Observe que, se o número de operações de qubits e de portão em um algoritmo ou programa Quantum for pequeno o suficiente, a correção de erro pode não ser absolutamente necessária.  No entanto, como o número de operações de qubits e portão aumenta, certamente será um requisito, portanto, arquitetamos nossa pilha de software e Q # para lidar com a correção de erros de forma apropriada e eficiente e habilitar a computação Quantum escalonável e tolerante a falhas.

### <a name="error-correction"></a>Correção de erro
A correção de erros requer que um computador clássico rápido e confiável seja executado em conjunto com o computador Quantum para corrigir erros à medida que eles aparecem na computação Quantum.  Na prática, os componentes como FPGAs (matrizes de Portable programáveis) ou processadores de Cryogenic rápidos podem ser necessários para identificar e corrigir os erros mais rapidamente do que eles se acumulam naturalmente no computador Quantum.  Como resultado, um computador Quantum é um computador híbrido composto por vários dispositivos computacionais diferentes que operam em uma ampla gama de temperaturas.  Por esse motivo, é muito mais útil pensar em programação de um computador Quantum por meio da lente de uma pilha de software, pois há muitas camadas de hardware e software (clássica e Quantum) necessárias para atingir a implementação de um Quantum algoritmo em um computador Quantum.

### <a name="quantum-conceptual-stack"></a>Pilha conceitual do Quantum
Uma pilha conceitual que ilustra o fluxo funcional de fatoração 8704143553785700723 em um ambiente de computação Quantum é mostrada abaixo:

![Pilha de software](~/media/concepts_stack.png)

### <a name="specification-and-algorithm"></a>Especificação e algoritmo
Há vários estágios amplos de programação, como uma computação Quantum.  A primeira e, de uma fase mais desafiadora, é especificar o problema que um deseja resolver.  Nesse caso, o problema é fatorar o número 8704143553785700723 em um produto de dois números primos.  A próxima etapa envolve a criação de um algoritmo para resolver esse problema computacional.  Nesse caso, o famoso algoritmo de fatoração Quantum da Atal pode ser usado para encontrar os fatores.  Esse algoritmo é expresso em Q # e, em seguida, uma sequência de operações Quantum é uma saída que pode ser executada em um computador Quantum sem erros ideal.  

### <a name="physical-gates"></a>Gates físicos
Neste exemplo, suponha que a natureza não seja tão como fornecer um computador Quantum sem erros para que a etapa subsequente use as operações emitidas por Q # e as traduza usando modelos especificados pelo método de correção de erro Quantum escolhido em Gates físicos que o hardware básico pode ser executado.  Esse processo envolve a substituição de todos os qubit lógicos descritos no modelo anterior por um host de qubits físicos que são usados para armazenar e proteger as informações em um único qubit de maneira redundante que pode resistir a erros locais nos componentes físicos qubits tempo suficiente para que esses erros sejam detectados e corrigidos.  Assim como os qubits lógicos descritos pelo código Q # precisam ser substituídos por muitos qubits físicos, de forma semelhante cada portão da Quantum descrito na saída precisa ser convertido em uma sequência de Gates físicos que atuam no qubits físico.  Por esse motivo, a saída de Q # raramente é o destino final da computação Quantum e mais níveis de abstração são necessários para executar o código em hardware de uma maneira alheios.

### <a name="control-computer"></a>Computador de controle
Em seguida, a sequência de portão físico é carregada em um computador comum que envia essas instruções para um computador de controle que interage diretamente com o computador Quantum.  Essa camada na pilha de software é geralmente tratada pelo software de controle experimental, como [QCoDeS](http://qcodes.github.io/Qcodes/).

### <a name="interface-computer"></a>Computador de interface
A etapa final desse processo envolve o computador da interface primeiro transmitindo as Gates conforme necessário para um computador de controle rápido. Em seguida, o computador de controle rápido aplica as tensões necessárias (geralmente chamadas de pulsos) para implementar as Gates necessárias em qubits. Isso deve ser feito ao corrigir quaisquer erros observados por meio da correção de erro Quantum.  O Cryogenic FPGAs ou outro hardware exóticas pode ser necessário para executar essas etapas dentro dos rigorosos requisitos de tempo impostos pela taxa na qual os erros aparecem no computador Quantum.  O idioma de destino nesse nível geralmente é [VHDL](https://en.wikipedia.org/wiki/VHDL), o que exige uma maneira distinta de pensar no que é usado na extremidade superior da pilha para analisar uma descrição de um algoritmo Quantum.

### <a name="the-q-quantum-programming-language"></a>A linguagem de programação da Quantum do Q #
O objetivo do Q # é fornecer uma linguagem simples que permita aos desenvolvedores escrever código direcionado a uma infinidade de plataformas e interfaces de computação Quantum com as camadas intermediárias de software que se deparam entre o usuário e o dispositivo Quantum.  A linguagem facilita isso adotando a noção de uma pilha de software e abstraindo muitos dos detalhes do computador Quantum subjacente, enquanto permite outros níveis da pilha, expostos por meio de uma linguagem como C#, para executar a traduções do código Q # para operações fundamentais.  Isso permite que o desenvolvedor se concentre no que eles fazem melhor: criando algoritmos e resolvendo problemas.
