
# Projeto - Entrega Final

# Projeto `Predição de Invasão Microvascular do Carcinoma Hepatocelular Pré- Ressecção ou Transplante Hepático Utilizando-se Dados Clínico-Laboratoriais e de Tomografia Computadorizada Trifásica`

# Project `<Title in English>`

# Apresentação

O presente projeto foi originado no contexto das atividades da disciplina de pós-graduação [*Ciência e Visualização de Dados em Saúde*](https://github.com/datasci4health/home), oferecida no primeiro semestre de 2021, na Unicamp.

|Nome  | RA | Especialização|
|--|--|--|
| [Daniel Alvarenga Fernandes](https://github.com/danielalvarengafernandes) | 190943  | Saúde / FCM |
| [Giovane William de Souza Gomes](https://github.com/giovanewsgomes)  | 093801  | Computação / FEEC |
| [Guilherme Paulino](https://github.com/paulinog) | 117119  | Computação / FEEC |
| [Stephane de Freitas Schwarz](https://github.com/stephanefschwarz) | 211518  | Computação / IC |


# Descrição Resumida do Projeto
> Descreva resumidamente o tema do projeto. O resumo idealmente deve: apresentar o contexto gerador e motivação; indicar o problema; apresentar a sua solução para o problema; indicar porque a sua solução é melhor do que os esforços atuais (não obrigatório); concluir com os resultados alcançados.

O carcinoma hepatocelular (CHC) é o tumor primário hepático mais comum e a principal causa de morte em pacientes cirróticos (1). O diagnóstico definitivo do CHC pode ser estabelecido apenas através de estudos de imagem, reservando-se a análise histopatológica somente para lesões indeterminadas, prática que tem sido adotada por diretrizes em todo o mundo desde 2012 (1-7). 
A ressecção cirúrgica e o transplante hepático são importantes tratamentos curativos disponíveis para o CHC, mas a taxa de recorrência para ambos permanece elevada. A taxa de recorrência em cinco anos do CHC é de aproximadamente 70% nos casos de ressecção hepática e 25% nos casos de transplante hepático (8). Um dos fatores mais importantes que explica a recorrência é a invasão microvascular (IMV), definida pela invasão de células tumorais em um espaço vascular revestido por endotélio, incluindo vasos microscópicos da veia porta, artéria hepática e vasos linfáticos, não sendo detectada na avaliação médica radiológica na rotina de trabalho (8). A IMV foi descrita como o mais forte preditor independente de sobrevida livre de recorrência (9, 10) e de mau prognóstico após ressecção hepática parcial ou transplante hepático em pacientes com CHC dentro dos critérios de Milão (11-13). Assim, predizer IMV no pré-operatório poderia permitir uma seleção mais adequada de pacientes para cada terapêutica. Além disso, se a ressecção hepática for considerada para pacientes com alto risco de invasão microvascular, por exemplo, um procedimento com ampla margem de ressecção pode ser preferível (14).  
No entanto, a IMV atualmente só é diagnosticada na rotina após ressecção cirúrgica ou transplante hepático, através da avaliação histopatológica. No conhecimento atual, é desafiador diagnosticar IMV através de exames pré-operatórios (14-16). Deste modo, há uma necessidade de um meio quantitativo de previsão de IMV no pré-operatório, preferencialmente através de uma modalidade de diagnóstico por imagem que seja realizada rotineiramente nos pacientes que serão submetidos à ressecção ou transplante hepático, como a Tomografia Computadorizada (TC) contrastada trifásica. Neste contexto, surge a radiômica. A radiômica consiste em um campo emergente na análise de imagens que através da extração de grande quantidade de características de dados de imagens médicas, habitualmente não observadas ao olho humano nú- pode vir a refletir o tecido biológico subjacente (17).  Busca-se então, identificar e validar novos parâmetros pré-operatórios que funcionem como “biomarcadores radiológicos”, indicando a agressividade do CHC como preditor prognóstico pré-operatório através da IMV. 

# Vídeos do Projeto

## Vídeo da Proposta
> https://drive.google.com/file/d/1RCdJ5aXSi8bzHtpRaHbQ-o3KIrWn5OPz/view?usp=sharing

## Vídeo da Apresentação Final
> Link para vídeo da apresentação final do projeto (máximo 8 minutos). *TODOS OS MEMBROS DO GRUPO DEVEM APARECER NO VÍDEO*.

# Slides do Projeto

## Slides da Proposta
> Link para slides de apresentação da proposta do projeto.

## Slides da Apresentação Final
> Link para slides da apresentação final do projeto.

# Introdução e Referenciais de Teóricos

## Contextualização do projeto

> Indicação (bastante resumida) da análise proposta
>
> Indicação (bastante resumida) dos resultados alcançados

## Trabalhos Relacionados

Pesquisas recentes na área de detecção e predição de invasão microvascular, (mVI, do inglês, Microvascular invasion) em imagens de ressonância magnética (RM), têm se beneficiado do advanto dos algoritmos de aprendizagem de máquina, mais precisamente, das redes neurais artificiais. Nos últimos anos, essas redes tem mostrado um potencial competitivo para explorar a mais variada gama de dados, inclusive, de imagens médicas.

Zheng et al. (18) elaboraram um método para predição de mVI através de uma análise quantitativa das imagens de RM. Para isso, foram coletados inicialmente achados radiômicos graduados, como quantidade e diâmetro dos tumores, identificação de artérias internas do tumor e realce do rebardo periférico, dentro outros. Subsequentemente foram coletados dados de textura da periferia do tumor e do parênquima hepática adjacente. Depois, os dados foram aplicados a dois modelos multivariados. Os autores angariaram uma AUC = 88.00 usando dados de textura extraídos com o Local Binary Pattern (LBP) e dados clínicos do pré-operatório.

Nebbia et al. (19) propuseram a utilizaram de três tipos de características para classificação de mVI no fígado, que são: (I) características presentes no tumor; (II) características que estão à margem da lesão; e (III) a união de ambas. Para isso, os autores segmentaram manualmente a região de interesse, no caso, a região lesada do fígado. Uma vez com a lesão salientada a região peri tumoral (cerca de 1cm ao redor do tumor) foi automaticamente definida. Em seguida, 100 características radiômicas foram extraídas dos volumes resultantes da segmentação, as quais foram submetidas ao LASSO para seleção das mais discriminativas. O vetor de características final foi passado para um classificador binário SVM que determina a presença ou ausência de mVI. Os autores alcançaram bons resultados (AUC = 86.99%) quando utilizados dados radiômicos tanto da sequência T2 quanto da portal. Os autores notaram que as informações extraídas apenas da margem das lesões são mais discriminativa para a identificação de mVI.

Song et al. (20) exploraram esse problema usando redes neurais profundas. Para isso, foi desenvolvida uma rede com oito entradas. Cada entrada processa um volume 3D de interesse (), com oito sequências da MRI. As entradas são processadas paralelamente, pela mesma topologia de rede, 4 camadas de convolução empilhadas. As saídas dessas convoluções são concatenadas junto a parâmetros clínicos e passadas para uma camada totalmente conectada com ativação softmax, que gera a probabilidade de haver ou não invasão. O arcabouço alcançou o valor de AUC equivalente a 93.33%. Superando os métodos anteriores que utilizavam informações radiômicas, meticulosamente extraídas por especialistas da área.

Apesar de todos esses métodos apresentarem resultados competitivos, todos são dependentes de segmentação e identificação prévia da área de interesse. Nessa linha, objetivamos o desenvolvimento de um consórcio de algoritmos baseados em redes neurais profundas, que dado um volume 3D não isotrópico (e.g. tem dimensões distintas), sejamos capazes de determinar a probabilidade de um paciente conter ou não invasão microvascular.

# Perguntas de Pesquisa

> É possível predizer IMV do CHC no pré-operatório utilizando-se dados clínico-laboratoriais e de tomografia computadorizada (TC) trifásica? 

# Objetivos do Projeto
> Como seu projeto propôs abordar o problema apresentado.

# Metodologia
> Abordagem adotada pelo projeto na busca pela resposta às perguntas de pesquisa.
> Justificar teoricamente, sempre que possível, a metodologia adotada.

## Bases de Dados e Evolução

O referido estudo foi aprovado pela Comissão de Ética institucional. Foram respeitadas as condições éticas pertinentes ao protocolo e seguidos rigorosamente os princípios enunciados na Declaração de Helsinque e do Ministério da Saúde do Brasil para pesquisa em seres humanos. A amostra analisada será realizada retrospectivamente em 200 nódulos (125 pacientes submetidos a transplante hepático e/ou ressecção hepática) que tiveram confirmação histopatológica diagnóstica de CHC. 


**Critérios de exclusão:**

- Pacientes que não tinham TC com parâmetros técnicos adequados para análise de lesões focais hepáticas. 
- Pacientes cujas localizações das lesões focais hepáticas identificadas na TC não tinham correspondência exata com as localizações das lesões descritas nos estudos anatomopatológicos.
- Nódulos com diagnóstico anatomopatológico de hepatocolangiocarcinoma.

**Tomografia computadorizada – técnica**

Todos os exames de TC realizados incluídos na amostra contemplaram minuciosamente critérios técnicos de qualidade das imagens. Foram realizados em aparelho com 64 canais de detectores, nas fases pré-contraste, arterial, portal e equilíbrio do fígado (estudo dinâmico). Foram utilizados 120 ml (ou volume menor – 100 ml - em pacientes com menos de 70 kg) de meio de contraste venoso iodado através de bomba injetora com fluxo de 4-5 ml/s, seguido de injeção de 40 ml de solução salina a 0,9%. Não foi utilizado meio de contraste via oral ou via retal. 

Foram adquiridas imagens nas seguintes fases do meio de contraste:

- fase pré-contraste: obtidas imediatamente antes da injeção do meio de contraste venoso;
- fase arterial: obtidas por detecção automática, em até 15 segundos após o pico de concentração de contraste da aorta abdominal;
- fase portal: obtidas entre 60 e 80 segundos após o início da injeção do meio de contraste venoso;
- fase de equilíbrio: obtidas cerca de 180 segundos após o início da injeção do meio de contraste venoso.

Foram analisadas as imagens dos cortes axiais das TCs, reconstruídas com 3mm de espessura, de todas as fases do estudo dinâmico com meio de contraste venoso da TC.


Dados clínico-laboratoriais e tomográficos foram avaliados, a saber: 

- Idade (anos)
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

Parâmetros quantitativos de hipervascularização arterial e lavagem do contraste dos carcinomas foram calculados através da avaliação manual consensual entre dois Médicos Radiologistas com experiência em Radiologia abdominal. “Regiões de Interesse” (ROIs) foram circuladas manualmente nas lesões e em duas regiões de parênquima do fígado adjacente aos CHCs, nas imagens pré-contraste e nas fases arterial, portal e equilíbrio após a injeção do meio de contraste. 

<p float="left">
  <img src="/assets/initial_exploration_imgs/different_phases_chc.JPG" width="500" />
</p>

**Figura 01: Carcinoma hepatocelular. Cortes axiais de TC pré-contraste (a) e nas fases arterial (b), portal (c) e de equilíbrio (d) com as ROIs posicionadas no nódulo e no parênquima adjacente.**

Em nódulos heterogêneos, a área com hipervascularização arterial mais intensa foi considerada para análise, com medidas nas localizações correspondentes das demais fases. Houve cuidado para evitar vasos intratumorais, ductos biliares e artefatos.

Subsequentemente, os seguintes parâmetros quantitativos foram calculados, baseados nas relações dos valores extraídos com as medidas objetivas de densidades:

- Diferença de atenuação (DA): diferença entre a atenuação da lesão e a média da atenuação do parênquima adjacente; foi calculada em todas as fases do estudo dinâmico (arterial, portal e equilíbrio).

- Razão de atenuação (RA) na fase portal - RAP: RAP = 1 00×(AMP /ALP), onde P = fase portal, AM = atenuação média do parênquima e AL = atenuação da lesão;

- Razão de atenuação (RA) na fase de equilíbrio - RAE: ERA = 100×(AME /ALE), onde E = fase de equilíbrio, AM = atenuação média do parênquima e AL = atenuação da lesão;

- Razão de “washout” relativo (RWR) na fase portal - RWRP: RWRP = 100× (ALA − ALP) / ALA, onde A = fase arterial, P = fase portal e AL = atenuação da lesão;

- Razão de “washout” relativo (RWR) na fase de equilíbrio - RWRE: RWRE = 100× (ALA − ALE) / ALA, onde A= fase arterial, E = fase de equilíbrio e AL = atenuação da lesão;

Estes parâmetros quantitativos do exame de tomografia computadorizada foram também comparados com a presença ou ausência de invasão microvascular confirmados anatomopatologicamente. 

Nesse projeto exploramos apenas uma base de dados. Contudo, esta se divide em dois grupos de dados. No primeiro conjunto foram exploradas informações tabulares clínico-laboratoriais de pacientes com lesões no fígado (CHC) e relacionadas ao exame histopatológico de presença ou ausência de IMV pré-operatória do CHC. No segundo conjunto de dados, realizamos uma investigação inicial nas imagens de tomografia computadorizada  dos pacientes em questão (prospecção de radiômica).

A base é constituída por 200 lesões de 125 indivíduos. Assim, existem pacientes com mais de uma lesão, e determinadas lesões com dimensões que se estendem por mais de um segmento do fígado. A abordagem de classificar a lesão por regiões é fundamental visto que intervenções cirúrgicas podem ser adotadas para remover apenas a parte lesada, sem a necessidade de remoção da peça inteira.

### Bases Estudadas mas Não Adotadas

Base de Dados | Endereço na Web | Resumo descritivo
----- | ----- | -----
Dados clínicos de TC | Domínio privado | Essa base de dados é composta por dados clínico-laboratoriais de pacientes com CHCs.

O primeiro conjunto de dados explorados consiste em uma tabela com informações clínico-laboratoriais de pacientes com CHCs confirmados histopatologicamente. Contém 26 características que variam desde o identificador dos pacientes e localização do nódulo até a causa da hepatopatia e  grau histológico do CHC. A descrição completa de cada uma das features presentes nessa base de dados pode ser encontrada [aqui](https://github.com/paulinog/2021.1-CienciaDeDadosEmSaude_IA368X-MO826A-CX002A/tree/main/data)

Das 26 características descritas na base de dados, 4 delas estavam completamente nulas, para todos os pacientes e nódulos listados. Essas quatro variáveis estão associadas a dados de exame alfafetoproteína, da recorrência do câncer hepático e se houve algum caso de morte desde o início da investigação.

Além dessas colunas com dados faltantes, 39 outros valores não estavam presentes na base, referentes a data de nascimento dos pacientes (embora tenhamos a idade dos pacientes, como substituto). Considerando a pouca importância dessas informações já que possuímos a idade, não realizamos nenhuma estratégia para substituição dos dados faltantes. 

Existem 4 features categóricas que descrevem o grau histológico, o sexo, a presença/ ausência de invasão microvascular e a causa da hepatopatia. Realizamos a transformação manualmente apenas para fins de aprendizagem. 

Dentre os 125 pacientes, 98 (78,4%) eram do sexo masculino. A mediana da idade foi de 59 anos (intervalo entre 36 e 81 anos). Sessenta e nove (55,2%) pacientes tinham um nódulo e 56 (44,8%) tinham dois ou mais nódulos. O tamanho médio dos nódulos foi de 3,0 cm (1,0-25,0 cm, mediana de 2,9). A invasão microvascular foi encontrada em 77 (38,5%) CHCs na análise histológica.

Verificamos que a maioria dos casos de hepatopatia subjacente foram causados pelo Vírus da Hepatite C (VHC), sendo majoritariamente pessoas do sexo masculino. 

Realizamos um estudo da correlação das features e chegamos a resultados equivalentes usando tanto a técnica de pearson quanto a de spearmam. Analisando os dados de correlação, notamos que o grau histopatológico está moderadamente associado a presença de invasão microvascular. Como ilustrado nas matrizes de correlação abaixo.


<p float="left">
  <img src="/assets/initial_exploration_imgs/person_corr_change_hist.png" width="500" />
  <img src="/assets/initial_exploration_imgs/spearman_corr_change_hist.png" width="500" /> 
</p>

Essa característica já havia sido descrita em alguns trabalhos da literatura médico-científica. Nossa investigação inicial alcançou resultados condizentes com os descritos em trabalhos anteriores.

Abaixo mostramos alguns gráficos de histogramas de algumas features presentes na base de dados. 

Através desses gráficos, é possível notar que a maior parte das lesões são pequenas. Não é possível, por outro lado, dizer se a presença de invasão microvascular está ligada majoritariamente a lesões maiores, visto que existem poucas grandes lesões descritas nesse conjunto.

A diferença de atenuação (DA) calculada manualmente de maneira consensual entre os dois Médicos Radiologistas nas diferentes fases dinâmicas do estudo tomográfico, incluindo a fase arterial, também não aparenta ter nenhuma correlação com a identificação de invasão microvascular.

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

Abaixo mais um gráfico onde confrontamos todas as features com todas. Embora algumas sigam uma distribuição normal ou linear, nenhuma está correlacionada a presença da invasão microvascular. Essa característica sugere que não é possível, a partir desses dados, inferir a probabilidade de um paciente conter ou não invasão microvascular pré-operatoriamente, reforçando a ideia original de que para identificar a presença ou a probabilidade de uma invasão microvascular do CHC antes de uma ressecção e/ou transplante hepático, devemos considerar principalmente durante a análise dados extraídos do exame de TC trifásico realizado.

<p float="center">
  <img src="/assets/initial_exploration_imgs/all.png" />
</p>


Os dados mostraram que em geral, a invasão microvascular está localizada na região 8 do fígado, identificamos 35 casos. Seguido pela região 7, com 21 casos registrados e a região 6, com 19 ocorrências. Todas essas regiões estão no lobo direito do fígado. Na imagem abaixo mostramos uma imagem com as segmentações e nomenclaturas de cada segmento do fígado.

<p float="center">
  <img src="/assets/initial_exploration_imgs/liver_segments.jpg" />
</p>

Os exames de TC foram disponibilizados em dois formatos: JPEG e DCM (DICOM). Utilizamos a biblioteca DICOM para exibições iniciais, conforme abaixo.

<p float="left">
  <img src="/assets/initial_exploration_imgs/dicom_phases.png" width="500" />
</p>

O relatório completo gerado para cada uma das features presentes nesse conjunto de dados pode ser encontrado na pasta [assets](https://github.com/paulinog/2021.1-CienciaDeDadosEmSaude_IA368X-MO826A-CX002A/blob/main/assets/initial_exploration_imgs/profiling.html).

### Bases Estudadas e Adotadas

ase de Dados | Endereço na Web | Resumo descritivo
----- | ----- | -----
Imagens de TC | Domínio privado | Essa base de dados é composta por imagens de tomografia computadorizada de pacientes com lesões hepatocelulares.

Além dos dados tabulares com informações diversas dos paciente e exames clínico- laboratoriais realizados, investigamos algumas características relacionadas a dados de imagens de tomografia computadorizada. Notamos que nas três fases que iremos explorar, existe uma disparidade com relação a quantidade de frames por exame. 

Na tabela abaixo mostramos as características gerais da base. É possível notar que para alguns pacientes, existem apenas dois frames ligados ao exame de TC. Sendo que na média, esse número é significativamente superior, aproximadamente 100 imagens por fase. 


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


### Integração entre Bases e Análise Exploratória

> Descreva etapas de integração de fontes de dados e apresente a seguir uma análise exploratória que envolva ambas.
>
>
>
> Resultados de Análise Exploratória
> * use estatística descritiva e gráficos;
> * inclua gráficos de sobre a distribuição dos dados (e.g., histogramas e boxplots);
> * analise correlação e use gráficos de dispersão;
> * descreva os resultados/gráficos, os analise e contextualize com o tema definido.

# Análises Realizadas

<p float="left">
  <img src="/assets/net_topology.png" width="500" />
</p>

> Descrição detalhada das análises realizadas.
>
>
>
>Relate aqui também a evolução do projeto: possíveis problemas enfrentados e possíveis mudanças de trajetória. Relatar o processo para se alcançar os resultados é tão importante quanto os resultados.
>
>
>
> Nesta seção ou na seção de Resultados podem aparecer destaques de código como indicado a seguir. Note que foi usada uma técnica de highlight de código, que envolve colocar o nome da linguagem na abertura de um trecho com `~~~`, tal como `~~~python`.
>
> Os destaques de código devem ser trechos pequenos de poucas linhas, que estejam diretamente ligados a alguma explicação. Não utilize trechos extensos de código. Se algum código funcionar online (tal como um Jupyter Notebook), aqui pode haver links. No caso do Jupyter, preferencialmente para o Binder abrindo diretamente o notebook em questão.

~~~python
df = pd.read_excel("/content/drive/My Drive/Colab Notebooks/dataset.xlsx");
sns.set(color_codes=True);
sns.distplot(df.Hemoglobin);
plt.show();
~~~

## Ferramentas

Ferramenta | Função
----- | -----
[Python 3](https://www.python.org/) | Linguagem de programação a ser utilizada para o desenvolvimento das soluções propostas.
[Keras](https://keras.io/) | Arcabouço de código aberto para desenvolvimento de modelos de aprendizagem de máquina e aprendizagem profunda.
[Pandas](https://pandas.pydata.org/) | Ferramenta para manipulação e análise de dados.
[Numpy](https://numpy.org/) | Biblioteca utilizada para manipulação de vetores multidimensionais.
[Matplotlib](https://matplotlib.org/) | Biblioteca para visualização dos dados.
[pydicom](https://pydicom.github.io/) | Biblioteca específica para manipulação de imagens médicas em formato dcm.

# Resultados
> Descrição dos resultados mais importantes obtidos.
>
> Apresente os resultados da forma mais rica possível, com gráficos e tabelas. Mesmo que o seu código rode online em um notebook, copie para esta parte a figura estática. A referência a código e links para execução online pode ser feita aqui ou na seção de Análises Realizadas (o que for mais pertinente).

# Discussão
> Discussão dos resultados. Relacionar os resultados com as perguntas de pesquisa ou hipóteses avaliadas.
>
> A discussão dos resultados também pode ser feita opcionalmente na seção de Resultados, na medida em que os resultados são apresentados. Aspectos importantes a serem discutidos: É possível tirar conclusões dos resultados? Quais? Há indicações de direções para estudo? São necessários trabalhos mais profundos?

# Conclusão
> Destacar as principais conclusões obtidas no desenvolvimento do projeto.
>
> Destacar os principais desafios enfrentados.
>
> Principais lições aprendidas.

# Trabalhos Futuros
> O que poderia ser melhorado se houvesse mais tempo?

# Referências Bibliográficas

1-	Bray F, Ferlay J, Soerjomataram I, Siegel RL, Torre LA, Jemal A. Global cancer statistics 2018: GLOBOCAN estimates of incidence and mortality worldwide for 36 cancers in 185 countries. Cancer J Clin. Forthcoming 2018.

2-	Kudo M, Matsui O, Izumi N, Iijima H, Kadoya M, Imai Y, et al. JSH Consensus- Based Clinical Practice Guidelines for the Management of Hepatocellular Carcinoma: 2014 Update by the Liver Cancer Study Group of Japan. Liver Cancer. 2014;3(3-4):458–68.

3-	Heimbach JK, Kulik LM, Finn RS, Sirlin CB, Abecassis MM, Roberts LR, et al. AASLD guidelines for the treatment of hepatocellular carcinoma. Hepatology. 2017 Dec 19;67(1):358–80.

4-	 Omata M, Cheng A-L, Kokudo N, Kudo M, Lee J-M, Jia J, et al. Asia–Pacific clinical practice guidelines on the management of hepatocellular carcinoma: a 2017 update. Hepatology International. 2017 Jun 15;11(4):317–70. 

5-	Wald C, Russo MW, Heimbach JK, Hussain HK, Pomfret EA, Bruix J. New OPTN/UNOS Policy for Liver Transplant Allocation: Standardization of Liver Imaging, Diagnosis, Classification, and Reporting of Hepatocellular Carcinoma. Radiology. 2013 Feb;266(2):376–82.

6-	Arslanoglu A, Seyal AR, Sodagari F, Sahin A, Miller FH, Salem R, et al. Current Guidelines for the Diagnosis and Management of Hepatocellular Carcinoma: A Comparative Review. American Journal of Roentgenology. 2016 Nov;207(5):W88–W98.

7-	American College of Radiology [internet]. Liver imaging reporting and data system version 2018 [updated 2018 Jul; acessed 2018 Oct 31]. Available from:
http://www.acr.org/Quality-Safety/Resources/LIRADS.

8-	Bruix J, Gores GJ, Mazzaferro VHepatocellular carcinoma: clinical frontiers and perspectivesGut 2014;63:844-855.

9-	Roayaie, S., et al., A system of classifying microvascular invasion to predict outcome after resection in patients with hepatocellular carcinoma. Gastroenterology, 2009. 137(3): p. 850-51. 

10-	Lim, K.C., et al., Microvascular invasion is a better predictor of tumor recurrence and overall survival following surgical resection for hepatocellular carcinoma compared to the Milan criteria. Ann Surg, 2011. 254(1): p. 108-13.

11-	Mazzaferro, V., et al., Predicting survival after liver transplantation in patients with hepatocellular carcinoma beyond the Milan criteria: a retrospective, exploratory analysis. Lancet Oncol, 2009. 10(1): p. 35-43. 

12-	Sumie S, Kuromatsu R, Okuda K, et al. Microvascular invasion in patients with hepatocellular carcinoma and its predictable clinicopathological factors. Ann Surg Oncol. 2008;15:1375–82.

13-	 Sumie S, Nakashima O, Okuda K, et al. The significance of classifying microvascular invasion in patients with hepatocellular carcinoma. Ann Surg Oncol. 2014;21:1002–9.

14-	Hirokawa F, Hayashi M, Miyamoto Y et al (2014) Outcomes and predictors of microvascular invasion of solitary hepatocellular carcinoma. Hepatol Res 44:846–853. 

15-	Sterling RK, Wright EC, Morgan TR et al (2012) Frequency of elevated hepatocellular carcinoma (HCC) biomarkers in patients with advanced hepatitis C. Am J Gastroenterol 107:64–74.

16-	Shim JH, Han S, Lee YJ et al (2013) Half-life of serum alphafetoprotein: an early prognostic index of recurrence and survival after hepatic resection for hepatocellular carcinoma. Ann Surg 257:708–717.

17-	Gillies, R.J., P.E. Kinahan, and H. Hricak, Radiomics: Images Are More than Pictures, They Are Data. Radiology, 2016. 278(2): p. 563-77.

18- Zheng, J., Chakraborty, J., Chapman, W.C., Gerst, S., Gonen, M., Pak, L.M., Jarnagin, W.R., DeMatteo, R.P., Do, R.K., Simpson, A.L. and Allen, P.J., 2017. Preoperative prediction of microvascular invasion in hepatocellular carcinoma using quantitative image analysis. Journal of the American College of Surgeons, 225(6), pp.778-788.

19- Nebbia, G., Zhang, Q., Arefan, D., Zhao, X. and Wu, S., 2020. Pre-operative Microvascular Invasion Prediction Using Multi-parametric Liver MRI Radiomics. Journal of Digital Imaging, pp.1-11.

20- Song, D., Wang, Y., Wang, W., Wang, Y., Cai, J., Zhu, K., Lv, M., Gao, Q., Zhou, J., Fan, J. and Rao, S., 2021. Using deep learning to predict microvascular invasion in hepatocellular carcinoma based on dynamic contrast-enhanced MRI combined with clinical parameters. Journal of Cancer Research and Clinical Oncology, pp.1-11.
