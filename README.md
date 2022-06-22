# ImageProcessing_RestorationProject
Final project developed to the SCC-0251 Image Processing Course at ICMC-USP.

## Grupo
 * [João Victor Sene Araújo](https://github.com/JoaoVSene) - nUSP: 11796382
 * [Pedro Augusto Ribeiro Gomes](https://github.com/pedroaurgomes) - nUSP: 11819125

## Abstract 

As imagens médicas obtidas a partir de exames de ressonância magnética (MRI scans) frequentemente apresentam danos á sua qualidade, normalmente pelo fato 
do paciente ter se movido durante o procedimento de aquisição da imagem, problemas no equipamento, entre outras coisas. O objetivo principal do projeto é receber essas imagens
danificadas na entrada e aplicar técnicas de restauração de imagens a fim de facilitar a visualização das mesmas por parte dos profissionais da área da
saúde, possibilitando assim que o diagnóstico possa ser dado de forma eficiente, sem que o exame precise ser repetido.

## Principais tarefas de processamento de imagem:
 * Restauração 

## Aplicação:
 * Imagens médicas

## Metodologia e Desenvolvimento

Primeiramente, obtivemos as imagens de ressonância magnética (MRI) de input a partir de um [Dataset](https://www.kaggle.com/datasets/navoneel/brain-mri-images-for-brain-tumor-detection) disponível no [Kaggle](https://www.kaggle.com/). No entanto, as imagens encontradas não apresentam danos suficientes 
que justificam reparo. Por esse motivo, optou-se por uma etapa de pré-processamento das imagens, na qual será inserido um efeito de degradação nas imagens com o intuito de simular acidentes que podem ocorrer na realidade, utilizando filtros de blur.

### [Algoritmo de pré-processamento](./src/PreProcBlurring.ipynb)

Exemplos de pré-processamento: <br>

| Original | Pré-processada|
|----------|---------------|
|![Imagem 3 Original ](./assets/Original3.jpg)|![Imagem 3 Blurred ](./assets/Blurred3.jpg)|
|![Imagem 6 Original ](./assets/Original6.jpg)|![Imagem 6 Blurred ](./assets/Blurred6.jpg)|


Após o pré-processamento, as imagens serão enviadas como entrada ao algoritmo que efetuará o processo de restauração.

Assim, considerando que a imagem real 'X' obtida pelo equipamento utilizado possui certos defeitos e ruídos, temos a seguinte relação:

X = I * H + N

, onde I é a imagem ideal, H é uma PSF (Point Spread Function) e N uma matrix que representa os ruídos.

Com isso, nosso objetivo é utilizar uma metodologia que permita, partindo somente da imagem X, nos aproximar da imagem ideal I.

Desse modo, a intenção é utilizar um método de deconvolução cega (Blind Deconvolution), uma vez que em situações reais não dispomos do conhecimento
da função de degradação (Point Spread Function). Sendo assim, após realizar uma pesquisa na literatura sobre os algoritmos existentes, foi decidido
que seria utilizado o Algoritmo de Deconvolução Cega Richardson-Lucy, o qual estima a imagem restaurada a partir da imagem dada na entrada, bem como
a PSF, a partir de uma PSF inicial arbitrária, após uma série de iterações.

### [Algoritmo de Restauração](./src/PartialResultsRestorationRL.ipynb)

#### Modelo RL para estimar a imagem restaurada: <br>

![modelo para estimar a imagem restaurada](./assets/EquacaoEstimarImg.png)

#### Modelo RL  para estimar a PSF: <br>
![modelo para estimar a PSF](./assets/EquacaoEstimarPSF.png)

**Referência:**
[Yu A Bunyak, O Yu Sofina and R N Kvetnyy 2012 Blind PSF estimation and methods of deconvolution optimization](https://arxiv.org/ftp/arxiv/papers/1206/1206.3594.pdf)

