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
# <a name="dumpmachine-function"></a>Função DumpMachine

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [](https://nuget.org/packages/)


Despeja o estado atual da máquina alvo.

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a>Entrada

### <a name="location--t"></a>localização : 'T

Fornece informações sobre onde gerar o despejo da máquina.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)

Nenhum.

## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="remarks"></a>Observações

Este método permite-lhe despejar informações sobre o estado atual da máquina-alvo num ficheiro ou noutro local.
A informação real gerada e a semântica `location` são específicas de cada máquina alvo. No entanto, fornecer um tuple vazio como um local `()` () ou apenas omitir o `location` parâmetro normalmente significa gerar a saída para a consola.

Para o simulador de estado completo local distribuído como parte do Kit de Desenvolvimento Quântico, este método espera uma cadeia com o caminho para um ficheiro no qual escreverá a função de onda como uma matriz unidimensional de números complexos, em que cada elemento representa as amplitudes da probabilidade de medir o estado correspondente.