# <a name="articles"></a>Artigos

Neste diretório pode encontrar os artigos para a documentação do Kit de Desenvolvimento Quântico. Este diretório contém:

- **Diretórios de artigos**: contenham os artigos para cada secção da documentação. Nestes diretórios pode encontrar os seguintes conteúdos:
  
  - Cada diretório contém um `toc.yml` ficheiro para exibir o conteúdo do diretório na tabela principal de conteúdos (TOC).
  - Artigos de marcação que contêm a documentação. Estes artigos devem seguir as orientações do [guia de contribuintes](https://docs.microsoft.com/en-us/contribute/)da Microsoft Docs .
  - Sub-directórios de artigos. Estes sub-directórios também devem conter o seu próprio `toc.yml` ficheiro.

> :pencil: Embora seja possível encaminhar os `*.md` ficheiros diretamente no ficheiro dos pais, para manter as `TOC.yml` coisas ordenadas, apenas os encaminhamos a partir `toc.yml` do seu diretório atual.

- **Tabela principal de `TOC.yml` ficheiros de conteúdos (TOC):** neste ficheiro as secções do toc do site são listadas juntamente com a referência ao ficheiro principal `toc.yml` do diretório de cada secção.
- **`index.yml`** YAML com a configuração da página de aterragem da documentação.
- **`\media`**: Um diretório para armazenar todas as imagens utilizadas na documentação. Contém uma `\media\src` subdiretório para armazenar ficheiros de origem das imagens.
- **Ficheiros de licença**: ficheiros que contenham licenças legais
- **Ficheiros técnicos**: ficheiros que contenham macros e metadados.

## <a name="guidelines"></a>Diretrizes

Algumas diretrizes gerais sobre a organização deste diretório para contribuintes:

- Todos os diretórios ou sub-directórios devem conter o seu próprio `toc.yml` ficheiro no qual são remetidos os artigos de mesmo nível ou os `toc.yml` ficheiros dos seus diretórios infantis.
- A organização dos diretórios do repositório deve estar o mais próxima possível da organização da tabela de conteúdos do site de documentação.
- Todas as imagens devem ser armazenadas `articles\media` e não na pasta de artigos.
- Os títulos dos artigos, os nomes no TOC e no *uid* dos metadados devem estar o mais próximos possível entre eles e representar claramente o cabeçalho H1 do documento Markdown.

## <a name="adding-images"></a>Adicionar imagens

Para que as imagens se tornem adequadamente em modo escuro, deve evitar transparências.
- Para `*.jpg` ficheiros não é necessário fazer nada, uma vez que o formato de ficheiro não suporta elementos transparentes.
- Para `*.png` ficheiros deve adicionar um fundo branco ou alterar o valor do canal alfa para 100. A forma mais fácil de o fazer no Windows é abrindo o ficheiro em Paint e economizando, sobressaíndo o ficheiro original.
- Para `*.svg` ficheiros deve adicionar um retângulo branco na camada mais baixa. Pode fazê-lo com o Inkscape:
  - Abra o ficheiro `*.svg`.
  - Selecione a ferramenta de máquina de fazer quadrados e desenhe um retângulo branco em cima da figura original.
  - Selecione a ferramenta "Selecione e transforme objetos" clicando na seta escura ou pressionando F1.
  - Enquanto seleciona o retângulo, clique no elemento da barra de ferramentas "Seleção inferior a baixo (Fim)".
  - Ajuste o retângulo com o rato ou as teclas de seta.
