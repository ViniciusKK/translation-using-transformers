# translation-using-transformers

## Visão Geral

Este repositório apresenta a implementação de um modelo de tradução utilizando Transformers. O treinamento do modelo foi realizado utilizando CPU e GPU para compararmos a eficiência de cada um.

## Desempenho do Treinamento

Tempo de treinamento com GPU (10 epochs): 18 minutos

Tempo de treinamento com CPU (1 epoch): 4149.31 segundos (~1 hora e 9 minutos)

A diferença de tempo de treinamento deixa evidente a vantagem do paralelismo proporcionado por uma GPU, que acelera significativamente o processo.

## Comentários sobre o notebook

Este código implementa um modelo de tradução automática baseado na arquitetura Transformer, utilizando TensorFlow e TensorFlow Text. A implementação segue o tutorial oficial do TensorFlow, com adaptações para o dataset ``ted_hrlr_translate/pt_to_en``, que contém pares de frases em português e inglês. O modelo é composto por camadas de encoder e decoder, com mecanismos de atenção multi-head e máscaras de padding e look-ahead para garantir que o modelo não "cole" em tokens futuros durante o treinamento. A tokenização é feita utilizando um tokenizer pré-treinado, e o treinamento é realizado com uma taxa de aprendizado personalizada (CustomSchedule) e otimizador Adam. O código também inclui funções para cálculo de loss e acurácia, além de um sistema de checkpoint para salvar o modelo durante o treinamento.

Durante o treinamento, o modelo foi avaliado em 10 épocas, com métricas de loss e acurácia sendo monitoradas. A função de tradução (Translator) foi implementada para gerar previsões a partir de frases em português, utilizando o modelo treinado. Dois exemplos de tradução foram testados: "este é um problema que temos que resolver." e "os meus vizinhos ouviram sobre esta ideia.", ambos com resultados próximos ao ground truth, mas com pequenas variações, como a adição da palavra "that" na primeira tradução.