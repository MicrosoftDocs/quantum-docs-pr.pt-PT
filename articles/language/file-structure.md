---
title: Estrutura de arquivos | Microsoft Docs
description: 'Estrutura de arquivos de Q #'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 40b2e7ddf5def6285250dffe130b152429dce1f8
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185193"
---
# <a name="file-structure"></a>Estrutura de Ficheiros

Um arquivo Q # consiste em uma sequência de declarações de namespace.
Cada declaração de namespace contém declarações para tipos, operações e funções definidas pelo usuário.
Uma declaração de namespace pode conter qualquer número de cada tipo de declaração e em qualquer ordem.
O único texto que pode aparecer fora de uma declaração de namespace é comments.
Em particular, comentários de documentação para um namespace precedem a declaração.

## <a name="namespace-declarations"></a>Declarações de namespace

Um arquivo Q # normalmente terá exatamente uma declaração de namespace, mas pode ter nenhum (e estar vazio ou apenas conter comentários) ou pode conter vários namespaces.
Declarações de namespace não podem ser aninhadas.

O mesmo namespace pode ser declarado em vários arquivos Q # que são compilados juntos, desde que não haja nenhuma declaração de tipo, operação ou função com o mesmo nome.
Em particular, é inválido definir o mesmo tipo no mesmo namespace em vários arquivos, mesmo que as declarações sejam idênticas.

Uma declaração de namespace consiste na `namespace`de palavras-chave, seguida pelo nome do namespace, uma chave de abertura `{`, as declarações contidas no namespace e uma chave de fechamento `}`.
Os nomes de namespace seguem o padrão .NET de uma sequência de um ou mais símbolos legais separados por pontos `.`.
Por exemplo, `MyQuantumStuff` e `Microsoft.Quantum.Canon` são nomes de namespace válidos.
Por convenção, os símbolos em um nome de namespace estão em letras maiúsculas, mas isso não é necessário.

Declarações podem aparecer em qualquer ordem em uma declaração de namespace.
Referências a tipos ou chamadores declarados mais abaixo em um arquivo são resolvidos corretamente; Não há necessidade de tipo, operação ou declaração de função para preceder uma referência a ele.

## <a name="open-directives"></a>Abrir diretivas

Dentro de um bloco de namespace, a diretiva `open` pode ser usada para importar todos os tipos e callables definidos em um determinado namespace e consultá-los por seu nome não qualificado. 

Essa diretiva de `open` consiste na palavra-chave `open`, seguida pelo namespace a ser aberto e um ponto e vírgula de terminação.

Por exemplo,

```qsharp
open Microsoft.Quantum.Canon;
```

Opcionalmente, um nome curto para o namespace aberto pode ser definido de modo que todos os elementos desse namespace possam (e precisam) ser qualificados pelo nome curto definido. Esse nome curto é definido pela adição da palavra-chave `as` seguida pelo nome curto desejado antes do ponto e vírgula em uma diretiva de `open`:

```qsharp
open Microsoft.Quantum.Math as Math;
```

Todas as diretivas de `open` devem aparecer antes de qualquer `function`, `operation`ou declarações de `newtype` no bloco de namespace.
A diretiva `open` se aplica ao bloco de namespace inteiro em um arquivo.

## <a name="user-defined-type-declarations"></a>Declarações de tipo definidas pelo usuário

O Q # fornece uma maneira para os usuários declararem novos tipos definidos pelo usuário, conforme descrito na seção [modelo do tipo Q #](xref:microsoft.quantum.language.type-model) .
Os tipos definidos pelo usuário são distintos mesmo se os tipos base forem idênticos.
Em particular, não há conversão automática entre valores de dois tipos definidos pelo usuário, mesmo que os tipos subjacentes sejam idênticos.

Uma declaração de tipo definida pelo usuário consiste na palavra-chave `newtype`, seguida pelo nome do tipo definido pelo usuário, uma `=`, uma especificação de tipo válida e um ponto e vírgula de terminação.

Por exemplo:

```qsharp
newtype PairOfInts = (Int, Int);
```

Cada arquivo de origem Q # pode declarar qualquer número de tipos definidos pelo usuário.
Os nomes de tipo devem ser exclusivos em um namespace e podem não entrar em conflito com os nomes de operação e de função.

Não é possível definir dependências circulares entre tipos definidos pelo usuário. Os tipos recursivos, portanto, não são possíveis em Q #.

## <a name="operation-declarations"></a>Declarações de operação

As operações são o núcleo de Q #, aproximadamente análogo a funções em outras linguagens.
Cada arquivo de origem Q # pode definir qualquer número de operações.

Os nomes de operação devem ser exclusivos em um namespace e podem não entrar em conflito com os nomes de tipo e função.

Uma declaração de operação consiste na `operation`de palavras-chave, seguida pelo símbolo que é o nome da operação, uma tupla de identificador tipada que define os argumentos para a operação, dois pontos `:`, uma anotação de tipo que descreve o tipo de resultado da operação, Opcionalmente, uma anotação com as características da operação, uma chave de abertura `{`, o corpo da declaração da operação e uma chave de fechamento final `}`.

O corpo da declaração da operação consiste na implementação padrão ou de uma lista de especializações.
A implementação padrão pode ser especificada diretamente dentro da declaração se apenas a implementação da especialização de corpo padrão precisar especificar explicitamente.
Nesse caso, uma anotação com as características da operação na declaração é útil para garantir que o compilador gere automaticamente outras especializações com base na implementação padrão. 

Por exemplo 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

As características da operação definem quais tipos de transmissão functors podem ser aplicados à operação declarada e qual efeito eles têm. Se uma operação implementar uma transformação unitário, será possível definir como a operação age quando *adjointed* ou *controlada*.
A existência dessas especializações pode ser declarada como parte da assinatura da operação. A implementação correspondente para cada tal especialização declarada implicitamente é gerada pelo compilador. No exemplo acima, um adjacente, um controlado e uma especialização de adjacente controlada são gerados pelo compilador. 

No caso em que a implementação não pode ser gerada pelo compilador, ela pode ser especificada explicitamente. Essas declarações de especialização explícitas podem consistir em uma diretiva de geração adequada que esclareça como uma determinada especialização deve ser criada ou uma implementação definida pelo usuário. O código em `PrepareEntangledPair` acima, por exemplo, é equivalente ao código abaixo que contém declarações de especialização explícitas: 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
A palavra-chave `auto` indica que o compilador deve determinar como gerar a implementação de especialização.
Se o compilador não puder gerar a implementação para uma determinada especialização sem mais instruções, como uma diretiva de geração mais precisa, ou se uma implementação mais eficiente puder ser fornecida, a implementação também poderá ser definida manualmente.

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```

No exemplo acima, `adjoint invert;` indica que a especialização de adjacente deve ser gerada ao inverter a implementação do corpo e `controlled adjoint invert;` indica que a especialização adjacente controlada deve ser gerada por meio da inversão da implementação fornecida do especialização controlada.

Para uma operação para dar suporte ao aplicativo do `Adjoint` e/ou `Controlled` functor, seu tipo de retorno precisa ser `Unit`. 


### <a name="explicit-specialization-declarations"></a>Declarações de especialização explícitas

As operações de Q # podem conter as seguintes declarações de especialização explícitas:

- A especialização de `body` especifica a implementação da operação sem nenhum transmissão functors aplicado.
- A especialização de `adjoint` especifica a implementação da operação com o `Adjoint` functor aplicado.
- A especialização de `controlled` especifica a implementação da operação com o `Controlled` functor aplicado.
- A especialização de `controlled adjoint` especifica a implementação da operação com o `Adjoint` e `Controlled` transmissão functors aplicados.
  Essa especialização também pode ser nomeada `adjoint controlled`, já que as duas transmissão functorsm.


Uma especialização de operação consiste na marca de especialização (como por exemplo, `body`ou `adjoint`, etc.) seguida de uma das:

- Uma declaração explícita, conforme descrito abaixo.
- Uma diretiva que informa ao compilador como gerar a especialização, uma das:
  - `intrinsic`, que indica que a especialização é fornecida pelo computador de destino.
  - `distribute`, que pode ser usado com as especializações `controlled` e `controlled adjoint`.
    Quando usado com `controlled`, ele indica que o compilador deve calcular a especialização aplicando `Controlled` a todas as operações no `body`.
    Quando usado com `controlled adjoint`, ele indica que o compilador deve calcular a especialização aplicando `Controlled` a todas as operações na especialização de `adjoint`.
  - `invert`, que indica que o compilador deve calcular a especialização de `adjoint` invertendo a `body`, ou seja, revertendo a ordem das operações e aplicando o adjacente a cada uma delas.
    Quando usado com `adjoint controlled`, isso indica que o compilador deve calcular a especialização invertendo a especialização de `controlled`.
  - `self`, para indicar que a especialização de adjacente é a mesma que a especialização de `body`.
    Isso é válido para as especialidades de `adjoint` e `adjoint controlled`.
    Por `adjoint controlled`, `self` implica que a especialização de `adjoint controlled` é a mesma que a especialização de `controlled`.
  - `auto`, para indicar que o compilador deve selecionar uma diretiva apropriada a ser aplicada.
    `auto` não pode ser usado para a especialização de `body`.

As diretivas e `auto` todos exigem um ponto-e-`;`vírgula de fechamento.
A diretiva `auto` é resolvida para a seguinte diretiva de geração se uma declaração explícita da `body` for fornecida:

- A especialização de `adjoint` é gerada de acordo com a diretiva `invert`.
- A especialização de `controlled` é gerada de acordo com a diretiva `distribute`.
- A especialização de `adjoint controlled` é gerada de acordo com a diretiva `invert` se uma declaração explícita para `controlled` for fornecida, mas não uma para `adjoint`e `distribute` caso contrário.

> [!TIP]   
> Se uma operação for autoadjacente, especifique explicitamente a prejunção ou a especialização de adjacente controlada por meio da diretiva de geração `self` para permitir que o compilador use essas informações para fins de otimização.

Uma declaração de especialização contendo uma implementação definida pelo usuário consiste em uma tupla de argumento seguida por um bloco de instrução com o código Q # que implementa a especialização.
Na lista de argumentos, `...` é usado para representar os argumentos declarados para a operação como um todo.
Para `body` e `adjoint`, a lista de argumentos sempre deve ser `(...)`; para `controlled` e `adjoint controlled`, a lista de argumentos deve ser um símbolo que representa a matriz de qubits de controle, seguida por `...`, entre parênteses; por exemplo, `(controls,...)`.

Se uma ou mais especializações além do corpo padrão precisarem ser declaradas explicitamente, a implementação do corpo padrão precisará ser encapsulada em uma declaração de especialização adequada também:

```qsharp
operation CountOnes(qs: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (q in qs) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="adjoint"></a>Adjacente

O erro de uma operação especifica como a seqüência conjugada complexa da operação é implementada, ou seja, como a operação atua quando "executar em ordem inversa".
É legal especificar uma operação sem nenhum erro; por exemplo, as operações de medição não têm nenhum adjacente porque não são invertível.
Uma operação dá suporte ao `Adjoint` functor se sua declaração contiver uma declaração implícita ou explícita de uma especialização adjacente.
Uma especialização adjacente controlada explicitamente implica a existência de uma especialização adjacente. 

Para a operação cujo corpo contém loops repetir-até-êxito, instruções SET, medidas, instruções de retorno ou chamadas para outras operações que não dão suporte ao `Adjoint` functor, gerando automaticamente uma especialização de adjacente após a `invert` ou @no__ a diretiva t_2_ não é possível.

### <a name="controlled"></a>Controlado

A versão controlada de uma operação especifica como uma versão controlada pelo Quantum da operação é implementada, ou seja, como uma operação age quando aplicada no estado de um registro Quantum.
Uma descrição mais completa é fornecida na seção [controlada](xref:microsoft.quantum.language.type-model#controlled) .

É legal especificar uma operação sem nenhuma versão controlada; por exemplo, as operações de medição não têm nenhuma versão controlada porque não são controláveis.
Uma operação dá suporte ao `Controlled` functor se e somente se sua declaração contiver uma declaração implícita ou explícita de uma especialização controlada.
Uma especialização adjacente controlada explicitamente implica a existência de uma especialização controlada. 

Para uma operação cujo corpo contém chamadas para outras operações que não dão suporte ao `Controlled` functor, a geração automática de uma especialização controlada seguindo a diretiva `distribute` ou `auto` não é possível.

### <a name="controlled-adjoint"></a>Adjacente controlado

A versão adjacente controlada de uma operação especifica como uma versão controlada pelo Quantum do adjoin da operação é implementada.
É legal especificar uma operação sem nenhuma versão adjacente controlada; por exemplo, as operações de medição não têm nenhuma versão adjacente controlada porque não são controláveis nem invertível.

Uma especialização de adjacente controlada para uma operação precisa existir se e somente se houver uma especialização de somente um e um adjacente. Nesse caso, a existência da especialização adjacente controlada é inferida e uma especialização apropriada é gerada pelo compilador se nenhuma implementação tiver sido definida explicitamente. 

Para uma operação cujo corpo contém chamadas para outras operações que não têm uma versão adjacente controlada, a geração automática de uma especialização de adjacente após o `invert`, `distribute` ou diretiva de `auto` não é possível.


### <a name="examples"></a>Exemplos

Uma declaração de operação pode ser tão simples quanto a seguinte, que define a operação primitiva de Pauli X:

```qsharp
operation X (q : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

O seguinte define a operação teleport.

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation EPR (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        EPR(target, ancilla);

        // Do the teleportation
        Adjoint EPR (ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a>Declarações de função

São rotinas puramente clássicas em Q #.
Cada arquivo de origem Q # pode definir qualquer número de funções.

Uma declaração de função consiste na `function`de palavras-chave, seguida pelo símbolo que é o nome da função, uma tupla de identificador tipada, uma anotação de tipo que descreve o tipo de retorno da função e um bloco de instruções que descreve a implementação do funcionamento.

O bloco de instrução que define uma função deve ser colocado entre `{` e `}` como qualquer outro bloco de instrução.

Os nomes de função devem ser exclusivos em um namespace e podem não entrar em conflito com os nomes de operação e tipo.
As funções podem não alocar ou emprestar qubits ou chamar operações. A aplicação parcial de operações ou a passagem de valores tipados da operação está bem.

Por exemplo,

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```
