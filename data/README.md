# Justificativa

Projeto com base de dados como parte de trabalho aprovado no Comitê de Ética em Pesquisas Institucional. Foi necessário um termo de compromisso, onde os pesquisadores se comprometeram a zelar pelas informações e assegurar o sigilo e a confidencialidade dos participantes da pesquisa. Nenhum (a) participante terá seu nome revelado publicamente. Foi respeitada assim a Resolução 466/2012 e a Resolução 510/2016 do Conselho Nacional de Saúde que se fundamentam nos principais documentos internacionais sobre pesquisas envolvendo seres humanos.

Embora os dados não possam ser divulgados, fornecemos uma descrição detalhada do mesmo.

Parâmetros quantitativos de hipervascularização arterial e lavagem do contraste dos carcinomas foram calculados. “Regiões de Interesse” (ROIs) foram circuladas manualmente nas lesões e em duas regiões de parênquima do fígado adjacente aos CHCs, nas imagens pré-contraste e nas fases arterial, portal e equilíbrio após a injeção do meio de contraste. 
Subsequentemente, os seguintes parâmetros quantitativos foram calculados, baseados nas relações dos valores extraídos com as medidas objetivas de densidades:

- Diferença de atenuação (DA): diferença entre a atenuação da lesão e
a média da atenuação do parênquima adjacente; foi calculada em
todas as fases do estudo dinâmico (arterial, portal e equilíbrio).

- Razão de atenuação (RA) na fase portal - RAP: RAP =100×(AMP
/ALP), onde P = fase portal, AM = atenuação média do parênquima e
AL = atenuação da lesão;

Razão de atenuação (RA) na fase de equilíbrio - RAE: RAE
=100×(AME /ALE), onde E = fase de equilíbrio, AM = atenuação média
do parênquima e AL = atenuação da lesão;

- Razão de “washout” relativo (RWR) na fase portal - RWRP: RWRP
=100× (ALA − ALP) / ALA, onde A = fase arterial, P = fase portal e AL =
atenuação da lesão;

- Razão de “washout” relativo (RWR) na fase de equilíbrio - RWRE:
RWRE =100× (ALA − ALE) / ALA, onde A= fase arterial, E = fase de
equilíbrio e AL = atenuação da lesão;

Estes parâmetros quantitativos do exame de tomografia computadorizada foram comparados com a presença ou ausência de invasão microvascular confirmados anatomopatologicamente. 

## Features tabulares

| Nome da Feature |  Descrição |
|-|-|
| paciente | Nome do paciente |
| num_nod | Numero adotado para o nódulo em análise |
| hc | Identificador do hospital |
| data_tc | Data da tomografia computadorizada |
| data_tx_cx | data transplante |
| delta_tc_tx_dias | data entre o transplante e a tomografia  |
| loc_nod |  Localização do nódulo considerando as diferentes segmentações do figado |
| tam_nod_tc_cm | Tamanho do nódulo identificado na tomografia em centímetros |
| par_portal | par na fase portal |
| par_equi | par na fase equilíbrio |
| ac_arterial | ac na fase arterial |
| ac_portal | ac na fase portal |
| ac_equi | ac na fase equilíbrio |
| rwr_portal | Razão do washout na fase portal |
| rwr_equi | Razão do washout na fase equilíbrio |
| aef | alfafetoproteína |
| invasao_microvascular | Se ha ou não a presença de invasão microvascular |
| grau_histologico | O grau histológico do paciente |
| sexo | Gênero do paciente |
| data_nasc | Data de nascimento do paciente |
| idade_tx_cx | Tempo entre o transplante e cx |
| causa_hepatopatia | O que causou a hepatopatia |
| recorrencia | Se o carcinoma retornou após a intervenção cirúrgica |
| obito | Se o paciente foi a óbito |
| afp_pre | valores extraídos do exame alfafetoproteína |
| data_afp | data do exame alfafetoproteína |


## Imagens de radiografia como Features

As imagens são representadas por volumes. Cada tomografia possuem várias fases. Nesse trabalho levaremos em consideração somente a fase arterial, equilíbrio e portal.