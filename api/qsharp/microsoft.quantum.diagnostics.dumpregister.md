---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: Função DespesoRegista
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: a6d29dbf0525077fd804563f85f189740fdc0429
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712837"
---
# <a name="dumpregister-function"></a><span data-ttu-id="ecbdc-102">Função DespesoRegista</span><span class="sxs-lookup"><span data-stu-id="ecbdc-102">DumpRegister function</span></span>

<span data-ttu-id="ecbdc-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="ecbdc-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="ecbdc-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ecbdc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ecbdc-105">Despeja o estado atual da máquina-alvo associada aos qubits dados.</span><span class="sxs-lookup"><span data-stu-id="ecbdc-105">Dumps the current target machine's status associated with the given qubits.</span></span>

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ecbdc-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="ecbdc-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="ecbdc-107">localização : 'T</span><span class="sxs-lookup"><span data-stu-id="ecbdc-107">location : 'T</span></span>

<span data-ttu-id="ecbdc-108">Fornece informações sobre onde gerar o lixo do estado.</span><span class="sxs-lookup"><span data-stu-id="ecbdc-108">Provides information on where to generate the state's dump.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="ecbdc-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ecbdc-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ecbdc-110">A lista de qubits a relatar.</span><span class="sxs-lookup"><span data-stu-id="ecbdc-110">The list of qubits to report.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ecbdc-111">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ecbdc-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="ecbdc-112">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="ecbdc-112">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ecbdc-113">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="ecbdc-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ecbdc-114">'T</span><span class="sxs-lookup"><span data-stu-id="ecbdc-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="ecbdc-115">Observações</span><span class="sxs-lookup"><span data-stu-id="ecbdc-115">Remarks</span></span>

<span data-ttu-id="ecbdc-116">Este método permite-lhe despejar as informações associadas ao estado dos qubits dados num ficheiro ou em qualquer outro local.</span><span class="sxs-lookup"><span data-stu-id="ecbdc-116">This method allows you to dump the information associated with the state of the given qubits into a file or some other location.</span></span>
<span data-ttu-id="ecbdc-117">A informação real gerada e a semântica `location` são específicas de cada máquina alvo.</span><span class="sxs-lookup"><span data-stu-id="ecbdc-117">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="ecbdc-118">No entanto, fornecer um tuple vazio como uma localização `()` () normalmente significa gerar a saída para a consola.</span><span class="sxs-lookup"><span data-stu-id="ecbdc-118">However, providing an empty tuple as a location (`()`) typically means to generate the output to the console.</span></span>

<span data-ttu-id="ecbdc-119">Para o simulador de estado completo local distribuído como parte do Kit de Desenvolvimento Quântico, este método espera uma cadeia com o caminho para um ficheiro no qual escreverá o estado dos qubits dados (isto é, a função de onda do subsistema correspondente) como uma matriz unidimensional de números complexos, em que cada elemento representa as amplitudes da probabilidade de medir o estado correspondente.</span><span class="sxs-lookup"><span data-stu-id="ecbdc-119">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the state of the given qubits (i.e. the wave function of the corresponding  subsystem) as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>
<span data-ttu-id="ecbdc-120">Se os qubits dados estiverem emaranhados com outro qubit e o seu estado não puder ser separado, apenas relata que os qubits estão emaranhados.</span><span class="sxs-lookup"><span data-stu-id="ecbdc-120">If the given qubits are entangled with some other qubit and their state can't be separated, it just reports that the qubits are entangled.</span></span>