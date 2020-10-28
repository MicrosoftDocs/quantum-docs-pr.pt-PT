---
uid: Microsoft.Quantum.ErrorCorrection.InjectPi4YRotation
title: Operação InjectPi4YRotation
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: InjectPi4YRotation
qsharp.summary: Rotates a single qubit by π/4 about the Y-axis.
ms.openlocfilehash: 8558767050c317661dfb490143fa3c8f4ea009e2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712319"
---
# <a name="injectpi4yrotation-operation"></a>Operação InjectPi4YRotation

Espaço de nome: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacote: [](https://nuget.org/packages/)


Roda um único qubit por π/4 sobre o eixo Y.

```qsharp
operation InjectPi4YRotation (data : Qubit, magic : Qubit) : Unit
```


## <a name="description"></a>Descrição

Executa uma rotação de π/4 sobre `Y` .

A rotação é realizada consumindo um estado mágico; ou seja, uma cópia do estado $\ \start{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} {8} \ket {1} .
\end{align} $$

## <a name="input"></a>Entrada

### <a name="data--qubit"></a>dados : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Um qubit a ser rodado cerca de $Y$ por $\pi / 4$.


### <a name="magic--qubit"></a>magia : [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Um qubit inicialmente no estado mágico. Após a aplicação desta operação, `magic` é devolvido ao estado $\ket {0} $.



## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Observações

Os seguintes são equivalentes:

```qsharp
Ry(PI() / 4.0, data);
```

e

```qsharp
using (magic = Qubit()) {
    Ry(PI() / 4.0, magic);
    InjectPi4YRotation(data, magic);
    Reset(magic);
}
```

Esta operação apoia o `Adjoint` functor, caso em que o mesmo estado mágico é consumido, mas o efeito no qubit de dados é de $-\pi/4$ $Y rotação de $.