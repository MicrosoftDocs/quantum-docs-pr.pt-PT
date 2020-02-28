---
title: Microsoft Q# Instalação e Validação da Biblioteca de Química
description: Aprenda a instalar a biblioteca de química Quantum da Microsoft e use-a com a plataforma de química computacional NWChem.
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: 48bf7bc980e238e622053f5c2bdd09604c572596
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907363"
---
# <a name="chemistry-library-installation-and-validation"></a>Instalação e Validação da Biblioteca química

O Kit de Desenvolvimento Quântico fornece suporte para aplicações de química quântica através do pacote [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) NuGet.
Tal como acontece com outros pacotes NuGet, é simples adicionar a biblioteca de química ao seu projeto.

**Estúdio Visual 2019:** Se estiver a usar o Visual Studio 2019, pode adicionar os pacotes de química quântica utilizando o NuGet Package Manager.
Para abrir o Gestor de Pacotes, clique no projeto que gostaria de adicionar a biblioteca de química e selecionar "Gerir pacotes NuGet...", como na imagem abaixo.

![Utilização do NuGet Package Manager no Visual Studio 2019](~/media/vs2017-nuget-manage-packages.png)

A partir do separador Browse, procure o nome de pacote "Microsoft.Quantum.Chemistry".

> [!NOTE]
> Certifique-se de marcar "Incluir pré-lançamento".

![Incluir caixa de verificação pré-lançamento](~/media/vs2017-nuget-package-search.png)

Isto listará os pacotes disponíveis para download.
Clique no "Microsoft.Quantum.Chemistry on the left-handpane, select the latest pré-release version on the right-hand pane" e clique em "Instalar":

![Instale o mais recente pacote Microsoft.Quantum.Chemistry](~/media/vs2017-nuget-select-chem.png)

Para mais detalhes, consulte o [guia UI do Gestor](https://docs.microsoft.com/nuget/tools/package-manager-ui)de Pacotes.

Em alternativa, pode utilizar a Consola de Gestor de Pacotes para adicionar a biblioteca de química quântica ao seu projeto com uma interface de linha de comando.

![Utilize a consola gestora de pacotes a partir da linha de comando](~/media/vs2017-nuget-console-menu.png)

A partir da consola gestora de pacotes, execute o seguinte:

```
Install-Package Microsoft.Quantum.Chemistry
```

Para mais detalhes, consulte o guia de [consolas do Gestor](https://docs.microsoft.com/nuget/tools/package-manager-console)de Pacotes .

**Linha de comando ou Código** de Estúdio Visual: Utilizando a linha de comando por si só ou dentro do Código visual do Estúdio, pode utilizar o comando `dotnet` para adicionar referência ao pacote NuGet ao seu projeto:

```dotnetcli
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a>Verificação da sua instalação 

Tal como o resto do Kit de Desenvolvimento Quântico, a biblioteca de química quântica vem com uma série de amostras totalmente documentadas para ajudá-lo a levantar-se e a funcionar rapidamente.
Para testar a sua instalação utilizando estas amostras, clone o [repositório de amostras principais](https://github.com/Microsoft/Quantum)e, em seguida, execute uma das amostras.  Por exemplo, executar a amostra [`MolecularHydrogen`:](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen)

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/chemistry/MolecularHydrogen
dotnet run
```

Para verificar a instalação da biblioteca de química quântica utilizando o Microsoft Visual Studio após a clonagem do repositório:
    1. Abra a solução ChemistrySamples.sLN na pasta Chemistry.  
    2. Selecione Amostras/1. Moléculas Simples/MolecularHydrogen como o projeto StartUp.
    3. Pressione F5 para executar a demonstração molecular de estimativa da fase quântica do hidrogénio.

Consulte [a obtenção de estimativas](xref:microsoft.quantum.chemistry.examples.energyestimate) de nível de energia para obter mais informações sobre a estimativa dos valores dos níveis de energia.   


## <a name="using-the-quantum-development-kit-with-nwchem"></a>Usando o Kit de Desenvolvimento Quântico com NWChem ##

A amostra MolecularHydrogen utiliza dados de entrada molecular que são configurados manualmente.  Embora isto seja bom para pequenos exemplos, a química quântica em escala requer hamiltonianos com milhões ou biliões de mandatos. Tais hamiltonianos, gerados por pacotes de química computacional escalável são demasiado grandes para serem importados à mão. 

A biblioteca de química quântica para o Kit de Desenvolvimento Quântico foi projetada para funcionar bem com pacotes de química computacional, mais notavelmente a plataforma de química computacional [**NWChem**](http://www.nwchem-sw.org/) desenvolvida pelo Laboratório de Ciências Moleculares Ambientais (EMSL) no Laboratório Nacional do Noroeste do Pacífico.
Em particular, o pacote `Microsoft.Quantum.Chemistry` fornece ferramentas para carregar casos de problemas de simulação de química quântica representados no esquema de [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), também suportado para exportação por versões recentes da NWChem.

Para se levantar e funcionar usando a NWChem juntamente com o Kit de Desenvolvimento Quântico, sugerimos um dos seguintes métodos:
- Começar a utilizar ficheiros Broombridge existentes fornecidos com as amostras em [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).
- Utilize o [emslômico](https://arrows.emsl.pnnl.gov/api/qsharp_chem) de setas para o Kit de Desenvolvimento Quântico da Microsoft, que é um frontend baseado na web para a NWChem, para gerar novos ficheiros de entrada molecular formados em Broombridge.  
- Use a [imagem Docker](https://hub.docker.com/r/nwchemorg/nwchem-qc/) fornecida pela PNNL para executar NWChem, ou
- [Compile a NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) para a sua plataforma.

Consulte [o End-to-End com](xref:microsoft.quantum.chemistry.examples.endtoend) a NWChem para obter mais informações sobre como trabalhar com a NWChem para modelos químicos para analisar com a biblioteca de química Quantum Developmen Kit.

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>Começar a usar ficheiros Broombridge fornecidos com as amostras

A pasta [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) no repositório de amostras do kit de desenvolvimento quântico contém ficheiros de dados de moléculas formados por Broombridge.  

Como um exemplo simples, use a amostra da biblioteca de química, [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) para carregar o Hamiltonian a partir de um dos ficheiros broombridge e executar estimativas de porta de algorigthms de simulação quântica:

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

Veja [o Loading a Hamiltonian do arquivo](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) para obter mais informações sobre como inserir moléculas representadas pelo esquema de Broombridge.  

Ver [Obtenção de recursos conta para](xref:microsoft.quantum.chemistry.examples.resourcecounts) obter mais informações sobre a estimativa de recursos.  

### <a name="getting-started-using-the-emsl-arrows-builder"></a>Começar a usar o construtor de setas EMSL

EmSL Arrows é uma ferramenta que usa BASES de dados computacionais NWChem e químicas para gerar dados de moléculas.  [O EMSL Arrows Builder para o Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) de Desenvolvimento Quântico da Microsoft permite-lhe entrar no seu modelo usando vários construtores de modelos moleculares e gerar o ficheiro de dados de Broombridge para ser usado pelo Kit de Desenvolvimento Quântico.  

A partir da página EMSL, clique no separador ['Instuctions'] e siga as instruções ['Exemplos Simples' para gerar ficheiros Broombridge.  Em seguida, tente executar o ['GetGateCount'] para ver as estimativas de recursos quânticos para estas moléculas.

### <a name="installing-nwchem-from-source"></a>Instalação NWChem a partir da Fonte

Instruções completas sobre como instalar a NWChem a partir da fonte [são fornecidas pela PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).

> [!TIP]
> Se desejar utilizar o NWChem a partir do Windows 10, o Subsistema Windows para O Linux é uma excelente opção.
> Depois de ter instalado [ubuntu 18.04 LTS para Windows,](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)faça `ubuntu18.04` do seu terminal favorito e siga as instruções acima para instalar a NWChem a partir da fonte.

Uma vez compilado o NWChem de origem, pode executar o `yaml_driver` script fornecido com NWChem para produzir rapidamente casos de Broombridge a partir de decks de entrada NWChem:

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

Este comando criará um novo ficheiro `input.yaml` no formato Broombridge dentro do seu diretório atual.

### <a name="using-nwchem-with-docker"></a>Usando NWChem com Docker

Imagens pré-construídas para utilização da NWChem estão disponíveis através da plataforma cruzada via [Docker Hub](https://hub.docker.com).
Para começar, siga as instruções de instalação do Docker para a sua plataforma:

- [Instalar Docker para Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [Instalar Docker para macOS](https://docs.docker.com/docker-for-mac/install/)
- [Instale docker para windows 10](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> Se estiver a utilizar o Docker para windows, terá de partilhar a unidade que contém o seu diretório temporário (normalmente este é o `C:\` unidade) com o daemon do Docker. Consulte a [documentação](https://docs.docker.com/docker-for-windows/#shared-drives) do Docker para mais detalhes.

Uma vez instalado o Docker, pode utilizar o módulo PowerShell fornecido com as amostras do Quantum Development Kit para executar a imagem, ou pode executar a imagem manualmente.
Detalhamos a utilização do PowerShell aqui; se quiser utilizar manualmente a imagem do Docker, consulte a [documentação fornecida com a imagem](https://hub.docker.com/r/nwchemorg/nwchem-qc/).

#### <a name="running-nwchem-through-powershell-core"></a>Executando NWChem através do PowerShell Core

Para utilizar a imagem NWChem Docker com o Kit de Desenvolvimento Quântico, fornecemos um pequeno módulo PowerShell que lida com ficheiros em movimento dentro e fora da NWChem para si.
Se ainda não tiver o PowerShell Core instalado, pode descarregá-lo através da plataforma transversal a partir do [repositório PowerShell no GitHub](https://github.com/PowerShell/PowerShell#get-powershell).

> [!NOTE]
> O PowerShell Core também é usado para algumas amostras para demonstrar interoperabilidade com a ciência dos dados e fluxos de trabalho de análise de negócios.

Assim que tiver o PowerShell Core instalado, importe `InvokeNWChem.psm1` para disponibilizar comandos NWChem na sua sessão atual:

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

Isto disponibilizará o comando `Convert-NWChemToBroombridge` na sua atual sessão PowerShell.
Para descarregar quaisquer imagens necessárias do Docker e usá-las para executar decks de entrada NWChem e capturar a saída para Broombridge, executar o seguinte:

```powershell
Convert-NWChemToBroombridge ./input.nw
```

Isto criará um ficheiro Broombridge executando a NWChem na `input.nw`.
Por predefinição, a saída de Broombridge terá o mesmo nome e caminho que o convés de entrada, com a extensão `.nw` substituída por `.yaml`.
Isto pode ser ultrapassado utilizando o parâmetro `-DestinationPath` para `Convert-NWChemToBroombridge`.
Mais informações podem ser obtidas utilizando a funcionalidade de ajuda incorporada da PowerShell:

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```
