---
title: Q# Estrutura de Arquivo
description: Saiba como estruturar espaços de nome, e operação, função e declarações de tipo utilizador definidos em programas e bibliotecas Q#.
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 96de062bc6ce4edf94520bec449e8d95259c0f5c
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320763"
---
# <a name="file-structure"></a>Estrutura de Ficheiros

Um ficheiro Q# consiste numa sequência de declarações de espaço de nome.
Cada declaração de espaço de nome contém declarações para tipos, operações e funções definidos pelo utilizador.
Uma declaração de espaço-nome pode conter qualquer número de cada tipo de declaração, e em qualquer ordem.
O único texto que pode aparecer fora de uma declaração de espaço de nome são os comentários.
Em particular, os comentários documentais relativos a um espaço de nome precedem a declaração.

## <a name="namespace-declarations"></a>Declarações de espaço de nome

Um ficheiro Q# terá normalmente uma declaração de espaço-nome, mas pode ter nenhuma (e estar vazia ou apenas conter comentários) ou pode conter vários espaços de nome.
As declarações de espaço-nome não podem ser aninhadas.

O mesmo espaço de nome pode ser declarado em vários ficheiros Q# que são compilados em conjunto, desde que não existam declarações de tipo, operação ou função com o mesmo nome.
Em particular, é inválido definir o mesmo tipo no mesmo espaço de nome em vários ficheiros, mesmo que as declarações sejam idênticas.

Uma declaração de espaço de nome consiste na palavra-chave `namespace`, seguida do nome do espaço de nome, de um `{`de cinta aberta, das declarações contidas no espaço de nome, e de um `}`de cinta estreita .
Os nomes do espaço de nome seguem o padrão .NET de uma sequência de um ou mais símbolos legais separados por períodos `.`.
Por exemplo, `MyQuantumStuff` e `Microsoft.Quantum.Canon` são nomes de espaço de nome válidos.
Por convenção, os símbolos de um nome de espaço de nome são capitalizados, mas isso não é necessário.

As declarações podem aparecer em qualquer ordem numa declaração de espaço de nome.
As referências a tipos ou callables declarados mais abaixo num ficheiro são devidamente resolvidas; não há necessidade de o tipo, operação ou declaração de função preceder uma referência a ele.

## <a name="open-directives"></a>Diretivas abertas

Dentro de um bloco de espaço-nome, a diretiva `open` pode ser utilizada para importar todos os tipos e calíveis definidos num determinado espaço de nome e encaminhá-los pelo seu nome não qualificado. 

Tal diretiva `open` consiste na palavra-chave `open`, seguida do espaço de nome a abrir e de um ponto evíceo que termina.

Por exemplo,

```qsharp
open Microsoft.Quantum.Canon;
```

Opcionalmente, pode ser definido um nome curto para o espaço de nome aberto de modo a que todos os elementos desse espaço de nome possam (e precisam) ser qualificados pelo nome curto definido. Este nome curto é definido adicionando a palavra-chave `as` seguida do nome curto desejado antes do ponto evícito numa diretiva `open`:

```qsharp
open Microsoft.Quantum.Math as Math;
```

Todas as diretivas `open` devem comparecer antes de qualquer `function`, `operation`ou `newtype` declarações no bloco de nomes.
A diretiva `open` aplica-se a todo o bloco de espaço de nome dentro de um ficheiro.

## <a name="user-defined-type-declarations"></a>Declarações de tipo definidos pelo utilizador

Q# fornece uma forma de os utilizadores declararem novos tipos definidos pelo utilizador, conforme descrito na secção do [modelo Q#.](xref:microsoft.quantum.language.type-model)
Os tipos definidos pelo utilizador são distintos mesmo que os tipos de base sejam idênticos.
Em particular, não existe uma conversão automática entre valores de dois tipos definidos pelo utilizador, mesmo que os tipos subjacentes sejam idênticos.

Uma declaração de tipo definido pelo utilizador consiste na palavra-chave `newtype`, seguida do nome do tipo definido pelo utilizador, de um `=`, de uma especificação de tipo válido e de um ponto e vírgula terminando.

Por exemplo:

```qsharp
newtype PairOfInts = (Int, Int);
```

Cada ficheiro de origem Q# pode declarar qualquer número de tipos definidos pelo utilizador.
Os nomes de tipo devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com nomes de funcionamento e função.

Não é possível definir dependências circulares entre tipos definidos pelo utilizador. Os tipos recursivos não são assim possíveis dentro do Q#.

## <a name="operation-declarations"></a>Declarações de Operação

As operações são o núcleo de Q#, aproximadamente análogo a funções em outras línguas.
Cada ficheiro de origem Q# pode definir qualquer número de operações.

Os nomes de funcionamento devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com nomes de tipo e função.

Uma declaração de operação consiste na palavra-chave `operation`, seguida do símbolo que é o nome da operação, de uma túnica de identificador dactilografada que define os argumentos da operação, de um cólon `:`, de uma anotação tipo que descreve o tipo de resultado da operação, opcionalmente uma anotação com as características de funcionamento, uma braçadeira aberta `{`, o corpo da declaração de operação e um `}`final de fecho.

O corpo da declaração de operação consiste na implementação por defeito ou numa lista de especializações.
A implementação por defeito pode ser especificada diretamente na declaração se apenas a implementação da especialização do corpo padrão precisar especificar explicitamente.
Neste caso, uma anotação com as características de funcionamento na declaração é útil para garantir que o compilador gera automaticamente outras especializações com base na implementação padrão. 

Por exemplo 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

As características de funcionamento definem que tipos de functores podem ser aplicados à operação declarada e que efeito têm. Se uma operação implementar uma transformação unitária, então é possível definir como a operação funciona quando *adjoint ou* *controlada*.
A existência destas especializações pode ser declarada como parte da assinatura da operação. A implementação correspondente para cada especialização declarada implicitamente é então gerada pelo compilador. No exemplo acima, um adjoint, um controlado e uma especialização adjoint controlada são gerados pelo compilador. 

No caso de a implementação não poder ser gerada pelo compilador, pode ser explicitamente especificada. Tais declarações explícitas de especialização podem consistir numa diretiva de geração adequada que clarifique a forma como uma determinada especialização deve ser construída, ou uma implementação definida pelo utilizador. O código em `PrepareEntangledPair` acima, por exemplo, equivale ao código abaixo contendo declarações explícitas de especialização: 

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
A palavra-chave `auto` indica que o compilador deve determinar como gerar a implementação da especialização.
Se o compilador não conseguir gerar a implementação de uma determinada especialização sem instruções adicionais - como uma diretiva de geração mais precisa - ou se uma implementação mais eficiente puder ser administrada, então a implementação também pode ser definida manualmente.

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

No exemplo acima, `adjoint invert;` indica que a especialização adjoint deve ser gerada invertendo a implementação do corpo, e `controlled adjoint invert;` indica que a especialização adjoint controlada deve ser gerada invertendo a implementação da especialização controlada.

Para uma operação de apoio à aplicação do functor `Adjoint` e/ou `Controlled`, o seu tipo de retorno precisa necessariamente de ser `Unit`. 


### <a name="explicit-specialization-declarations"></a>Declarações explícitas de especialização

Q# as operações podem conter as seguintes declarações explícitas de especialização:

- A `body` especialização especifica a implementação da operação sem functores aplicados.
- A `adjoint` especialização especifica a implementação da operação com o functor `Adjoint` aplicado.
- A `controlled` especialização especifica a implementação da operação com o functor `Controlled` aplicado.
- A `controlled adjoint` especialização especifica a implementação da operação com os functores `Adjoint` e `Controlled` aplicados.
  Esta especialização também pode ser nomeada `adjoint controlled`, uma vez que os dois functors viajam.


Uma especialização de operação consiste na etiqueta de especialização (como, por exemplo, `body`, ou `adjoint`, etc.) seguida de uma das:

- Uma declaração explícita, como descrito abaixo.
- Uma diretiva que diz ao compilador como gerar a especialização, uma das:
  - `intrinsic`, o que indica que a especialização é fornecida pela máquina-alvo.
  - `distribute`, que podem ser utilizados com as especialidades `controlled` e `controlled adjoint`.
    Quando utilizado com `controlled`, indica que o compilador deve calcular a especialização aplicando `Controlled` a todas as operações do `body`.
    Quando utilizado com `controlled adjoint`, indica que o compilador deve calcular a especialização aplicando `Controlled` a todas as operações na `adjoint` especialização.
  - `invert`, que indica que o compilador deve calcular a `adjoint` especialização invertendo a `body`, ou seja, inverter a ordem de operações e aplicar o adjoint a cada um.
    Quando utilizado com `adjoint controlled`, isto indica que o compilador deve calcular a especialização invertendo a `controlled` especialização.
  - `self`, para indicar que a especialização adjoint é a mesma que a `body` especialização.
    Isto é legal para as `adjoint` e `adjoint controlled` especializações.
    Para `adjoint controlled`, `self` implica que a `adjoint controlled` especialização é a mesma que a `controlled` especialização.
  - `auto`, para indicar que o compilador deve selecionar uma diretiva adequada a aplicar.
    `auto` não pode ser utilizado para a especialização `body`.

As diretivas e `auto` todos exigem um `;`de fecho do ponto-de-meia-cólon.
A diretiva `auto` resolve-se com a seguinte diretiva de geração se for fornecida uma declaração explícita do `body`:

- A `adjoint` especialização é gerada de acordo com a diretiva `invert`.
- A `controlled` especialização é gerada de acordo com a diretiva `distribute`.
- A `adjoint controlled` especialização é gerada de acordo com a diretiva `invert` se for dada uma declaração explícita para `controlled`, mas não para `adjoint`, e `distribute` o contrário.

> [!TIP]   
> Se uma operação for auto-adjoint, especifique explicitamente a adjoint ou a especialização adjoint controlada através da diretiva de geração `self` permitir que o compilador utilize essa informação para fins de otimização.

Uma declaração de especialização contendo uma implementação definida pelo utilizador consiste num argumento de tuple seguido de um bloco de declaração com o código Q# que implementa a especialização.
Na lista de argumentos, `...` é usada para representar os argumentos declarados para a operação como um todo.
Para `body` e `adjoint`, a lista de argumentos deve ser sempre `(...)`; Para `controlled` e `adjoint controlled`, a lista de argumentos deve ser um símbolo que represente o conjunto de qubits de controlo, seguidos de `...`, em parênteses; por exemplo, `(controls,...)`.

Se uma ou mais especializações para além do corpo padrão precisarde matem explicitamente, então a implementação do organismo predefinido deve ser embrulhada numa declaração de especialização adequada:

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="adjoint"></a>Adjoint

O adjoint de uma operação especifica como é implementada a transposição complexa conjugada da operação, ou seja, como funciona a operação quando "corre ao contrário".
É legal especificar uma operação sem adjoint; por exemplo, as operações de medição não têm adjoint porque não são invertáveis.
Uma operação apoia o functor `Adjoint` se a sua declaração contiver uma declaração implícita ou explícita de uma especialização adjoint.
Uma especialização adjoint explicitamente declarada implica a existência de uma especialização adjoint. 

Para a operação cujo corpo contenha ciclos de repetição até ao sucesso, definindo declarações, medições, declarações de devolução ou chamadas para outras operações que não suportem o functor `Adjoint`, gerando automaticamente uma especialização adjoint na sequência da diretiva `invert` ou `auto` não é possível.

### <a name="controlled"></a>Controlado

A versão controlada de uma operação especifica como é implementada uma versão quântica da operação, ou seja, como uma operação funciona quando aplicada condicionada no estado de um registo quântico.
Uma descrição mais completa é fornecida na secção [Controlada.](xref:microsoft.quantum.language.type-model#controlled)

É legal especificar uma operação sem versão controlada; por exemplo, as operações de medição não têm versão controlada porque não são controláveis.
Uma operação apoia o functor `Controlled` se e apenas se a sua declaração contiver uma declaração implícita ou explícita de uma especialização controlada.
Uma especialização adjoint explicitamente declarada implica a existência de uma especialização controlada. 

Para uma operação cujo corpo contenha chamadas para outras operações que não suportem o functor `Controlled`, não é possível gerar automaticamente uma especialização controlada na sequência da diretiva `distribute` ou `auto`.

### <a name="controlled-adjoint"></a>Adjoint controlado

A versão adjoint controlada de uma operação especifica como é implementada uma versão quântica da adjoint da operação.
É legal especificar uma operação sem versão adjoint controlada; por exemplo, as operações de medição não têm versão adjoint controlada porque não são controláveis nem invertíveis.

Uma especialização adjoint controlada para uma operação precisa de existir se e apenas se existir uma especialização adjoint e controlada. Nesse caso, a existência da especialização adjoint controlada é inferida e uma especialização adequada é gerada pelo compilador se não tiver sido definida explicitamente nenhuma implementação. 

Para uma operação cujo corpo contenha chamadas para outras operações que não tenham uma versão adjoint controlada, gerando automaticamente uma especialização adjoint na sequência da diretiva `invert`, `distribute` ou `auto` não é possível.


### <a name="examples"></a>Exemplos

Uma declaração de operação pode ser tão simples como a seguinte, que define a operação primitiva Pauli X:

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

O seguinte define a operação do teletransporte.

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation PrepareEntangledPair (q1 : Qubit, q2 : Qubit) : Unit 
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
        PrepareEntangledPair(target, ancilla);

        // Do the teleportation
        Adjoint PrepareEntangledPair(ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a>Declarações de Funções

As funções são rotinas puramente clássicas em Q#.
Cada ficheiro de origem Q# pode definir qualquer número de funções.

Uma declaração de função consiste na palavra-chave `function`, seguida do símbolo que é o nome da função, um túnica identificador dactilografado, uma anotação tipo que descreve o tipo de retorno da função, e um bloco de declaração que descreve a implementação da função.

O bloco de declaração que define uma função deve ser incluído em `{` e `}` como qualquer outro bloco de declaração.

Os nomes de funções devem ser únicos dentro de um espaço de nome e não podem entrar em conflito com o funcionamento e os nomes de tipo.
As funções não podem alocar ou emprestar qubits, ou operações de chamada. A aplicação parcial das operações ou a passagem em torno dos valores dactilografados de operação é boa.

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


## <a name="internal-declarations"></a>Declarações Internas

Os tipos, operações e funções definidos pelo utilizador também podem ser declarados *internos*.
Isto significa que só podem ser acedidos a partir do âmbito do projeto Q# em que são declarados.
Quando um projeto é usado como referência, todas as suas declarações *públicas* (não internas) são disponibilizadas, mas tentar utilizar uma declaração interna de outro projeto produzirá um erro.
As declarações internas são úteis para escrever código modular que pode ser reutilizado por outras partes do seu projeto, mas ainda assim ser alterado mais tarde sem quebrar outros projetos que possam depender dele.

Um tipo, funcionamento ou função interno definido pelo utilizador pode ser declarado simplesmente adicionando `internal` no início da declaração.
Por exemplo,

```qsharp
internal newtype PairOfQubits = (Qubit, Qubit);

internal operation PrepareEntangledPair(pair : PairOfQubits) : Unit 
is Adj + Ctl {
    let (q1, q2) = pair!;
    H(q2);
    CNOT(q2, q1);
}

internal function DotProduct(a : Double[], b : Double[]) : Double {
    ...
}
```

> [!WARNING]
> Os tipos internos definidos pelo utilizador só podem ser utilizados em assinaturas ou tipos subjacentes se o tipo correspondente de callable ou definido pelo utilizador também for interno.
> Por exemplo, se houver um tipo definido pelo utilizador `InternalOptions` que tenha sido declarado com a palavra-chave `internal`, então as seguintes declarações resultarão em erros:
>
> ```qsharp
> // Error: Can't use InternalOptions as an output type of a public function.
> function DefaultInternalOptions() : InternalOptions { ... }
>
> // Error: Can't use InternalOptions as an item in a public user-defined type.
> newtype ExtendedOptions = (Internal : InternalOptions);
> ```
