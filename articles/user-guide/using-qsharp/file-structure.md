---
title: Q# Estrutura de Arquivos
description: Descreve a estrutura e a sintaxe de um Q# ficheiro.
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
no-loc:
- Q#
- $$v
ms.openlocfilehash: 98b3a2e35186989b8191cc566a5d5310bc26eafc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833315"
---
# <a name="no-locq-file-structure"></a>Q# Estrutura de Arquivos

Um Q# ficheiro consiste numa sequência de *declarações de espaço de nome*.
Cada declaração de espaço de nome contém declarações para tipos, operações e funções definidos pelo utilizador, e pode conter qualquer número de cada tipo de declaração e em qualquer ordem.
Para obter mais informações sobre declarações dentro de um espaço de nome, consulte tipos, [operações](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)e [funções definidos](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) [pelo utilizador.](xref:microsoft.quantum.guide.types#user-defined-types)

O único texto que pode aparecer fora de uma declaração de espaço de nome são os comentários.
Em particular, os comentários documentais relativos a um espaço de nome precedem a declaração. Para mais informações, consulte [comentários de documentação](#documentation-comments) neste artigo. 

## <a name="namespace-declarations"></a>Declarações de espaço de nome

Um Q# ficheiro normalmente tem apenas uma declaração de espaço de nome, mas pode não ter nenhuma (e estar vazia ou apenas conter comentários) ou pode conter vários espaços de nome.
As declarações do espaço de nome não podem ser aninhadas.

Pode declarar o mesmo espaço de nome em Q# vários ficheiros que são compilados em conjunto, desde que não existam declarações de tipo, operação ou função com o mesmo nome.
Em particular, é inválido definir o mesmo tipo no mesmo espaço de identificação em vários ficheiros, mesmo que as declarações sejam idênticas.

Uma declaração de espaço de nome consiste na palavra-chave, `namespace` seguida do nome do espaço de nome, e das declarações contidas no espaço de nome incluído em aparelhos. `{ }`
Os nomes do espaço de nome seguem o padrão .NET de uma sequência de um ou mais símbolos legais separados por períodos `.` .
Por exemplo, `MyQuantumStuff` e `Microsoft.Quantum.Intrinsic` são nomes válidos para o espaço de nome.
Por convenção, capitalize os símbolos num nome de espaço de nome, no entanto, isso não é necessário.

Referências a tipos ou chamadas declaradas mais abaixo numa resolução de ficheiros corretamente; não há necessidade de que o tipo, o funcionamento ou a declaração de função precedam uma referência ao mesmo.

## <a name="open-directives"></a>Diretivas abertas

Dentro de um bloco de espaço de nome, utilize a `open` diretiva para importar todos os tipos e callables declarados num determinado espaço de nome e consulte-os pelo seu nome não qualificado.
Esta `open` diretiva consiste na `open` palavra-chave, seguida do espaço de nome a abrir e de um ponto de terminação.

> [!NOTE] 
> Todas as `open` diretivas devem ser apresentadas antes de qualquer `function` , ou `operation` `newtype` declarações no bloco de espaços de nome.

Opcionalmente, pode definir um nome curto para o espaço de nome aberto. Se um nome curto for definido, deve qualificar todos os elementos desse espaço pelo nome curto definido. Por exemplo, tendo em conta a seguinte declaração de espaço de nome e diretivas abertas,

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

se uma operação declarada utilizar uma operação `Op` a partir de , `Microsoft.Quantum.Intrinsic` chame-a simplesmente utilizando `Op` .
No entanto, para chamar uma determinada função `Fn` de `Microsoft.Quantum.Math` , deve chamá-lo de uso `Math.Fn` .

A `open` diretiva aplica-se a todo o bloco de espaço de nome dentro de um ficheiro.
Assim, se definir um espaço de nome adicional no mesmo Q# ficheiro `NS` que anteriormente, então quaisquer operações/funções/tipos definidos no segundo espaço de nome não teriam acesso a nada a partir `Microsoft.Quantum.Intrinsic` ou a menos que `Microsoft.Quantum.Math` repetisse as diretivas abertas neles. 

Para fazer referência a um tipo ou chamada definido noutro espaço de nome que *não* esteja aberto no espaço de nomes atual, deve fazê-lo referenciar pelo seu nome totalmente qualificado.
Por exemplo, dada uma operação denominada `Op` a partir do espaço de `X.Y` nome:

* Deve fazê-lo referenciar pelo seu nome totalmente `X.Y.Op` qualificado, a menos que o `X.Y` espaço de nome tenha sido aberto mais cedo no bloco atual. 
* Mesmo que o `X` espaço de nome seja aberto, não é possível referenciar a operação como `Y.Op` .
* Se definir o nome curto `Z` para esse espaço e arquivo de `X.Y` nomes, deve fazer referência `Op` como `Z.Op` . 

Normalmente, é melhor incluir um espaço de nome através de uma `open` diretiva.
A utilização de um nome totalmente qualificado é necessária se dois espaços de nome definirem construções com o mesmo nome, e a fonte atual utiliza construções de ambos.

Q# segue as mesmas regras para nomear como outras línguas .NET.
No entanto, Q# não suporta referências relativas a espaços de nome.
Por exemplo, se o espaço de nome `a.b` estiver aberto, uma referência a uma operação nomeada `c.d` *não* se resolve a uma operação com nome completo `a.b.c.d` .

## <a name="formatting"></a>Formatação

A maioria das Q# declarações e diretivas terminam com um semicolon de encerramento, `;` .
Declarações e declarações como `for` e `operation` que terminam com um bloco de declaração (ver secção seguinte) não requerem um ponto de terminação.
Cada descrição da declaração observa se o ponto de terminação é necessário.

Declarações, como expressões, declarações e diretivas, podem ser divididas em várias linhas.
Evite colocar várias declarações numa única linha.

## <a name="statement-blocks"></a>Blocos de Declaração

Q# as declarações são agrupadas em blocos de declaração, que são contidos com aparelhos `{ }` . Um bloco de declaração começa com uma abertura `{` e termina com um fecho `}` .

Um bloco de declaração que seja lexicamente fechado dentro de outro bloco é considerado um sub-bloco do bloco contendo; contendo e sub-blocos também são chamados blocos exteriores e internos.

## <a name="comments"></a>Comentários

Os comentários começam com dois cortes para a `//` frente, e continuam até ao fim da linha.
Um comentário pode aparecer em qualquer lugar de um Q# ficheiro de origem.

## <a name="documentation-comments"></a>Comentários de documentação

Comentários que começam com três cortes dianteiros, `///` são tratados especialmente pelo compilador quando aparecem imediatamente antes de um espaço de nome, operação, especialização, função ou definição de tipo.
Nesse caso, o compilador trata-os como documentação para o tipo definido de calável ou definido pelo utilizador, o mesmo que outras línguas .NET.

Dentro `///` dos comentários, o texto a aparecer como parte da documentação da API é formatado como [Markdown,](https://daringfireball.net/projects/markdown/syntax)com diferentes partes da documentação indicada por cabeçalhos especialmente nomeados.
Em Markdown, utilize a `@"<ref target>"` extensão para operações de referência cruzada, funções e tipos definidos pelo utilizador em Q# . `<ref target>`Substitua-o pelo nome totalmente qualificado do objeto de código referenciado.
Diferentes motores de documentação também podem suportar extensões adicionais de Markdown.

Por exemplo:

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

Os seguintes nomes são válidos como cabeçalhos de comentário de documentação.

- **Resumo**: Um breve resumo do comportamento de uma função ou funcionamento, ou o propósito de um tipo. O primeiro parágrafo do resumo é utilizado para informações sobre hover. Deve ser um texto simples.
- **Descrição:** Descrição do comportamento de uma função ou operação, ou o propósito de um tipo. Em conjunto, o resumo e descrição formam o ficheiro de documentação gerada para a função, operação ou tipo.
  A descrição suporta símbolos e equações formatados em linha laTeX.
- **Entrada**: Descrição do tuple de entrada para uma operação ou função.
  Pode conter subsecções de markdown adicionais que indicam cada elemento do tuple de entrada.
- **Saída**: Descrição do tuple devolvido por uma operação ou função.
- **Parâmetros do tipo**: Secção vazia que contém uma subsecção adicional para cada parâmetro genérico do tipo.
- **Exemplo:** Um pequeno exemplo do funcionamento, função ou tipo de utilização.
- **Observações**: Prosa diversa descrevendo algum aspeto da operação, função ou tipo.
- **Consulte também:** Uma lista de nomes totalmente qualificados que indiquem funções, operações ou tipos definidos pelo utilizador.
- **Referências**: Uma lista de referências e citações para o item documentado.

## <a name="next-steps"></a>Passos seguintes

Conheça as [Operações e Funções](xref:microsoft.quantum.guide.operationsfunctions) em Q# .