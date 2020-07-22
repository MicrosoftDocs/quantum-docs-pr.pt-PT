---
title: Instalação da Biblioteca de Química Microsoft Q#
description: Aprenda a instalar a biblioteca de química quântica da Microsoft e use-a com a plataforma de química computacional NWChem.
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: 0e870bb3421dddb632375a2fc8633249954f8c8b
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871539"
---
# <a name="chemistry-library-installation"></a>Instalação da Biblioteca de Química

A amostra [ **molecular de hidrogénio** ](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) usa dados de entrada molecular que são configurados manualmente.
Embora isto seja bom para pequenos exemplos, a química quântica em escala requer hamiltonianos com milhões ou biliões de termos.
Estes hamiltonianos, gerados por pacotes de química computacional escalável, são demasiado grandes para serem importados à mão.

A biblioteca de química quântica para o Kit de Desenvolvimento Quântico foi projetada para funcionar bem com pacotes de química computacional, mais notavelmente a plataforma de química computacional [**NWChem**](http://www.nwchem-sw.org/) desenvolvida pelo Laboratório de Ciências Moleculares Ambientais (EMSL) do Pacific Northwest National Laboratory.
Em particular, o pacote [ **Microsoft.Quantum.Chemistry** ](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) fornece ferramentas para carregar casos de problemas de simulação de química quântica representados no [esquema de Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), também suportado para exportação por versões recentes da NWChem.

A biblioteca de química do Kit de Desenvolvimento Quântico também fornece uma ferramenta de linha de comando, `qdk-chem` para converter entre formatos legados e [Broombridge.](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)

Esta secção detalha como usar o Kit de Desenvolvimento Quântico com NWChem e Broombridge, ou formatos legados e `qdk-chem` .

## <a name="using-the-quantum-development-kit-with-nwchem"></a>Usando o Kit de Desenvolvimento Quântico com NWChem

Para se levantar e funcionar usando o NWChem juntamente com o Kit de Desenvolvimento Quântico, utilize um dos seguintes métodos:

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

## <a name="using-the-quantum-development-kit-with-qdk-chem"></a>Usando o Kit de Desenvolvimento Quântico com`qdk-chem`

Para `qdk-chem` instalar, pode utilizar o .NET Core SDK na linha de comando:

```dotnetcli
dotnet tool install --global Microsoft.Quantum.Chemistry.Tools
```

Uma vez `qdk-chem` instalado, pode utilizar a `--help` opção para obter mais detalhes sobre a funcionalidade oferecida pela `qdk-chem` ferramenta.

Para converter de e para Broombridge, pode usar o `qdk-chem convert` comando:

```
qdk-chem convert --from fcidump --to broombridge data.fcidump --out data.yml
```

O `qdk-chem convert` comando também pode aceitar os seus dados a partir da entrada padrão, e pode escrever para a saída padrão; isso é especialmente útil dentro dos scripts e para integrar-se com ferramentas que exportam para formatos antigos.
Por exemplo, no Bash:

```bash
cat data.fcidump | qdk-convert --from fcidump --to broombridge - > data.yml
```
