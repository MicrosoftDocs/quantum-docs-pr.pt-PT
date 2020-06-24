---
title: Instalação e validação da Biblioteca de Química Microsoft Q#
description: Aprenda a instalar a biblioteca de química quântica da Microsoft e use-a com a plataforma de química computacional NWChem.
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: 48bf7bc980e238e622053f5c2bdd09604c572596
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85276102"
---
# <a name="chemistry-library-installation-and-validation"></a>Instalação e Validação da Biblioteca de Química

O Kit de Desenvolvimento Quântico fornece suporte para aplicações de química quântica através do [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) pacote NuGet.
Tal como acontece com outros pacotes NuGet, é simples adicionar a biblioteca de química ao seu projeto.

**Estúdio Visual 2019:** Se estiver a utilizar o Visual Studio 2019, pode adicionar os pacotes de química quântica utilizando o NuGet Package Manager.
Para abrir o Gestor de Pacotes, clique com o botão direito no projeto a que pretende adicionar a biblioteca de química e selecionar "Gerir pacotes NuGet...", como na imagem abaixo.

![Utilização do Gestor de Pacotes NuGet no Estúdio Visual 2019](~/media/vs2017-nuget-manage-packages.png)

A partir do separador Browse, procure o nome do pacote "Microsoft.Quantum.Chemistry".

> [!NOTE]
> Certifique-se de marcar "Inclua pré-relançar".

![Incluir caixa de verificação pré-lançamento](~/media/vs2017-nuget-package-search.png)

Isto listará os pacotes disponíveis para download.
Clique no painel "Microsoft.Quantum.Chemistry no painel esquerdo, selecione a versão pré-lançamento mais recente no painel direito e clique em "Instalar":

![Instale o mais recente pacote Microsoft.Quantum.Chemistry](~/media/vs2017-nuget-select-chem.png)

Para mais detalhes, consulte o [guia uI do Gestor de Pacotes.](https://docs.microsoft.com/nuget/tools/package-manager-ui)

Em alternativa, pode utilizar a Consola Gestor de Pacotes para adicionar a biblioteca de química quântica ao seu projeto com uma interface de linha de comando.

![Utilize a consola do gestor de pacotes a partir da linha de comando](~/media/vs2017-nuget-console-menu.png)

A partir da consola do gestor de pacotes, execute o seguinte:

```
Install-Package Microsoft.Quantum.Chemistry
```

Para mais detalhes, consulte o guia da [consola do Gestor de Pacotes.](https://docs.microsoft.com/nuget/tools/package-manager-console)

**Linha de comando ou Código do Estúdio Visual:** Utilizando a linha de comando por si só ou a partir do Código do Estúdio Visual, pode utilizar o `dotnet` comando para adicionar referência ao pacote NuGet ao seu projeto:

```dotnetcli
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a>Verificação da sua instalação 

Tal como o resto do Kit de Desenvolvimento Quântico, a biblioteca de química quântica vem com uma série de amostras totalmente documentadas para ajudá-lo a levantar-se e a funcionar rapidamente.
Para testar a sua instalação utilizando estas amostras, clone o [repositório principal](https://github.com/Microsoft/Quantum)de amostras e, em seguida, execute uma das amostras.  Por exemplo, para executar a [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) amostra:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/chemistry/MolecularHydrogen
dotnet run
```

Para verificar a instalação da biblioteca de química quântica utilizando o Microsoft Visual Studio após a clonagem do repositório:
    1. Abra a solução ChemistrySamples.sln na pasta De Chemistry.  
    2. Selecione Amostras/1. Moléculas Simples/MolecularHydrogen como o projeto StartUp.
    3. Pressione F5 para executar a demonstração de estimativa da fase quântica de hidrogénio molecular.

Consulte [a obtenção de estimativas de nível de energia](xref:microsoft.quantum.chemistry.examples.energyestimate) para obter mais informações sobre a estimativa dos valores dos níveis de energia.   


## <a name="using-the-quantum-development-kit-with-nwchem"></a>Usando o Kit de Desenvolvimento Quântico com NWChem ##

A amostra molecular de hidrogénio usa dados de entrada molecular que são configurados manualmente.  Embora isto seja bom para pequenos exemplos, a química quântica em escala requer hamiltonianos com milhões ou biliões de termos. Estes hamiltonianos, gerados por pacotes de química computacional escalável são demasiado grandes para serem importados à mão. 

A biblioteca de química quântica para o Kit de Desenvolvimento Quântico foi projetada para funcionar bem com pacotes de química computacional, mais notavelmente a plataforma de química computacional [**NWChem**](http://www.nwchem-sw.org/) desenvolvida pelo Laboratório de Ciências Moleculares Ambientais (EMSL) do Pacific Northwest National Laboratory.
Em particular, o `Microsoft.Quantum.Chemistry` pacote fornece ferramentas para carregar casos de problemas de simulação de química quântica representados no [esquema de Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), também apoiado para exportação por versões recentes da NWChem.

Para se levantar e funcionar usando o NWChem juntamente com o Kit de Desenvolvimento Quântico, sugerimos um dos seguintes métodos:
- Começar a utilizar os ficheiros broombridge existentes fornecidos com as amostras no [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).
- Utilize o [construtor de setas EMSL para o Microsoft Quantum Development Kit,](https://arrows.emsl.pnnl.gov/api/qsharp_chem) que é um frontend baseado na web para NWChem, para gerar novos ficheiros de entrada molecular formato broombridge.  
- Use a [imagem Docker](https://hub.docker.com/r/nwchemorg/nwchem-qc/) fornecida pela PNNL para executar NWChem, ou
- [Compilar NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) para a sua plataforma.

Consulte [end-to-end com a NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) para obter mais informações sobre como trabalhar com a NWChem para modelos químicos para analisar com a biblioteca de química Quantum Developmen Kit.

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>Começar a usar ficheiros broombridge fornecidos com as amostras

A pasta [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) no repositório de amostras de kit de desenvolvimento quântico contém ficheiros de dados de moléculas formatados por Broombridge.  

Como um exemplo simples, use a amostra da biblioteca de química, [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) para carregar o Hamiltonian de um dos ficheiros de Broombridge e executar estimativas de porta de algorítmicos de simulação quântica:

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

Consulte [carregar um Hamiltonian do ficheiro](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) para obter mais informações sobre como inserir moléculas representadas pelo esquema de Broombridge.  

Consulte [a obtenção de contagens de recursos](xref:microsoft.quantum.chemistry.examples.resourcecounts) para obter mais informações sobre a estimativa de recursos.  

### <a name="getting-started-using-the-emsl-arrows-builder"></a>Começar a usar o construtor de setas EMSL

EmSL Arrows é uma ferramenta que usa bases de dados computacionais e químicos para gerar dados de moléculas.  [O Construtor de Setas EMSL para o Kit de Desenvolvimento Quântico da Microsoft](https://arrows.emsl.pnnl.gov/api/qsharp_chem) permite-lhe introduzir o seu modelo utilizando vários construtores de modelos moleculares e gerar o ficheiro de dados de Broombridge para ser utilizado pelo Kit de Desenvolvimento Quântico.  

Na página EMSL, clique no separador ['Instuctions'] e siga as instruções ['Exemplos simples] para gerar ficheiros Broombridge.  Em seguida, tente executar o ['GetGateCount'] para ver as estimativas de recursos quânticos para estas moléculas.

### <a name="installing-nwchem-from-source"></a>Instalação NWChem da Source

As instruções completas sobre como instalar o NWChem a partir da fonte [são fornecidas pela PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).

> [!TIP]
> Se desejar utilizar o NWChem do Windows 10, o Subsistema Windows para Linux é uma excelente opção.
> Depois de ter instalado [Ubuntu 18.04 LTS para Windows,](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab)corra `ubuntu18.04` a partir do seu terminal favorito e siga as instruções acima para instalar o NWChem a partir da fonte.

Uma vez compilado o NWChem a partir da fonte, pode executar o `yaml_driver` script fornecido com a NWChem para produzir rapidamente instâncias de Broombridge a partir de decks de entrada NWChem:

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

Este comando criará um novo `input.yaml` ficheiro no formato Broombridge dentro do seu diretório atual.

### <a name="using-nwchem-with-docker"></a>Usando NWChem com Docker

As imagens pré-construídas para a utilização do NWChem estão disponíveis através de [Docker Hub.](https://hub.docker.com)
Para começar, siga as instruções de instalação do Docker para a sua plataforma:

- [Instalar Docker para Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [Instalar Docker para macOS](https://docs.docker.com/docker-for-mac/install/)
- [Instalar Docker para o Windows 10](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> Se estiver a utilizar o Docker para o Windows, terá de partilhar a unidade que contém o seu diretório temporário (normalmente esta é a `C:\` unidade) com o daemon Domon Do Docker. Consulte a [documentação](https://docs.docker.com/docker-for-windows/#shared-drives) do Docker para mais detalhes.

Uma vez instalado o Docker, pode utilizar o módulo PowerShell fornecido com as amostras do Kit de Desenvolvimento Quântico para executar a imagem, ou pode executar a imagem manualmente.
Detalhamos a utilização do PowerShell aqui; se quiser utilizar a imagem do Docker manualmente, consulte a [documentação fornecida com a imagem](https://hub.docker.com/r/nwchemorg/nwchem-qc/).

#### <a name="running-nwchem-through-powershell-core"></a>Executando NWChem através do PowerShell Core

Para utilizar a imagem do NWChem Docker com o Kit de Desenvolvimento Quântico, fornecemos um pequeno módulo PowerShell que lida com ficheiros móveis dentro e fora da NWChem para si.
Se ainda não tiver o PowerShell Core instalado, pode descarregá-lo na plataforma transversal do [repositório PowerShell no GitHub.](https://github.com/PowerShell/PowerShell#get-powershell)

> [!NOTE]
> PowerShell Core também é usado para algumas amostras para demonstrar interoperabilidade com data science e fluxos de trabalho de análise de negócios.

Uma vez instalado o PowerShell Core, importe `InvokeNWChem.psm1` para disponibilizar os comandos NWChem na sua sessão atual:

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

Isto tornará o `Convert-NWChemToBroombridge` comando disponível na sua sessão atual do PowerShell.
Para descarregar as imagens necessárias do Docker e usá-las para executar decks de entrada NWChem e capturar saída para Broombridge, execute o seguinte:

```powershell
Convert-NWChemToBroombridge ./input.nw
```

Isto criará um ficheiro Broombridge executando o NWChem em `input.nw` .
Por predefinição, a saída de Broombridge terá o mesmo nome e caminho que o convés de entrada, com a `.nw` extensão substituída por `.yaml` .
Isto pode ser ultrapassado utilizando o `-DestinationPath` parâmetro para `Convert-NWChemToBroombridge` .
Mais informações podem ser obtidas utilizando a funcionalidade de ajuda incorporada da PowerShell:

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```
