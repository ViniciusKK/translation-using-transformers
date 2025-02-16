# translation-using-transformers

## Visão Geral

Este repositório apresenta a implementação de um modelo de tradução utilizando Transformers. O treinamento do modelo foi realizado utilizando CPU e GPU para compararmos a eficiência de cada um.

## Desempenho do Treinamento

Tempo de treinamento com GPU (10 epochs): 18 minutos

Tempo de treinamento com CPU (1 epoch): 4149.31 segundos (~1 hora e 9 minutos)

A diferença de tempo de treinamento deixa evidente a vantagem do paralelismo proporcionado por uma GPU, que acelera significativamente o processo.