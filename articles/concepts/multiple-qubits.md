---
título: Descrição de múltiplos qubits: Aprenda a realizar operações em dois ou mais qubits.
autor: QuantumWriter uid: microsoft.quantum.concepts.multiple-qubits ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="multiple-qubits"></a>Múltiplos Qubits

Enquanto os portões de um único qubit possuem algumas características contraintuitivas, tais como a capacidade de estar em mais do que um estado de cada vez, se tudo o que tínhamos num computador quântico fosse portas de um único qubit, então teríamos um dispositivo com poder computacional que seria atenuado até mesmo por uma calculadora, quanto mais um supercomputador clássico.
O verdadeiro poder da computação quântica só se torna evidente à medida que aumentamos o número de qubits.
Este poder surge, em parte, porque a dimensão do espaço vetorial dos vetores do estado quântico cresce exponencialmente com o número de qubits.
Isto significa que, embora um único qubit possa ser trivialmente modelado, simular uma computação quântica de 50 qubits iria indiscutivelmente empurrar os limites dos supercomputadores existentes.
Aumentar o tamanho da computação em *apenas* um qubit adicional duplica a memória necessária para armazenar o estado e aproximadamente *duplica* o tempo computacional.
Esta rápida duplicação de poder computacional é a razão pela qual um computador quântico com um número relativamente pequeno de qubits pode ultrapassar em muito os supercomputadores mais poderosos de hoje, amanhã e além para algumas tarefas computacionais.

Por que temos crescimento exponencial para vetores de estado quântico?  O nosso objetivo nesta secção é rever as regras usadas para construir estados multi-qubit saindo de estados de um único qubit, bem como discutir as operações de portão que precisamos incluir no nosso portão definido para formar um computador quântico universal de muitos qubits.
Estas ferramentas são absolutamente necessárias para entender os conjuntos de porta que são comumente usados em Q# código e também para ganhar intuição sobre por que os efeitos quânticos, como o emaranhado ou a interferência, tornam a computação quântica mais poderosa do que a computação clássica.

## <a name="representing-two-qubits"></a>Representando Dois Qubits
A principal diferença entre estados de um e dois qubits é que os estados de dois qubits são quatro dimensões em vez de bidimensionais.
Isto porque a base computacional para estados de dois qubits é formada pelos produtos tensores de estados de um qubit.  Por exemplo, temos\begin{align}
00 \equiv \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ \end{bmatrix} & = \begin{bmatrix} 0 1 \\\\ 0 \\\\ \\\\ 0 0 \end{bmatrix} , \qquad 01 \equiv \begin{bmatrix} \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} \\\\ 0 1 0 1 \end{bmatrix} = \begin{bmatrix} \\\\ 0 1 \\\\ 0 0 \\\\ 0 0 \end{bmatrix} ,\\\\
10 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ \end{bmatrix} & = \begin{bmatrix} 0 \\\\ 0 \\\\ 1 \\\\ 0 \end{bmatrix} 10 , \qquad 11 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} \\\\ 0 1 \end{bmatrix} = \begin{bmatrix} \\\\ 0 0 \\\\ 0 \\\\ 0 1 \end{bmatrix} .
\end{align}

É fácil ver que, de uma forma mais geral, o estado quântico de $ n $ qubits é representado por um vetor unitário de dimensão $ 2^n $ usando esta construção.  O vetor

$$
\begin{bmatrix}\alpha _ { } 00 \\\\ \alpha   _ { 01 } \\\\ \alpha _ { 10 } \\\\ 11 \alpha   _ { }  \end{bmatrix}
$$

representa um estado quântico em dois qubits se $ | \alpha _ { 00 } | | \alpha ^2+_ { 01 } | ^2+ | \alpha _ { 10 } | ^2+ | \alpha _ { 11 } | ^2 = 1 $ . Assim como com os qubits individuais, o vetor de estado quântico de múltiplos qubits contém toda a informação necessária para descrever o comportamento do sistema.

Se nos forem dados dois qubits separados, um no estado $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ e um segundo qubit no $ \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ estado, o estado de dois qubits correspondente é    

$$
\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} 
=\begin{bmatrix} \alpha \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\  \delta \end{bmatrix} \end{bmatrix}
= \begin{bmatrix} \alpha\gamma \\\\  \alpha\delta \\\\  \beta\gamma \\\\  \beta\delta \end{bmatrix}, $$

onde a operação $ \otimes $ é chamada de produto tensor (ou produto Kronecker) de vetores. Note-se que, embora possamos sempre tomar o produto tensor de dois estados de um único qubit para formar um estado de dois qubits, nem todos os estados quânticos de dois qubits podem ser escritos como o produto tensor de dois estados de um único qubit.
Por exemplo, não há estados $ \psi = \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ e $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ de tal forma que o seu produto tensor é o estado     

$$\psi\otimes\phi = \begin{bmatrix} 1/ \sqrt { 2 } \\\\ 0 \\\\ 0 \\\\ 1/ \sqrt { 2 } \end{bmatrix} .$$ 

Um estado de dois qubits, que não pode ser escrito como o produto de tensor de estados de um único qubit, é chamado de "estado emaranhado"; dizem que os dois qubits estão [*emaranhados.*](https://en.wikipedia.org/wiki/Quantum_entanglement)  Em termos frouxos, porque o estado quântico não pode ser considerado como um produto tensor de estados de qubit único, a informação que o Estado detém não se limita a nenhum dos qubits individualmente.  Pelo contrário, a informação é armazenada não localmente nas correlações entre os dois estados.  Esta não localidade da informação é uma das principais características distintivas da computação quântica sobre a computação clássica e é essencial para uma série de protocolos quânticos, incluindo [teletransporte quântica](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/teleportation) e [correção de erros quânticos.](xref:microsoft.quantum.libraries.error-correction)

## <a name="measuring-two-qubit-states"></a>Medindo estados de dois qubits ##
Medir estados de dois qubits é muito semelhante às medições de um único qubit. Medir o estado

$$
    \begin{bmatrix}
        \alpha_ { } \\\\ 00 \alpha _ { 01 }\\\\ 
        \alpha_ { } \\\\ 10 \alpha _ { 11}
    \end{bmatrix}
$$

produz $ 00 $ com probabilidade $ | \alpha _ { 00 } | ^2 , $ $ 01 $ com probabilidade $ | \alpha _ { 01 } | ^2 $ , $ 10 $ com probabilidade $ | \alpha _ { 10^2 , e } | $ $ 11 $ com probabilidade $ | \alpha _ { 11 } | ^2 $ . As variáveis $ \alpha _ { } 00, \alpha _ { 01, } \alpha _ { 10 } $ e $ \alpha _ { 11 } $ foram deliberadamente nomeadas para tornar esta ligação clara. Após a medição, se o resultado for $ 00, $ então o estado quântico do sistema de dois qubits entrou em colapso e é agora

$$
    00\equiv
    \begin{bmatrix}
        1\\\\ 
        0\\\\ 
        0\\\\ 
        0 \end{bmatrix} .
$$

Também é possível medir apenas um qubit de um estado quântico de dois qubits. Nos casos em que se mede apenas um dos qubits, o impacto da medição é subtilmente diferente porque todo o Estado não é colapsado para um estado de base computacional, pelo contrário, é colapsado para apenas um subsiste.  Por outras palavras, nestes casos, medir apenas um qubit colapsa apenas um dos subsistemas, mas não todos.  

Para ver este considerar medir o primeiro qubit do seguinte estado, que é formado pela aplicação da transformação Hadamard $ H $ em dois qubits inicialmente definidos para o estado "0":$$
H^ { \otimes 2 } \left ( \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \right ) = \frac { 1 } { 2 } \begin{bmatrix} 1 & & 1 & \\\\ 1 & & 1 1 1 & -1 \\\\ & 1 1 1 1 & & -1 \\\\ & -1 & -1 -1 & \end{bmatrix} \begin{bmatrix} 1 1 \\\\ 1 1 1 1 \\\\ 0 \\\\ \end{bmatrix} = \frac { 0 0 } { } \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \mapsto \begin{cases} \text { } = & \frac { } { \sqrt { } } \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \\\\ \text { } = & \frac { } { \sqrt { } } \begin{bmatrix} \\\\ \\\\ 0 \\\\ 11 1 \end{bmatrix} \\\\ \end{cases} .  
$$
Ambos os resultados têm 50% de probabilidade de ocorrer.  O resultado sendo 50% de probabilidade para ambos pode ser intuido pelo facto de que o vetor de estado quântico inicial é invariante sob a troca $ de 0 $ com $ 1 no primeiro $ qubit.

A regra matemática para medir o primeiro ou segundo qubit é simples.  Se deixarmos $ e_k $ ser o $ vetor de base computacional k^ { \rm } $ e deixar S ser o conjunto $ de todos os e_k de tal forma que o $ $ $ qubit em questão leva o valor $ 1 para esse valor de k $ $ $ .  Por exemplo, se estivermos interessados em medir o primeiro qubit, $ S $ consistirá em $ e_1 \equiv 10 $ e e_3 $ \equiv 11 $ .  Da mesma forma, se estivermos interessados no segundo qubit $ S $ consistiria em $ e_2 \equiv 01 $ e e_3 $ \equiv 11 $ .  Em seguida, a probabilidade de medir o qubit escolhido para ser $ 1 $ é para o vetor de estado$\psi$

$$
P( \text { resultado } = 1) = \sum _ e_k no conjunto { S \text { } } \psi ^ \dagger e_k e_k^ \dagger \psi .
$$

> [!NOTE]
>Neste documento estamos a usar o formato pouco endiano para rotular a base computacional. Em formato pequeno endiano, os pedaços menos significativos vêm em primeiro lugar. Por exemplo, o número quatro em formato pequeno-endiano é representado pela cadeia de bits 001.

Uma vez que cada medida de qubit só pode produzir $ 0 $ ou $ $ 1, a probabilidade de medir $ 0 é simplesmente $ $ 1-P( \text { resultado } = 1) $ .  É por isso que apenas explicitamente damos uma fórmula para a probabilidade de medir $ 1 $ .

A ação que tal medida tem sobre o estado pode ser expressa matematicamente como

$$
\psi\mapsto \frac{\sum _ { e_k no conjunto S \text { } } e_k e_k^ \dagger \psi } { \sqrt { P( \text { resultado } = 1) } } .
$$

O leitor cauteloso pode preocupar-se com o que acontece quando a probabilidade da medição é zero.  Embora o estado resultante seja tecnicamente indefinido neste caso, nunca precisamos de nos preocupar com tais eventualidades porque a probabilidade é zero!


Se tomarmos $ \psi $ para ser o vetor de estado uniforme dado acima e estamos interessados em medir o primeiro qubit, então 

$$
P( \text { medição do primeiro qubit } = 1) = \psi ^ \dagger (e_1)(e_1^2) \dagger \psi \psi ^ \dagger \dagger \psi (e_3 e_3)) = | \dagger \psi | e_1^2+ | \dagger \psi | e_3^2.
$$

Note-se que esta é apenas a soma das duas probabilidades que seria de esperar para medir os resultados $ 10 $ e $ 11 $ foram todos os qubits a medir.
Para o nosso exemplo, isto avalia a

$$
\frac{1 } { 4 } \left | \begin{bmatrix} 0 & 0 & 1 & \end{bmatrix} \begin{bmatrix} 1 \\\\ 1 \\\\ \\\\ 1 1 \end{bmatrix} \right | 1 ^2+ \frac { 1 } { 4 } \left | \begin{bmatrix} 0 & & 0 & 0 1 \end{bmatrix} \begin{bmatrix} \\\\ \\\\ 1 \\\\ 1 1 1 \end{bmatrix} \right | 1 ^2 = \frac { 1 } { 2 } .
$$

que combina perfeitamente com o que a nossa intuição nos diz que a probabilidade deve ser.  Da mesma forma, o estado pode ser escrito como

$$
\frac{\frac{e_1 } { 2 } + \frac { e_3 } { } } { \sqrt { \frac { 2 1 } { } } } = \frac { 2 1 } { \sqrt { 2 } } \begin{bmatrix} 0 \\\\ \\\\ 1 \\\\ 1\end{bmatrix}
$$

novamente de acordo com a nossa intuição.

## <a name="two-qubit-operations"></a>Operações de Dois Qubits
Como no caso de um único qubit, qualquer transformação unitária é uma operação válida em qubits. Em geral, uma transformação unitária em $ n $ qubits é uma matriz $ U de tamanho $ $ 2^n \times 2^n $ (de modo que atua em vetores de tamanho $ 2^n), $ tal que $ U^ { -1 } = U^ \dagger $ .
Por exemplo, o portão CNOT (CONTROLLED-NOT) é um portão de dois qubits comumente utilizado e é representado pela seguinte matriz unitária:

$$
\operatorname{CNOT } = \begin{bmatrix} 1\ 0\ 0\ \\\\ 0\ 1\ 0\ \\\\ 0\ 0\ 0\ 0\ 0\ 0\ 1 \\\\ 0\ 0\ 1\ 0\ 0\end{bmatrix}
$$

Também podemos formar portões de dois qubits aplicando portas de um único qubit em ambos os qubits. Por exemplo, se aplicarmos os portões 

$$
\begin{bmatrix}
a\ b \\\\ c\ d\end{bmatrix}
$$

e

$$\begin{bmatrix}
e\ f \\\\ g\ h\end{bmatrix}
$$

aos primeiros e segundos qubits, respectivamente, isto equivale à aplicação do unitário de dois qubits dado pelo seu produto tensor:$$\begin{bmatrix}
a\ b \\\\ c\ d\end{bmatrix}
\otimes 
\begin{bmatrix}
e\ f \\\\ g\ h\end{bmatrix}=
    \begin{bmatrix}
    ae\ af\ ser\ bf\\\\
    ag\ ah\ bg\ bh\\\\
    ce\ cf\ de\ df\\\\
    cg\ ch\ dg\ dh \end{bmatrix} .$$
Assim, podemos formar portões de dois qubits tomando o produto tensor de alguns portões de um único qubit conhecido. Alguns exemplos de portões de dois qubits incluem $ H \otimes $ $ \otimes \boldone $ H, X, e $ X Z \otimes $ .

Note que, embora dois portões de um único qubit definam um portão de dois qubits tomando o seu produto tensor, o inverso não é verdade. Nem todos os portões de dois qubits podem ser escritos como o produto de tensor de portas de um único qubit.  Tal portão é chamado de portão *de enredar.* Um exemplo de um portão de enredar é o portão CNOT.

A intuição por trás de um portão não controlado pode ser generalizada a portões arbitrários.  Um portão controlado em geral é um portão que age como identidade (ou seja, não tem ação) a menos que um qubit específico seja $ 1 $ .  Denotamos um unitário controlado, controlado neste caso no qubit rotulado $ $ x, com um $ \Lambda \_ x(U) $ .  Como exemplo $ \Lambda _0(U) e \_ { 1 } \otimes { \psi } = e \_ { 1 } \otimes U { \psi } $ e $ \Lambda \_ 0(U) e \_ { 0 } \otimes { \psi } = e \_ { 0 } \otimes { \psi } $ , onde $ e \_ 0 $ e $ \_ 1 são os $ vetores de base computacional para um único qubit correspondente aos valores $ 0 e $ $ 1 $ .  Por exemplo, considere o seguinte $ portão controlado-Z, $ em seguida, podemos expressar isto como$$
\Lambda\_0(Z) = \begin{bmatrix} 1 & 0 & & 0 \\\\ & 0 1 & 0 & \\\\ 0 & & 0 0 & \\\\ 0 & 0 & 0 0 0 & -1 \end{bmatrix} = \boldone \otimes (H) \operatorname { CNOT } \boldone \otimes (H).
$$

Construir unidades controladas de forma eficiente é um grande desafio.  A forma mais simples de implementar isto requer a formação de uma base de dados de versões controladas de portões fundamentais e a substituição de todos os portões fundamentais da operação unitária original pela sua contraparte controlada.  Isto é muitas vezes uma visão bastante desperdiçada e inteligente muitas vezes pode ser usado apenas para substituir alguns portões por versões controladas para obter o mesmo impacto.  Por esta razão, fornecemos no nosso enquadramento a capacidade de executar o método ingénuo de controlo ou permitir que o utilizador defina uma versão controlada do unitário se for conhecida uma versão afinada à mão.

Os portões também podem ser controlados usando informações clássicas.  Um não-portão controlado clássicamente, por exemplo, é apenas um não-portão comum, mas só é aplicado se um pedaço clássico é $ 1 $ em oposição a um bit quântico.  Neste sentido, um portão controlado clássicamente pode ser considerado como uma declaração no código quântico em que o portão é aplicado apenas em um ramo do código.


Tal como no caso de um único qubit, um conjunto de portão de dois qubits é universal se qualquer $ \times matriz unitária de 4 4 $ pode ser aproximadada por um produto de portões deste conjunto para precisão arbitrária.
Um exemplo de um portão universal é o portão Hadamard, o portão T e o portão CNOT. Tomando produtos destes portões, podemos aproximar qualquer matriz unitária em dois qubits.

## <a name="many-qubit-systems"></a>Sistemas Muitos Qubit
Seguimos exatamente os mesmos padrões explorados no caso dos dois qubits para construir estados quânticos de muitos qubits a partir de sistemas mais pequenos.  Estes Estados são construídos através da formação de produtos de tensor de estados mais pequenos.  Por exemplo, considere codificar a corda $ bit 1011001 $ num computador quântico.  Podemos codificar isto como

$$
1011001 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} \\\\ 0 1 \end{bmatrix} \otimes \begin{bmatrix} \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ \end{bmatrix} \otimes \begin{bmatrix} 1 0 1 \\\\ \end{bmatrix} \otimes \begin{bmatrix} 0 0 \\\\ 0 1 \end{bmatrix} .
$$

Os portões quânticos funcionam exatamente da mesma forma.  Por exemplo, se quisermos aplicar o $ portão X ao primeiro $ qubit e, em seguida, executar um CNOT entre o segundo e o terceiro qubits, podemos expressar esta transformação como

\begin{align}
&(X \otimes \operatorname { CNOT } _ { 12 } \otimes \boldone \otimes \boldone \otimes \boldone \otimes \boldone ) \begin{bmatrix} \\\\ 0 1 \end{bmatrix} \otimes \begin{bmatrix} \\\\ 1 0 \end{bmatrix} \otimes \begin{bmatrix} \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} \\\\ 0 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ \end{bmatrix} \otimes \begin{bmatrix} 1 0 1 \\\\ \end{bmatrix} \otimes \begin{bmatrix} 0 0 0 \\\\ 1 0 1\end{bmatrix}\\\\
&\qquad\qquad\equiv0011001.\end{align}

Em muitos sistemas qubits, há muitas vezes a necessidade de alocar e translocar qubits que servem de memória temporária para o computador quântico.  Tal qubit é chamado de ancilla.  Por defeito, assumimos que o estado qubit é inicializado para $ e_0 $ após a atribuição.  Assumimos ainda que é devolvida de novo a $ e_0 $ antes da negociação.  Esta suposição é importante porque se um qubit de ancilla ficar enredado com outro registo qubit quando se torna transatado, então o processo de transação prejudicará a ancilla.  Por esta razão, assumimos sempre que tais qubits são revertidos para o seu estado inicial antes de serem libertados.

Finalmente, embora fossem necessários novos portões para alcançar a computação quântica universal para dois computadores qubit qubit, não é necessário introduzir novos portões no caso multi-qubit.  Os portões $ $ H, $ T e $ CNOT formam um portão universal definido em muitos qubits porque qualquer transformação unitária geral pode ser dividida numa série de duas rotações de qubit.  Podemos então aproveitar a teoria desenvolvida para o caso de dois qubits e usá-la novamente aqui quando temos muitos qubits.

Embora a notação algébrica linear que temos usado até agora possa certamente ser usada para descrever estados multi-qubit, torna-se cada vez mais complicado à medida que aumentamos o tamanho dos Estados.  O vetor de coluna resultante para uma corda de 7 bits de comprimento, por exemplo, é $ 128 $ dimensional, o que faz expressá-lo usando a notação descrita anteriormente muito pesado.  Por esta razão, apresentamos uma notação comum na computação quântica que nos permite descrever concisamente estes vetores de alta dimensão.
