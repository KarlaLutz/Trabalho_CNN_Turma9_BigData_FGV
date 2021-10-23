<img src="https://github.com/KarlaLutz/cripto/blob/main/Funda%C3%A7%C3%A3o%20Get%C3%BAlio%20Vargas.jpg">

### Objetivo

Criar modelo preditivo para análise de imagens Raios-X de pulmões de crianças onde será possível identificar com acurácia se a imagem indica que a criança possui pneumonia ou não.

### Breve Descrição do Dataset Utilizado

O conjunto de dados proposto foi disponibilizado pelo professor e será uutilizado para avaliar o desempenho do modelo. Este conjunto consiste em um total de 5.863 imagens de raios-X (JPEG) do tórax de pacientes com idade entre um e cinco anos.
Além disso, o dataset é organizado em três pastas (train, test, val) e contém subpastas para cada categoria de imagem (Pneumonia / Normal). A fim de ilustrar a generalização de diferentes modelos, após obter essa divisão o mesmo foi testado contendo 70%, 10% e 20% do total das imagens. 

### Data Augmentation

Temos como definição que Data Augmentation são técnicas usadas para aumentar a quantidade de dados adicionando cópias ligeiramente modificadas de dados já existentes ou dados sintéticos a partir de dados existentes. Ele atua como um regularizador e ajuda a reduzir o overfitting ao treinar um modelo de aprendizado de máquina.
Então para nosso caso vamos expandir artificialmente nosso conjunto de dados de treino utilizando dessas técnicas, deixando-o enriquecido com tais variações das imagens dos Raios-X que já existem obtendo um dataset bem mais robusto.

### ExplanabeAI

ExplanabeAI é uma inteligência artificial onde os resultados da solução do modelo preditivo gerado podem ser compreendidos por humanos. Isso contrasta com o conceito de "caixa preta" no machine learning.
Utilizaremos o ExplanabeAI para plotarmos de forma clara quais foram os pontos das imagens que o modelo considerou como pontos chaves para determinar que aquela imagem em específico teve uma classificação como Pneumonia ou Normal.

### Conclusões


