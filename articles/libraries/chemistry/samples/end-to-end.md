---
title: Programa quântico da amostra NWChem
description: Usando um deck de entrada NWChem, caminhe por um exemplo de obter contagens de portão para simulação de química quântica.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
ms.openlocfilehash: 545ade99859f2a9939477fb18604921f70a5d9aa
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906513"
---
# <a name="end-to-end-with-nwchem"></a>Ponto a ponto com NWChem #

Nesta página, vamos percorrer um exemplo de obter contagens de portão para simulação de química quântica, a partir de um deck de entrada [NWChem.](http://www.nwchem-sw.org/index.php/Main_Page)
Antes de prosseguir com este exemplo, certifique-se de que instalou o Docker, seguindo o guia de [instalação e validação](xref:microsoft.quantum.chemistry.concepts.installation).

Para obter mais informações:
- [Estrutura dos decks de entrada NWChem](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [Comandos de deck de entrada para uso com o Kit de Desenvolvimento Quântico](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [Instalação da biblioteca de química e dependências](xref:microsoft.quantum.chemistry.concepts.installation)
- [Contagem de recursos](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> Este exemplo requer que o Windows PowerShell Core seja executado.
> Baixe powerShell Core para Windows, macOS ou Linux em https://github.com/PowerShell/PowerShell.

## <a name="importing-required-powershell-modules"></a>Importação de módulos PowerShell necessários ##

Se ainda não o fez, clone o [repositório Microsoft/Quantum,](https://github.com/Microsoft/Quantum)que contém amostras e utilidades para trabalhar com o Kit de Desenvolvimento Quântico:

```powershell
git clone https://github.com/Microsoft/Quantum
```

Depois de clonar `Microsoft/Quantum`, execute `cd` na pasta `utilities/` e importe o módulo PowerShell para trabalhar com Docker e NWChem:

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> Por predefinição, o Windows impede a execução de quaisquer scripts ou módulos como medida de segurança.
> Para permitir que módulos como `Invoke-NWChem.psm1` a funcionar no Windows, poderá ter de alterar a política de execução.
> Para isso, dirija o comando `Set-ExecutionPolicy`:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> A política de execução será revertida quando sair da PowerShell.
> Se quiser salvar a política de execução, utilize um valor diferente para `-Scope`:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

Deve agora ter o comando `Convert-NWChemToBroombridge` disponível:

```powershell
Get-Command -Module InvokeNWChem
```

Em seguida, importaremos o comando `Get-GateCount` fornecido com a amostra **GetGateCount.**
Para mais detalhes, consulte as [instruções fornecidas com a amostra](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount).
Em seguida, execute o seguinte, substituindo `<runtime>` por `win10-x64`, `osx-x64`, ou `linux-x64`, dependendo do seu sistema operativo:

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

Deve agora ter o comando `Get-GateCount` disponível:

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a>Decks de entrada ##

O pacote NWChem pega num ficheiro de texto chamado deck de _entrada_ que especifica um problema de química quântica a ser resolvido, juntamente com outros parâmetros, tais como definições de atribuição de memória.
Para este exemplo, usaremos um dos decks de entrada pré-fabricados que vem com a NWChem.
Primeiro, clone o [repositório nwchemgit/nwchem:](https://github.com/nwchemgit/nwchem)

> [!NOTE]
> Uma vez que este é um repositório muito grande, podemos fazer um clone raso para poupar algum espaço de largura de banda e disco, usando o argumento `--depth 1`.
> Isto é opcional, no entanto.
> A clonagem funcionará muito bem sem `--depth 1`.

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

O repositório `nwchemgit/nwchem` vem com uma variedade de decks de entrada destinados a ser utilizados com o Kit de Desenvolvimento Quântico, listado na [pasta`QA/chem_library_tests`](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).
Para este exemplo, usaremos o deck de entrada `H4`:

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

A molécula em questão é um sistema de 4 átomos de hidrogénio que estão dispostos numa certa geometria que depende de um ângulo, o parâmetro `alpha` como indicado no nome `h4_sto6g_alpha.nw` do convés. H4 é uma [referência molecular](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) conhecida para química computacional desde a década de 1970. O parâmetro `sto6g` indica que o convés implementa uma representação no que diz respeito a um orbital do tipo Slater, especificamente, uma representação em relação a uma [base STO-nG definida](https://en.wikipedia.org/wiki/STO-nG_basis_sets) com 6 funções de base gaussiana. Este deck de entrada contém ainda várias instruções para o NWChem Tensor Contraction Engine (TCE) que direciona a NWChem para produzir as informações necessárias para interoperação com o Kit de Desenvolvimento Quântico:

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a>Produção e Consumo de Broombridge Output da NWChem ##

Agora temos tudo o que precisamos para produzir e consumir documentos de Broombridge.
Para executar a NWChem e produzir um documento broombridge para o deck de entrada `h4_sto6g_0.000.nw`, executar `Convert-NWChemToBroombridge`:

> [!NOTE]
> A primeira vez que dirigeeste este comando, o Docker vai descarregar a imagem `nwchemorg/nwchem-qc` para ti.
> Isto pode demorar um pouco, dependendo da sua velocidade de ligação, possivelmente proporcionando uma oportunidade de tomar uma xícara de café.

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

Isto produzirá um documento de Broombridge chamado `h4_sto6g_0.000.yaml` que podemos usar com `Get-GateCount`:

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

Deve agora ver a saída da consola que contém estimativas de recursos, tais como contagem de T, contagem de rotações, contagem de CNOT, etc. para vários métodos de simulação quântica:

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

Há muitas coisas para fazer a partir daqui: 
- Experimente diferentes decks de entrada predefinidos, por exemplo, variando o parâmetro `alpha` em `h4_sto6g_alpha.nw`, 
- Tente modificar os decks editando diretamente os decks NWChem, por exemplo, explorando `STO-nG` modelos para várias escolhas de n, 
- Experimente outros decks de entrada PRÉ-definidos da NWChem que estão disponíveis em `nwchem/qa/chem_library_tests`,
- Experimente um conjunto de referências YAML de Broombridge pré-definidas que foram geradas a partir da NWChem e estão disponíveis como parte do [repositório Microsoft/Quantum](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML). Estes critérios incluem: 
    - pequenas moléculas como o hidrogénio molecular (H2), Beryllium (Be), o hidreto de lítio (LiH),
    - moléculas maiores como o ozono (O3), beta-caroteno, citosina, e muito mais. 
- Experimente as [setas emslémicas](https://arrows.emsl.pnnl.gov/api/qsharp_chem) de ponta gráfica que possui uma interface para o Kit de Desenvolvimento Quântico da Microsoft. 


## <a name="producing-broombridge-output-from-emsl-arrows"></a>Produção de saída de Broombridge a partir de setas EMSL ##

Para começar com as setas EMSL front-based web, navegue um navegador [aqui](https://arrows.emsl.pnnl.gov/api/qsharp_chem). 

> [!NOTE]
> Executar setas EMSL num navegador web requer que o JavaScript seja ativado. Consulte estas [instruções](https://www.enable-javascript.com/) sobre como ativar o JavaScript no seu navegador. 

Primeiro, introduza uma molécula na caixa de consulta que diz ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.`` 

Pode introduzir muitas moléculas pelo seu nome coloquial, como "cafeína" em vez de "1,3,7-Trimetilxantina". 

Em seguida, clique no botão que diz ``theory{qsharp_chem}``. Isto irá povoar ainda mais a caixa de consulta com uma instrução que dirá a corrida para exportar a produção no formato Broombridge YAML. 

Agora, o relógio na ``Run Arrows``. Dependendo do tamanho da entrada, isto pode demorar um pouco. Ou, caso o modelo em particular já tenha sido calculado antes, pode ser feito extremamente rápido, uma vez que só será procurado numa base de dados. Em qualquer dos casos, você será levado para uma nova página que contém uma infinidade de informações sobre a execução particular de NWChem contra o deck especificado pela sua entrada. 

Pode descarregar e guardar o ficheiro Broombridge YAML da secção que começa com o seguinte cabeçalho: 
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

Clique em ``download``, que guarda uma cópia local com um nome de ficheiro único, como ``qsharp_chem48443.yaml`` (o nome em particular será diferente para cada execução). Em seguida, pode processar ainda mais este ficheiro como acima, por exemplo, com 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
para obter contagens de recursos. 

Você pode desfrutar do construtor de moléculas 3D que pode ser acedido a partir do separador ``Arrows Entry - 3D Builder`` na página de início de Setas EMSL. Clicar na imagem 3D de [JSMol](http://wiki.jmol.org/index.php/JSmol) da molécula mostrada permitirá que a edite. Pode mover átomos, arrastar átomos para que as suas distâncias intermoleculares mudem, adicione/remova átomos, etc. Para cada uma destas escolhas, uma vez adicionado``theory{qsharp_chem}`` na caixa de consulta, pode então gerar uma instância do esquema YAML de Broombridge e explorá-lo ainda mais usando a Biblioteca de Química Quântica. 
