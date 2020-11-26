---
uid: Microsoft.Quantum.Math.RealMod
title: Função RealMod
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228258"
---
# <a name="realmod-function"></a><span data-ttu-id="eedb8-102">Função RealMod</span><span class="sxs-lookup"><span data-stu-id="eedb8-102">RealMod function</span></span>

<span data-ttu-id="eedb8-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="eedb8-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="eedb8-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eedb8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eedb8-105">Calcula o módulo entre dois números reais.</span><span class="sxs-lookup"><span data-stu-id="eedb8-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="eedb8-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="eedb8-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="eedb8-107">valor : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eedb8-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eedb8-108">Um número real $x dólares para tomar o módulo de.</span><span class="sxs-lookup"><span data-stu-id="eedb8-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="eedb8-109">modulo : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eedb8-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eedb8-110">Um número real para tomar o módulo de $x$ em relação a.</span><span class="sxs-lookup"><span data-stu-id="eedb8-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="eedb8-111">minValue : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eedb8-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eedb8-112">O menor valor a ser devolvido por esta função.</span><span class="sxs-lookup"><span data-stu-id="eedb8-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="eedb8-113">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eedb8-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="eedb8-114">Observações</span><span class="sxs-lookup"><span data-stu-id="eedb8-114">Remarks</span></span>

<span data-ttu-id="eedb8-115">Esta função calcula o verdadeiro módulo envolvendo a linha real sobre o círculo unitário e, em seguida, encontrando o ângulo no círculo unitário correspondente à entrada.</span><span class="sxs-lookup"><span data-stu-id="eedb8-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="eedb8-116">`minValue`A entrada especifica então eficazmente onde cortar o círculo unitário.</span><span class="sxs-lookup"><span data-stu-id="eedb8-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>