# 2021.1-CienciaDeDadosEmSaude_IA368X-MO826A-CX002A
Disciplina de Ciência e Visualização de Dados em Saúde (2021.1)

UNICAMP - Universidade Estadual de Campinas

FEEC, IC e FCM

# Projeto: Detecção e Delineamento Automático de Lesões Hepáticas Focais Benignas e Malignas em Ressonância Magnética com Contraste Hepatoespecífico Utilizando Deep Learning

## Apresentação 
O presente projeto foi originado no contexto das atividades da disciplina de pós-graduação [*Ciência e Visualização de Dados em Saúde*](https://github.com/datasci4health/home), oferecida no primeiro semestre de 2021, na Unicamp.

|Nome  | RA | Especialização|
|--|--|--|
| [Daniel Alvarenga Fernandes](https://github.com/danielalvarengafernandes) | 190943  | Saúde / FCM |
| [Giovane William de Souza Gomes](https://github.com/giovanewsgomes)  | 093801  | Computação / FEEC |
| [Guilherme Paulino](https://github.com/paulinog) | 117119  | Computação / FEEC |
| [Stephane de Freitas Schwarz](https://github.com/stephanefschwarz) | 211518  | Computação / IC |

## Descrição Resumida do Projeto

Diferentes características radiômicas têm sido estudadas e estão associadas à histologia tumoral [(1)](#referências), estágio da lesão [(2)](#referências), sobrevida do paciente [(3)](#referências), metabolismo [(4)](#referências), além de muitos outros desfechos clínicos adicionais [(5)](#referências). Recentemente, um grupo de especialistas do Cancer Research UK (CRUK) e da Organização Europeia para Pesquisa e Tratamento do Câncer (EORTC) produziu 14 recomendações principais para acelerar a translação clínica da radiômica [(6)](#referências). Dentre estas, duas das recomendações foram a padronização dos biomarcadores de imagem e a revisão contínua da sua precisão [(6)](#referências). 

Na busca da padronização nos biomarcadores imaginológicos, a segmentação do tumor é a mais crítica e um componente contencioso da radiômica já que as análises de dados de recursos subsequentes dependem dos resultados da segmentação do tumor [(7,8)](#referências). Como método rotineiro de segmentação na clínica, o delineamento manual demanda mais tempo e pode estar propensa a maior variabilidade devido às fronteiras indistintas de muitos tumores. Abordagens semiautomáticas são mais rápidas e podem vir a reduzir a variabilidade interobservador, podendo contribuir, em análise subsequente, para melhoria da reprodutibilidade dos biomarcadores de imagem e da precisão dos dados de imagens médicas [(8,9)](#referências).  

No contexto exposto, o objetivo deste estudo é desenvolver um algoritmo de deep learning para segmentação hepática, detecção e delineamento automático de diferentes lesões hepáticas focais (LHF) benignas e malignas em ressonância magnética (RM) com o contraste hepatoespecífico, buscando-se assim fornecer uma contribuição inicial na busca da padronização dos recursos radiômicos. Tal algoritmo pode também facilitar a dinâmica do fluxo da rotina médica radiológica na emissão de laudos incluindo a produtividade em exames de RM em Medicina Interna/ Abdome. 

> https://drive.google.com/file/d/1RCdJ5aXSi8bzHtpRaHbQ-o3KIrWn5OPz/view?usp=sharing

## Perguntas de Pesquisa

- É possível identificar a presença de lesões no fígado por meio de imagens de tomografia computadorizadas?

- É possível identificar traços de invasão microvascular através de dados clínicos, laboratoriais e de imagem de tomografia computadorizada?

## Bases de Dados

Projeto com base de dados como parte de trabalho aprovado no Comitê de Ética em Pesquisas Institucional. Foi necessário um termo de compromisso, onde os pesquisadores se comprometeram a zelar pelas informações e assegurar o sigilo e a confidencialidade dos participantes da pesquisa. Nenhum (a) participante terá seu nome revelado publicamente. Foi respeitada assim a Resolução 466/2012 e a Resolução 510/2016 do Conselho Nacional de Saúde que se fundamentam nos principais documentos internacionais sobre pesquisas envolvendo seres humanos [(10)](#referências).

Os exames foram realizados em aparelho de RM 1,5 T (Tesla), com bobina específica; os pacientes realizaram jejum de 06 horas. Foram realizadas sequências sem contraste, ponderadas em T1 em fase e fora de fase e sequências coronais ponderadas em T2. Em seguida, prosseguiu-se estudo dinâmico após injeção do meio de contraste com sequências ponderadas em T1 com saturação de gordura antes e após injeção intravenosa do meio de contraste, com dose de 0,1 mL/kg de peso (equivalente a 0,025 mmol/kg) em bolus, por meio de injetora automática, velocidade de 3 mL/s, seguido de um flush de 20 ml de solução salina na mesma velocidade de infusão.  Após a injeção do ácido gadoxético, obtiveram-se imagens axiais, sequência gradiente eco ponderada em T1 com saturação de gordura, nas fases dinâmicas: fase arterial (15 a 20 segundos após o início da injeção intravenosa), portal (após 60 segundos) e de transição (após 120 segundos); e na fase hepatobiliar (10 e 20 minutos após o início da injeção intravenosa).  Entre a fase de transição e a fase hepatobiliar foram adquiridas imagens ponderadas em T2 com e sem saturação de gordura e sequências ponderadas em difusão.  Os parâmetros técnicos utilizados em cada sequência são mostrados na tabela 1. 

> As amostras foram manualmente anotadas por especialistas clínicos, para denotar a região onde foram identificados traços que salientam a presenta da lesão.

### Tabela 1 – Parâmetros técnicos utilizados nas sequências dos exames de ressonância magnética.

| Parâmetro | T2 | T2 com saturação de gordura | T1 “em fase” e “fora de fase” | Difusão | Imagens ponderadas em T1 sem contraste e após contraste |
|--|--|--|--|--|--|
| Sequência | Fast spin-echo | Fast spin-echo | Gradient-echo FFE\* | EPI\*** | Gradient-echo 3D/TFE\** | 
| Respiração livre | Sim | Sim | Não | Não | Não | 
| Matriz | 268 x 184 | 300 x 261 | 236 x 161 | 152 x150 | 168 x 228 | 
| Espessura (mm) | 6,5 | 7 | 7 | 7 | 2.5 | 
| Espaçamento (Gap) | 1,5 | 1 | 1 | 1 | -- | 
| Ângulo de  giro | 90 | 90 | 80 | 90 | 10 | 
|Campo de visão (AP, LL, CC) | 297x 335 x 222 | 363x 400 x 223 | 353 x 400 x 223 | 380 x 380 x 239 | 295 x 400 x 225 | 
| Tempo de repetição (ms) | 5299 | 1299 | 104 | 2160 | 4.1 | 
| Tempo de eco (ms) | 160 | 80 | 4.6/2.3 | 80 | 2.0 | 
| Tempo de aquisição | 02:48 | 02:24 | 00:21 | 02:57 | 00:15 | 
| Número de excitações | 2 | 2 | 1 | 4 | 1 | 

\* FFE- Fast field echo. 
\** TFE- Turbo field echo. 
\*** EPI- Echo Planar Imaging. 

Dois médicos radiologistas (radiologista A com 5 anos, B com mais de 10 anos de experiência em radiologia abdominal) independentemente avaliaram os exames de imagens  de modo cego quanto a dados clínico e laboratoriais. Os casos discordantes foram discutidos, chegando-se a consenso. 

O critério diagnóstico definitivo das lesões malignas (metástases hepáticas e CHCs) e dos adenomas foi baseado na confirmação anatomopatológica. Os critérios utilizados para o diagnóstico definitivo das demais lesões benignas (HNFs, cistos e hemangiomas) foram a avaliação histopatológica e/ou a ausência de alterações no acompanhamento por imagem (TC ou RM) por dois anos sem tratamento. 

A amostra final de acordo com os critérios utilizados para o diagnóstico definitivo foi de 302 lesões em 136 pacientes que realizaram exames de RM utilizando o ácido gadoxético como contraste na avaliação de LHF, sendo 160 lesões benignas (53,0 %) e 142 malignas (47,0%).  A maioria das 160 lesões benignas era hiperplasia nodular focal (n=90; 56,2%) seguida de cistos (n= 36; 22,5%), hemangiomas (n=22; 13,7 %) e adenomas (n=12; 7,5%).  Das 142 lesões malignas a maioria correspondia à metástase (n=87; 61,3 %), seguida pelos CHCs (n=55; 38,7%).

A quantidade de lesões de acordo com os critérios para o diagnóstico definitivo em cada paciente variou entre 1 e 5 lesões (média 2,4; DP 1,8).  O diâmetro das 160 lesões benignas variou entre 0,4 cm e 8,8 cm (média 2,7 cm; DP 1,9 cm). O diâmetro das 142 lesões malignas variou entre 0,4 cm e 7,8 cm (média 2,1 cm; DP 1,7 cm). Comparativamente, as médias dos diâmetros das lesões benignas foram maiores que as malignas (valor-p=0.0051- EEG- tabela 2).  

### Tabela 2 – Análise descritiva e comparação do tamanho entre tipos de lesão.

| Tamanho da lesão\* | N   |    Média    | DP   |  Mínimo |  Mediana |     Máximo |
|---                | ---  | ---         | ---  | ---     | ---      | ---        |
| Benignas          | 160  |      2,7    | 1,9  |  0,4    |  2,5     |        8,8 |
| Malignas          | 142  |      2,1    | 1,7  |  0,4    |  0,9     |        7,8 |  
|---                | ---  | ---         | ---  | ---     | ---      | ---        |
|                   | N    |    Média    | DP   |  Mínimo |  Mediana |     Máximo |
| Cisto             | 36   |      0,7    | 0,2  |  0,4    |  0,7     |        1,5 |
| Hemangioma        | 22   |      0,7    | 0,2  |  0,4    |  0,7     |        0,9 | 
| HNF               | 90   |      3,7    | 1,4  |  1,4    |  3,5     |        8,8 | 
| Adenoma           | 12   |      4,6    | 0,4  |  4,1    |  4,6     |        5,3 | 
| Metástase         | 87   |      0,9    | 0,5  |  0,4    |  0,8     |        3,2 | 
| CHC               | 55   |      4,0    | 1,3  |  2,1    |  3,8     |        7,8 |

\* valor-p=0.0051 (EEG) lesões benignas maiores que as malignas. 


## Metodologia

Nosso principal objetivo é desenvolver uma solução capaz de detectar LHF a partir de imagens de ressonância magnética, e localizar a região da lesão. Nessa linha, inicialmente iremos explorar o método desenvolvido por Bousabarah et al. [(11)](#referências), os quais utilizaram a rede U-Net para classificação e delimitação de carcinoma hepatocelular mediante decomposição de amostras de ressonância magnética multifásica.

Essa arquitetura é composta por dois componentes principais, um codificador e um decodificador. A função do codificador é extrair características de complexidade crescente e criar uma representação de baixo nível da imagem. O decodificador, por sua vez, é responsável por reconstruir o mapa de características da representação correspondente. Os autores mostraram que tal método reduz resultados competitivos para segmentação e classificação de regiões comprometidas do fígado.

Além disso, fizemos uma breve revisão na literatura e identificamos trabalhos que nos ajudarão durante o desenvolvimento do presente trabalho.

Hamm et al. [(12)](#referências) desenvolveram um método para classificação de lesões baseando-se em redes convolucionais. Para isso, os autores propuseram uma topologia de rede que empilha níveis que combinam operações em camadas totalmente conectadas, convolução e pooling.

Nesse projeto adotaremos a metodologia CRISP-DM. 

## Bases de Dados e Evolução

Nesse projeto exploramos apenas uma base de dados. Contudo, esta se divide em dois grupos de dados. No primeiro conjunto foram exploradas informações tabulares clínicas e laboratoriais de pacientes com lesões no fígado e relacionadas ao exame realizado nos sujeitos. No segundo conjunto de dados, realizamos uma investigação inicial nas imagens de tomografia computadorizada extraídas dos pacientes em questão.

A base é constituída por 200 lesões de 125 indivíduos. Assim, existem pacientes com lesão que se estende por mais de um segmento do fígado. A abordagem de classificar a lesão por regiões é fundamental visto que intervenções cirúrgicas podem ser adotadas para remover apenas a parte lesada, sem a necessidade de remoção da peça inteira.

### Bases Estudadas, mas Não Adotadas

Base de Dados | Endereço na Web | Resumo descritivo
----- | ----- | -----
Dados clínicos de TC | Domínio privado | Essa base de dados é composta por dados clínicos e laboratoriais de pacientes com lesões hepatocelulares.

O primeiro conjunto de dados explorados consiste em uma tabela com informações clínicas e laboratoriais de pacientes com lesão hepática. Contém 26 características que variam desde o identificador dos pacientes e localização do nódulo até a causa e grau histológico da hepatopatia. A descrição completa de cada uma das features presentes nessa base de dados pode ser encontrada [aqui](#https://github.com/paulinog/2021.1-CienciaDeDadosEmSaude_IA368X-MO826A-CX002A/data/README.md)

Das 26 características descritas na base de dados, 4 delas estavam completamente nulas, para todos os pacientes e nódulos listados. Essas quatro variáveis estão associadas a dados de exame alfafetoproteína, da recorrência do câncer hepático e se houve algum caso de morte desde o início da investigação até o momento.

Além dessas colunas com dados faltantes, 40 outros valores não estavam presentes na base. 39 dados referentes a data de nascimento dos pacientes e 1 relacionado a localização da lesão. Considerando a importância dessas informações, não realizamos nenhuma estratégia para substituição dos dados faltantes. Porém, dado que não é possível determinar se há ou não a presença de carcinoma hepático levando em consideração a idade do indivíduo, apenas ignoramos a ausência desses valores. Entrementes, a localização da lesão é fundamental para a identificação de invasão microvascular, nessa linha, para a amostra onde a informação de localização da lesão não foi passada, descartamos o dado.

Existem 4 features categorias que descrevem o grau histológico, o sexo, a presença de invasão microvascular e a causa da hepatopatia. Realizamos a transformação manualmente apenas para fins de aprendizagem. 

Verificamos que a maioria dos casos de hepatopatia celular foram causados pelo Vírus da Hepatite C (VHC), a maioria homens. 

Realizamos um estudo da correlação das features e chegamos a resultados equivalentes usando a técnica de pearson e a de spearmam. Analisando os dados de correlação, notamos que nenhuma característica está fortemente ou moderadamente associada a presença de invasão microvascular. Como ilustrado nas matrizes de correlação abaixo.


<p float="left">
  <img src="/assets/initial_exploration_imgs/pearson_corr.png" width="500" />
  <img src="/assets/initial_exploration_imgs/spearman_corr.png" width="500" /> 
</p>

Abaixo mostramos alguns gráficos de histogramas de algumas features presentes na base de dados. 

Através desses gráficos é possível notar que a maior parte das lesões são pequenas. Não é possível dizer se a presença de invasão microvascular está ligada majoritariamente a lesões pequenas visto que existem poucas grandes lesões descritas na base.

A fração de contraste arterial (AEF),  também não aparenta ter nenhuma correlação com a identificação de invasão microvascular.

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

Abaixo mais um gráfico onde confrontamos todas as features com todas. Embora algumas sigam uma distribuição normal ou linear, nenhuma está correlacionada a presenta da invasão microvascular.

<p float="center">
  <img src="/assets/initial_exploration_imgs/all.png" />
</p>


### Bases Estudadas e Adotadas

Base de Dados | Endereço na Web | Resumo descritivo
----- | ----- | -----
Imagens de TC | Domínio privado | Essa base de dados é composta por imagens de tomografia computadorizada de pacientes com lesões hepatocelulares.



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
