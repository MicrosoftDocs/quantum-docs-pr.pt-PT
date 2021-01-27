---
title: Utilização da Q# Biblioteca Dos Numéricos da Microsoft
description: Saiba mais sobre os tipos e operações disponíveis na biblioteca dos Numericos Quânticos da Microsoft.
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: conceptual
uid: microsoft.quantum.numerics.usage
no-loc:
- Q#
- $$v
ms.openlocfilehash: 92efd3b8677d2f27bc59f986ce6c9e915cd23652
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856449"
---
# <a name="using-the-numerics-library"></a>Usando a biblioteca numérica

## <a name="overview"></a>Descrição geral

A biblioteca numérica é composta por três componentes

1. **Aritmética de inteiros** básicos com suplementos inteiros e comparadores
1. **Funcionalidade de número inteiro de alto nível** que é construída em cima da funcionalidade básica; inclui multiplicação, divisão, inversão, etc.  para inteiros assinados e não assinados.
1. **Funcionalidade aritmética de ponto fixo** com inicialização de ponto fixo, adição, multiplicação, avaliação recíproca, polinomial e medição.

Todos estes componentes podem ser acedidos através de uma única `open` declaração:
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>Tipos

A biblioteca numérica suporta os seguintes tipos

1. **`LittleEndian`**: Uma matriz qubit `qArr : Qubit[]` que representa um número inteiro onde `qArr[0]` denota a parte menos significativa.
1. **`SignedLittleEndian`**: O mesmo `LittleEndian` que representa um número inteiro assinado armazenado no complemento de dois.
1. **`FixedPoint`**: Representa um número real constituído por uma matriz de qubit `qArr2 : Qubit[]` e uma posição de ponto `pos` binário, que conta o número de dígitos binários à esquerda do ponto binário. `qArr2` é armazenado da mesma forma que `SignedLittleEndian` . .

## <a name="operations"></a>Operações

Para cada um dos três tipos acima, está disponível uma variedade de operações:

1. **`LittleEndian`**
    - Adição
    - Comparação
    - Multiplicação
    - Esquartejar
    - Divisão (com o restante)

1. **`SignedLittleEndian`**
    - Adição
    - Comparação
    - Complemento de inversão modulo 2
    - Multiplicação
    - Esquartejar

1. **`FixedPoint`**
    - Preparação/ inicialização a valores clássicos
    - Adição (constante clássica ou outro ponto fixo quântico)
    - Comparação
    - Multiplicação
    - Esquartejar
    - Avaliação polinomial com especialização para funções par e ímpares
    - Recíproco (1/x)
    - Medição (duplo clássico)

Para obter mais informações e documentação detalhada para cada uma destas operações, consulte os documentos de referência da Q# biblioteca em [docs.microsoft.com](https://docs.microsoft.com/quantum)

## <a name="sample-integer-addition"></a>Amostra: Adição de inteiros

Como exemplo básico, considere a operação $$ \ket x\ket y\mapsto \ket x\ket{x+y} $00, isto é, uma operação que leva um número inteiro n-qubit $x$ e um registo n-ou (n+1)-qubit $y$ como entrada, a última das quais mapeia para a soma $(x+y)$. Note que a soma é computada modulo $2^n$ se $y$ for armazenado num registo de $n de $-bit.

Utilizando o Kit de Desenvolvimento Quântico, esta operação pode ser aplicada da seguinte forma:
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        let x = LittleEndian(xQubits); // define bit order
        let y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a>Amostra: Avaliação de funções suaves

Para avaliar funções suaves como $\sin (x)$ num computador quântico, onde $x$ é um número quântico, `FixedPoint` a biblioteca numérica do Kit de Desenvolvimento Quântico fornece as operações `EvaluatePolynomialFxP` e `Evaluate[Even/Odd]PolynomialFxP` .

O primeiro, `EvaluatePolynomialFxP` permite avaliar um polinómio do formulário $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ onde $d$ denota o *grau*. Para tal, tudo o que é necessário são os coeficientes polinómicos `[a_0,..., a_d]` (do `Double[]` tipo), a entrada `x : FixedPoint` e a saída `y : FixedPoint` (inicialmente zero):
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
O resultado, $P(x)=1+2x$, será armazenado em `yFxP` .

A segunda, `EvaluateEvenPolynomialFxP` e a `EvaluateOddPolynomialFxP` terceira, são especializações para os casos de funções par e ímpares, respectivamente. Isto é, para uma função par/ímpar $f(x)$ e $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ é aproximadamente bem por $P_{even}(x)$ ou $P_{odd}(x) := x\cdot P_{even}(x)$, respectivamente.
Em Q# , estes dois casos podem ser tratados da seguinte forma:
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
que avalia $P_{even}(x) = 1 + 2x^2$, e
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
que avalia $P_{odd}(x) = x + 2x^3$.

## <a name="more-samples"></a>Mais exemplos

Pode encontrar mais amostras no [repositório principal de amostras.](https://github.com/Microsoft/Quantum)

Para começar, clone o repo e abra a `Numerics` sub-página:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics
```

Em seguida, `cd` em uma das pastas de amostra e executar a amostra através

```bash
dotnet run
```
