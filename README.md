# Modelo Transformer para Tradução de Português para Inglês

## Descrição
Este projeto implementa um modelo Transformer utilizando TensorFlow para traduzir frases do português para o inglês. O dataset utilizado é o `ted_hrlr_translate/pt_to_en`, e o objetivo principal foi explorar as capacidades dos Transformers na tarefa de tradução.

## Resultados
### Pontos Positivos:
- **Paralelização e Eficiência**: Diferente de redes sequenciais como RNNs e LSTMs, os Transformers permitem uma maior paralelização do treinamento. O uso das attention heads possibilita que o modelo observe diferentes partes da frase simultaneamente, o que otimiza o processamento e melhora o desempenho em GPUs.
- **Captura de Relações Complexas**: As attention heads são capazes de capturar relações complexas entre palavras, especialmente quando a posição relativa das palavras na frase é relevante. Isso ajuda o modelo a generalizar melhor para frases com estruturas variadas.
- **Desempenho em Frases Curtas**: O modelo apresentou um bom desempenho em frases curtas, conseguindo capturar o contexto corretamente e gerando traduções coerentes.

### Pontos Negativos:
- **Tempo de Treinamento**: O tempo de treinamento do Transformer foi significativamente longo, o que torna o processo de teste e iteração mais demorado. A impressão que obtive do processo, é que essa arquitetura tende a usar muito recurso computacional, que pode aumentar consideravelmente de acordo com o número de attention heads.
- **Dificuldades com Frases Longas**: O modelo teve problemas para traduzir frases mais longas, apresentando algumas alucinações e perda de precisão. O uso de mais attention heads pode levar a uma melhora na acurácia, em detrimento de um maior uso de recursos.

## Conclusões
O Transformer apresentou resultados satisfatórios em termos de paralelização e captura de relações complexas entre palavras. Entretanto, o tempo de treinamento prolongado e a dificuldade em lidar com frases mais longas são desafios que podem ser abordados com ajustes nos hiperparâmetros e mais experimentação. O modelo tem potencial de ser aplicado em contextos além do NLP, como outros domínios onde a posição relativa e o contexto são decisivos, como em fotos ou análises de imagem.

## Pontos a melhorar
- Ajustar os hiperparâmetros para melhorar a performance em frases longas.
- Explorar técnicas como **fine-tuning** em datasets maiores para potencializar a capacidade de generalização.
- Implementar regularizações como **dropout** ou **early stopping** para mitigar overfitting e acelerar o treinamento.
