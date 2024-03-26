# Criação de IA para reconhecimento facial e transformando imagens em dados no Azure ML

Este projeto tem como objetivo o aprendizado e utilização dos serviços de Machine Learning da Microsoft Azure.

## Criando um workshop

Para utilizar o serviço de aprendizado de máquina do Azure, é necessário realizar uma assinatura dos serviços Microsoft Azure.

Após realizar a assinatura, deve-se se dirigir até a opção "Criar um recurso" e pesquisar pelo serviço "Serviços Cognitivos" ou caso você esteja utilizando em inglês: "Azure AI Service"

Agora é necessário configurar o Workspace, selecionando a qual assinatura ele será atrelado e selecionar um grupo de recursos, que basicamente é uma coleção de recursos que compartilham o mesmo ciclo de vida e as mesmas permissões.
Exemplo:

Nome: LabIA002
Servidor: Us East (Não compensa utilizar o servidor brasileiro por ter um custo maior.)
Conta de armazenamento: LABIA02
Tipo de preço: Standard S0
E marque a caixa de termos.

Após finalizar as configurações, basta clicar em Examinar + criar e se direcionar ao Azure Vision Studio.

Dentro do Portal vision, iremos testar as seguintes funções:
<ul>
    <li>Reconhecimento ótico de caracteres (OCR)</li>
    <li>Análise espacial</li>
    <li>Reconhecimento facial</li>
    <li>Identificador de imagem</li>
</ul>

Mas antes de iniciar, é necessário já no Vision Studio, clicar em <em>"View all resources"</em> e selecionar o recurso(workshop) criado e dar <em>"Select as default resource"</em> após isso podemos voltar ao Vision Studio e dar continuidade.

Os arquivos utilizados estão localizados em:

Reconhecimento ótico: <em>['OCR'](/Inputs/ocr-images/)</em>
Reconhecimento Facial: <em>['Face'](/Inputs/detect-faces/)</em>
Identificador de imagem: <em>['Image analysis'](/Inputs/image-analysis/)</em>
Análise espacial: <em>['Videos'](/Inputs/spatial-analysis/)</em>

### Reconhecimento ótico de caracteres

O OCR serve para detectar e extrair textos de imagensm facilitando a captura de nomes de ruas, textos, cartões e etc.

Para iniciar, selecionamos a opção <em>"Optical character recognition"</em> e em seguida: <em>"Extract text from images</em>. Os demais procedimentos funcionarão praticamente da mesma forma ao buscar um arquivo local <em>"Browse for files"</em> ou para procurar o conteúdo em uma blob existente <em>"Browse container for your videos"</em>, que não será utilizada neste caso.

Dentro da aba de extração de texto, podemos ver a documentação da função, olhar o SDK referencial, os comandos para utilização em API e as línguas suportadas e no final da página, está as opções sobre passos a seguir.

Mas para realizarmos o teste, vamos concordar com os termos de teste e inserir uma imagem de nossa escolha ou utilizar uma da galeria Microsoft.

Aqui utilizaremos uma imagem própria:
![mangá "Frieren"](/Outputs/ocr-images/mangá%20-%20result.png "Trecho do mangá Frieren")

Onde é possível visualizar os quadros destacando o texto e sendo reescrito na caixa de texto ao lado.

Outros resultados: ['OCR resultados'](/Outputs/ocr-images/)

### Análise espacial

Voltando ao Vision Studio podemos ir até a aba Spatial Analysis e temos algumas opções que nos demonstram como a IA pode funcionar, seja detectando a quantidade de pessoas em uma determinada área, a quantidade de vezes que alguém ultrapassou um determinado local, quantas vezes entraram e sairam de um determinado lugar e podemos monitorar a distância entre as pessoas.

Mas no momento vamos utilizar a opção <em>Video retrieval and Summary</em>, onde também podemos verificar como seria utilizado em API e sua documentação. 
Também podemos utilizar de um vídeo próprio para realizar buscas personalizadas por conteúdos que estão em determinados frames ou utilizar um vídeo da galeria da Microsoft que já possui resultados prontos demonstrando como funciona.

Aqui eu utilizei um vídeo da internet, em que busco determinadas cores no vídeo e ele me retorna com o momento em que o frame demonstra tais cores:
![Cena do BBB](/Outputs/spatial-analysis/video-summary-and-frame-locator.png "Davi discutindo com Bin laden após noite de sincerão")

Porém, o serviço também é capaz de detectar os frames onde estão pessoas, acessórios, objetos e etc.

### Detecção facial
Voltando ao início, basta ir na aba <em>Face</em> e selecionar a única opção disponível.

Dentro da aba, podemos visualizar um exemplo simples no github e as outras opções que aparecem em abas anteriores. 

Aqui, devemos que a IA é capaz de detectar os rostos e realizar a verificação se a pessoa está utilizando máscara ou não, se estiver utilizando, ele verifica se ela está tampando o nariz e a boca ou apenas um dos dois como no exemplo a baixo:
![Dfacial](/Outputs/detect-faces/masked%20woman%20-%20results.png "Mulher mascarada tampando boca e nariz")

### Analizador de imagens

Já no analizador de imagens, temos diversas opções que vão desde a detectação de produtudos, removedor de fundo a opções como uma IA que detecta conteúdos sensíveis e um legendador de imagens.

No exemplo a baixo é utilizado o legendador simples, porém, na própria plataforma tem uma opção q ue descreve diversos conteúdos presentes na imagem, ao invés de tentar detectar de maneira simples:

![Aimagens](/Outputs/image-analysis/Add-captions-to-images.png "Imagem em análise e legenda ao lado")


## Documentação
Segue a documentação utilizada neste projeto:

Reconhecimento ótico: <em>['OCR docs'](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/05-ocr.html)</em>
Reconhecimento Facial: <em>['Face docs'](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/04-face.html)</em>
Identificador de imagem: <em>['Image analysis docs'](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/03-image-analysis.html)</em>
Digital Innovation One: <em>['Dio'](https://www.dio.me/)</em># Azure-IA-Services-Project
