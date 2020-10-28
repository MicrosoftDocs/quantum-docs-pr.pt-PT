---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: Função deficantes expandidos
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 8f5a2319b5839d0d9e47972389330dc16dffcaf0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713716"
---
# <a name="expandedcoefficients-function"></a>Função deficantes expandidos

Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Pacote: [](https://nuget.org/packages/)


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