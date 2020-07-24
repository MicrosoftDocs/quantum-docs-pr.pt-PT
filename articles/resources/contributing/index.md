---
title: Contribuir para o Microsoft Quantum Development kit
description: Saiba como pode contribuir para o Microsoft Quantum Development kit e para a comunidade de desenvolvimento quântico.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing
ms.openlocfilehash: 108a50302422e5ae41e14b30ef22169370c2a35a
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871421"
---
# <a name="contributing-to-the-quantum-development-kit"></a>Contribuir para o Quantum Development Kit

O Quantum Development Kit é mais do que uma coleção de ferramentas para escrever programas quânticos.
Faz parte de uma comunidade alargada de pessoas à descoberta da computação quântica, que investiga algoritmos quânticos, desenvolve novas aplicações para dispositivos quânticos e trabalha no sentido de tirar o máximo partido da computação quântica.
Como membro dessa comunidade, o Quantum Development Kit pretende dar a programadores quânticos de diversos quadrantes as funcionalidades de que precisam.
Os seus contributos para o Quantum Development Kit ajudam a cumprir esse objetivo, a melhorar as ferramentas utilizadas por outros programadores quânticos, a forma como estas ferramentas são documentadas e até ao criar novas funcionalidades e características que ajudam toda a comunidade de programação quântica a descobrir e criar.
Estamos muito agradecidos pelos seus contributos e pela oportunidade de colaborar consigo no sentido de melhorar ainda mais a nossa comunidade.

Neste guia, fornecemos conselhos sobre como tornar o seu contributo o mais útil possível para a comunidade alargada de programação quântica.

## <a name="building-community"></a>Criar a Comunidade

A primeira coisa a pensar ao dar o seu contributo é ter sempre em conta a comunidade para a qual está a contribuir.
Ao agir de forma respeitosa e profissional para com os seus pares na comunidade de programação quântica e no geral, garante que o seu trabalho ajuda a criar a melhor e mais acolhedora comunidade possível.

Neste sentido, todos os projetos do Quantum Development Kit adotaram o [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/) (Código de Conduta Open Source da Microsoft).
Para obter mais informações, veja as [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) (FAQ do Código de Conduta) ou contacte [opencode@microsoft.com](mailto:opencode@microsoft.com) com quaisquer questões ou comentários adicionais.

## <a name="what-kinds-of-contributions-help-the-community"></a>Que tipos de contributos ajudam a comunidade?

Existem muitas formas diferentes de ajudar a comunidade de programação quântica através dos contributos.
Neste guia, vamos abordar três formas especialmente relevantes para o Quantum Development Kit.
São todas formas fundamentais para fomentar uma comunidade quântica que capacite as pessoas.
No entanto, esta não é uma lista exaustiva. Recomendamos que explore outras formas de ajudar a comunidade quântica a realizar o desígnio da programação quântica.

- **Reportar erros.** O primeiro passo na correção de erros e outros problemas é identificá-los. Se encontrou um erro no Quantum Development Kit, diga-nos, para que possamos corrigi-lo e criar um melhor conjunto de ferramentas para a comunidade de programação quântica.
- **Melhorar a documentação.** Qualquer conjunto de documentos pode ser melhor, abranger mais detalhes e tornar-se mais acessível.
- **Contribuir com código.** Naturalmente, uma das formas mais diretas de contribuir é adicionar novo código ao Quantum Development Kit.

Estes diferentes tipos de contributos são incrivelmente valiosos e muito apreciados.
No resto do guia, daremos conselhos sobre como fazer cada tipo de contributo.

## <a name="where-do-contributions-go"></a>Para onde vão os contributos?

O Quantum Development Kit inclui diferentes componentes que, em conjunto, criam uma plataforma para escrever programas quânticos.
Cada um destes componentes existe num repositório diferente, por isso, uma das primeiras coisas a decidir é onde colocar cada contributo.

- [**microsoft/Quantum**](https://github.com/Microsoft/Quantum): Exemplos e ferramentas de introdução ao Quantum Development Kit.
- [**microsoft/QuantumLibraries**](https://github.com/Microsoft/QuantumLibraries): bibliotecas padrão e específicas de domínios do Quantum Development Kit.
- [**microsoft/QuantumKatas**](https://github.com/Microsoft/QuantumKatas): exercícios personalizados de programação para aprender computação quântica e a linguagem de programação Q#.
- [**microsoft/qsharp-compiler**](https://github.com/microsoft/qsharp-compiler): o compilador Q#, a extensão do Visual Studio e a extensão do Visual Studio Code.
- [**microsoft/qsharp-runtime**](https://github.com/microsoft/qsharp-runtime): estrutura de simulação, geração de código e computadores de destino de simulação do Quantum Development Kit.
- [**microsoft/iqsharp**](https://github.com/microsoft/iqsharp): funcionalidade de anfitrião Python e kernel do Jupyter para Q#, bem como imagens do Docker para utilizar IQ# em ambientes na cloud.
- [**MicrosoftDocs/quantum-docs-pr**](https://github.com/MicrosoftDocs/quantum-docs-pr): código-fonte da documentação publicada em https://docs.microsoft.com/quantum.

> [!NOTE]
> Infelizmente, não podemos aceitar contributos de código e documentação no repositório [**microsoft/Quantum-NC**](https://github.com/microsoft/Quantum-NC) de momento, mas agradecemos imenso os relatórios de erros.

Existem também alguns repositórios mais especializados que incidem sobre funcionalidades auxiliares relacionadas com o Quantum Development Kit.

- [**msr-quarc/qsharp.sty**](https://github.com/msr-quarc/qsharp.sty): suporte de formatação LaTeX para sintaxe Q#.

## <a name="next-steps"></a>Passos seguintes

Obrigado fazer parte da comunidade Quantum Development Kit e aguardamos com entusiasmo os seus contributos.
Se quiser saber mais sobre os contributos, continue com um dos seguintes guias.

> [!div class="nextstepaction"]
> [Saiba como reportar erros](xref:microsoft.quantum.contributing.reporting)

> [!div class="nextstepaction"]
> [Saiba como contribuir para a documentação](xref:microsoft.quantum.contributing.docs)

> [!div class="nextstepaction"]
> [Saiba como abrir pedidos pull](xref:microsoft.quantum.contributing.pulls)
