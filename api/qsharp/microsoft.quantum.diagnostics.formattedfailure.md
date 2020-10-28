---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: Função formatadaFilure
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712680"
---
# <a name="formattedfailure-function"></a>Função formatadaFilure

Espaço de nome: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pacote: [](https://nuget.org/packages/)


Função interna usada para falhar com mensagens de erro significativas.

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a>Entrada

### <a name="actual--t"></a>real : 'T




### <a name="expected--t"></a>esperado : 'T




### <a name="message--string"></a>mensagem : [Corda](xref:microsoft.quantum.lang-ref.string)





## <a name="output--unit"></a>Saída : [Unidade](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parâmetros de Tipo Genérico

### <a name="t"></a>'T



## <a name="remarks"></a>Observações

Esta função destina-se a ser emulsionada por tempos de simulação, de modo a permitir o encaminhamento de contradições formatadas.