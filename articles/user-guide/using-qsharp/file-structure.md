---
title: Q# Estrutura de Arquivos
description: Descreve a estrutura e a sintaxe de um ficheiro Q#.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: b8c24dae6cc8d8f37ad4f1f74017c05cabe3a4b4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327463"
---
# <a name="q-file-structure"></a>Q# Estrutura de Arquivos

Cada operação Q#, função e tipo definido pelo utilizador é definido dentro de um espaço de nome.

Um ficheiro Q# consiste numa sequência de *declarações de espaço de nome*.
Cada declaração de espaço de nome contém declarações para tipos, operações e funções definidos pelo utilizador.
Uma declaração de espaço de nome pode conter qualquer número de cada tipo de declaração, e em qualquer ordem.
Siga estes links para obter mais detalhes sobre a declaração [de tipos,](xref:microsoft.quantum.guide.types#user-defined-types) [operações](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)e [funções definidas](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) pelo utilizador dentro de um espaço com nomes.

O único texto que pode aparecer fora de uma declaração de espaço de nome são os comentários.
Em particular, os comentários de documentação (mais detalhes abaixo) para um espaço de nome precedem a declaração.

## <a name="namespace-declarations"></a>Declarações de espaço de nome

Um ficheiro Q# normalmente terá exatamente uma declaração de espaço de nome, mas pode não ter nenhuma (e estar vazia ou apenas conter comentários) ou pode conter vários espaços de nome.
As declarações do espaço de nome não podem estar aninhadas.

O mesmo espaço de nome pode ser declarado em vários ficheiros Q# que são compilados em conjunto, desde que não existam declarações de tipo, operação ou função com o mesmo nome.
Em particular, é inválido definir o mesmo tipo no mesmo espaço de identificação em vários ficheiros, mesmo que as declarações sejam idênticas.

Uma declaração de espaço de nome consiste na palavra-chave, `namespace` seguida do nome do espaço de nome, uma cinta `{` aberta, as declarações contidas no espaço de nome, e uma cinta de `}` proximidade.
Os nomes do espaço de nome seguem o padrão .NET de uma sequência de um ou mais símbolos legais separados por períodos `.` .
Por exemplo, `MyQuantumStuff` e `Microsoft.Quantum.Intrinsic` são nomes válidos para o espaço de nome.
Por convenção, os símbolos de um nome de espaço são maiúsculas, mas isso não é necessário.

As referências a tipos ou chamadas declaradas mais abaixo num ficheiro são resolvidas corretamente; não há necessidade de que o tipo, o funcionamento ou a declaração de função precedam uma referência ao mesmo.

## <a name="open-directives"></a>Diretivas abertas

Dentro de um bloco de espaço de nome, a `open` diretiva pode ser utilizada para importar todos os tipos e callables declarados num determinado espaço de nome e encaminhá-los pelo seu nome não qualificado.
Esta `open` diretiva consiste na `open` palavra-chave, seguida do espaço de nome a abrir e de um ponto de terminação.

> [!NOTE] 
> Todas as `open` diretivas devem ser apresentadas antes de qualquer `function` , ou `operation` `newtype` declarações no bloco de espaços de nome.

Opcionalmente, um nome curto para o espaço de nome aberto pode ser definido de modo que todos os elementos desse espaço de nome podem (e precisam) ser qualificados pelo nome curto definido. Por exemplo, tendo em conta a seguinte declaração de espaço de nome e diretivas abertas,

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

se uma operação que declaramos usar uma operação `Op` `Microsoft.Quantum.Intrinsic` de, nós chamá-la-íamos simplesmente usando `Op` .
No entanto, se quiséssemos uma chamada de uma determinada `Fn` `Microsoft.Quantum.Math` função, teríamos de chamá-la de `Math.Fn` utilização.

A `open` diretiva aplica-se a todo o bloco de espaço de nome dentro de um ficheiro.
Assim, se definissemos um espaço de nome adicional no mesmo ficheiro Q# `NS` acima, então quaisquer operações/funções/tipos definidos no segundo espaço de nome não teriam acesso a nada a partir `Microsoft.Quantum.Intrinsic` ou a menos que `Microsoft.Quantum.Math` repetissemos as diretivas abertas neles. 

Um tipo ou callable definido em outro espaço de nome que *não* seja aberto no espaço de nome atual deve ser referenciado pelo seu nome totalmente qualificado.
Por exemplo, uma operação denominada `Op` a partir do espaço de `X.Y` nomes deve ser referenciada pelo seu nome totalmente qualificado `X.Y.Op` , a menos que o espaço de nome tenha sido aberto `X.Y` anteriormente no bloco atual. Como mencionado acima, mesmo que o `X` espaço de nome tenha sido aberto, não é possível referir a operação como `Y.Op` .
Se um nome curto `Z` para ter sido definido nesse espaço e arquivo de `X.Y` nomes, então `Op` deve ser referido como `Z.Op` . 

Normalmente, é melhor incluir um espaço de nome através de uma `open` diretiva.
A utilização de um nome totalmente qualificado é necessária se dois espaços de nome definirem construções com o mesmo nome, e a fonte atual utiliza construções de ambos.

Q# segue as mesmas regras para nomear outras línguas .NET.
No entanto, Q# não suporta referências relativas a espaços de nome.
Ou seja, se o espaço de nome `a.b` tiver sido aberto, uma referência a uma operação com o nome `c.d` *não* será resolvida para uma operação com nome completo `a.b.c.d` .

## <a name="formatting"></a>Formatação

A maioria das declarações e diretivas Q# terminam com um semicolon terminante, `;` .
Declarações e declarações como `for` e `operation` que terminam com um bloco de declaração (ver abaixo) não requerem um ponto de terminação.
Cada descrição da declaração observa se o ponto de terminação é necessário.

Declarações, como expressões, declarações e diretivas, podem ser divididas em várias linhas.
Deve evitar-se várias declarações numa única linha.

## <a name="statement-blocks"></a>Blocos de Declaração

As declarações q# são agrupadas em blocos de declaração.
Um bloco de declaração começa com uma abertura `{` e termina com um fecho `}` .

Um bloco de declaração que seja lexicamente fechado dentro de outro bloco é considerado um sub-bloco do bloco contendo; contendo e sub-blocos também são chamados blocos exteriores e internos.

## <a name="comments"></a>Comentários

Os comentários começam com dois cortes para a `//` frente, e continuam até ao fim da linha.
Um comentário pode aparecer em qualquer lugar de um ficheiro de origem Q#.

## <a name="documentation-comments"></a>Comentários de documentação

Comentários que começam com três cortes dianteiros, `///` são tratados especialmente pelo compilador quando aparecem imediatamente antes de um espaço de nome, operação, especialização, função ou definição de tipo.
Nesse caso, os seus conteúdos são tomados como documentação para o tipo definido de calável ou definido pelo utilizador, como para outras línguas .NET.

Dentro `///` dos comentários, o texto a aparecer como parte da documentação da API é formatado como [Markdown,](https://daringfireball.net/projects/markdown/syntax)com diferentes partes da documentação a serem indicadas por cabeçalhos especialmente nomeados.
Como extensão a Markdown, podem incluir referências cruzadas a operações, funções e tipos definidos pelo utilizador em Q# utilizando o `@"<ref target>"` , onde é substituído pelo nome totalmente qualificado do objeto de código que está a ser `<ref target>` referenciado.
Opcionalmente, um motor de documentação também pode suportar extensões adicionais de Markdown.

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

Os seguintes nomes são reconhecidos como cabeçalhos de comentário de documentação.

- **Resumo**: Um breve resumo do comportamento de uma função ou funcionamento, ou da finalidade de um tipo. O primeiro parágrafo do resumo é utilizado para informações sobre hover. Deve ser um texto simples.
- **Descrição:** Descrição do comportamento de uma função ou operação, ou da finalidade de um tipo. O resumo e a descrição são concatenados para formar o ficheiro de documentação gerada para a função, operação ou tipo.
  A descrição pode conter símbolos e equações formatados laTeX em linha.
- **Entrada**: Descrição do tuple de entrada para uma operação ou função.
  Pode conter subsecções de markdown adicionais que indiquem cada elemento individual do tuple de entrada.
- **Saída**: Descrição do tuple devolvido por uma operação ou função.
- **Parâmetros do tipo**: Secção vazia que contém uma subsecção adicional para cada parâmetro genérico do tipo.
- **Exemplo:** Um pequeno exemplo do funcionamento, função ou tipo de utilização.
- **Observações**: Prosa diversa descrevendo algum aspeto da operação, função ou tipo.
- **Consulte também:** Uma lista de nomes totalmente qualificados que indiquem funções, operações ou tipos definidos pelo utilizador.
- **Referências**: Uma lista de referências e citações para o artigo que está a ser documentado.

## <a name="next-steps"></a>Próximos passos

Saiba mais [sobre Operações e Funções](xref:microsoft.quantum.guide.operationsfunctions) em Q#.