---
title: Notas de versão do Quantum Development kit
description: Fique a par das mais recentes atualizações à pré-visualização do Microsoft Quantum Development kit.
author: natke
ms.author: nakersha
ms.date: 09/30/2019
ms.topic: article
uid: microsoft.quantum.relnotes
ms.openlocfilehash: 84e5db17ab8d963a75c72da38d3e4487b89abc9d
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: HT
ms.contentlocale: pt-PT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030604"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a>Notas de Versão do Microsoft Quantum Development Kit

Este artigo contém informações sobre cada versão do Quantum Development Kit.

Para obter as instruções de instalação, veja o [guia de instalação](xref:microsoft.quantum.install).

Para obter as instruções de atualização, veja o [guia de atualização](xref:microsoft.quantum.update).

## <a name="version-01120033107"></a>Versão 0.11.2003.3107

*Data da versão: 31 de março de 2020*

Esta versão contém pequenas correções de erros para a versão 0.11.2003.2506.

## <a name="version-01120032506"></a>Versão 0.11.2003.2506

*Data da versão: 26 de março de 2020*

Esta versão contém o seguinte:

- Novo suporte para modificadores de acesso em Q#, para saber mais veja [Estruturas de Ficheiro](xref:microsoft.quantum.language.file-structure#internal-declarations)
- Atualizado para SDK de .NET Core 3.1

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilador](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01020022610"></a>Versão 0.10.2002.2610

*Data da versão: 27 de fevereiro de 2020*

Esta versão contém o seguinte:

- Nova biblioteca de Machine Learning Quântico; para obter mais informações, aceda à nossa [página de documentos de QML](https://docs.microsoft.com/quantum/libraries/machine-learning/?view=qsharp-preview).
- Correções de erros de IQ#, que resultam num aumento de desempenho entre 10 a 20 vezes ao carregar pacotes NuGet.

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilador](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01020012831"></a>Versão 0.10.2001.2831

*Data da versão: 29 de janeiro de 2020*

Esta versão contém o seguinte:

- O novo pacote NuGet Microsoft.Quantum.SDK, que substituirá o pacote NuGet Microsoft.Quantum.Development.Kit quando forem criados projetos novos. O pacote NuGet Microsoft.Quantum.Development.Kit continuará a ser suportado para os projetos existentes. 
- Suporte para extensões de compilador Q#, permitidas pelo novo pacote NuGet Microsoft.Quantum.SDK; para obter mais informações, veja a [documentação no Github](https://github.com/microsoft/qsharp-compiler/tree/master/src/QuantumSdk#extending-the-q-compiler), o [exemplo de extensões de compilador](https://github.com/microsoft/qsharp-compiler/tree/master/examples/CompilerExtensions) e o [Blogue Q# Dev](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/)
- Suporte adicionado para .NET Core 3.1; recomenda-se vivamente ter instalada a versão 3.1.100, uma vez que compilar com versões mais antigas do SDK de .NET Core pode provocar problemas
- Novas transformações de compilador disponíveis em Microsoft.Quantum.QsCompiler.Experimental
- Nova funcionalidade para expor vetores de estado de saída como HTML em IQ#
- Suporte adicionado para EstimateFrequencyA a Microsoft.Quantum.Characterization para testes Hadamard e SWAP
- O espaço de nomes AmplitudeAmplification utiliza agora o guia de estilo da Q#

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilador](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01019120501"></a>Versão 0.10.1912.0501

*Data da versão: 5 de dezembro de 2019*

Esta versão contém o seguinte:

- Novo atributo de Teste para o teste de unidades Q#. Veja a documentação atualizada da API [aqui](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test) e o guia atualizado sobre testes e depuração [aqui](xref:microsoft.quantum.techniques.testing-and-debugging)
- Adição do rastreio de pilha em caso da ocorrência de um erro de execução de um programa Q#
- Suporte para pontos de interrupção no Visual Studio Code devido a uma atualização na [extensão OmniSharp C# Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilador](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01019111607"></a>Versão 0.10.1911.1607

*Data da versão: 17 de novembro de 2019*

Esta versão contém o seguinte:

- Correção de desempenho para [Quantum Katas](https://github.com/Microsoft/QuantumKatas) e blocos de notas Jupyter

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilador](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  


## <a name="version-0101911307"></a>Versão 0.10.1911.307

*Data da versão: 1 de novembro de 2019*

Esta versão contém o seguinte:

- Atualizações para as extensões do Visual Studio Code e Visual Studio para implementar o servidor de linguagem como executável autónomo, eliminando a dependência da versão do SDK de .NET Core  
- Migração para o .NET Core 3.0
- Alteração interruptiva ao Microsoft.Quantum.Simulation.Core.IOperationFactory com a introdução do novo método `Fail`. Apenas afeta os simuladores personalizados que não abrangem o SimulatorBase. Para obter mais detalhes, [veja o pedido Pull no GitHub](https://github.com/microsoft/qsharp-runtime/pull/59).
- Novo suporte para atributos Preteridos

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilador](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-0919093002"></a>Versão 0.9.1909.3002

*Data da versão: 30 de setembro de 2019*

Esta versão contém o seguinte:

- Novo suporte para conclusão do código Q# no Visual Studio 2019 (versões 16.3 e posteriores) e Visual Studio Code
- O novo [Quantum Kata](https://github.com/Microsoft/QuantumKatas) para somadores quânticos

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilador](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-09-packagereference-0919082902"></a>Versão 0.9 (*PackageReference 0.9.1908.2902*)

*Data da versão: 29 de agosto de 2019*

Esta versão contém o seguinte:

- Novo suporte para [instruções de conjugação](xref:microsoft.quantum.language.statements#conjugations) em Q#
- Novas ações de código no compilador, como: “substituir por”, “adicionar documentação” e uma atualização simples de item de matriz
- Foi adicionado um modelo de instalação e novos comandos de projeto à extensão do Visual Studio Code
- Foram adicionadas novas variantes do combinador ApplyIf, como [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone)
- [Quantum Katas](https://github.com/Microsoft/QuantumKatas) adicionais convertidos em Jupyter Notebooks
- A Extensão do Visual Studio agora requer o Visual Studio 2019

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [compilador](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) e [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

As alterações estão resumidas aqui, bem como as instruções para atualizar os programas existentes.  Leia mais sobre estas alterações no [Q# dev blog](https://devblogs.microsoft.com/qsharp) (Blogue de desenvolvimento em Q#).

## <a name="version-08-packagereference-0819071701"></a>Versão 0.8 (*PackageReference 0.8.1907.1701*)

*Data da versão: 12 de julho de 2019*

Esta versão contém o seguinte:

- Novos locais de indexação para segmentar as matrizes; [veja a referência de linguagem](xref:microsoft.quantum.language.expressions#array-slices) para obter mais informações.
- Foi adicionado o Dockerfile alojado no [Microsoft Container Registry](https://github.com/microsoft/ContainerRegistry); veja o [Repositório de IQ# para obter mais informações](https://github.com/microsoft/iqsharp/blob/master/README.md)
- Alteração interruptiva do [simulador de rastreio](xref:microsoft.quantum.machines.qc-trace-simulator.intro), atualização das definições de configuração, alterações de nome; veja o [Browser da API .NET para obter os nomes atualizados](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration).

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) e [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-07-packagereference-0719053109"></a>Versão 0.7 (*PackageReference 0.7.1905.3109*)

*Data da versão: 31 de maio de 2019*

Esta versão contém o seguinte:
- Adições à linguagem Q#. 
- Atualizações à biblioteca de química. 
- Uma nova biblioteca numérica.

Veja a lista completa de PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) e [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

As alterações estão resumidas aqui, bem como as instruções para atualizar os programas existentes.  Leia mais sobre estas alterações no [Q# dev blog](https://devblogs.microsoft.com/qsharp) (Blogue de desenvolvimento em Q#).

### <a name="q-language-syntax"></a>Sintaxe da linguagem Q#
Esta versão adiciona a nova sintaxe da linguagem Q#:
* Adicione de itens nomeados para [tipos definidos pelo utilizador](xref:microsoft.quantum.language.type-model#user-defined-types).  
* Os construtores de tipos definidos pelo utilizador podem agora ser utilizados como funções.
* Adicione de suporte para [copiar-e-atualizar](xref:microsoft.quantum.language.expressions#copy-and-update-expressions) e [aplicar-e-reatribuir ]((xref:microsoft.quantum.language.statements#rebinding-of-mutable-symbols)) em tipos definidos pelo utilizador.
* O bloco de correções para ciclos [repetir-até-obter-êxito](xref:microsoft.quantum.language.statements#repeat-until-success-loop) é agora opcional.
* Agora oferecemos suporte durante ciclos em funções (não em operações).

### <a name="library"></a>Biblioteca 

Esta versão adiciona uma biblioteca numérica: Saiba mais sobre como [utilizar a nova biblioteca numérica](xref:microsoft.quantum.numerics.usage) e experimente as [novas amostras](https://github.com/microsoft/quantum/tree/master/Numerics).  [PR 102](https://github.com/Microsoft/QuantumLibraries/pull/102).  

Esta versão reorganiza as extensões e atualiza a biblioteca de química:
* Melhora a modularidade dos componentes, a extensibilidade e a limpeza de código geral.  [PR 58](https://github.com/microsoft/QuantumLibraries/pull/58).
* Adicione suporte para [wavefunctions de várias referências](xref:microsoft.quantum.chemistry.concepts.multireference), wavefunctions de várias referências dispersas e cluster conjugado unitário.  [PR 110](https://github.com/Microsoft/QuantumLibraries/pull/110).
* (Obrigado!) Contribuidor do [1QBit](https://1qbit.com) ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)): avaliação energética com ansatz de variação. [PR 120](https://github.com/Microsoft/QuantumLibraries/pull/120).
* Atualização do esquema [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) para a nova [versão 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2), ao adicionar a especificação de cluster conjugado unitário. [Problema 65](https://github.com/microsoft/QuantumLibraries/issues/65).
* Adicione interoperabilidade Python às funções da biblioteca de química. Experimente esta [amostra](https://github.com/microsoft/Quantum/tree/master/Chemistry/PythonIntegration). [Problema 53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110).

## <a name="version-061905"></a>Versão 0.6.1905

*Data da versão: 3 de maio de 2019*

Esta versão contém o seguinte:
- Faz alterações à linguagem Q#. 
- Reestrutura as bibliotecas do Quantum Development Kit. 
- Adiciona novas amostras. 
- Corrige bugs.  Vários PRs fechados de [bibliotecas](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) e [amostras](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

As alterações estão resumidas aqui, bem como as instruções para atualizar os programas existentes.  Pode ler mais sobre estas alterações em devblogs.microsoft.com/qsharp.

### <a name="q-language-syntax"></a>Sintaxe da linguagem Q#
Esta versão adiciona a nova sintaxe da linguagem Q#:
* Adicione uma [forma abreviada de expressar especializações de operações quânticas](xref:microsoft.quantum.language.type-model#functors) (controlo e adjacentes) com operadores `+`.  A sintaxe antiga foi preterida.  Os programas que utilizam a sintaxe antiga (por exemplo, `: adjoint`) continuarão a funcionar, mas será gerado um aviso de tempo de compilação.  
* Adicione um novo operador para [copiar-e-atualizar](xref:microsoft.quantum.language.expressions#copy-and-update-expressions); `w/` pode ser utilizado para expressar a criação de matriz como uma modificação de uma matriz existente.
* Adicione a [instrução aplicar-e-atualizar](xref:microsoft.quantum.language.statements#rebinding-of-mutable-symbols) comum; por exemplo, `+=`, `w/=`.
* Adicione uma forma para especificar um nome abreviado para os espaços de nomes nas [diretivas abertas](xref:microsoft.quantum.language.file-structure#open-directives).

Com esta versão, deixámos de permitir que um elemento de matriz seja especificado no lado esquerdo de uma instrução definida.  Tal deve-se ao facto de que essa sintaxe indica que as matrizes são mutáveis quando, na verdade, o resultado da operação sempre foi a criação de uma nova matriz com a modificação.  Em vez disso, será gerado um erro do compilador com uma sugestão para utilizar o novo operador copiar-e-colar, `w/`, para conseguir o mesmo resultado.  

### <a name="library-restructuring"></a>Reestruturação das bibliotecas
Esta versão reorganiza as bibliotecas para permitir o aumento das bibliotecas de forma consistente:
* Renomeia o espaço de nomes Microsoft.Quantum.Primitive para Microsoft.Quantum.Intrinsic.  Estas operações são implementadas pelo computador de destino.  O espaço de nomes Microsoft.Quantum.Primitive foi preterido.  Um aviso de runtime indicará quando os programas chamarem operações e funções com nomes preteridos.

* Renomeia o pacote Microsoft.Quantum.Canon para Microsoft.Quantum.Standard.  Este pacote contém espaços de nomes comuns à maioria dos programas em Q#.  Isto inclui:  
    - Microsoft.Quantum.Canon para operações comuns
    - Microsoft.Quantum.Arithmetic para operações aritméticas para fins gerais
    - Microsoft.Quantum.Preparation para operações utilizadas para preparar o estado de qubit
    - Microsoft.Quantum.Simulation para a funcionalidade de simulação

Com esta alteração, poderão ocorrer erros de compilação nos programas que incluem uma única instrução “aberta” para o espaço de nomes Microsoft.Quatum.Canon se o programa referenciar operações que foram movidas para os outros três novos espaços de nomes.  Adicionar as instruções abertas adicionais aos três novos espaços de nomes é uma maneira simples de resolver este problema.  

* Vários espaços de nomes foram preteridos porque as operações no seu interior foram reorganizadas para outros espaços de nomes. Os programas que utilizam estes espaços de nomes vão continuar a funcionar e um aviso de tempo de compilação denotará o espaço de nomes onde é definida a operação.  

* O espaço de nomes Microsoft.Quantum.Arithmetic foi normalizado para utilizar o tipo definido pelo utilizador <xref:microsoft.quantum.arithmetic.littleendian>. Utilize a função [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian), quando necessário, para converter para little endian.  

* Os nomes de vários elementos disponíveis (funções e operações) foram alterados para estarem em conformidade com o [Guia de Estilo de Q#](xref:microsoft.quantum.contributing.style).  Os antigos nomes disponíveis foram preteridos.  Os programas que utilizam os antigos nomes disponíveis continuarão a funcionar com um aviso de tempo de compilação. 

### <a name="new-samples"></a>Novos Exemplos

Adicionámos um [exemplo de utilização de Q# com o controlador F#](https://github.com/Microsoft/Quantum/pull/164).  

**Obrigado** ao seguinte contribuidor da nossa base de código aberto em http://github.com/Microsoft/Quantum. Estas contribuições acrescentam um valor significativo aos exemplos avançados de código Q#:

* Mathias Soeken ([@msoeken](https://github.com/msoeken)): síntese da função Oracle. [PR 135](https://github.com/Microsoft/Quantum/pull/135).

### <a name="migrating-existing-projects-to-061905"></a>Migração de projetos existentes para 0.6.1905.

Veja o [guia de instalação](xref:microsoft.quantum.install) para atualizar o QDK.
  
Se tiver projetos Q# existentes da versão 0.5 do Quantum Development Kit, os passos que se seguem servirão para migrar esses projetos para a versão mais recente.

    1. Os projetos precisam de ser atualizados por ordem.  Se tiver uma solução com vários projetos, atualize cada um deles pela ordem em que estão referenciados.
    2. Numa linha de comandos, execute `dotnet clean` para remover todos ficheiros intermediários e binários existentes.
    3. Num editor de texto, edite o ficheiro .csproj para alterar a versão de todas as `PackageReference` do “Microsoft.Quantum” para a versão 0.6.1904 e altere o nome do pacote “Microsoft.Quantum.Canon” para “Microsoft.Quantum.Standard”, por exemplo:

         ```xml
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
        ```
    4. Na linha de comandos, execute este comando: `dotnet msbuild`  
    5. Depois de o fazer, poderá continuar a precisar de resolver manualmente os erros relacionados com as alterações listadas acima.  Em muitos casos, estes erros também serão comunicados pelo IntelliSense no Visual Studio ou no Visual Studio Code.
        - Abra a pasta raiz do projeto ou a solução contida no Visual Studio 2019 ou no Visual Studio Code.
        - Depois de abrir um ficheiro .qs no editor, verá o resultado da extensão de linguagem Q# na janela de resultados.
        - Depois de carregar o projeto com êxito (indicado na janela de resultados), abra cada ficheiro manualmente para resolver todos os problemas restantes.

> [!NOTE]
> * Na versão 0.6, o servidor de linguagem incluído no Quantum Development Kit não suporta várias áreas de trabalho.
> * Para trabalhar com um projeto no Visual Studio Code, abra a pasta raiz que contém o projeto em si e todos os projetos referenciados.   
> * Para poder trabalhar com uma solução no Visual Studio, todos os projetos contidos na solução têm de estar na mesma pasta que a solução ou numa das suas subpastas.  
> * As referências entre projetos migrados para a versão 0.6 e posterior e os projetos que utilizam versões de pacotes mais antigas **não** são suportadas.

## <a name="version-051904"></a>Versão 0.5.1904

*Data da versão: 15 de abril de 2019*

Esta versão contém correções de bugs.


## <a name="version-051903"></a>Versão 0.5.1903

*Data da versão: 27 de março de 2019*

Esta versão contém o seguinte:

- Adiciona suporte para o Jupyter Notebook, que constitui uma ótima forma para saber mais sobre o Q#.  [Veja os novos exemplos do Jupyter Notebook e saiba como escrever os seus próprios Notebooks](xref:microsoft.quantum.install). 

- Adiciona aritmética de somador de números inteiros à biblioteca Quantum Canon.  Veja também um Jupyter Notebook que [descreve como utilizar os novos somadores de números inteiros](https://github.com/microsoft/Quantum/blob/master/samples/arithmetic/AdderExample.ipynb).

- Correção de bug para o problema do DumpRegister comunicado pela Comunidade ([148](https://github.com/Microsoft/Quantum/issues/148)).

- Foi adicionada a capacidade de devolução a partir de uma [instrução de utilização](xref:microsoft.quantum.language.statements).

- [Guia de introdução](xref:microsoft.quantum.install) remodelado.


## <a name="version-051902"></a>Versão 0.5.1902

*Data da versão: 27 de fevereiro de 2019*

Esta versão contém o seguinte:

- Adiciona suporte para um anfitrião Python de várias plataformas.  O pacote `qsharp` para Python torna mais fácil simular operações e funções Q# no Python. Saiba mais sobre a [interoperabilidade do Python](xref:microsoft.quantum.install). 

- As extensões do Visual Studio e do Visual Studio Code agora suportam a alteração de nome dos símbolos (por exemplo, funções e operações).

- A extensão do Visual Studio agora pode ser instalada no Visual Studio 2019.

## <a name="version-041901"></a>Versão 0.4.1901

*Data da versão: 30 de janeiro de 2019*

Esta versão contém o seguinte:

- Adiciona suporte para um novo tipo primitivo, BigInt, que representa um número inteiro com sinal de tamanho arbitrário.  Saiba mais sobre o [tipo BigInt](xref:microsoft.quantum.language.type-model).
- Adiciona o novo simulador Toffoli, um simulador rápido para fins gerais que pode simular operações quânticas X, CNOT e X com vários controladores com números muito grandes de qubits.  Saiba mais sobre o [Simulador Toffoli](xref:microsoft.quantum.machines.toffoli-simulator).
- Adiciona um estimador de recursos simples que estima os recursos necessários para executar uma determinada instância de uma operação Q# num computador quântico.  Saiba mais sobre o [Estimador de Recursos](xref:microsoft.quantum.machines.resources-estimator).


## <a name="version-0318112802"></a>Versão 0.3.1811.2802

*Data da versão: 28 de novembro de 2018*

Embora a nossa extensão do VS Code não a estivesse a utilizar, foi sinalizada e removida do marketplace durante [a remoção de extensões](https://code.visualstudio.com/blogs/2018/11/26/event-stream) relacionada com o pacote NPM `event-stream`. Esta versão remove todas as dependências de runtime que podem fazer com que a extensão acione sinalizadores vermelhos.

Se anteriormente tiver instalado a extensão, terá de instalá-la novamente. Para tal, aceda à extensão [Microsoft Quantum Development Kit para Visual Studio Code](vscode:extension/quantum.quantum-devkit-vscode) no Marketplace do Visual Studio e prima Instalar. Lamentamos o inconveniente.


## <a name="version-0318111511"></a>Versão 0.3.1811.1511

*Data da versão: 20 de novembro de 2018*

Esta versão corrige um bug que impedia que alguns utilizadores carregassem com êxito a extensão do Visual Studio.

Se estiver a atualizar de uma versão 0.2 do Quantum Development Kit, saiba mais sobre [as alterações da linguagem Q# e a migração do programa Q#](xref:microsoft.quantum.relnotes.migration-0-3).

## <a name="version-031811203"></a>Versão 0.3.1811.203

*Data da versão: 2 de novembro de 2018*

Esta versão inclui algumas correções de bugs, incluindo:

* A invocação de `DumpMachine` poderia alterar o estado do simulador em determinadas situações.
* Foram removidos os avisos de compilação durante a compilação de projetos com uma versão do .NET Core anterior à 2.1.403.
* Limpeza da documentação, especialmente das descrições mostradas durante a passagem do rato no VS Code ou no Visual Studio.

Se estiver a atualizar de uma versão 0.2 do Quantum Development Kit, saiba mais sobre [as alterações da linguagem Q# e a migração do programa Q#](xref:microsoft.quantum.relnotes.migration-0-3).

## <a name="version-0318102508"></a>Versão 0.3.1810.2508

*Data da versão: 29 de outubro de 2018*

Esta versão inclui novos recursos de linguagem e uma experiência de programação melhorada:

* Esta versão inclui um servidor de linguagem para Q#, bem como as integrações do cliente para o Visual Studio e o Visual Studio Code. Tal permite um novo conjunto de funcionalidades do IntelliSense, juntamente com os comentários em direto sobre a escrita de sublinhados ondulados de erros e avisos. 
* Esta atualização melhora bastante as mensagens de diagnóstico em geral, com navegação fácil e intervalos precisos para diagnóstico e detalhes adicionais nas informações apresentadas durante a passagem do rato.
* A linguagem Q# foi expandida de formas que unificam as maneiras como os programadores podem realizar operações comuns e novas melhorias nas funcionalidades de linguagem para expressar de forma eficiente a computação quântica.  Existem algumas alterações interruptivas na linguagem Q# com esta versão.   

Saiba mais sobre [as alterações na linguagem Q# e a migração do programa Q#](xref:microsoft.quantum.relnotes.migration-0-3).

Esta versão também inclui uma nova biblioteca de química quântica:

* A biblioteca de química contém novas funcionalidades de simulação Hamiltoniana, incluindo:
    - Integradores de Trotter–Suzuki de ordem arbitrária igual para melhorar a precisão da simulação.
    - Técnica de simulação de “qubitization” com otimizações específicas de química para reduzir a complexidade de $T $-gate.
* Foi introduzido um novo esquema open source, chamado esquema Broombridge (em referência a um [ponto de referência](https://en.wikipedia.org/wiki/Broom_Bridge) celebrado como o lugar de nascimento dos Hamiltonianos), para importar representações de moléculas e para as simular.
* São fornecidas várias representações químicas definidas com o esquema Broombridge.  Estes modelos foram gerados por [NWChem](http://www.nwchem-sw.org/), uma ferramenta química computacional de alto desempenho open source.
* Os tutoriais e exemplos descrevem como utilizar a biblioteca de química e os modelos de dados Broombridge para:
    - Construir Hamiltonianos simples com a biblioteca de química
    - Visualizar energias no estado estacionário e de excitação de Hidreto de Lítio com a estimativa de fase.
    - Executar estimativas de recursos da simulação química quântica.
    - Estimar os níveis de energia de moléculas representados pelo esquema Broombridge.
* A documentação descreve como utilizar o NWChem para gerar modelos químicos adicionais para simulação quântica com Q#.

Saiba mais sobre a [biblioteca de química do Quantum Development Kit](xref:microsoft.quantum.chemistry.concepts.intro).

Com a nova biblioteca de química, estamos a separar as bibliotecas num novo repositório GitHub, [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries).  Os exemplos continuam no repositório [Microsoft/Quantum](https://github.com/Microsoft/Quantum).  As contribuições para ambos são bem-vindas!

Esta versão inclui correções de bugs e funcionalidades para problemas denunciados pela comunidade:

* Intellisense para Q#? ([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918)).
* Ficheiros .qs ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049)).
* Melhore a mensagem de erro quando as chavetas são abreviadas na instrução if ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518)).
* Suporte para desconstrução de cadeias de identificação na (re)vínculação mutável ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444)).
* Erro ao executar BitFlipCode fornecido ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).
* A H2SimulationGUI às vezes apresenta picos elevados ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370)).

### <a name="community-contributions"></a>Contribuições da Comunidade

**Obrigado** aos seguintes contribuidores da nossa base de código aberto em http://github.com/Microsoft/Quantum. Estas contribuições acrescentam um valor significativo aos exemplos avançados de código Q#:

* Rolf Huisman ([@RolfHuisman](https://github.com/RolfHuisman)): melhorou a experiência dos programadores de QASM/Q# ao criar um conversor de QASM para Q#. [PR 58](https://github.com/Microsoft/Quantum/pull/58).

* Andrew Helwer ([@ahelwer](https://github.com/ahelwer)):  contribuiu com um exemplo ao implementar o Jogo CHSH, um jogo quântico relacionado com a não localidade.  [PR 84](https://github.com/Microsoft/Quantum/pull/84).

Agradecemos também a Rohit Gupta ([@guptarohit](https://github.com/guptarohit),[PR 90](https://github.com/Microsoft/quantum/pull/90)), Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi),[PR 289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)) e Lee James O'Riordan ([@mlxd](https://github.com/mlxd),[PR 96](https://github.com/Microsoft/Quantum/pull/96)) por todo o trabalho em melhorar o conteúdo para todos nós através da correção da documentação, da ortografia e de gralhas. 

## <a name="version-021809701"></a>Versão 0.2.1809.701

*Data da versão: 10 de setembro de 2018*

Esta versão inclui correções de bugs para problemas denunciados pela comunidade. Incluindo:

* Não é possível utilizar o operador shift ([GitHub](https://github.com/Microsoft/Quantum/issues/75)).
* `DumpMachine` / `DumpRegister` falha no `QCTraceSimulator` ao imprimir para a consola ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680)).
* Permitir a alocação de 0 qubits ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits)).
* O `AssertQubitState` requer a chamada Complex() explícita ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call)).
* A operação `Measure` devolve sempre `One` no macOS ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).

Obrigado! 

## <a name="version-0218063001"></a>Versão 0.2.1806.3001

*Data da versão: 30 de junho de 2018*

Este lançamento é apenas uma correção rápida do [problema 48 denunciado no GitHub](https://github.com/Microsoft/Quantum/issues/48) (a compilação de Q# falhará se o nome de utilizador contiver um espaço em branco). Siga as mesmas instruções de atualização que a `0.2.1806.1503` com a nova versão correspondente (`0.2.1806.3001-preview`).

## <a name="version-0218061503"></a>Versão 0.2.1806.1503

*Data da versão: 22 de junho de 2018*

Esta versão inclui várias contribuições da comunidade, bem como uma experiência de depuração melhorada e um melhor desempenho.  Mais concretamente:

* Melhorias no desempenho em simulações pequenas e grandes no computador de destino QuantumSimulator.
* Funcionalidade de depuração melhorada.
* Contribuições da comunidade para correções de bugs, novas funções do programa auxiliar, operações e novos exemplos.

### <a name="performance-improvements"></a>Melhorias no desempenho

Esta atualização inclui melhorias significativas no desempenho para a simulação de números grandes e pequenos de qubits em todos os computadores de destino.  Esta melhoria é facilmente visível com a simulação H<sub>2</sub>, que é um exemplo padrão no Quantum Development Kit.

### <a name="improved-debugging-functionality"></a>Funcionalidade de depuração melhorada

Esta atualização adiciona a nova funcionalidade de depuração:
* Foram adicionadas duas novas operações, @"microsoft.quantum.extensions.diagnostics.dumpmachine" e @"microsoft.quantum.extensions.diagnostics.dumpregister", que geram informações de função de onda sobre o computador quântico num determinado momento.  
* No Visual Studio, a probabilidade de medir um $\ket{1}$ num único qubit é agora mostrada automaticamente na janela de depuração do computador de destino QuantumSimulator.
* No Visual Studio, foi melhorada a apresentação das propriedades variáveis nas janelas de depuração **Automóveis** e **Locais**. 

Saiba mais sobre [Teste e Depuração](xref:microsoft.quantum.techniques.testing-and-debugging).

### <a name="community-contributions"></a>Contribuições da Comunidade

A comunidade de codificadores Q# está a crescer e é para nós entusiasmante ver as primeiras bibliotecas e exemplos contribuídos por utilizadores que foram enviados para a nossa base de código aberto em http://github.com/Microsoft/quantum.  **O nosso muito obrigado** aos seguintes contribuidores:
* Mathias Soeken ([@msoeken](https://github.com/msoeken)): contribuiu com um exemplo que define um método de síntese de lógica baseado em transformação que constrói redes Toffoli para implementar uma determinada permutação. O código é totalmente escrito em funções e operações Q#.  [PR 41](https://github.com/Microsoft/Quantum/pull/41).
* RolfHuisman ([@RolfHuisman](https://github.com/RolfHuisman)): o MVP da Microsoft Rolf Huisman contribuiu com um exemplo que gera código QASM simples a partir de código Q# para uma classe restrita de programas que não têm um fluxo de controlo clássico e operações quânticas restritas. [PR 59](https://github.com/Microsoft/Quantum/pull/59)
* Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314)): ajudou a melhorar a nossa base de código ao submeter uma função de biblioteca para operações controladas. [PR 53](https://github.com/Microsoft/Quantum/pull/53)
* Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111)): corrigiu @"microsoft.quantum.canon.quantumphaseestimation" e criou novos testes de unidade.  [PR 54](https://github.com/Microsoft/Quantum/pull/54)
* Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit)): limpou o exemplo de Teletransporte ao garantir que a instância do QuantumSimulator é eliminada. [PR 20](https://github.com/Microsoft/Quantum/pull/20)

Além disso, um enorme **obrigado** a estes Engenheiros de Software da Microsoft dos contribuidores da equipa de Serviços de Engenharia Comercial, que fizeram alterações valiosas à nossa documentação durante a Hackathon.  As alterações melhoraram muito a clareza e a experiência de integração para todos nós:
* Sascha Corti
* Mihaela Curmei
* John Donnelly
* Kirill Logachev
* Jan Pospisil
* Anita Ramanan
* Frances Tibble
* Alessandro Vozza

### <a name="update-existing-projects"></a>Atualizar projetos existentes

Esta versão é totalmente compatível com versões anteriores. Basta atualizar os pacotes NuGet nos projetos para a versão `0.2.1806.1503-preview` e fazer uma **recompilação completa** para garantir que todos os ficheiros intermediários são regenerados.

No Visual Studio, siga as instruções normais sobre como [atualizar um pacote](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package).

Para atualizar os modelos do projeto da linha de comandos, execute o seguinte comando:
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

Depois de executar este comando, todos os novos projetos criados com o `dotnet new <project-type> -lang Q#` utilizarão automaticamente esta versão do Quantum Development Kit.

Para atualizar um projeto existente para utilizar a versão mais recente, execute o seguinte comando dentro do diretório de cada projeto:

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

Se um projeto existente também utilizar a integração XUnit para testes de unidades, poderá utilizar um comando semelhante para atualizar também esse pacote:
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

Dependendo da versão do XUnit que o projeto de teste utiliza, talvez também tenha de atualizar o XUnit para a versão 2.3.1:
```
dotnet add package xunit -v "2.3.1" 
```

Após a atualização, confirme que remove todos os ficheiros temporários gerados pela versão anterior. Para tal, faça o seguinte:
```
dotnet clean 
```

### <a name="known-issues"></a>Problemas Conhecidos

Nenhum problema conhecido adicional a comunicar.


## <a name="version-0218022202"></a>Versão 0.2.1802.2202

*Data da versão: 26 de fevereiro de 2018*

Esta versão oferece suporte para desenvolvimento em mais plataformas, interoperabilidade da linguagem e melhorias de desempenho. Mais concretamente:

- Suporte para desenvolvimento baseado no macOS e no Linux. 
- Compatibilidade com .NET Core, incluindo suporte para o Visual Studio Code nas várias plataformas.
- Uma licença de Open Source completa para as Bibliotecas do Quantum Development Kit.
- Melhoria do desempenho do simulador em projetos que exigem 20 ou mais qubits.
- Interoperabilidade com a linguagem Python (versão de pré-visualização disponível no Windows).

### <a name="net-editions"></a>Edições .NET

A plataforma .NET está disponível através de duas edições diferentes, o .NET Framework fornecido com o Windows e o .NET Core open-source que está disponível no Windows, no macOS e no Linux.
Com esta versão, a maioria das partes do Quantum Development Kit são fornecidas como bibliotecas para o .NET Standard, o conjunto de classes comum ao Framework e ao Core.
Portanto, estas bibliotecas são compatíveis com as versões recentes do .NET Framework e do .NET Core.

Assim, para ajudar a garantir que os projetos escritos com o Quantum Development Kit são o mais portáteis possíveis, recomendamos que os projetos da biblioteca escritos com o Quantum Development Kit tenham como destino o .NET Standard, enquanto as aplicações de consola tenham como destino o .NET Core.
Uma vez que as versões anteriores do Quantum Development Kit suportavam apenas o .NET Framework, talvez seja necessário migrar os projetos existentes; veja as informações abaixo para saber como fazer isso.

### <a name="project-migration"></a>Migração de Projetos

Os projetos criados com versões anteriores do Quantum Development Kit vão continuar a funcionar, desde que não atualize os pacotes do NuGet utilizados nos mesmos. Para migrar código existente para a nova versão, execute os seguintes passos:
1. Crie um novo projeto .NET Core com o tipo correto de modelo de projeto Q# (Aplicação, Biblioteca ou Projeto de Teste).
2. Copie os ficheiros .qs e .cs/.fs existentes do projeto antigo para o novo projeto (através de Adicionar > Item Existente). Não copie o ficheiro AssemblyInfo.cs.
3. Crie e execute o novo projeto.

Note que a operação RandomWalkPhaseEstimation do espaço de nomes Microsoft.Quantum.Canon foi movida para o espaço de nomes Microsoft.Research.Quantum.RandomWalkPhaseEstimation no repositório [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc).

### <a name="known-issues"></a>Problemas Conhecidos

- A opção `--filter` para `dotnet test` não funciona corretamente com testes escritos em Q#.
  Como resultado, os testes de unidade individuais não podem ser executados no Visual Studio Code; recomendamos que utilize o `dotnet test` na linha de comandos para executar novamente todos os testes.

## <a name="version-0118011707"></a>Versão 0.1.1801.1707

*Data da versão: 18 de janeiro de 2018*

Esta versão corrige alguns problemas denunciados pela comunidade. Nomeadamente:

- O simulador agora funciona com CPUs que não estavam inicialmente ativadas para AVX.
- As definições decimais regionais não farão com que o parser Q# falhe.
- A operação primitiva `SignD` devolve agora `Int` em vez de `Double`.


## <a name="version-011712901"></a>Versão 0.1.1712.901

*Data da versão: 11 de dezembro de 2017*

### <a name="known-issues"></a>Problemas Conhecidos

#### <a name="hardware-and-software-requirements"></a>Requisitos de Hardware e Software

- O simulador incluído no Quantum Development Kit requer uma instalação de 64 bits do Microsoft Windows para poder ser executado.
- O simulador quântico da Microsoft, instalado com o Quantum development kit, utiliza Extensões de Vetor Avançadas (AVX) e requer uma CPU compatível com AVX. Os processadores Intel fornecidos no Q1 2011 (Sandy Bridge) ou posterior suportam AVX. Estamos a avaliar o suporte para CPUs anteriores e poderemos anunciar mais pormenores mais tarde.

#### <a name="project-creation"></a>Criação de Projetos

- Ao criar uma solução (.sln) que utilizará Q#, a solução deve ser um diretório maior do que cada projeto (.csproj) na solução. Ao criar uma nova solução, poderá conseguir isso ao garantir que a caixa de verificação “Criar diretório da solução” está marcada na caixa de diálogo “Novo Projeto”. Se não o fizer, os pacotes NuGet do Quantum Development Kit terão de ser instalados manualmente.

#### <a name="q"></a>Q#

- O IntelliSense não apresenta os erros corretos do código Q#. Confirme que está a apresentar os erros de Compilação na Lista de Erros do Visual Studio para ver os erros de Q# corretos. Note também que os erros de Q# não aparecerão até que tenha feito uma compilação.
- Utilizar uma matriz mutável numa aplicação parcial pode levar a um comportamento inesperado.
- Vincular uma matriz imutável a uma matriz mutável (por exemplo, a = b, em que b é uma matriz mutável) pode levar a um comportamento inesperado.
- A criação de perfis, a cobertura do código e outros plug-ins do VS nem sempre podem contar as linhas e os blocos de Q# com precisão.
- O compilador Q# não valida as cadeias interpoladas. É possível criar erros de compilação C# ao escrever incorretamente nomes de variáveis ou ao utilizar expressões em cadeias interpoladas em Q#.

#### <a name="simulation"></a>Simulação

- O QuantumSimulator utiliza OpenMP para paralelizar a álgebra linear necessária. Por predefinição, o OpenMP utiliza todos os threads de hardware disponíveis, o que significa que os programas com pequenos números de qubits serão normalmente executados lentamente, pois a coordenação necessária diminuirá o trabalho real. Esse erro pode ser corrigido ao definir a variável de ambiente OMP_NUM_THREADS para um número pequeno. Como regra geral muito superficial, um thread é bom para um máximo de quatro qubits e, em seguida, um thread adicional por qubit é bom, embora isto seja altamente dependente do algoritmo.

#### <a name="debugging"></a>Depurar

- F11 (próxima instrução) não funciona no código Q#.
- O realce no código Q# num ponto de interrupção ou numa pausa de um único passo é, por vezes, impreciso. A linha correta será realçada, mas às vezes o realce começa e termina em colunas incorretas na linha.

#### <a name="testing"></a>Testar

- Os testes devem ser executados no modo de 64 bits. Se os testes estiverem a falhar com um BadImageFormatException, aceda ao menu Teste e selecione Definições de Teste > (Arquitetura do Processador Predefinida) > x64.
- Alguns testes demoram muito tempo (possivelmente até cinco minutos, dependendo do computador) a ser executados. Tal é normal, pois alguns utilizam mais de 20 qubits; o nosso maior teste atualmente é executado em 23 qubits.

#### <a name="samples"></a>Amostras

- Em certos computadores, alguns exemplos pequenos poderão ser executados lentamente exceto se a variável de ambiente OMP_NUM_THREADS estiver definida como “1”. Veja também a nota de versão em “Simulação”.

#### <a name="libraries"></a>Bibliotecas

- Existe uma pressuposição implícita de que os qubits que passaram para uma operação em argumentos diferentes são todos distintos. Por exemplo, todas as operações da biblioteca (e todos os simuladores) pressupõem que os dois qubits passaram para um NOT controlado são qubits diferentes. Desrespeitar esta pressuposição pode levar a algo inesperado imprevisível. É possível testar isso com o simulador de rastreio do computador quântico.
- A função Microsoft.Quantum.Bind pode não funcionar conforme o esperado em todos os casos.
- No espaço de nomes Microsoft.Quantum.Extensions.Math, a função SignD devolve um Double, em vez de um Int, embora a função System.Math.Sign subjacente devolva sempre um número inteiro. É seguro comparar o resultado com 1.0, -1.0 e 0.0, uma vez que estes doubles têm todos representações binárias exatas.
