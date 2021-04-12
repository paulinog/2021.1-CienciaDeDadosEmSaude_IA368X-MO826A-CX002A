# 2021.1-CienciaDeDadosEmSaude_IA368X-MO826A-CX002A
Disciplina de Ciência e Visualização de Dados em Saúde (2021.1)

UNICAMP - Universidade Estadual de Campinas

FEEC, IC e FCM

# Projeto: Detecção e Delineamento Automático de Lesões Hepáticas Focais Benignas e Malignas em Ressonância Magnética com Contraste Hepatoespecífico Utilizando Deep Learning

## Apresentação 
O presente projeto foi originado no contexto das atividades da disciplina de pós-graduação [*Ciência e Visualização de Dados em Saúde*](https://github.com/datasci4health/home), oferecida no primeiro semestre de 2021, na Unicamp.

|Nome  | RA | Especialização|
|--|--|--|
| Daniel Alvarenga Fernandes | 190943  | Saúde / FCM |
| [Giovane William de Souza Gomes](https://github.com/giovanewsgomes)  | 093801  | Computação / FEEC |
| [Guilherme Paulino](https://github.com/paulinog) | 117119  | Computação / FEEC |
| [Stephane de Freitas Schwarz](https://github.com/stephanefschwarz) | 211518  | Computação / IC |

## Descrição Resumida do Projeto
Diferentes características radiômicas têm sido estudadas e estão associadas à histologia tumoral (1), estágio da lesão (2), sobrevida do paciente (3), metabolismo (4), além de muitos outros desfechos clínicos adicionais (5). Recentemente, um grupo de especialistas do Cancer Research UK (CRUK) e da Organização Europeia para Pesquisa e Tratamento do Câncer (EORTC) produziu 14 recomendações principais para acelerar a translação clínica da radiômica (6). Dentre estas, duas das recomendações foram a padronização dos biomarcadores de imagem e a revisão contínua da sua precisão (6). 

Na busca da padronização nos biomarcadores imaginológicos, a segmentação do tumor é a mais crítica e um componente contencioso da radiômica já que as análises de dados de recursos subsequentes dependem dos resultados da segmentação do tumor (7,8). Como método rotineiro de segmentação na clínica, o delineamento manual demanda mais tempo e pode estar propensa a maior variabilidade devido às fronteiras indistintas de muitos tumores. Abordagens semiautomáticas são mais rápidas e podem vir a reduzir a variabilidade interobservador, podendo contribuir, em análise subsequente, para melhoria da reprodutibilidade dos biomarcadores de imagem e da precisão dos dados de imagens médicas (8,9).  

No contexto exposto, o objetivo deste estudo é desenvolver um algoritmo de deep learning para segmentação hepática, detecção e delineamento automático de diferentes lesões hepáticas focais (LHF) benignas e malignas em ressonância magnética (RM) com o contraste hepatoespecífico, buscando-se assim fornecer uma contribuição inicial na busca da padronização dos recursos radiômicos. Tal algoritmo pode também facilitar a dinâmica do fluxo da rotina médica radiológica na emissão de laudos incluindo a produtividade em exames de RM em Medicina Interna/ Abdome. 

> Link para vídeo de apresentação da proposta do projeto (máximo 3 minutos).

## Perguntas de Pesquisa

- Como algoritmos de Deep Learning podem ser usados para contribuir na detecção de lesões em imagens para diagnóstico.
- Avaliar a viabilidade de um algoritmo de deep learning treinado para segmentar o fígado e delinear automaticamente LHF em exames de RM. 
- Comparar a rede de detecção e delineamento automático de LHF em exames de RM com o método “padrão de referência” consensual entre dois radiologistas experientes em radiologia abdominal. 

## Bases de Dados

A base de dados adotada para realização desse trabalho contém imagens <2D e 3D?> de ressonância magnética multifásica com contraste, obtidas no <local de coleta|HC?>, entre o período de <INICIO> e <FIM>. Foram coletadas amostras de N pacientes, sendo X diagnosticados com carcinoma hepatocelular (HCC) e Y controles. <O critério para inclusão dos pacientes ao grupo de controle são adultos que não possuem HCC, entretanto podem apresentar outras patologias hepáticas|PODE?>.

As amostras foram manualmente anotadas por especialistas clínicos, para denotar a região onde foram identificados traços que salientam a presenta da lesão.

<EXPLICAR: Como é feito o processo de aquisição das HCC?>


## Metodologia

Nosso principal objetivo é desenvolver uma solução capaz de classificar a presença de carcinoma no fígado, a partir de imagens de ressonância magnética, e localizar a região da lesão. Nessa linha, inicialmente iremos explorar o método desenvolvido por Bousabarah et al. [[1]](#referências), os quais utilizaram a rede U-Net para classificação e delimitação de carcinoma hepatocelular mediante decomposição de amostras de ressonância magnética multifásica.

Essa arquitetura é composta por dois componentes principais, um codificador e um decodificador. A função do codificador é extrair características de complexidade crescente e criar uma representação de baixo nível da imagem. O decodificador, por sua vez, é responsável por reconstruir o mapa de características da representação correspondente. Os autores mostraram que tal método reduz resultados competitivos para segmentação e classificação de regiões comprometidas do fígado.

Além disso, fizemos uma breve revisão na literatura e identificamos trabalhos que nos ajudarão durante o desenvolvimento do presente trabalho.

Hamm et al. [[2]](#referências) desenvolveram um método para classificação de lesões baseando-se em redes convolucionais. Para isso, os autores propuseram uma topologia de rede que empilha níveis que combinam operações em camadas totalmente conectadas, convolução e pooling.

    

Nesse projeto adotaremos a metodologia CRISP-DM. 

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

9. Parmar C, Velazquez ER, Leijenaar R, Jermoumi M, Carvalho S, Mak RH, Mitra S, Shankar BU, Kikinis RHaibe-Kains B. Robust radiomics feature quantification using semiautomatic volumetric segmentation. PLoS one 2014;9:e102107. Brasil. Ministério da Saúde. Conselho Nacional de Saúde. Resolução nº 466/2012 sobre diretrizes e normas regulamentadoras de pesquisas envolvendo seres humanos. Disponível em:<http://conselho.saude.gov.br/resolucoes/2012/Reso466.pdf>. Acesso em: 14 jan. 2018.

10. Brasil. Ministério da Saúde. Conselho Nacional de Saúde. Resolução nº 510/2016 sobre diretrizes e normas regulamentadoras de pesquisas envolvendo seres humanos. Disponível em:< http://conselho.saude.gov.br/resolucoes/2016/reso510.pdf >. Acesso em: 17 out. 2018.

[1] Bousabarah, K., Letzen, B., Tefera, J., Savic, L., Schobert, I., Schlachter, T., Staib, L.H., Kocher, M., Chapiro, J. and Lin, M., 2020. Automated detection and delineation of hepatocellular carcinoma on multiphasic contrast-enhanced MRI using deep learning. Abdominal Radiology, pp.1-10.

[2] Hamm, C.A., Wang, C.J., Savic, L.J., Ferrante, M., Schobert, I., Schlachter, T., Lin, M., Duncan, J.S., Weinreb, J.C., Chapiro, J. and Letzen, B., 2019. Deep learning for liver tumor diagnosis part I: development of a convolutional neural network classifier for multi-phasic MRI. European radiology, 29(7), pp.3338-3347.

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
