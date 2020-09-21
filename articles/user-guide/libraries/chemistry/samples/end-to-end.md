---
title: Programa quântico da amostra NWChem
description: Usando um deck de entrada NWChem, caminhe através de um exemplo de obter contagens de portão para simulação de química quântica.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
no-loc:
- Q#
- $$v
ms.openlocfilehash: 528c34ea9b28b2f9b8f9a8bad681557f44bfcdaa
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759720"
---
# <a name="end-to-end-with-nwchem"></a>Ponto a ponto com NWChem #

Neste artigo, você vai percorrer um exemplo de obter contagens de portão para simulação de química quântica, a partir de um deck de entrada [NWChem.](http://www.nwchem-sw.org/index.php/Main_Page)
Antes de prosseguir com este exemplo, certifique-se de que instalou o Docker, seguindo o guia de [instalação e validação](xref:microsoft.quantum.chemistry.concepts.installation).

Para obter mais informações:
- [Estrutura dos decks de entrada NWChem](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [Comandos do deck de entrada para uso com o Kit de Desenvolvimento Quântico](https://github.com/nwchemgit/nwchem/tree/main/contrib/quasar)
- [Instalação da biblioteca de química e dependências](xref:microsoft.quantum.chemistry.concepts.installation)
- [Contagem de recursos](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> Este exemplo requer que o Windows PowerShell Core seja executado.
> Descarregue PowerShell Core para Windows, macOS ou Linux em https://github.com/PowerShell/PowerShell .

## <a name="importing-required-powershell-modules"></a>Importar Módulos PowerShell necessários ##

Se ainda não o fez, clone o [repositório Microsoft/Quantum,](https://github.com/Microsoft/Quantum)que contém amostras e utilitários para trabalhar com o Kit de Desenvolvimento Quântico:

```powershell
git clone https://github.com/Microsoft/Quantum
```

Depois de `Microsoft/Quantum` clonado, execute na pasta e `cd` `utilities/` importe o módulo PowerShell para trabalhar com Docker e NWChem:

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> Por predefinição, o Windows impede a execução de quaisquer scripts ou módulos como medida de segurança.
> Para permitir que os módulos, como `Invoke-NWChem.psm1` o Windows, possam ter de alterar a política de execução.
> Para tal, executar o `Set-ExecutionPolicy` comando:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> A política de execução será então revertida quando saires do PowerShell.
> Se quiser guardar a política de execução, use um valor diferente `-Scope` para:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

Deve agora ter o `Convert-NWChemToBroombridge` comando disponível:

```powershell
Get-Command -Module InvokeNWChem
```

Em seguida, importaremos o `Get-GateCount` comando fornecido com a amostra **GetGateCount.**
Para obter todos os detalhes, consulte as [instruções fornecidas com a amostra](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/GetGateCount).
Em seguida, executar o seguinte, substituindo `<runtime>` por qualquer `win10-x64` , `osx-x64` `linux-x64` ou, dependendo do seu sistema operativo:

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

Deve agora ter o `Get-GateCount` comando disponível:

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a>Decks de entrada ##

O pacote NWChem requer um ficheiro de texto chamado deck de _entrada_ que especifica um problema de química quântica a ser resolvido, juntamente com outros parâmetros, tais como definições de atribuição de memória.
Para este exemplo, vamos usar um dos decks de entrada pré-fabricados que vem com o NWChem.
Primeiro, clone o [repositório nwchemgit/nwchem:](https://github.com/nwchemgit/nwchem)

> [!NOTE]
> Uma vez que este é um repositório muito grande, podemos fazer um clone raso para salvar alguma largura de banda e espaço em disco, usando o `--depth 1` argumento.
> Isto é opcional, no entanto.
> A clonagem funcionará bem `--depth 1` sem.

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

O `nwchemgit/nwchem` repositório vem com uma variedade de decks de entrada destinados a ser utilizados com o Kit de Desenvolvimento Quântico, listados sob a [ `QA/chem_library_tests` pasta](https://github.com/nwchemgit/nwchem/tree/main/QA/chem_library_tests).
Para este exemplo, usaremos o `H4` deck de entrada:

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

A molécula em questão é um sistema de 4 átomos de hidrogénio que estão dispostos numa certa geometria que depende de um ângulo, o parâmetro `alpha` como indicado no nome do `h4_sto6g_alpha.nw` convés. H4 é uma [referência molecular](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) conhecida para a química computacional desde a década de 1970. O parâmetro `sto6g` é indicativo de que o convés implementa uma representação no que diz respeito a um orbital do tipo Slater, especificamente, uma representação no que diz respeito a uma [base STO-nG definida](https://en.wikipedia.org/wiki/STO-nG_basis_sets) com 6 funções base gaussianas. Este deck de entrada contém ainda várias instruções para o motor de contração de tensores NWChem (TCE) que direcionam a NWChem para produzir as informações necessárias para a interoperação com o Kit de Desenvolvimento Quântico:

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a>Produção e consumo de produção de Broombridge da NWChem ##

Agora tem tudo o que precisa para produzir e consumir documentos de Broombridge.
Para executar o NWChem e produzir um documento broombridge para o `h4_sto6g_0.000.nw` deck de entrada, `Convert-NWChemToBroombridge` corra:

> [!NOTE]
> A primeira vez que executar este comando, o Docker descarregará a `nwchemorg/nwchem-qc` imagem por si.
> Isto pode demorar um pouco, dependendo da velocidade de ligação, possivelmente proporcionando uma oportunidade para tomar um café.

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

Isto irá produzir um documento de Broombridge chamado `h4_sto6g_0.000.yaml` que pode usar `Get-GateCount` com:

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

Deve agora ver a saída da consola que contém estimativas de recursos tais como contagem de recursos, contagem de rotações, contagem de CNOT, etc. para vários métodos de simulação quântica:

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

Há muitas coisas a fazer a partir daqui: 
- Experimente diferentes decks de entrada predefinidos, por exemplo, variando o parâmetro `alpha` em `h4_sto6g_alpha.nw` , 
- Tente modificar os decks editando diretamente os decks NWChem, por exemplo, explorando `STO-nG` modelos para várias escolhas de n, 
- Experimente outros decks de entrada NWChem pré-definidos que estão disponíveis em `nwchem/qa/chem_library_tests` ,
- Experimente um conjunto de referências YAML pré-definidas de Broombridge que foram geradas a partir da NWChem e estão disponíveis como parte do [repositório Microsoft/Quantum](https://github.com/Microsoft/Quantum/tree/main/samples/chemistry/IntegralData/YAML). Estes critérios de referência incluem: 
    - pequenas moléculas como o hidrogénio molecular (H2), Beryllium (Be), o hino de lítio (LiH),
    - moléculas maiores como o ozono (O3), beta-caroteno, citosina, e muito mais. 
- Experimente as [setas EMSL](https://arrows.emsl.pnnl.gov/api/qsharp_chem) frontais gráficas que apresentam uma interface com o Microsoft Quantum Development Kit. 


## <a name="producing-broombridge-output-from-emsl-arrows"></a>Produção de Broombridge Output a partir de Setas EMSL ##

Para começar com as setas EMSL da frente baseadas na Web, navegue por um navegador [aqui.](https://arrows.emsl.pnnl.gov/api/qsharp_chem) 

> [!NOTE]
> Executar Setas EMSL num navegador web requer que o JavaScript seja ativado. Consulte estas [instruções](https://www.enable-javascript.com/) sobre como ativar o JavaScript no seu navegador. 

Primeiro, introduza uma molécula na caixa de consulta que diz ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.`` 

Pode introduzir muitas moléculas pelo seu nome coloquial, como "cafeína" em vez de "1,3,7-Trimethylxanthine". 

Em seguida, clique no botão que diz ``theory{qsharp_chem}`` . Isto irá preencher ainda mais a caixa de consulta com uma instrução que dirá a corrida para exportar a produção no formato YAML de Broombridge. 

Agora, relógio ``Run Arrows`` ligado. Dependendo do tamanho da entrada, isto pode demorar um pouco. Ou, caso o modelo em particular já tenha sido calculado anteriormente, pode ser feito extremamente rápido, uma vez que apenas equivalerá a uma procura numa base de dados. Em qualquer dos casos, você será levado para uma nova página que contém uma infinidade de informações sobre a corrida particular de NWChem contra o convés especificado pela sua entrada. 

Pode descarregar e guardar o ficheiro YAML de Broombridge a partir da secção que começa com o seguinte cabeçalho: 
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

Clique em ``download`` , que guarda uma cópia local com um nome de ficheiro único, como ``qsharp_chem48443.yaml`` (o nome em particular será diferente para cada execução). Em seguida, pode processar este ficheiro como acima, por exemplo, com 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
para obter contagem de recursos. 

Você pode desfrutar do construtor de moléculas 3D que pode ser acedido a partir do ``Arrows Entry - 3D Builder`` separador na página inicial em EMSL Arrows. Clicar na imagem 3D [JSMol](http://wiki.jmol.org/index.php/JSmol) da molécula mostrada permitirá editá-la. Pode mover átomos, arrastar os átomos para longe para que as suas distâncias inter-moleculares mudem, adicione/remova átomos, etc. Para cada uma destas escolhas, uma vez ``theory{qsharp_chem}`` adicionadas na caixa de consulta, podes então gerar uma instância do esquema YAML de Broombridge e explorá-la ainda mais utilizando a Biblioteca de Química Quântica. 
