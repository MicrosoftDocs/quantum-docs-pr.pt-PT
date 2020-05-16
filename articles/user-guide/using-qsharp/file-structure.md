---
title: Q# Estrutura de Arquivo
description: Descreve a estrutura e a sintaxe de um ficheiro Q#.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: cbee92c6d7e765237a7a42532dd7012b51421708
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430973"
---
# <a name="q-file-structure"></a>Q# Estrutura de Arquivo

Cada operação, função e tipo definido pelo utilizador é definido dentro de um espaço de nome.

Um ficheiro Q# consiste numa sequência de *declarações*de espaço de nome .
Cada declaração de espaço de nome contém declarações para tipos, operações e funções definidos pelo utilizador.
Uma declaração de espaço-nome pode conter qualquer número de cada tipo de declaração, e em qualquer ordem.
Siga estes links para obter mais detalhes sobre a declaração [de tipos definidos](xref:microsoft.quantum.guide.types#user-defined-types)pelo utilizador, [operações](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)e [funções](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) dentro de um espaço de nome.

O único texto que pode aparecer fora de uma declaração de espaço de nome são os comentários.
Em particular, os comentários documentais (mais detalhes abaixo) para um espaço de nome precedem a declaração.

## <a name="namespace-declarations"></a>Declarações de espaço de nome

Um ficheiro Q# terá normalmente uma declaração de espaço-nome, mas pode ter nenhuma (e estar vazia ou apenas conter comentários) ou pode conter vários espaços de nome.
As declarações de espaço-nome não podem ser aninhadas.

O mesmo espaço de nome pode ser declarado em vários ficheiros Q# que são compilados em conjunto, desde que não existam declarações de tipo, operação ou função com o mesmo nome.
Em particular, é inválido definir o mesmo tipo no mesmo espaço de nome em vários ficheiros, mesmo que as declarações sejam idênticas.

Uma declaração de espaço de nome consiste na palavra-chave, seguida do nome do espaço de `namespace` nome, de uma cinta `{` aberta, das declarações contidas no espaço de nome, e de uma cinta de `}` proximidade.
Os nomes do espaço de nome seguem o padrão .NET de uma sequência de um ou mais símbolos legais separados por períodos `.` .
Por exemplo, `MyQuantumStuff` e `Microsoft.Quantum.Intrinsic` são nomes de espaço de nome válidos.
Por convenção, os símbolos de um nome de espaço de nome são capitalizados, mas isso não é necessário.

As referências a tipos ou callables declarados mais abaixo num ficheiro são devidamente resolvidas; não há necessidade de o tipo, operação ou declaração de função preceder uma referência a ele.

## <a name="open-directives"></a>Diretivas abertas

Dentro de um bloco de espaço-nome, a `open` diretiva pode ser utilizada para importar todos os tipos e callables declarados num determinado espaço de nome e encaminhá-los pelo seu nome não qualificado.
Tal `open` diretiva consiste na `open` palavra-chave, seguida do espaço-nome a abrir e de um ponto evíceo que termina.

> [!NOTE] 
> Todas as `open` diretivas devem apresentar-se antes de quaisquer `function` , ou `operation` `newtype` declarações no bloco de espaço de nome.

Opcionalmente, pode ser definido um nome curto para o espaço de nome aberto de modo a que todos os elementos desse espaço de nome possam (e precisam) ser qualificados pelo nome curto definido. Por exemplo, dada a seguinte declaração de espaço de nome e diretivas abertas,

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

se uma operação que declaramos usa uma `Op` `Microsoft.Quantum.Intrinsic` operação, nós a chamaríamos simplesmente usando `Op` .
No entanto, se quiséssemos uma chamada de uma determinada `Fn` `Microsoft.Quantum.Math` função, teríamos de chamá-la de `Math.Fn` utilização.

A `open` diretiva aplica-se a todo o bloco de espaço de nome dentro de um ficheiro.
Assim, se definissemos um espaço de nome adicional no mesmo ficheiro Q# que `NS` acima, quaisquer operações/funções/tipos definidos no segundo espaço de nome não teriam acesso a nada a partir `Microsoft.Quantum.Intrinsic` ou a menos que `Microsoft.Quantum.Math` repetissemos as diretivas abertas nele. 

Um tipo ou callable definido em outro espaço de nome que *não* esteja aberto no espaço de nome atual deve ser referenciado pelo seu nome totalmente qualificado.
Por exemplo, uma operação denominada a partir do espaço de `Op` `X.Y` nome deve ser referenciada pelo seu nome totalmente `X.Y.Op` qualificado, a menos que o espaço de `X.Y` nome tenha sido aberto mais cedo no bloco atual. Como mencionado acima, mesmo que o espaço de `X` nome tenha sido aberto, não é possível fazer referência à operação como `Y.Op` .
Se um nome curto `Z` tiver sido definido nesse espaço de nome e `X.Y` arquivo, então `Op` deve ser referido como `Z.Op` . 

Normalmente, é melhor incluir um espaço de nome através da utilização de uma `open` diretiva.
É necessário utilizar um nome totalmente qualificado se dois espaços de nome definirem construções com o mesmo nome, e a fonte atual utiliza construções de ambos.

Q# segue as mesmas regras para nomear outras línguas .NET.
No entanto, Q# não suporta referências relativas a espaços de nome.
Ou seja, se o espaço de nome `a.b` supor, uma referência a uma operação nomeada `c.d` *não* será resolvida a uma operação com nome completo `a.b.c.d` .

## <a name="formatting"></a>Formatação

A maioria das declarações e diretivas q# terminam com um ponto evígula terminando, `;` .
Declarações e declarações como e que terminam com um bloco de `for` `operation` declaração (ver abaixo) não requerem um ponto evívio terminando.
Cada descrição da declaração observa se o ponto evículo terminando é necessário.

Declarações, como expressões, declarações e diretivas, podem ser quebradas em várias linhas.
Deve evitar-se várias declarações numa única linha.

## <a name="statement-blocks"></a>Blocos de Declaração

As declarações de Q# são agruparadas em blocos de declaração.
Um bloco de declaração começa com uma abertura `{` e termina com um fecho `}` .

Um bloco de declaração que seja lexicamente fechado dentro de outro bloco é considerado um subbloco do bloco contendo; contendo e subblocos também são chamados blocos exteriores e internos.

## <a name="comments"></a>Comentários

Os comentários começam com dois cortes para a `//` frente, e continuam até ao fim da linha.
Um comentário pode aparecer em qualquer lugar num ficheiro de origem Q#.

## <a name="documentation-comments"></a>Comentários de Documentação

Os comentários que começam com três cortes `///` dianteiros, são tratados especialmente pelo compilador quando aparecem imediatamente antes de um espaço de nome, operação, especialização, função ou definição de tipo.
Nesse caso, os seus conteúdos são tomados como documentação para o tipo definido de callable ou definido pelo utilizador, como para outros idiomas .NET.

Dentro dos comentários, o `///` texto a aparecer como parte da documentação da API é formatado como [Markdown](https://daringfireball.net/projects/markdown/syntax), com diferentes partes da documentação a serem indicadas por cabeçalhos especialmente nomeados.
Como extensão ao Markdown, as referências cruzadas a operações, funções e tipos definidos pelo utilizador em Q# podem ser incluídas utilizando o , onde é substituído pelo nome totalmente qualificado do objeto de código que está a `@"<ref target>"` `<ref target>` ser referenciado.
Opcionalmente, um motor de documentação também pode suportar extensões de Markdown adicionais.

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

Os seguintes nomes são reconhecidos como cabeçalhos de comentário documentais.

- **Resumo**: Um resumo curto do comportamento de uma função ou operação, ou do propósito de um tipo. O primeiro parágrafo do resumo é utilizado para informações sobre pairar. Deve ser um texto simples.
- **Descrição**: Uma descrição do comportamento de uma função ou operação, ou do propósito de um tipo. O resumo e a descrição são concatenados para formar o ficheiro de documentação gerado para a função, operação ou tipo.
  A descrição pode conter símbolos e equações formatados em linha LaTeX.
- **Entrada**: Uma descrição do tuple de entrada para uma operação ou função.
  Pode conter subsecções de Markdown adicionais indicando cada elemento individual da tuple de entrada.
- **Saída**: Uma descrição do tuple devolvido por uma operação ou função.
- **Parâmetros do tipo**: Uma secção vazia que contém uma subsecção adicional para cada parâmetro genérico do tipo.
- **Exemplo**: Um pequeno exemplo do funcionamento, função ou tipo de utilização.
- **Observações**: Prosa diversa que descreve algum aspeto da operação, função ou tipo.
- **Ver Também:** Uma lista de nomes totalmente qualificados que indicam funções, operações ou tipos definidos pelo utilizador.
- **Referências**: Uma lista de referências e citações para o artigo que está a ser documentado.

## <a name="whats-next"></a>O que se segue?
Conheça [operações e funções](xref:microsoft.quantum.guide.operationsfunctions) em Q#.