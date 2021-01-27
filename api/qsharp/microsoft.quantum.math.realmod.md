---
uid: Microsoft.Quantum.Math.RealMod
title: Função RealMod
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848354"
---
# <a name="realmod-function"></a><span data-ttu-id="871dd-102">Função RealMod</span><span class="sxs-lookup"><span data-stu-id="871dd-102">RealMod function</span></span>

<span data-ttu-id="871dd-103">Espaço de nome: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="871dd-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="871dd-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="871dd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="871dd-105">Calcula o módulo entre dois números reais.</span><span class="sxs-lookup"><span data-stu-id="871dd-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="871dd-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="871dd-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="871dd-107">valor : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="871dd-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="871dd-108">Um número real $x dólares para tomar o módulo de.</span><span class="sxs-lookup"><span data-stu-id="871dd-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="871dd-109">modulo : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="871dd-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="871dd-110">Um número real para tomar o módulo de $x$ em relação a.</span><span class="sxs-lookup"><span data-stu-id="871dd-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="871dd-111">minValue : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="871dd-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="871dd-112">O menor valor a ser devolvido por esta função.</span><span class="sxs-lookup"><span data-stu-id="871dd-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="871dd-113">Saída : [Duplo](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="871dd-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="example"></a><span data-ttu-id="871dd-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="871dd-114">Example</span></span>

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a><span data-ttu-id="871dd-115">Observações</span><span class="sxs-lookup"><span data-stu-id="871dd-115">Remarks</span></span>

<span data-ttu-id="871dd-116">Esta função calcula o verdadeiro módulo envolvendo a linha real sobre o círculo unitário e, em seguida, encontrando o ângulo no círculo unitário correspondente à entrada.</span><span class="sxs-lookup"><span data-stu-id="871dd-116">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="871dd-117">`minValue`A entrada especifica então eficazmente onde cortar o círculo unitário.</span><span class="sxs-lookup"><span data-stu-id="871dd-117">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>