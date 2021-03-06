---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: Estimativa OperaçãoEnergia
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: a64ac3970e3e67568f91b4e67775d834a80c04a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835716"
---
# <a name="estimateenergy-operation"></a>Estimativa OperaçãoEnergia

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


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