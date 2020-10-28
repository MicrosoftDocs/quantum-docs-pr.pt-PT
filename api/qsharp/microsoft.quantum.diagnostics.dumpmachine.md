---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: Função DumpMachine
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: c85cf6764bdc913a71448c525318f45743bf1df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712876"
---
# <a name="dumpmachine-function"></a><span data-ttu-id="31f4c-102">Função DumpMachine</span><span class="sxs-lookup"><span data-stu-id="31f4c-102">DumpMachine function</span></span>

<span data-ttu-id="31f4c-103">Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="31f4c-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="31f4c-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="31f4c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="31f4c-105">Despeja o estado atual da máquina alvo.</span><span class="sxs-lookup"><span data-stu-id="31f4c-105">Dumps the current target machine's status.</span></span>

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="31f4c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="31f4c-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="31f4c-107">localização : 'T</span><span class="sxs-lookup"><span data-stu-id="31f4c-107">location : 'T</span></span>

<span data-ttu-id="31f4c-108">Fornece informações sobre onde gerar o despejo da máquina.</span><span class="sxs-lookup"><span data-stu-id="31f4c-108">Provides information on where to generate the machine's dump.</span></span>



## <a name="output--unit"></a><span data-ttu-id="31f4c-109">Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="31f4c-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="31f4c-110">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="31f4c-110">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="31f4c-111">Parâmetros de Tipo Genérico</span><span class="sxs-lookup"><span data-stu-id="31f4c-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="31f4c-112">'T</span><span class="sxs-lookup"><span data-stu-id="31f4c-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="31f4c-113">Observações</span><span class="sxs-lookup"><span data-stu-id="31f4c-113">Remarks</span></span>

<span data-ttu-id="31f4c-114">Este método permite-lhe despejar informações sobre o estado atual da máquina-alvo num ficheiro ou noutro local.</span><span class="sxs-lookup"><span data-stu-id="31f4c-114">This method allows you to dump information about the current status of the target machine into a file or some other location.</span></span>
<span data-ttu-id="31f4c-115">A informação real gerada e a semântica `location` são específicas de cada máquina alvo.</span><span class="sxs-lookup"><span data-stu-id="31f4c-115">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="31f4c-116">No entanto, fornecer um tuple vazio como um local `()` () ou apenas omitir o `location` parâmetro normalmente significa gerar a saída para a consola.</span><span class="sxs-lookup"><span data-stu-id="31f4c-116">However, providing an empty tuple as a location (`()`) or just omitting the `location` parameter typically means to generate the output to the console.</span></span>

<span data-ttu-id="31f4c-117">Para o simulador de estado completo local distribuído como parte do Kit de Desenvolvimento Quântico, este método espera uma cadeia com o caminho para um ficheiro no qual escreverá a função de onda como uma matriz unidimensional de números complexos, em que cada elemento representa as amplitudes da probabilidade de medir o estado correspondente.</span><span class="sxs-lookup"><span data-stu-id="31f4c-117">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the wave function as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>