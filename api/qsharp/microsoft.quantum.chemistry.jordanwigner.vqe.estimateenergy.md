---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: Estimativa OperaçãoEnergia
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: 52e527a68818c80f93bc177d3563064fd0f2aea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713747"
---
# <a name="estimateenergy-operation"></a>Estimativa OperaçãoEnergia

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Pacote: [](https://nuget.org/packages/)


Estima a energia da molécula somando a energia contribuida pelo indivíduo Jordan-Wigner termos.

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a>Descrição

Esta operação baseia-se implicitamente na convenção de indexação de rotação para cima.

## <a name="input"></a>Entrada

### <a name="jwhamiltonian--jordanwignerencodingdata"></a>jwHamiltonian : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)

O Jordan-Wigner Hamiltonian.


### <a name="nsamples--int"></a>nSamples : [Int](xref:microsoft.quantum.lang-ref.int)

O número de amostras a utilizar para a estimativa das expectativas do termo.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)

A energia estimada da molécula