---
title: Usando a Biblioteca numérica Microsoft Q#
description: Conheça os tipos e operações disponíveis na biblioteca de Numéricos Quânticos da Microsoft.
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: 10d5675e0ef182211a38db4d09347b05afe109c3
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: pt-PT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82677114"
---
# <a name="using-the-numerics-library"></a>Usando a biblioteca numérica

## <a name="overview"></a>Descrição geral

A biblioteca numérica é composta por três componentes

1. **Aritmética de inteiro básico** com adders inteiros e comparadores
1. **Funcionalidade inteiro de alto nível** que é construída em cima da funcionalidade básica; inclui multiplicação, divisão, inversão, etc.  para os inteiros assinados e não assinados.
1. **Funcionalidade aritmética de ponto fixo** com inicialização de ponto fixo, adição, multiplicação, avaliação recíproca, polinomial e medição.

Todos estes componentes podem ser acedidos através de uma única `open` declaração:
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>Tipos

A biblioteca numérica suporta os seguintes tipos

1. **`LittleEndian`**: Um conjunto `qArr : Qubit[]` qubit que representa `qArr[0]` um inteiro onde denota a parte menos significativa.
1. **`SignedLittleEndian`**: O `LittleEndian` mesmo que, exceto, representa um inteiro assinado armazenado no complemento de dois.
1. **`FixedPoint`**: Representa um número real constituído por `qArr2 : Qubit[]` uma matriz `pos`qubit e uma posição de ponto binário, que conta o número de dígitos binários à esquerda do ponto binário. `qArr2`é armazenado da mesma `SignedLittleEndian`forma que .

## <a name="operations"></a>Operações

Para cada um dos três tipos acima, existe uma variedade de operações:

1. **`LittleEndian`**
    - Adição
    - Comparação
    - Multiplicação
    - Esquartejar
    - Divisão (com restante)

1. **`SignedLittleEndian`**
    - Adição
    - Comparação
    - Complemento de modulo 2 de inversão
    - Multiplicação
    - Esquartejar

1. **`FixedPoint`**
    - Preparação/inicialização a valores clássicos
    - Adição (constante clássica ou outro ponto fixo quântico)
    - Comparação
    - Multiplicação
    - Esquartejar
    - Avaliação polinomial com especialização para funções iguais e ímpares
    - Recíproco (1/x)
    - Medição (duplo clássico)

Para obter mais informações e documentação detalhada para cada uma destas operações, consulte os documentos de referência da biblioteca Q# na [docs.microsoft.com](https://docs.microsoft.com/quantum)

## <a name="sample-integer-addition"></a>Amostra: Adição de inteiro

Como exemplo básico, considere a operação $$ \ket x\ket y\mapsto \ket {x+y} $, isto é, uma operação que leva um integer n-qubit $x$ e um registo n- ou (n+1)-qubit $y$ como entrada, esta última da qual mapeia para a soma $(x+y)$. Note que a soma é calculada modulo $2^n$ se $y$ for armazenado num registo de $n$bit.

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

Para avaliar funções suaves como $\sin(x)$ num computador quântico, `FixedPoint` onde $x$ é um número quântico, `EvaluatePolynomialFxP` `Evaluate[Even/Odd]PolynomialFxP`a biblioteca de numéricos do Quantum Development Kit fornece as operações e .

O primeiro, `EvaluatePolynomialFxP`permite avaliar um polinómio do formulário $$ P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_dx^d, $$ onde $d$ denota o *grau.* Para tal, tudo o que é necessário são os `[a_0,..., a_d]` coeficientes polinomais (de tipo), `Double[]`a entrada `x : FixedPoint` e a saída `y : FixedPoint` (inicialmente zero):
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
O resultado, $P(x)=1+2x$, será `yFxP`armazenado em .

A segunda, `EvaluateEvenPolynomialFxP`e a `EvaluateOddPolynomialFxP`terceira, são especializações para os casos de funções paras e ímpares, respectivamente. Ou seja, para uma função uniforme/ímpar $f(x)$ e $$ P_{even}(x)=a_0 + a_1 x^2 + a_2 x^4 + \cdots + a_d x^{2d}, $$ $f(x)$ é aproximadado bem por $P_{{}(x)$ ou $P{odd}(x) ==x=t={odd}(x) == x\cdot P_{mesmo(x)$, respectivamente.
Em Q#, estes dois casos podem ser tratados da seguinte forma:
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
que avalia $P_{even}(x) = 1 + 2x^2$, e
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
que avalia $P_{odd}(x) = x + 2x^3$.

## <a name="more-samples"></a>Mais exemplos

Pode encontrar mais amostras no [repositório de amostras principais.](https://github.com/Microsoft/Quantum)

Para começar, clone o repo `Numerics` e abra a subpasta:

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

Em `cd` seguida, em uma das pastas da amostra e executar a amostra via

```bash
dotnet run
```
