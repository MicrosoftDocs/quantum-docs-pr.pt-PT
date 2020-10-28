---
uid: Microsoft.Quantum.Math.RealMod
title: Função RealMod
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720406"
---
# <a name="realmod-function"></a><span data-ttu-id="f935a-102">Função RealMod</span><span class="sxs-lookup"><span data-stu-id="f935a-102">RealMod function</span></span>

<span data-ttu-id="f935a-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f935a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f935a-104">Pacote: [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f935a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f935a-105">Calcula o módulo entre dois números reais.</span><span class="sxs-lookup"><span data-stu-id="f935a-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="f935a-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="f935a-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="f935a-107">valor : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f935a-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f935a-108">Um número real $x dólares para tomar o módulo de.</span><span class="sxs-lookup"><span data-stu-id="f935a-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="f935a-109">modulo : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f935a-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f935a-110">Um número real para tomar o módulo de $x$ em relação a.</span><span class="sxs-lookup"><span data-stu-id="f935a-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="f935a-111">minValue : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f935a-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f935a-112">O menor valor a ser devolvido por esta função.</span><span class="sxs-lookup"><span data-stu-id="f935a-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="f935a-113">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f935a-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="f935a-114">Observações</span><span class="sxs-lookup"><span data-stu-id="f935a-114">Remarks</span></span>

<span data-ttu-id="f935a-115">Esta função calcula o verdadeiro módulo envolvendo a linha real sobre o círculo unitário e, em seguida, encontrando o ângulo no círculo unitário correspondente à entrada.</span><span class="sxs-lookup"><span data-stu-id="f935a-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="f935a-116">`minValue`A entrada especifica então eficazmente onde cortar o círculo unitário.</span><span class="sxs-lookup"><span data-stu-id="f935a-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>