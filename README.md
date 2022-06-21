# ImageProcessing_RestorationProject
Final project developed to the SCC-0251 Image Processing Course at ICMC-USP.

## Grupo
 * [João Victor Sene Araújo](https://github.com/JoaoVSene) - nUSP: 11796382
 * [Pedro Augusto Ribeiro Gomes](https://github.com/pedroaurgomes) - nUSP: 11819125

## Abstract 

As imagens médicas obtidas a partir de exames de ressonância magnética (MRI scans) frequentemente apresentam danos á sua qualidade, normalmente pelo fato 
do paciente ter se movido durante o procedimento de aquisição da imagem, entre outras coisas. O objetivo principal do projeto é receber essas imagens danificadas na entrada e aplicar técnicas de restauração de imagens a fim de facilitar a visualização das mesmas por parte dos profissionais da área da saúde, possibilitando assim que o diagnóstico possa ser dado de forma eficiente, sem que o exame precise ser repetido.

## Principais tarefas de processamento de imagem:
 * Restauração 

## Aplicação:
 * Imagens médicas

## Exemplos de input:

<img src="https://user-images.githubusercontent.com/62620260/169727499-55496bd7-361a-4249-82a7-c6c3d7535dd1.jpeg" alt="MRI Blurred" height="400"/>

<img src="https://user-images.githubusercontent.com/62620260/169727750-cb42ed18-b0cf-4d1d-8e63-737aee592dbc.jpeg" alt="MRI Blurred" height="400"/>

## Descrição das imagens de input:


## Desenvolvimento (descrição dos passos para atingir o objetivo)

Primeiramente, obtivemos as imagens de ressonância magnética (MRI) de input a partir de um [Dataset](https://www.kaggle.com/datasets/navoneel/brain-mri-images-for-brain-tumor-detection) disponível no [Kaggle](https://www.kaggle.com/). No entanto, as imagens encontradas não apresentam danos suficientes 
que justificam reparo. Por esse motivo, optou-se por uma etapa de pré-processamento das imagens, na qual será inserido um efeito de degradação 
nas imagens com o intuito de simular uma PSF (Point Spread Function), isto é , uma função de degradação, proveniente de acidentes que podem 
ocorrer na realidade, utilizando filtros de blur.

Algoritmo de pré-processamento: < COLOCAR LINK DO PROGRAMA AQUI>

Exemplos de imagens pré-processadas: <COLOCAR IMAGENS ANTES E DEPOIS DO PRÉ-PROCESSAMENTO AQUI>


Após o pré-processamento, as imagens serão enviadas de fato ao algoritmo que efetuará o processo de restauração.



[Yu A Bunyak, O Yu Sofina and R N Kvetnyy 2012 Blind PSF estimation and methods of deconvolution optimization](https://arxiv.org/ftp/arxiv/papers/1206/1206.3594.pdf)

## Código inicial
