# 2021.1-CienciaDeDadosEmSaude_IA368X-MO826A-CX002A
Disciplina de Ciência e Visualização de Dados em Saúde (2021.1)

UNICAMP - Universidade Estadual de Campinas

FEEC, IC e FCM

# Projeto: Comparação Radiômica x Radiológica na Detecção e Localização de LHF em RM Morfofuncional

## Apresentação 
O presente projeto foi originado no contexto das atividades da disciplina de pós-graduação [*Ciência e Visualização de Dados em Saúde*](https://github.com/datasci4health/home), oferecida no primeiro semestre de 2021, na Unicamp.

> |Nome  | RA | Especialização|
> |--|--|--|
> | Daniel Alvarenga Fernandes | 190943  | Saúde / FCM |
> | [Giovane William de Souza Gomes](https://github.com/giovanewsgomes)  | 093801  | Computação / FEEC |
> | [Guilherme Paulino](https://github.com/paulinog) | 117119  | Computação / FEEC |
> | [Stephane de Freitas Schwarz](https://github.com/stephanefschwarz) | 211518  | Computação / IC |

## Descrição Resumida do Projeto
> Descrição do tema do projeto, incluindo motivação e contexto gerador.
> 
> Link para vídeo de apresentação da proposta do projeto (máximo 3 minutos).

## Perguntas de Pesquisa
> Perguntas de pesquisa que o projeto pretende responder ou hipóteses a serem avaliadas, enunciadas de maneira objetiva e verificável.

## Bases de Dados

A base de dados adotada para realização desse trabalho contém imagens <2D e 3D?> de ressonância magnética multifásica com contraste, obtidas no <local de coleta|HC?>, entre o período de <INICIO> e <FIM>. Foram coletadas amostras de N pacientes, sendo X diagnosticados com carcinoma hepatocelular (HCC) e Y controles. <O critério para inclusão dos pacientes ao grupo de controle são adultos que não possuem HCC, entretanto podem apresentar outras patologias hepáticas|PODE?>.

As amostras foram manualmente anotadas por especialistas clínicos, para denotar a região onde foram identificados traços que salientam a presenta da lesão.

<EXPLICAR: Como é feito o processo de aquisição das HCC?>


## Metodologia

Nosso principal objetivo é desenvolver uma solução capaz de classificar a presença de carcinoma no fígado, a partir de imagens de ressonância magnética, e localizar a região da lesão. Nessa linha, inicialmente iremos explorar o método desenvolvido por Bousabarah et al. [[1]](#referencias), os quais utilizaram a rede U-Net para classificação e delimitação de carcinoma hepatocelular mediante decomposição de amostras de ressonância magnética multifásica.

Essa arquitetura é composta por dois componentes principais, um codificador e um decodificador. A função do codificador é extrair características de complexidade crescente e criar uma representação de baixo nível da imagem. O decodificador, por sua vez, é responsável por reconstruir o mapa de características da representação correspondente. Os autores mostraram que tal método reduz resultados competitivos para segmentação e classificação de regiões comprometidas do fígado.

Além disso, fizemos uma breve revisão na literatura e identificamos trabalhos que nos ajudarão durante o desenvolvimento do presente trabalho.

Hamm et al. desenvolveram um método para classificação de lesões baseando-se em redes convolucionais. Para isso, os autores propuseram uma topologia de rede que empilha níveis que combinam operações em camadas totalmente conectadas, convolução e pooling.

    

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
