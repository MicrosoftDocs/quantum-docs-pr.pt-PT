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
# <a name="expandedcoefficients-function"></a><span data-ttu-id="e8b7c-102">Função deficantes expandidos</span><span class="sxs-lookup"><span data-stu-id="e8b7c-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="e8b7c-103">Espaço de nome: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="e8b7c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="e8b7c-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e8b7c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e8b7c-105">Expande a representação compacta dos coeficientes Jordan-Wigner de forma a obter um mapeamento um-para-um entre estes e os termos Pauli.</span><span class="sxs-lookup"><span data-stu-id="e8b7c-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="e8b7c-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="e8b7c-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="e8b7c-107">coeff : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e8b7c-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e8b7c-108">Uma variedade de coeficientes, como lidos a partir da estrutura de dados Jordan-Wigner Hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="e8b7c-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="e8b7c-109">termoType : [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e8b7c-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e8b7c-110">O tipo de termo Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="e8b7c-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="e8b7c-111">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="e8b7c-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="e8b7c-112">Matrizes expandidas de coeficientes, um por termo Pauli.</span><span class="sxs-lookup"><span data-stu-id="e8b7c-112">Expanded arrays of coefficients, one per Pauli term.</span></span>