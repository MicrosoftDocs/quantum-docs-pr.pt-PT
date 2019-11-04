---
title: De ponta a ponta com NWChem | Microsoft Docs
description: Ponta a ponta com o NWChem docs
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
ms.openlocfilehash: 8f727ea4599e06b41ced561c624c4e773b9887d9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185822"
---
# <a name="end-to-end-with-nwchem"></a>Ponta a ponta com NWChem #

Nesta página, veremos um exemplo de como obter contagens de portão para a simulação química do Quantum, a partir de um baralho de entrada [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) .
Antes de continuar com este exemplo, verifique se você instalou o Docker, seguindo o [Guia de instalação e validação](xref:microsoft.quantum.chemistry.concepts.installation).

Para mais informações:
- [Estrutura de baralhos de entrada NWChem](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [Comandos de baralho de entrada para uso com o kit de desenvolvimento Quantum](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [Instalando a biblioteca e as dependências química](xref:microsoft.quantum.chemistry.concepts.installation)
- [Contagem de recursos](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> Este exemplo requer que o Windows PowerShell Core seja executado.
> Baixe o PowerShell Core para Windows, macOS ou Linux em https://github.com/PowerShell/PowerShell.

## <a name="importing-required-powershell-modules"></a>Importando módulos do PowerShell necessários ##

Se você ainda não fez isso, clone o [repositório Microsoft/Quantum](https://github.com/Microsoft/Quantum), que contém exemplos e utilitários para trabalhar com o kit de desenvolvimento Quantum:

```powershell
git clone https://github.com/Microsoft/Quantum
```

Depois de clonar `Microsoft/Quantum`, execute `cd` na pasta `utilities/` e importe o módulo do PowerShell para trabalhar com Docker e NWChem:

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> Por padrão, o Windows impede a execução de qualquer script ou módulo como uma medida de segurança.
> Para permitir que módulos como `Invoke-NWChem.psm1` sejam executados no Windows, talvez seja necessário alterar a política de execução.
> Para fazer isso, execute o comando `Set-ExecutionPolicy`:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> A política de execução será revertida quando você sair do PowerShell.
> Se você quiser salvar a política de execução, use um valor diferente para `-Scope`:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

Agora você deve ter o comando `Convert-NWChemToBroombridge` disponível:

```powershell
Get-Command -Module InvokeNWChem
```

Em seguida, importaremos o comando `Get-GateCount` fornecido com o exemplo **GetGateCount** .
Para obter detalhes completos, consulte as [instruções fornecidas com o exemplo](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount).
Em seguida, execute o seguinte, substituindo `<runtime>` pelo `win10-x64`, `osx-x64`ou `linux-x64`, dependendo do seu sistema operacional:

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

Agora você deve ter o comando `Get-GateCount` disponível:

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a>Baralhos de entrada ##

O pacote NWChem pega um arquivo de texto chamado um _baralho de entrada_ que especifica um problema de química do Quantum a ser resolvido, juntamente com outros parâmetros, como configurações de alocação de memória.
Para este exemplo, usaremos um dos baralhos de entrada predefinidos que vem com NWChem.
Primeiro, clone o [repositório nwchemgit/nwchem](https://github.com/nwchemgit/nwchem):

> [!NOTE]
> Como esse é um repositório muito grande, podemos fazer um clone superficial para economizar alguma largura de banda e espaço em disco, usando o argumento `--depth 1`.
> No entanto, isso é opcional.
> A clonagem funcionará bem sem `--depth 1`.

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

O repositório de `nwchemgit/nwchem` vem com uma variedade de baralhos de entrada destinados ao uso com o kit de desenvolvimento Quantum, listado na [pasta`QA/chem_library_tests`](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).
Para este exemplo, usaremos o baralho de entrada `H4`:

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

O molécula em questão é um sistema de 4 Hydrogen Atoms que são organizados em uma determinada geometria que depende de um ângulo, o parâmetro `alpha` conforme indicado no nome `h4_sto6g_alpha.nw` do baralho. H4 é um parâmetro de [comparação molecular](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) conhecido para química computacional desde o 70. O parâmetro `sto6g` é indica que o baralho implementa uma representação em relação a um orbital de tipo Slater, especificamente, uma representação com relação a um [conjunto de base ARM-ng](https://en.wikipedia.org/wiki/STO-nG_basis_sets) com 6 funções de base gaussianas. Esse baralho de entrada contém várias instruções para o mecanismo de NWChem tensor (TCE) que direciona o NWChem para produzir as informações necessárias para interoperar com o kit de desenvolvimento Quantum:

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a>Produzindo e consumindo a saída de Broombridge de NWChem ##

Agora temos tudo o que precisamos para produzir e consumir documentos Broombridge.
Para executar o NWChem e produzir um documento Broombridge para o baralho de entrada `h4_sto6g_0.000.nw`, execute `Convert-NWChemToBroombridge`:

> [!NOTE]
> Na primeira vez que você executar esse comando, o Docker baixará a imagem de `nwchemorg/nwchem-qc` para você.
> Isso pode demorar um pouco, dependendo da velocidade da sua conexão, possivelmente oferecendo uma oportunidade de café.

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

Isso produzirá um documento Broombridge chamado `h4_sto6g_0.000.yaml` que podemos usar com `Get-GateCount`:

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

Agora você deve ver a saída do console que contém a estimativa de recurso, como contagem de T, contagem de rotações, contagem de CNOT, etc. para vários métodos de simulação de Quantum:

```powershell 
IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Trotter
TCount              : 0
RotationsCount      : 92
CNOTCount           : 520
ElapsedMilliseconds : 327

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Qubitization
TCount              : 438
RotationsCount      : 516
CNOTCount           : 2150
ElapsedMilliseconds : 528

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Optimized Qubitization
TCount              : 3540
RotationsCount      : 18
CNOTCount           : 7932
ElapsedMilliseconds : 721
```

Há muitas coisas a serem passadas aqui: 
- Experimente os baralhos de entrada predefinidos diferentes, por exemplo, variando o parâmetro `alpha` em `h4_sto6g_alpha.nw`, 
- Tente modificar os baralhos editando os barNWChems diretamente, por exemplo, explorando modelos de `STO-nG` para várias opções de n, 
- Tente outros barNWChem de entrada predefinidos que estejam disponíveis em `nwchem/qa/chem_library_tests`,
- Experimente um conjunto de benchmarks predefinidos do Broombridge YAML que foram gerados do NWChem e estão disponíveis como parte do [repositório Microsoft/Quantum](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML). Esses parâmetros de comparação incluem: 
    - moléculas pequeno, como molecular Hydrogen (H2), Beryllium (ser), lítio hydride (LiH),
    - moléculas maiores, como ozônio (O3), beta-carotene, cytosine e muito mais. 
- Experimente as [setas de EMSL](https://arrows.emsl.pnnl.gov/api/qsharp_chem) de front-end gráficas que apresenta uma interface para a Microsoft Quantum Development Kit. 


## <a name="producing-broombridge-output-from-emsl-arrows"></a>Produzindo saída Broombridge de setas EMSL ##

Para começar a usar as setas EMSL de front-end baseadas na Web, navegue até um navegador [aqui](https://arrows.emsl.pnnl.gov/api/qsharp_chem). 

> [!NOTE]
> A execução de setas EMSL em um navegador da Web requer que o JavaScript esteja habilitado. Veja estas [instruções](https://www.enable-javascript.com/) sobre como habilitar o JavaScript em seu navegador. 

Primeiro, insira um molécula na caixa de consulta que diz ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.`` 

Você pode inserir muitos moléculas por seu nome de uso coloquial, como "cafeína" em vez de "1, 3, 7-Trimethylxanthine". 

Em seguida, clique no botão que indica ``theory{qsharp_chem}``. Isso preencherá a caixa de consulta mais detalhadamente com uma instrução que dirá a execução para exportar a saída no formato Broombridge YAML. 

Agora, o relógio ``Run Arrows``. Dependendo do tamanho da entrada, isso pode levar algum tempo. Ou, caso o modelo específico já tenha sido computado antes, ele pode ser feito de forma muito rápida, uma vez que será apenas uma pesquisa em um banco de dados. Em ambos os casos, você será levado para uma nova página que contém uma grande quantidade de informações sobre a execução específica de NWChem em relação ao baralho especificado por sua entrada. 

Você pode baixar e salvar o arquivo Broombridge YAML da seção que começa com o seguinte cabeçalho: 
```powershell
+==================================================+
||              Molecular Calculation             ||
+==================================================+

Id     = 48443

NWOutput = Link to NWChem Output (download)

Datafiles:
qsharp_chem.yaml-2018-10-23-14:37:42 (download)
...
```

Clique em ``download``, que salva uma cópia local com um nome de arquivo exclusivo, como ``qsharp_chem48443.yaml`` (o nome específico será diferente para cada execução). Em seguida, você pode processar esse arquivo como acima, por exemplo, com 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
para obter contagens de recursos. 

Você pode desfrutar do construtor de molécula 3D que pode ser acessado na guia ``Arrows Entry - 3D Builder`` na página inicial das setas EMSL. Clicar na imagem 3D [JSMol](http://wiki.jmol.org/index.php/JSmol) do molécula mostrado permitirá que você o edite. Você pode mover os átomos, arrastar Atoms para que suas distâncias entre molecular sejam alteradas, adicionar/remover Atoms, etc. Para cada uma dessas opções, depois de adicionar ``theory{qsharp_chem}`` na caixa de consulta, você pode gerar uma instância do esquema Broombridge YAML e explorá-la ainda mais usando a biblioteca química do Quantum. 
