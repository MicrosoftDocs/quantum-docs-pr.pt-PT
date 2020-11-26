---
uid: Microsoft.Quantum.AmplitudeAmplification
title: Microsoft.Quantum.AmplitudeAmplificação espaço de nomes
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: namespace
qsharp.name: Microsoft.Quantum.AmplitudeAmplification
qsharp.summary: This namespace contains functions and operations for performing amplitude amplification.
ms.openlocfilehash: f265f1f8b41513f9201a758f85451e768b7564e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191419"
---
# <a name="microsoftquantumamplitudeamplification-namespace"></a>Microsoft.Quantum.AmplitudeAmplificação espaço de nomes

Este espaço de nome contém funções e operações para a realização de amplificação de amplitude.



## <a name="description"></a>Description

Amplificação de amplitude alheia com reflexos parciais é a forma mais geral de amplificação de amplitude implementada aqui.

Isto é chamado através da operação AmpAmpObliviousByReflectionPhases.

Este tem dois registos: `ancillaRegister` e `systemRegister` .

Isto aceita dois oráculos para estas reflexões do tipo `ReflectionOracle` que atuam apenas no `ancillaRegister` registo.

Isto aceita um oráculo especial para amplificação de amplitude alheia do tipo `ObliviousOracle` que atua conjuntamente em ambos os registos.

O estado de entrada `ancillaRegister` é assumido como o único $-1$ eigenstate do primeiro operador de reflexão $I - 2\ket{s}\bra{s}$.

As reflexões sobre um estado quântico alvo são frequentemente implementadas assumindo o acesso a um oráculo que prepara esse estado a partir da base computacional $\ket{0\cdots 0}$.

A nossa convenção para estes oráculos requer dois registos: um registo de um único qubit `flagQubit` e um registo para tudo o resto no registo do Registo DeCilla.

O oráculo do tipo `StateOracle` atua conjuntamente em ambos os registos para criar o estado-alvo sinalizado por $\ket {1} $ no registo com alguma amplitude `flagQubit` real.

A reflexão `ReflectionOracle` sobre o estado de bandeira é gerada pela operação. `TargetStateReflectionOracle`

A reflexão `ReflectionOracle` sobre o estado de entrada é gerada pelo `ancillaRegister` StateOracle inverting e, em seguida, refletindo sobre $\ket{0\cdots 0}$ com ReflectionStart().

O oráculo do tipo `DeterministicStateOracle` atua nos `qubitState` registos para criar o estado-alvo exatamente sem bandeira.

`AmpAmpObliviousByOraclePhases` é uma versão da amplificação da amplitude alheia que aceita oráculos `StateOracle` e em vez de `ObliviousOracle` reflexões.

Note que a amplificação da amplitude é um caso especial de amplificação de amplitude alheia onde `ObliviousOracle` está o operador de identidade, e não existem qubits de sistema, ou seja, está `systemRegister` vazio.

Isto é chamado através da operação `AmpAmByReflectionPhases` e `AmpAmpByOraclePhases` .

As fases para reflexões parciais no caso padrão da pesquisa grover são fornecidas pela função AmpAmpPhasesStandard.

Por exemplo, temos as seguintes dependências: AmpAmpByOracle -> AmpAmpByOraclePhases -> AmpAmpObliviousByOraclePhases -> AmpAmpObliviousByReflectionPhases.