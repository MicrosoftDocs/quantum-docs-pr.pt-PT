---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: Função LittleEndianAsBigEndian
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: c89288e1eb421fd5abd8fcd5d9c12049aa47ac89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843080"
---
# <a name="littleendianasbigendian-function"></a><span data-ttu-id="616d2-102">Função LittleEndianAsBigEndian</span><span class="sxs-lookup"><span data-stu-id="616d2-102">LittleEndianAsBigEndian function</span></span>

<span data-ttu-id="616d2-103">Espaço de nome: [Microsoft.Quantum.Aritmética](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="616d2-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="616d2-104">Pacote: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="616d2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="616d2-105">Converte um `LittleEndian` registo de qubits num `BigEndian` registo qubit invertendo o pedido de qubit.</span><span class="sxs-lookup"><span data-stu-id="616d2-105">Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function LittleEndianAsBigEndian (input : Microsoft.Quantum.Arithmetic.LittleEndian) : Microsoft.Quantum.Arithmetic.BigEndian
```


## <a name="input"></a><span data-ttu-id="616d2-106">Entrada</span><span class="sxs-lookup"><span data-stu-id="616d2-106">Input</span></span>

### <a name="input--littleendian"></a><span data-ttu-id="616d2-107">entrada : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="616d2-107">input : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="616d2-108">Registo de qubit em `LittleEndian` formato.</span><span class="sxs-lookup"><span data-stu-id="616d2-108">Qubit register in `LittleEndian` format.</span></span>



## <a name="output--bigendian"></a><span data-ttu-id="616d2-109">Saída : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="616d2-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="616d2-110">Registo de qubit em `BigEndian` formato.</span><span class="sxs-lookup"><span data-stu-id="616d2-110">Qubit register in `BigEndian` format.</span></span>