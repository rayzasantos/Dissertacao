# Similaridade entre poços com DTW e clustering hierárquico

Código da minha dissertação de mestrado em Estatística (PIPGEs, ICMC-USP/UFSCar, 2026): *Aprendizado Não Supervisionado para Análise de Similaridade em Perfilagem de Poços de Petróleo via Dynamic Time Warping e Agrupamentos Hierárquicos*.

## O problema

Perfis geofísicos de poço são séries medidas ao longo da profundidade. Comparar dois poços ponto a ponto não funciona bem, porque as mesmas camadas aparecem em profundidades e espessuras diferentes de um poço para outro. O Dynamic Time Warping (DTW) alinha as séries antes de medir a distância entre elas, e o clustering hierárquico agrupa os poços a partir dessas distâncias, sem rótulos prévios.

## Dados

30 poços de cinco bacias sedimentares brasileiras (Sergipe, Recôncavo, Potiguar, Parnaíba e Solimões), com os perfis GR, RHO, PHI, PE e DT. Os poços vêm do acervo público de arquivos DLIS da ANP. A amostra é exploratória e não representa toda a população de poços das bacias.

## Método

- pré-processamento padronizado das séries;
- DTW exato univariado, dentro de cada poço e entre poços;
- clustering hierárquico sobre as matrizes de distância DTW;
- escolha do número de grupos e avaliação com os índices de Silhueta, Dunn e Davies-Bouldin e com a correlação cofenética;
- dendrogramas com as séries reamostradas na ordem das folhas.

## Arquivos

- `Pipeline_Oficial.ipynb`: fluxo principal da análise
- arquivo `.zip`: dados já pré-processados

## Como rodar

Use Python 3 com numpy, pandas, scipy, scikit-learn e matplotlib. Descompacte os dados na pasta do notebook e execute `Pipeline_Oficial.ipynb` do início ao fim.

## Painel interativo

Os dados também podem ser explorados no [dashboard da dissertação](https://github.com/rayzasantos/Dashboard_Disserta-o), feito em Dash.
