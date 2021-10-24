<img src="https://github.com/KarlaLutz/cripto/blob/main/Funda%C3%A7%C3%A3o%20Get%C3%BAlio%20Vargas.jpg">

### Objetivo

Criar modelo preditivo para análise de imagens Raios-X de pulmões de crianças onde será possível identificar com acurácia se a imagem indica que a criança possui pneumonia ou não.

### Breve Descrição do Dataset Utilizado

O conjunto de dados proposto foi disponibilizado pelo professor e será uutilizado para avaliar o desempenho do modelo. Este conjunto consiste em um total de 5.863 imagens de raios-X (JPEG) do tórax de pacientes com idade entre um e cinco anos.
Além disso, o dataset é organizado em três pastas (train, test, val) e contém subpastas para cada categoria de imagem (Pneumonia / Normal). A fim de ilustrar a generalização de diferentes modelos, após obter essa divisão o mesmo foi testado contendo 70%, 10% e 20% do total das imagens. 

### Classificação binária

Para montar este modelo de classificação, geramos um backup em ‘pickle’ para não precisar processar a base de imagens a cada vez que iniciamos uma nova sessão em Colab (pickle files ‘train’, ‘test’ e ‘val’). Com isto conseguimos montar os modelos CNN, usando a técnica de adição de camadas ‘Convulacao+Maxpoling’ iterando com os tamanhos dos filtros desde 32 até 256. Em todas as camadas de convolução usamos stride igual a 1 e para as camadas de Maxpolling um stride igual a 2. O padding utilizado foi o mesmo da convolução (‘same’). Tanto no modelo 1 quanto no modelo 2 se obtiveram Recall acima do 90%, tanto para detecção de casos normais quanto com pneumonia.

### Data Augmentation

Temos como definição que Data Augmentation são técnicas usadas para aumentar a quantidade de dados adicionando cópias ligeiramente modificadas de dados já existentes ou dados sintéticos a partir de dados existentes. Ele atua como um regularizador e ajuda a reduzir o overfitting ao treinar um modelo de aprendizado de máquina.
Então para nosso caso vamos expandir artificialmente nosso conjunto de dados de treino utilizando dessas técnicas, deixando-o enriquecido com tais variações das imagens dos Raios-X que já existem obtendo um dataset bem mais robusto.

### Classificação Multi-classe

Conseguimos montar modelos de classificação multi-classe onde a principal diferença com a classificação binária foi : (1) na carrega das imagens para arrays onde precisamos estender ate 3 categorias de pulmao (pickle files ‘train_cat’, ‘test_cat’ e ‘val_cat’) e (2) na definição de nosso loss function dentro do modelo cnn, onde invés de usar ‘binary_crossentropy’ mudamos para ‘sparse_categorical_crossentropy’. 

### ExplanabeAI

ExplanabeAI é uma inteligência artificial onde os resultados da solução do modelo preditivo gerado podem ser compreendidos por humanos. Isso contrasta com o conceito de "caixa preta" no machine learning.
Utilizaremos o ExplanabeAI para plotarmos de forma clara quais foram os pontos das imagens que o modelo considerou como pontos chaves para determinar que aquela imagem em específico teve uma classificação como Pneumonia ou Normal.

### Conclusões

Após termos as análises dos modelos montados a partir dos datasets dividimos, notamos que ao rodarmos o CNN diretamente no dataset de treino sem nenhum tipo de data augmentation, temos a presença de um overfitting. Justamente devido a esses resultados, notamos que a quantidade de imagens Normais são muitos desiguais em relação as imagens de Pneumonia, por isso foi realizado o procedimento do Data Augmentation e ao rodar novamente o modelo com o dataset incrementado, obtivemos resultados mais realistas onde caso uma nova imagem for inserida, conseguimos ter a certeza que nosso modelo conseguirá processá-la e categorizá-la corretamente.

A performance de nossos modelos de classificação binária foram muito boas, tanto o modelo sem data augmentation quanto o modelo com data augmentation. Nossos modelos conseguiram aprender com bastante eficácia a diferença entre um pulmão normal e um pulmão doente (pneumonia). Mas é muito recomendado incrementar nossa base de treino com novos features utilizando técnicas de data augmentation.

Já no exercício de classificação multi-classe não foi possível conseguir um modelo com uma boa performance. Tal parece que o modelo precisa de mais dados (imagens) de casos com pneumonia bacteriana e viral para conseguir aprender a diferença entre estas duas doenças. Para este último foram executados vários modelos onde alternamos a função de ativação na última camada, gerando um melhor desempenho com a função 'sigmóide'. 
