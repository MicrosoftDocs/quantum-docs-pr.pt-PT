---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: Função deficantes expandidos
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: b953fb8f5737956e8597cd90a7d6bfc0bafce4e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835626"
---
# <a name="expandedcoefficients-function"></a>Função deficantes expandidos

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Pacote: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Expande a representação compacta dos coeficientes Jordan-Wigner de forma a obter um mapeamento um-para-um entre estes e os termos Pauli.

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a>Entrada

### <a name="coeff--double"></a>coeff : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Uma variedade de coeficientes, como lidos a partir da estrutura de dados Jordan-Wigner Hamiltonian.


### <a name="termtype--int"></a>termoType : [Int](xref:microsoft.quantum.lang-ref.int)

O tipo de termo Jordan-Wigner.



## <a name="output--double"></a>Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)[]

Matrizes expandidas de coeficientes, um por termo Pauli.