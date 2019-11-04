---
title: Instalação e validação da biblioteca de química | Microsoft Docs
description: Instalação e validação da biblioteca de química
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: fd43c783fa82c7219e143a57759919606fdd197f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184207"
---
# <a name="chemistry-library-installation-and-validation"></a>Instalação e validação da biblioteca de química

O kit de desenvolvimento Quantum fornece suporte para aplicativos químicas da Quantum por meio do pacote NuGet [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) .
Assim como acontece com outros pacotes NuGet, é simples adicionar a biblioteca química ao seu projeto.

**Visual Studio 2019:** Se você estiver usando o Visual Studio 2019, poderá adicionar os pacotes de química do Quantum usando o Gerenciador de pacotes NuGet.
Para abrir o Gerenciador de pacotes, clique com o botão direito do mouse no projeto ao qual você deseja adicionar a biblioteca de química e selecione "gerenciar pacotes NuGet...", como na captura de tela abaixo.

![](~/media/vs2017-nuget-manage-packages.png)

Na guia procurar, procure o nome do pacote "Microsoft. Quantum. química".

> [!NOTE]
> Certifique-se de marcar "incluir pré-lançamento".

![](~/media/vs2017-nuget-package-search.png)

Isso listará os pacotes disponíveis para download.
Clique no "Microsoft. Quantum. química no painel esquerdo, selecione a versão de pré-lançamento mais recente no painel direito e clique em" instalar ":

![](~/media/vs2017-nuget-select-chem.png)

Para obter mais detalhes, consulte o [Guia de interface do usuário do Gerenciador de pacotes](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Como alternativa, você pode usar o console do Gerenciador de pacotes para adicionar a biblioteca química do Quantum ao seu projeto com uma interface de linha de comando.

![](~/media/vs2017-nuget-console-menu.png)

No console do Gerenciador de pacotes, execute o seguinte:

```
Install-Package Microsoft.Quantum.Chemistry
```

Para obter mais detalhes, consulte o [Guia do console do Gerenciador de pacotes](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Linha de comando ou Visual Studio Code:** Usando a linha de comando por conta própria ou de dentro Visual Studio Code, você pode usar o comando `dotnet` para adicionar a referência do pacote NuGet ao seu projeto:

```bash
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a>Verificando sua instalação 

Assim como o restante do kit de desenvolvimento Quantum, a biblioteca química do Quantum vem com uma série de amostras totalmente documentadas para ajudá-lo a entrar em funcionamento rapidamente.
Para testar a instalação usando esses exemplos, clone o [repositório principal de exemplos](https://github.com/Microsoft/Quantum)e, em seguida, execute um dos exemplos.  Por exemplo, para executar o exemplo de [`MolecularHydrogen`](https://github.com/Microsoft/Quantum/tree/master/Chemistry/MolecularHydrogen) :

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Chemistry/MolecularHydrogen
dotnet run
```

Para verificar a instalação da biblioteca química do Quantum usando Microsoft Visual Studio depois de clonar o repositório:
    1. Abra a solução ChemistrySamples. sln na pasta química.  
    2. Selecione amostras/1. Moléculas/MolecularHydrogen simples como o projeto de inicialização.
    3. Pressione F5 para executar a demonstração de estimativa da fase Quantum do molecular Hydrogen.

Consulte [obtendo estimativas de nível de energia](xref:microsoft.quantum.chemistry.examples.energyestimate) para obter mais informações sobre como estimar os valores dos níveis de energia.   


## <a name="using-the-quantum-development-kit-with-nwchem"></a>Usando o kit de desenvolvimento Quantum com NWChem ##

O exemplo MolecularHydrogen usa os dados de entrada do molecular que são configurados manualmente.  Embora isso seja bom para exemplos pequenos, o quantum química em escala exige Hamiltonians com milhões ou bilhões de termos. Esses Hamiltonians, gerados por pacotes de química computacional escalonáveis, são muito grandes para serem importados manualmente. 

A biblioteca química do Quantum para o kit de desenvolvimento Quantum foi projetada para funcionar bem com pacotes químicas computacionais, mais notavelmente a plataforma química computacional [**NWChem**](http://www.nwchem-sw.org/) desenvolvida pelo laboratório de Ciências molecular ambiental ( EMSL) no laboratório nacional do noroeste do Pacífico.
Em particular, o pacote de `Microsoft.Quantum.Chemistry` fornece ferramentas para carregar instâncias de problemas de simulação de química do Quantum representados no [esquema Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), também com suporte para exportação por versões recentes do NWChem.

Para começar a usar o NWChem junto com o kit de desenvolvimento Quantum, sugerimos um dos seguintes métodos:
- Comece a usar os arquivos Broombridge existentes fornecidos com os exemplos em [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML).
- Use o [Construtor de setas EMSL para o Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) que é um front-end baseado na Web para NWChem, para gerar novos arquivos de entrada molecular Broombridge.  
- Use a [imagem do Docker](https://hub.docker.com/r/nwchemorg/nwchem-qc/) fornecida pelo PNNL para executar NWChem ou
- [Compile o NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) para sua plataforma.

Consulte de [ponta a ponta com NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) para obter mais informações sobre como trabalhar com o NWChem para modelos químicos para analisar com a biblioteca do Quantum Developer Kit química.

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>Introdução ao uso de arquivos Broombridge fornecidos com os exemplos
A pasta [IntegralData/YAML](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML) no repositório de exemplos do kit de desenvolvimento do Quantum contém arquivos de dados molécula com formato Broombridge.  

Como um exemplo simples, use o exemplo de biblioteca de química, [GetGateCount](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount) para carregar o Hamiltonian de um dos arquivos Broombridge e executar estimativas de portão de algorigthms de simulação de Quantum:

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

Consulte [carregando um Hamiltonian do arquivo](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) para obter mais informações sobre como inserir moléculas representado pelo esquema Broombridge.  

Confira [obtendo contagens de recursos](xref:microsoft.quantum.chemistry.examples.resourcecounts) para obter mais informações sobre a estimativa de recursos.  

### <a name="getting-started-using-the-emsl-arrows-builder"></a>Introdução ao uso do construtor de setas EMSL

EMSL Arrows é uma ferramenta que usa bancos de dados computacionais NWChem e químicas para gerar molécula.  [O EMSL Arrows Builder para o Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) permite que você insira seu modelo usando vários construtores de modelo molecular e gere o arquivo de configuração do Broombridge para ser usado pelo kit de desenvolvimento Quantum.  

Na página EMSL, clique na guia [' instuctions '] e siga as instruções [' exemplos simples '] para gerar arquivos Broombridge.  Em seguida, tente executar [' GetGateCount '] para ver as estimativas de recursos Quantum para esses moléculas.

### <a name="installing-nwchem-from-source"></a>Instalando o NWChem da origem

Instruções completas sobre como instalar o NWChem da origem [são fornecidas pelo PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).

> [!TIP]
> Se você quiser usar o NWChem do Windows 10, o subsistema do Windows para Linux é uma ótima opção.
> Depois de instalar o [Ubuntu 18, 4 LTS para Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), execute `ubuntu18.04` do seu terminal favorito e siga as instruções acima para instalar o NWChem da origem.

Depois de ter compilado o NWChem da origem, você pode executar o script de `yaml_driver` fornecido com NWChem para produzir rapidamente instâncias de Broombridge de baralhos de entrada NWChem:

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

Esse comando criará um novo arquivo de `input.yaml` no formato Broombridge no diretório atual.

### <a name="using-nwchem-with-docker"></a>Usando o NWChem com o Docker

As imagens predefinidas para usar o NWChem estão disponíveis para a plataforma cruzada por meio do [Hub do Docker](https://hub.docker.com).
Para começar, siga as instruções de instalação do Docker para sua plataforma:

- [Instalar o Docker para Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [Instalar o Docker para macOS](https://docs.docker.com/docker-for-mac/install/)
- [Instalar o Docker for Windows 10](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> Se estiver usando Docker for Windows, você precisará compartilhar a unidade que contém seu diretório temporário (geralmente, essa é a unidade `C:\`) com o daemon do Docker. Consulte a [documentação do Docker](https://docs.docker.com/docker-for-windows/#shared-drives) para obter mais detalhes.

Depois de instalar o Docker, você pode usar o módulo do PowerShell fornecido com os exemplos do kit de desenvolvimento do Quantum para executar a imagem ou pode executar a imagem manualmente.
Nós detalhamos o uso do PowerShell aqui; Se você quiser usar a imagem do Docker manualmente, consulte a [documentação fornecida com a imagem](https://hub.docker.com/r/nwchemorg/nwchem-qc/).

#### <a name="running-nwchem-through-powershell-core"></a>Executando o NWChem por meio do PowerShell Core

Para usar a imagem do Docker NWChem com o kit de desenvolvimento Quantum, fornecemos um pequeno módulo do PowerShell que lida com a movimentação de arquivos para dentro e fora do NWChem para você.
Se você ainda não tiver o PowerShell Core instalado, poderá baixá-lo entre plataformas do [repositório do PowerShell no GitHub](https://github.com/PowerShell/PowerShell#get-powershell).

> [!NOTE]
> O PowerShell Core também é usado para alguns exemplos para demonstrar a interoperabilidade com fluxos de trabalho de ciência de dados e análise de negócios.

Depois de instalar o PowerShell Core, importe `InvokeNWChem.psm1` para disponibilizar os comandos do NWChem em sua sessão atual:

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

Isso tornará o comando `Convert-NWChemToBroombridge` disponível em sua sessão atual do PowerShell.
Para baixar todas as imagens necessárias do Docker e usá-las para executar os baralhos de entrada do NWChem e capturar a saída para Broombridge, execute o seguinte:

```powershell
Convert-NWChemToBroombridge ./input.nw
```

Isso criará um arquivo Broombridge executando NWChem em `input.nw`.
Por padrão, a saída de Broombridge terá o mesmo nome e caminho que o baralho de entrada, com a extensão de `.nw` substituída por `.yaml`.
Isso pode ser substituído usando o parâmetro `-DestinationPath` para `Convert-NWChemToBroombridge`.
Mais informações podem ser obtidas usando a funcionalidade interna de ajuda do PowerShell:

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```


