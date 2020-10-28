---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedGeneratorSystem
title: Função JWOptimizedGeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 8e4c06b9447a2e5838cced876febee03d1af5315
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710779"
---
# <a name="jwoptimizedgeneratorsystem-function"></a>Função JWOptimizedGeneratorSystem

Espaço de nome: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Pacote: [](https://nuget.org/packages/)


Converte um Hamiltonian descrito por `JWOptimizedHTerms` um expresso em termos da `GeneratorSystem` `GeneratorIndex` convenção definida neste ficheiro.

```qsharp
function JWOptimizedGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Entrada

### <a name="data--jwoptimizedhterms"></a>dados : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)

Descrição de Hamiltonian em `JWOptimizedHTerms` formato.



## <a name="output--generatorsystem"></a>Saída : [Sistema Gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Representação de Hamiltonian como `GeneratorSystem` .