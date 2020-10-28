---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: Função HTermsToGenSys
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: b78ff393fa1e51c38028ef56bb3c61b8f1d5e478
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714839"
---
# <a name="htermstogensys-function"></a>Função HTermsToGenSys

Espaço de nome: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)

Pacote: [](https://nuget.org/packages/)


Converte um Hamiltonian em `HTerm[]` formato de dados para um GeneratorSystem.

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Entrada

### <a name="data--hterm"></a>dados : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

Inserir dados em `HTerm[]` formato.


### <a name="termtype--int"></a>termoType : [Int](xref:microsoft.quantum.lang-ref.int)[]

Informação adicional adicionada ao GeneratorIndex.



## <a name="output--generatorsystem"></a>Saída : [Sistema Gerador](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Um Sistema Gerador representando um Hamiltonian representado pela entrada `data` .