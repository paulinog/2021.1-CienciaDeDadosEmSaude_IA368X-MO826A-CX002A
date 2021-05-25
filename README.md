# 2021.1-CienciaDeDadosEmSaude_IA368X-MO826A-CX002A
Disciplina de Ciência e Visualização de Dados em Saúde (2021.1)

UNICAMP - Universidade Estadual de Campinas

FEEC, IC e FCM

PREDIÇÃO DE INVASÃO MICROVASCULAR DO CARCINOMA HEPATOCELULAR PRÉ- RESSECÇÃO OU TRANSPLANTE HEPÁTICO UTILIZANDO-SE DADOS CLÍNICO-LABORATORIAIS E DE TOMOGRAFIA COMPUTADORIZADA TRIFÁSICA
## Apresentação
 
O presente projeto foi originado no contexto das atividades da disciplina de pós-graduação [*Ciência e Visualização de Dados em Saúde*](https://github.com/datasci4health/home), oferecida no primeiro semestre de 2021, na Unicamp.

|Nome  | RA | Especialização|
|--|--|--|
| [Daniel Alvarenga Fernandes](https://github.com/danielalvarengafernandes) | 190943  | Saúde / FCM |
| [Giovane William de Souza Gomes](https://github.com/giovanewsgomes)  | 093801  | Computação / FEEC |
| [Guilherme Paulino](https://github.com/paulinog) | 117119  | Computação / FEEC |
| [Stephane de Freitas Schwarz](https://github.com/stephanefschwarz) | 211518  | Computação / IC |

## Descrição Resumida do Projeto

O carcinoma hepatocelular (CHC) é o tumor primário hepático mais comum e a principal causa de morte em pacientes cirróticos1. O diagnóstico definitivo do CHC pode ser estabelecido apenas através de estudos de imagem, reservando-se a análise histopatológica somente para lesões indeterminadas, prática que tem sido adotada por diretrizes em todo o mundo desde 20012 (1-7). 
A ressecção cirúrgica e o transplante hepático são importantes tratamentos curativos disponíveis para o CHC, mas a taxa de recorrência para ambos permanece elevada. A taxa de recorrência em cinco anos do CHC é de aproximadamente 70% nos casos de ressecção hepática e 25% nos casos de transplante hepático8. Um dos fatores mais importantes que explica a recorrência é a invasão microvascular (IMV), definida pela invasão de células tumorais em um espaço vascular revestido por endotélio, incluindo vasos microscópicos da veia porta, artéria hepática e vasos linfáticos, não sendo detectada na avaliação médica radiológica na rotina de trabalho8. A IMV foi descrita como o mais forte preditor independente de sobrevida livre de recorrência9, 10 e de mau prognóstico após ressecção hepática parcial ou transplante hepático em pacientes com CHC dentro dos critérios de Milão11-13. Assim, predizer IMV no pré-operatório poderia permitir uma seleção mais adequada de pacientes para cada terapêutica. Além disso, se a ressecção hepática for considerada para pacientes com alto risco de invasão microvascular, por exemplo, um procedimento com ampla margem de ressecção pode ser preferível14.  
No entanto, a IMV atualmente só é diagnosticada na rotina após ressecção cirúrgica ou transplante hepático, através da avaliação histopatológica. No conhecimento atual, é desafiador diagnosticar IMV através de exames pré-operatórios14-16. Deste modo, há uma necessidade de um meio quantitativo de previsão de IMV no pré-operatório, preferencialmente através de uma modalidade de diagnóstico por imagem que seja realizada rotineiramente nos pacientes que serão submetidos s ressecção ou transplante hepático, como a Tomografia Computadorizada (TC) contrastada trifásica. Neste contexto, surge a radiômica. A radiômica consiste em um campo emergente na análise de imagens que através da extração de grande quantidade de características de dados de imagens médicas, habitualmente não observadas ao olho humano nú- pode vir a refletir o tecido biológico subjacente17.  Busca-se então, identificar e validar novos parâmetros pré-operatórios que funcionem como “biomarcadores radiológicos”, indicando a agressividade do CHC como preditor prognóstico pré-operatório através da IMV. 


## Perguntas de Pesquisa

- É possível predizer IMV do CHC no pré-operatório utilizando-se dados clínico-laboratoriais e de tomografia computadorizada (TC) trifásica? 

## Bases de Dados - Descrição do processo de aquisição


O referido estudo foi aprovado pela Comissão de Ética institucional. Foram respeitadas as condições éticas pertinentes ao protocolo e seguidos rigorosamente os princípios enunciados na Declaração de Helsinque e do Ministério da Saúde do Brasil para pesquisa em seres humanos. A amostra analisada será realizada retrospectivamente em 200 nódulos (125 pacientes submetidos a transplante hepático e/ ou ressecção hepática) que tiveram confirmação histológica diagnóstica de CHC. 
Critérios de exclusão: Pacientes que não tinham TC com parâmetros técnicos adequados para análise de lesões focais hepáticas. 
- Pacientes cujas localizações das lesões focais hepáticas identificadas na TC não tinham correspondência exata com as localizações das lesões descritas nos estudos anatomopatológicos.
- Nódulos com diagnóstico anatomopatológico de hepatocolangiocarcinoma.
Tomografia computadorizada – técnica
Todos os exames de TC realizados incluídos na amostra contemplaram minuciosamente critérios técnicos de qualidade das imagens. Foram realizados em aparelho com 64 canais de detectores, nas fases pré-contraste, arterial, portal e equilíbrio do fígado (estudo dinâmico). Foram utilizados 120 ml (ou volume menor – 100 ml - em pacientes com menos de 70 kg) de meio de contraste venoso iodado através de bomba injetora com fluxo de 4-5 ml/s, seguido de injeção de 40 ml de solução salina a 0,9%. Não foi utilizado meio de contraste via oral ou via retal. Foram adquiridas imagens nas seguintes fases do meio de contraste:
- fase pré-contraste: obtidas imediatamente antes da injeção do meio de contraste venoso;
- fase arterial: obtidas por detecção automática, em até 15 segundos após o pico de concentração de contraste da aorta abdominal;
- fase portal: obtidas entre 60 e 80 segundos após o início da injeção do meio de contraste venoso;
- fase de equilíbrio: obtidas cerca de 180 segundos após o início da injeção do meio de contraste venoso.
Foram analisadas as imagens dos cortes axiais das TCs, reconstruídas com 3mm de espessura, de todas as fases do estudo dinâmico com meio de contraste venoso da TC.
	Dados clínico-laboratoriais e tomográficos foram avaliados, a saber: 
-Idade (anos)
- Sexo do paciente
- Diâmetro máximo do tumor
- Fígado subjacente (cirrótico/ não cirrótico)
- Tipo de hepatopatia subjacente/ etiologia
- HBsAg- negativo ou positivo
- Grau patológico
- Alfafetopreoteína, mediana (IQR)
- Localização do nódulo (lobo esquerdo, lobo direito, lobo caudado);
- atenuação média do nódulo nas fases dinâmicas do exame tomográfico;
- Presença ou ausência de invasão microvascular histopatológica; 
Parâmetros quantitativos de hipervascularização arterial e lavagem do contraste dos carcinomas foram calculados. “Regiões de Interesse” (ROIs) foram circuladas manualmente nas lesões e em duas regiões de parênquima do fígado adjacente aos CHCs, nas imagens pré-contraste e nas fases arterial, portal e equilíbrio após a injeção do meio de contraste. 

 
Figura 01: Carcinoma hepatocelular. Cortes axiais de TC pré-contraste (a) e nas fases arterial (b), portal (c) e de equilíbrio (d) com as ROIs posicionadas no nódulo e no parênquima adjacente.

Em nódulos heterogêneos, a área com hipervascularização arterial mais intensa foi considerada para análise, com medidas nas localizações correspondentes das demais fases. Houve cuidado para evitar vasos intratumorais, ductos biliares e artefatos.
Subsequentemente, os seguintes parâmetros quantitativos foram calculados, baseados nas relações dos valores extraídos com as medidas objetivas de densidades:
- Diferença de atenuação (DA): diferença entre a atenuação da lesão e a média da atenuação do parênquima adjacente; foi calculada em todas as fases do estudo dinâmico (arterial, portal e equilíbrio).
- Razão de atenuação (RA) na fase portal - RAP: RAP =100×(AMP /ALP), onde P = fase portal, AM = atenuação média do parênquima e AL = atenuação da lesão;
- Razão de atenuação (RA) na fase de equilíbrio - RAE: ERA =100×(AME /ALE), onde E = fase de equilíbrio, AM = atenuação média do parênquima e AL = atenuação da lesão;
- Razão de “washout” relativo (RWR) na fase portal - RWRP: RWRP =100× (ALA − ALP) / ALA, onde A = fase arterial, P = fase portal e AL = atenuação da lesão;
- Razão de “washout” relativo (RWR) na fase de equilíbrio - RWRE: RWRE =100× (ALA − ALE) / ALA, onde A= fase arterial, E = fase de equilíbrio e AL = atenuação da lesão;
Estes parâmetros quantitativos do exame de tomografia computadorizada foram comparados com a presença ou ausência de invasão microvascular confirmados anatomopatologicamente. 



## Metodologia


Nesse projeto adotaremos a metodologia CRISP-DM. 

## Bases de Dados e Evolução

Nesse projeto exploramos apenas uma base de dados. Contudo, esta se divide em dois grupos de dados. No primeiro conjunto foram exploradas informações tabulares clínicas e laboratoriais de pacientes com lesões no fígado e relacionadas ao exame realizado nos sujeitos. No segundo conjunto de dados, realizamos uma investigação inicial nas imagens de tomografia computadorizada extraídas dos pacientes em questão.

A base é constituída por 200 lesões de 125 indivíduos. Assim, existem pacientes com lesão que se estende por mais de um segmento do fígado. A abordagem de classificar a lesão por regiões é fundamental visto que intervenções cirúrgicas podem ser adotadas para remover apenas a parte lesada, sem a necessidade de remoção da peça inteira.

### Bases Estudadas, mas Não Adotadas

Base de Dados | Endereço na Web | Resumo descritivo
----- | ----- | -----
Dados clínicos de TC | Domínio privado | Essa base de dados é composta por dados clínicos e laboratoriais de pacientes com lesões hepatocelulares.

O primeiro conjunto de dados explorados consiste em uma tabela com informações clínicas e laboratoriais de pacientes com lesão hepática. Contém 26 características que variam desde o identificador dos pacientes e localização do nódulo até a causa e grau histológico da hepatopatia. A descrição completa de cada uma das features presentes nessa base de dados pode ser encontrada [aqui](https://github.com/paulinog/2021.1-CienciaDeDadosEmSaude_IA368X-MO826A-CX002A/tree/main/data)

Das 26 características descritas na base de dados, 4 delas estavam completamente nulas, para todos os pacientes e nódulos listados. Essas quatro variáveis estão associadas a dados de exame alfafetoproteína, da recorrência do câncer hepático e se houve algum caso de morte desde o início da investigação.

Além dessas colunas com dados faltantes, 40 outros valores não estavam presentes na base. 39 dados referentes a data de nascimento dos pacientes e 1 relacionado a localização da lesão. Considerando a importância dessas informações, não realizamos nenhuma estratégia para substituição dos dados faltantes. Porém, dado que não é possível determinar se há ou não a presença de carcinoma hepático levando em consideração a idade do indivíduo, apenas ignoramos a ausência desses valores. Entrementes, a localização da lesão é fundamental para a identificação de invasão microvascular, nessa linha, para a amostra onde a informação de localização da lesão não foi passada, descartamos o dado.

Existem 4 features categorias que descrevem o grau histológico, o sexo, a presença de invasão microvascular e a causa da hepatopatia. Realizamos a transformação manualmente apenas para fins de aprendizagem. 

Verificamos que a maioria dos casos de hepatopatia celular foram causados pelo Vírus da Hepatite C (VHC), sendo majoritariamente pessoas do sexo masculino. 

Realizamos um estudo da correlação das features e chegamos a resultados equivalentes usando tanto a técnica de pearson e quanto a de spearmam. Analisando os dados de correlação, notamos que nenhuma característica está fortemente ou moderadamente associada a presença de invasão microvascular. Como ilustrado nas matrizes de correlação abaixo.


<p float="left">
  <img src="/assets/initial_exploration_imgs/pearson_corr.png" width="500" />
  <img src="/assets/initial_exploration_imgs/spearman_corr.png" width="500" /> 
</p>

Essa característica já havia sido descrita em alguns trabalhos da literatura médico científica. Nossa investigação inicial alcançou resultados condizentes com os descritos em trabalhos anteriores.

Abaixo mostramos alguns gráficos de histogramas de algumas features presentes na base de dados. 

Através desses gráficos, é possível notar que a maior parte das lesões são pequenas. Não é possível, por outro lado, dizer se a presença de invasão microvascular está ligada majoritariamente a lesões pequenas, visto que existem poucas grandes lesões descritas nesse conjunto.

A fração de contraste arterial (AEF), também não aparenta ter nenhuma correlação com a identificação de invasão microvascular.

Nos gráficos abaixo mostramos a distribuição dos dados, rotulados com a informação de presença ou ausência de invasão microvascular. A base de dados é ligeiramente desbalanceada, mas iremos lidar com isso através de técnicas de normalização por batch ou ponderando as classes.

<p float="left">
  <img src="/assets/initial_exploration_imgs/2.png" width="250" />
  <img src="/assets/initial_exploration_imgs/3.png" width="250" /> 
  <img src="/assets/initial_exploration_imgs/4.png" width="250" /> 
  <img src="/assets/initial_exploration_imgs/5.png" width="250" /> 
  <img src="/assets/initial_exploration_imgs/6.png" width="250" /> 
  <img src="/assets/initial_exploration_imgs/7.png" width="250" /> 
  <img src="/assets/initial_exploration_imgs/8.png" width="250" /> 
  <img src="/assets/initial_exploration_imgs/9.png" width="250" /> 
  <img src="/assets/initial_exploration_imgs/10.png" width="250" /> 
</p>

Abaixo mais um gráfico onde confrontamos todas as features com todas. Embora algumas sigam uma distribuição normal ou linear, nenhuma está correlacionada a presenta da invasão microvascular. Essa característica sugere que não é possível, a partir desses dados, inferir a probabilidade de um paciente conter ou não invasão microvascular, reforçando a ideia original de que para identificar a presença ou a probabilidade de uma invasão microvascular, devemos considerar principalmente durante a análise o exame tomográfico realizado.

<p float="center">
  <img src="/assets/initial_exploration_imgs/all.png" />
</p>


Os dados mostraram que em geral, a invasão microvascular está localizada na região 8 do fígado, identificamos 35 casos. Seguido pela região 7, com 21 casos registrados e a região 6, com 19 ocorrências. Todas essas regiões estão no lobo direito do fígado. Na imagem abaixo mostramos uma imagem com as segmentações e nomenclaturas de cada segmento do fígado.

<p float="center">
  <img src="/assets/initial_exploration_imgs/liver_segments.jpg" />
</p>

O relatório completo gerado para cada uma das features presentes nesse conjunto de dados pode ser encontrado na pasta [assets](https://github.com/paulinog/2021.1-CienciaDeDadosEmSaude_IA368X-MO826A-CX002A/blob/main/assets/initial_exploration_imgs/profiling.html).

### Bases Estudadas e Adotadas

Base de Dados | Endereço na Web | Resumo descritivo
----- | ----- | -----
Imagens de TC | Domínio privado | Essa base de dados é composta por imagens de tomografia computadorizada de pacientes com lesões hepatocelulares.

Além dos dados tabulares com informações diversas dos paciente e exames clínicos e laboratoriais realizados, investigamos algumas características relacionadas a dados de imagens de tomografia computadorizada. Notamos que nas três fases que iremos explorar, existe uma disparidade com relação a quantidade de frames por exame. 

Na tabela abaixo mostramos as características gerais da base. É possível notar que para alguns pacientes, existem apenas dois frames ligados ao exame TC. Sendo que na média, esse número é significativamente superior, aproximadamente 100 imagens por fase. 


|       |       s1 |      s2 |       s3 |
|:------|---------:|--------:|---------:|
| count | 127      | 127     | 127      |
| mean  |  98.1102 | 131.827 | 175.024  |
| std   |  96.7247 |  70.369 |  60.1046 |
| min   |   2      |   1     |   1      |
| 25%   |   2      |  91     | 143      |
| 50%   |  88      | 113     | 161      |
| 75%   | 124.5    | 152.5   | 224.5    |
| max   | 348      | 489     | 349      |



## Próximos passos

Para as próximas semanas, iremos iniciar uma investigação mais profunda considerando as imagens. Nosso principal objetivo será explorar métodos para identificação de invasão microvascular através de imagens de tomografia computadorizada. 


## Ferramentas

Ferramenta | Função
----- | -----
[Python 3](https://www.python.org/) | Linguagem de programação a ser utilizada para o desenvolvimento das soluções propostas.
[Pytorch](https://pytorch.org) | Arcabouço de código aberto para desenvolvimento de modelos de aprendizagem de máquina e aprendizagem profunda.
[Pandas](https://pandas.pydata.org/) | Ferramenta para manipulação e análise de dados.
[Numpy](https://numpy.org/) | Biblioteca utilizada para manipulação de vetores multidimensionais.
[Matplotlib](https://matplotlib.org/) | Biblioteca para visualização dos dados.

## Cronograma

O cronograma foi proposto de acordo com as etapas da metodologia CRISP-DM.

```text
+---------------------------+-----------------------------------------------+-----------+-----------+
|                           |                     Meses                     |           |           |
|                           +-----------------------+-----------------------+-----------+-----------+
|          Tarefas          |         Abril         |          Maio         |         Junho         |
|                           +-----------+-----------+-----------+-----------+-----------+-----------+
|                           | 1° quinz. | 2° quinz. | 1° quinz. | 2° quinz. | 1° quinz. | 2° quinz. |
+---------------------------+-----------+-----------+-----------+-----------+-----------+-----------+
| Definir escopo do projeto |    [x]    |           |           |           |           |           |
+---------------------------+-----------+-----------+-----------+-----------+-----------+-----------+
| Plano inicial de pesquisa |    [x]    |    [x]    |           |           |           |           |
+---------------------------+-----------+-----------+-----------+-----------+-----------+-----------+
| Compreensão dos dados     |           |    [x]    |    [x]    |           |           |           |
+---------------------------+-----------+-----------+-----------+-----------+-----------+-----------+
| Processamento dos dados   |           |           |    [x]    |    [x]    |           |           |
+---------------------------+-----------+-----------+-----------+-----------+-----------+-----------+
| Modelar a solução         |           |           |           |    [x]    |    [x]    |           |
+---------------------------+-----------+-----------+-----------+-----------+-----------+-----------+
| Avaliar                   |           |           |           |           |    [x]    |           |
+---------------------------+-----------+-----------+-----------+-----------+-----------+-----------+
| Definir próximos passos   |           |           |           |           |    [x]    |    [x]    |
+---------------------------+-----------+-----------+-----------+-----------+-----------+-----------+
| Desenvolver Relatório     |           |    [x]    |    [x]    |    [x]    |    [x]    |    [x]    |
+---------------------------+-----------+-----------+-----------+-----------+-----------+-----------+
```

# Referências

1. Yokoo T, Wolfson T, Iwaisako K, Peterson MR, Mani H, Goodman Z, Changchien C, Middleton MS, Gamst AC, Mazhar SM, Kono Y, Ho SB, Sirlin CB. Evaluation of Liver Fibrosis Using Texture Analysis on Combined-Contrast-Enhanced Magnetic Resonance Images at 3.0T. Biomed Res Int 2015;2015:387653.

2. Mu W, Chen Z, Liang Y, Shen W, Yang F, Dai R, Wu N, Tian J. Staging of cervical cancer based on tumor heterogeneity characterized by texture features on 18F-FDG PET images. Phys Med Biol 2015;60:5123-39.

3. Cui Y, Tha KK, Terasaka S, Yamaguchi S, Wang J, Kudo K, Xing L, Shirato H, Li R. Prognostic imaging biomarkers in glioblastoma: development and independent validation on the basis of multiregion and quantitative analysis of MR images. Radiology 2016;278:546-53.

4. Huynh E, Coroller TP, Narayan V, Agrawal V, Romano J, Franco I, Parmar C, Hou Y, Mak RH, Aerts HJ. Associations of radiomic data extracted from static and respiratory-gated CT scans with disease recurrence in lung cancer patients treated with SBRT. PLoS One 2017;12:e0169172.

5. Mazzei MA, Nardone V, Di Giacomo L, Bagnacci G, Gentili F, Tini P, Marrelli D. The role of delta radiomics in gastric cancer. Quant Imaging Med Surg 2018;8:719-21.

6. O’Connor JP, Aboagye EO, Adams JE, Aerts HJ, Barrington SF, Beer AJ, Boellaard R, Bohndiek SE, Brady M, Brown G. Imaging biomarker roadmap for cancer studies. Nat Rev Clin Oncol 2017;14:169-86.

7. Yip SS, Aerts H. Applications and limitations of radiomics. Phys Med Biol 2016;61:R150-66.

8. Velazquez ER, Parmar C, Jermoumi M, Mak RH, Van Baardwijk A, Fennessy FM, Lewis JH, De Ruysscher D, Kikinis R, Lambin P. Volumetric CT-based segmentation of NSCLC using 3D-Slicer. Sci Rep 2013;3:3529.

9. Parmar C, Velazquez ER, Leijenaar R, Jermoumi M, Carvalho S, Mak RH, Mitra S, Shankar BU, Kikinis RHaibe-Kains B. Robust radiomics feature quantification using semiautomatic volumetric segmentation. PLoS one 2014;9:e102107. Brasil. Ministério da Saúde. Conselho Nacional de Saúde. Resolução nº 466/2012 sobre diretrizes e normas regulamentadoras de pesquisas envolvendo seres humanos. Disponível em:\<[http://conselho.saude.gov.br/resolucoes/2012/Reso466.pdf](http://conselho.saude.gov.br/resolucoes/2012/Reso466.pdf)\>. Acesso em: 14 jan. 2018.

10. Brasil. Ministério da Saúde. Conselho Nacional de Saúde. Resolução nº 510/2016 sobre diretrizes e normas regulamentadoras de pesquisas envolvendo seres humanos. Disponível em: \<[http://conselho.saude.gov.br/resolucoes/2016/reso510.pdf](http://conselho.saude.gov.br/resolucoes/2016/reso510.pdf)\>. Acesso em: 17 out. 2018.

11. Bousabarah, K., Letzen, B., Tefera, J., Savic, L., Schobert, I., Schlachter, T., Staib, L.H., Kocher, M., Chapiro, J. and Lin, M., 2020. Automated detection and delineation of hepatocellular carcinoma on multiphasic contrast-enhanced MRI using deep learning. Abdominal Radiology, pp.1-10.

12. Hamm, C.A., Wang, C.J., Savic, L.J., Ferrante, M., Schobert, I., Schlachter, T., Lin, M., Duncan, J.S., Weinreb, J.C., Chapiro, J. and Letzen, B., 2019. Deep learning for liver tumor diagnosis part I: development of a convolutional neural network classifier for multi-phasic MRI. European radiology, 29(7), pp.3338-3347.

# Estrutura do Repositório

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.readthedocs.io


---

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
