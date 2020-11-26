---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: Função deficantes expandidos
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 92d7deb7010791e7de3d22ad4616b20110d5e84e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214386"
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