---
uid: Microsoft.Quantum.Core.Deprecated
title: Tipo definido pelo utilizador precotado
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 122cbc113a68cec107558d68a6fb145cf6bbd9db
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224093"
---
# <a name="deprecated-user-defined-type"></a>Tipo definido pelo utilizador precotado

Espaço de nome: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)

Pacote: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Atributo reconhecido pelo compilador usado para marcar um tipo ou calável como precado.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a>Itens nomeados

### <a name="newname--string"></a>Novo Nome : [Corda](xref:microsoft.quantum.lang-ref.string)

O nome completo do tipo ou callable para usar em vez disso.
Está definido para a corda vazia se um tipo ou callable tiver sido depreciado sem substituição.