
# Predição de Invasão Microvascular do Carcinoma Hepatocelular Pré- Ressecção ou Transplante Hepático Utilizando-se Dados Clínico-Laboratoriais e de Tomografia Computadorizada Trifásica

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

O carcinoma hepatocelular (CHC) é o tumor primário hepático mais comum e a principal causa de morte em pacientes cirróticos (1). O diagnóstico definitivo do CHC pode ser estabelecido apenas através de estudos de imagem, reservando-se a análise histopatológica somente para lesões indeterminadas, prática que tem sido adotada por diretrizes em todo o mundo desde 2012 (1-7). 

A ressecção cirúrgica e o transplante hepático são importantes tratamentos curativos disponíveis para o CHC, mas a taxa de recorrência para ambos permanece elevada. A taxa de recorrência em cinco anos do CHC é de aproximadamente 70% nos casos de ressecção hepática e 25% nos casos de transplante hepático (8). Um dos fatores mais importantes que explica a recorrência é a invasão microvascular (IMV), definida pela invasão de células tumorais em um espaço vascular revestido por endotélio, incluindo vasos microscópicos da veia porta, artéria hepática e vasos linfáticos, não sendo detectada na avaliação médica radiológica na rotina de trabalho (8). 

A IMV foi descrita como o mais forte preditor independente de sobrevida livre de recorrência (9, 10) e de mau prognóstico após ressecção hepática parcial ou transplante hepático em pacientes com CHC dentro dos critérios de Milão (11-13). Assim, predizer IMV no pré-operatório poderia permitir uma seleção mais adequada de pacientes para cada terapêutica. Além disso, se a ressecção hepática for considerada para pacientes com alto risco de invasão microvascular, por exemplo, um procedimento com ampla margem de ressecção pode ser preferível (14). 

No entanto, a IMV atualmente só é diagnosticada na rotina após ressecção cirúrgica ou transplante hepático, através da avaliação histopatológica. No conhecimento atual, é desafiador diagnosticar IMV através de exames pré-operatórios (14-16). Deste modo, há uma necessidade de um meio quantitativo de previsão de IMV no pré-operatório, preferencialmente através de uma modalidade de diagnóstico por imagem que seja realizada rotineiramente nos pacientes que serão submetidos à ressecção ou transplante hepático, como a Tomografia Computadorizada (TC) contrastada trifásica. Neste contexto, surge a radiômica. 

A radiômica consiste em um campo emergente na análise de imagens que através da extração de grande quantidade de características de dados de imagens médicas, habitualmente não observadas ao olho humano nú- pode vir a refletir o tecido biológico subjacente (17).  Busca-se então, identificar e validar novos parâmetros pré-operatórios que funcionem como “biomarcadores radiológicos”, indicando a agressividade do CHC como preditor prognóstico pré-operatório através da IMV. 

Verificamos que as redes convolucionais de 2 e 3 dimensões podem ser aplicados como método competitivo para identificação de tais invasões. Mostramos uma análise inicial onde pudemos notar alguns desafios que ainda precisam ser superados pela comunidade científica. Porém, os achados sugerem que usando redes profundas e dados volumétricos, existem prospecções para o desenvolvimento de um processo de identificação automatizado.



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

Pesquisas recentes na área de detecção e predição de invasão microvascular, (mVI, do inglês, Microvascular invasion) em imagens de ressonância magnética (RM), têm se beneficiado do advento dos algoritmos de aprendizagem de máquina, mais precisamente, das redes neurais artificiais. Nos últimos anos, essas redes têm mostrado um potencial competitivo para explorar a mais variada gama de dados, inclusive, de imagens médicas.

Zheng et al. (18) elaboraram um método para predição de mVI através de uma análise quantitativa das imagens de RM. Para isso, foram coletados inicialmente achados radiômicos graduados, como quantidade e diâmetro dos tumores, identificação de artérias internas do tumor e realce do rebardo periférico, dentro outros. Subsequentemente foram coletados dados de textura da periferia do tumor e do parênquima hepática adjacente. Depois, os dados foram aplicados a dois modelos multivariados. Os autores angariaram uma AUC = 88.00 usando dados de textura extraídos com o Local Binary Pattern (LBP) e dados clínicos do pré-operatório.

Nebbia et al. (19) propuseram a utilizaram de três tipos de características para classificação de mVI no fígado, que são: (I) características presentes no tumor; (II) características que estão à margem da lesão; e (III) a união de ambas. Para isso, os autores segmentaram manualmente a região de interesse, no caso, a região lesada do fígado. Uma vez com a lesão salientada a região peri tumoral (cerca de 1cm ao redor do tumor) foi automaticamente definida. Em seguida, 100 características radiômicas foram extraídas dos volumes resultantes da segmentação, as quais foram submetidas ao LASSO para seleção das mais discriminativas. O vetor de características final foi passado para um classificador binário SVM que determina a presença ou ausência de mVI. Os autores alcançaram bons resultados (AUC = 86.99%) quando utilizados dados radiômicos tanto da sequência T2 quanto da portal. Os autores notaram que as informações extraídas apenas da margem das lesões são mais discriminativa para a identificação de mVI.

Song et al. (20) exploraram esse problema usando redes neurais profundas. Para isso, foi desenvolvida uma rede com oito entradas. Cada entrada processa um volume 3D de interesse (), com oito sequências da MRI. As entradas são processadas paralelamente, pela mesma topologia de rede, 4 camadas de convolução empilhadas. As saídas dessas convoluções são concatenadas junto a parâmetros clínicos e passadas para uma camada totalmente conectada com ativação softmax, que gera a probabilidade de haver ou não invasão. O arcabouço alcançou o valor de AUC equivalente a 93.33%. Superando os métodos anteriores que utilizavam informações radiômicas, meticulosamente extraídas por especialistas da área.

Apesar de todos esses métodos apresentarem resultados competitivos, todos são dependentes de segmentação e identificação prévia da área de interesse. Nessa linha, objetivamos o desenvolvimento de um consórcio de algoritmos baseados em redes neurais profundas, que dado um volume 3D não isotrópico (e.g. tem dimensões distintas), sejamos capazes de determinar a probabilidade de um paciente conter ou não invasão microvascular.


# Perguntas de Pesquisa

É possível predizer IMV do CHC no pré-operatório utilizando-se dados clínico-laboratoriais e de tomografia computadorizada (TC) trifásica? 

# Objetivos do Projeto

O principal objetivo do presente trabalho, é verificar se é possível identificar a presença de invasões microvasculares em imagens de ressonância magnética do fígado. Para isso, exploramos técnicas de análise de imagens que se baseiam em arquiteturas de redes neurais convolucionais. 

# Metodologia

Para lidar com o desafio da identificação da presença de mVI, consideramos duas frentes de pesquisa. Na primeira, buscamos compreender se dado com conjunto de imagens volumétricas, não isotrópicas, de diferentes fases, era possível verificar a presença de mVI. Na segunda frente, exploramos meios para melhorar a identificação através da determinação prévia de regiões de interesse.

---

Trabalhos anteriores mostraram que através da análise de regiões específicas e atributos radiômicos das imagens, resultados promissões são alcançados para resolução desta tarefa. Contudo, existe um alto grau de complexidade associado ao processo de identificação de áreas de interesse que descrevem uma lesão. Essas regiões são usadas como ponto de referência para a busca das mVI na lesão e regiões periféricas a ela. Além disso, em alguns trabalhos, os autores utilizaram técnicas laboriosas de engenharia de características. Nessa sentido, buscamos explorar meios mais robustos, capazes de extrair informações discriminativas dos dados, com um menor esforço associado a triagem inicial por especialistas da área.

Para isso propusemos o uso de redes neurais convolucionais de 2 e 3 dimensões. Essas redes recebem em paralelo três entrada, que correspondem a três fases do exame, a saber, fase arterial, portal e equilíbrio. 

Para cada uma dessas entradas aplicamos dois filtros de convolução. A ideia essa estrutura aqui é salientar características de alta ordem que descrevem as classes do problema. Para toda camada de convolução adicionamos um mecanismo de pooling para, de modo a reduzir a quantidade de parâmetros, além de manter apenas as características mais discriminativas.

Em seguida, a rede transforma os volumes resultantes em sinais unidimensionais para serem concatenados. A racionalidade por trás dessa abordagem é proporcionar que a rede consiga olhar simultaneamente para todas as fases e encontra pontos de similaridade entre as entradas, e intuitivamente, contribuir para aumentar a sensibilidade do arcabouço.

Por fim, o vetor gerado é passado por três camadas totalmente conectadas até chegar a camada de decisão final. Intercalamos nessas camadas operações de dropout 30% para evitar a especialização dos dados durante o treinamento.

Esse consórcio de convoluções foi construído baseado na visão dos especialistas que afirmam que a micro invasão pode ser melhor encontra quando todas as fases são consideradas no processo de tomada de decisão. Vale lembrar que para o ser humano, não é possível identificar uma micro invasão olhando para dados de ressonância.

A imagem abaixo mostra a arquitetura desenvolvimento para o estudo desse projeto.


<p float="left">
  <img src="/assets/net_topology.png" width="500" />
</p>


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


# Análises Realizadas

Como supramencionado, iniciamos a investigação baseando-se na classificação por paciente, ou seja, dado um conjunto de MRI de 3 fases distintas, e a informação se o paciente possui ou não a micro-invasão, criamos uma rede convolucional tridimensional, e passamos os slices através da arquitetura. Ocorre que, a quantidade de slices varia não somente entre pacientes, mas também entre fases. Das imagens volumétricas analisadas, o maior voxel contém 441 slices, enquanto o menor possue 58 slices. Com isso nos deparamos com o primeiro desafio da tarefa, responder como organizar os dados de modo que se encaixem na rede convolucional, visto que requerem amostras de tamanho fixo.

Como uma alternativa a esse impasse, determinamos uma quantia fixa de slices, no caso, 64 slices - esse número foi empiricamente definido levando em consideração os achados na literatura e a quantidade de memória que tinhamos disponível. Em seguida, dividimos o voxel em pedaços igualmente espaçados para conseguir a quantidade de slices requerida (como descrito no trecho de código abaixo). E então, experimentamos atribuir a estes pedados três valores, que correspondem ao valor médio dos slices nos conjuntos menores, ao valor máximo do pedaço ou ao valor mínimo. Assim, o volume de entrada para essa abordagem tem dimensões iguais a 128 x 128 x 64 px. As dimensões de altura e largura da imagem foram definidas com base nos valores adotados pelos trabalhos base desse projeto (Vide seção de trabalhos relacionados).

~~~python
def get_chuncks(slices, n_chuncks):

  n_chuncks = math.ceil(len(slices) / n_chuncks)

  for i in range(0, len(slices), n_chuncks):
    yield slices[i:i+n_chuncks]
~~~

Para pré-processar estes dados, foram necessárias aproximadamente 2 horas para cada fase. 

Entretanto, o principal problema dessa abordagem é a perda da precisão com relação aos frames individuais. Nem todos os slices da ressonância contém informações que conduzem a identificação da presença da invasão. Pelo contrário, parte significativa dos slices nem sequer mostram a lesão.

Para superar essa limitação, resolvemos olhar individualmente para cada um dos frames, mas agora, através de uma rede convolucional de 2 dimensões. Nesse caso, ainda estamos usando como alvo a anotação sobre o paciente com a existência da mVI.

Novamente nos deparamos com um obstáculo. Classificar frames individuais considerando uma anotação para um voxel adiciona muito ruído ao processo de inferência, visto que as imagens, muitas vezes, sem qualquer informação que descreve o fígado, a lesão e em última instância a micro invasão, estão categorizadas, nessa abordagem, como positivo. Aumentando assim a taxa de falso positivo.

Finalmente resolvemos anotar manualmente quais eram os frames em cada uma das fases que continham uma lesão hepática. Com isso aumentamos as chances da rede dar atenção às regiões que verdadeiramente podem trazer informações que ressaltam traços da existência as mVIs. Aqui, nos deparamos com um desafio similar ao citato anteriormente. A quantidade de frames com lesão depende de diversos fatores, sendo o principal deles o tamanho do carcinoma. Nessa linha, quanto maior a lesão, maior é a quantidade de frames observados. 

Com isso, caímos no mesmo dilema, sobre como tratar esses dados com dimensões não fixas. Então, com base no estudo feito por Song et al. (20), consideramos 8 frames a partir da primeira ocorrência da lesão. Dessa forma, o volume final contém 128 x 128 x 8 px.

Para cada uma das topologias propostas, experimentamos diversos hiper parâmetros, desde regularização, taxa de dropout para evitar overffiting, normalização de batch, otimizadores, inicializadores e quantidade de camadas internas, dentre outros. Como descrito na tabela abaixo:

| Hiperparametros | Valores testados |
|-|-|
| Fun. ativaçao interna | [softmax, sigmoid, tanh, relu] |
| Fun. ativaçao saida | [softmax, sigmoid, tanh, relu] |
| Inicializador | [zeros, RandomNormal, glorot_uniform] |
| Qtd camadas conv. | [Adam, Adagrad, RMSprop, SDG] |
| Qtd camadas full. | 1 ou mais |
| Regularizaçao | [1e-5, 1e-2, 1e-1, 1, 1.5] |


As redes tridimensionais contêm muitos parâmetros, por isso, o computo da arquitetura é naturalmente demorada. Além disso, devido à alta quantidade de parâmetros, existe uma alta probabilidade de overffiting.

## Ferramentas

Ferramenta | Função
----- | -----
[Python 3](https://www.python.org/) | Linguagem de programação a ser utilizada para o desenvolvimento das soluções propostas.
[Keras](https://keras.io/) | Arcabouço de código aberto para desenvolvimento de modelos de aprendizagem de máquina e aprendizagem profunda.
[Pandas](https://pandas.pydata.org/) | Ferramenta para manipulação e análise de dados.
[Numpy](https://numpy.org/) | Biblioteca utilizada para manipulação de vetores multidimensionais.
[Matplotlib](https://matplotlib.org/) | Biblioteca para visualização dos dados.
[pydicom](https://pydicom.github.io/) | Biblioteca específica para manipulação de imagens médicas em formato dcm.
[Colab](https://pydicom.github.io/) | Ambiente de desenvolvimento com acesso a uma quantidade limitada, mas gratuida, de GPU.

# Resultados

### Experimento 1

No primeiro experimento investigamos se é possível identificar a probabilidade da presença de mVI olhando para a média, o valor máximo ou mínimo entre um fragmento dos dados. Os valores de AUC na validação tanto para a média quanto para o máximo foram semelhantes, cerca de 42%. Conjecturamos que essa característica decorre da perda de informações discriminativas das lesões. Isso é, quanto maior era a quantidade de slices em um voxel, mais frames eram combinados. Diminuindo a importância individual das amostras.

Já o valor mínimo gerou uma melhora de 10% na AUC na validação, com relação ao anterior. Embora o mesmo problema da perda de informações discriminativas ocorra aqui também, usando o valor mínimo entre um subconjunto de slices aumentou a capacidade de identificação das micro-invasão. Podemos explicar essa melhora, pois, em geral, as lesões contêm valores baixos de intensidade. Sendo assim, ao considerarmos a região com mais baixa intensidade, conseguimos identificar automaticamente a lesão. E como vimos anteriormente, a mVI pode estar localizada na lesão, ou tangenciando ela. A AUC durante o treinamento para o mínimo chegou a 70%. A diferença entre os valores de teste e treinamento sugere que a rede de especificou aos dados de treino. Para lidar com isso, usamos regularização nas camadas de convolução, entretanto, não conseguimos angariar uma melhora significativa.


### Experimento 2

No segundo experimento, partimos para a exploração da rede convolucional 2D. A principal diferença dessa abordagem para a anterior, é que o label do voxel foi estendido para todas os slices, independentemente se o frame contém ou não informações do fígado. 

Antes mesmo de testarmos essa abordagem já sabíamos haver uma grande probabilidade dos resultados serem baixos, visto que estamos adicionando muito ruído a rede dizendo que amostras que não retratam a lesão são tratadas como se tivessem. Os resultados da AUC para esse teste ficou abaixo de 20% na validação.

### Experimento 3

Considerando os resultados de baixa qualidade, consideramos realizar a inferência usando não mais a rotulação por paciente, mas sim por slice. Para isso, manualmente anotamos quais amostras continham o nódulo. Verificamos que quanto maior o tamanho da lesão, mas slices contêm tal informação. Como mencionado na seção de análises realizadas, tivemos que fixar um tamanho máximo para a profundidade do voxel. Baseado em trabalhos anteriores, fixamos esse valor em 8 frames. Assim, para cada paciente, consideramos 8 frames a partir do primeiro que mostra uma lesão hepática.

<p float="center">
  <img src="/assets/ex3_resultados.png" />
</p>

Com essa abordagem conseguimos reduzir significativamente a taxa de falso negativo, como mostra o gráfico de recall na imagem acima. Porém, o algoritmo ainda erra mais de 50% dos casos positivos, como descrito no gráfico da precisão.

Tentamos reduzir o erro adicionando regularização nas camadas, porém não conseguimos um bom balanço entre a precisão e a revocação.

### Experimento 4

Em seguida, considerando os 8 slices a partir da primeira ocorrência da lesão, testamos novamente a rede 2D. Na tabela abaixo, mostramos os resultados angariados em cada conjunto. Os valores do teste foi computado usando a melhor configuração dos parâmetros explorados. Notem que as métricas de avaliação do conjunto de teste foram substancialmente maiores e melhores que as do conjunto de validação. Sugerindo que existe alguma característica no conjunto de validação de dificulta a identificação das invasões microvasculares.

Buscamos compreender se o tamanho da lesão estava influenciando nos resultados da classificação, entrementes, não encontramos nenhum padrão entre o tamanho as amostras e as taxas de falso positivo e negativo. 

|Conjunto | Loss | Acc | Prec | Recall | AUC|
|-|-|-|-|-|-|
|Treinamento| 0.9241  | 0.6711  | 0.6711  | 0.6711  | 0.7242  | 
|Validação | 6.4818| 0.4262| 0.4262| 0.4262| 0.3321| 
|Test | 3.7914 | 0.6824 | 0.6824 | 0.6824 | 0.6968 | 

### Experimento 5

resultados com o crop fixo

### Experimento 6

resultados com o crop da região específica

# Discussão

Nesse projeto, pudemos entender que trabalhar com imagens médicas volumétricas de exames de ressonância magnética, impõe desafios significativos, especialmente considerando a complexidade do problema abordado.

Como visto na seção de experimentos, não conseguimos alcançar resultados satisfatórios no conjunto de validação. Contudo, no treinamento, a rede foi capaz de identificar a presença das invasões de forma promissora. Essa característica sugere que o modelo se especializou nos dados de treino. Todavia, no fim do _grid search_, quando testamos no conjunto de teste, verificamos que o modelo foi capaz de classificar corretamente as amostras com grau promissor de certeza, amostras essas que nunca tinham viso vistas pelo classificador. Dessa forma, buscamos encontrar alguma ligação entre as imagens e os resultados que justificassem tal comportamento, porém não identificamos nada. 

Em trabalhos futuros, iremos adicionar no topo da rede uma camada chamada CancelOut(CO) para verificar quais são regiões da imagem ou volume e mais contribuem para a inferência. Essa camada é similar a camada fully-connected (FC), exceto porque os neurônios da FC se conectam com todas as entradas, enquanto os neurônios da CO tem apenas uma conexão com uma entrada em particular. A intuição primordial por trás dessa técnica consiste em ponderar as entradas durante o treinamento de tal forma que características irrelevantes são canceladas comum peso negativo, ao passo que as que contribuem mais no processo de aprendizagem são positivamente ponderadas.

Apesar dos baixos resultados, podemos concluir que não é possível identificar uma invasão microvascular olhando para o voxel do paciente, sem antes fazer um filtragem dos slices que, pelo mesmo, descrevem a região do fígado.

Ademais, a detecção da invasão é mais promissora quando olhamos para cada slice, e não para todo o voxel. Isso não parece lógico, dado que certas informações discriminativas são vistas apenas quando olhamos para as três dimensões. Porém, acreditamos que a limitação esteja correlacionada a adequação da rede. Talvez teríamos que aumentar a profundidade das camadas internas, visto que dessa forma, traços finos das classes são salientados, como reportados em vários trabalhos de visão computacional. Contudo, isso requer uma grande capacidade computacional, a qual não dispomos no momento.

Olhar apenas para a lesão mais cerca de 1 centímetro dela não proporciona melhora no processo de inferência. Conjecturamos que essa característica se dá ao fato de uma região maior da periferia da lesão não ser considerada. Reduzindo a margem para identificação da lesão.


# Conclusão

Desenvolvemos e exploramos métodos para identificação de invasão microvascular em lesões no fígado. Verificamos que esse não é um problema fácil de se resolver, visto que existem diversas limitações que podem prejudicar o processo de tomada de decisão.

Em suma, não é possível identificar invasões olhando apenas para a região da lesão, como já havia sido documentado na literatura, a periferia do carcinoma é peça fundamental para a detecção.

As redes neurais convolucionais 3D, apesar de serem ferramentas poderosas, elas exitem um auto poder computacional para que o modelo se adéque aos dados e possa com precisão e sensibilidade classificar os voxels.

As redes 2D são uma alternativa para superar tal impasse, no entanto, isso exigirá um esforço coletivo junto a especialistas da área para identificar os slices que descrevem uma lesão, - processo esse que pode ser automatizado, com outro classificador, mas de lesões.


# Trabalhos Futuros

Em trabalhos futuros, iremos explorar meios para refinar o processo de tomada de decisão, usando técnicas de explicabilidade e segmentação automatica por saliência.

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
