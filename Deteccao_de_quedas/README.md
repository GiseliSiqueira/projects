### **IOT APLICADA AO MONITORAMENTO DA SAÚDE DE PESSOAS IDOSAS: UM SISTEMA PARA IDENTIFICAÇÃO DE QUEDAS**

---

#### 🎯 Objetivo:
Nesse projeto é desenvolvido um sistema de monitoramento das condições de saúde humana, mais especificamente a ocorrência de quedas de pessoas idosas, utilizando dados de indicadores físicos de saúde obtidos através de dispositivos vestíveis como smartwatches a fim de identificar situações atípicas.

---

#### 🛠️ Tecnologias
Python\
Google Colab\
Pandas\
Matplotlib\
Seaborn\
Scikit-learn

---

#### 🖼️ Cenário
A utilização da IoT unida à capacidade de processamento e a economia de recursos energéticos que os dispositivos embarcados possuem, é adotada em sistemas que auxiliam em tarefas como o monitoramento de áreas para plantação, monitoramento de saúde de pessoas através de dispositivos pervasivos conectados ao corpo, gerenciamento de condição física de produtos, casas com seus ambientes inteligentes, etc. Em vista disso, esse trabalho propõe o desenvolvimento de um algoritmo para detecção de situações atípicas como quedas de pessoas idosas e de outros grupos de pessoas que necessitem de cuidados de saúde específicos através do monitoramento das condições de saúde humana utilizando acelerômetro contidos em smartwatches (Relógios inteligentes) tendo como base o algoritmo descrito em Kostopoulos et al. (2015) onde utiliza-se um smartwatch baseado no sistema Android para dispositivos móveis. Realiza também avaliação da performance preditiva do mesmo utilizando-se a matriz de confusão para exibir frequências referentes a classificação de cada classe analisada em um modelo.

---

#### 📈 Base de dados
Foi utilizado um conjunto de dados multimodal para detecção de quedas coletado através de experimento utilizando 17 pessoas jovens e saudáveis utilizando diversos sensores dos tipos vestíveis, ambientais e dispositivos visuais coletados no trabalho de MartínezVillaseñor (2019). Esse conjunto de dados está disponível [aqui](https://sites.google.com/up.edu.mx/har-up/).

---

#### 🛠️ Preparação dos dados
Foi realizado  pré-processamento dos dados buscando tratar dados de acelerômetro que estavam fora do padrão, filtrar, conhecer as características dos dados e realizar alteração de tipagem.
A base em formato .csv foi convertida para arquivo no formado .xlsx do aplicativo de criação de planilhas Excel para facilitação do entendimento, contendo 47 colunas com dados de acelerômetros colocados em tornozelo, acelerômetro em dispositivos no bolso, acelerômetro no pulso, infravermelho, etc., coletados a uma frequência de 100 Hz.
Os dados considerados foram os tempos no formato de data e hora, os valores de acelerômetro com eixo x, eixo y e eixo z, além das colunas indicando o ID dos sujeitos, atividades e tentativas. As colunas também foram renomeadas para facilitar a utilização do dataset, e a coluna com os tempos foi tratada, sendo convertida para o tipo datetime e posteriormente numérico da linguagem Python.
Para calculo correto da aceleração, também ajustou-se a escala do eixo Y que estava com 7 casas decimais realizando-se para isso o calculo do valor absoluto onde nos casos em que este era maior que 30 dividia-se por 1000.

---

#### 📊 Análise

* Na avaliação utilizando-se apenas o limite superior o algoritmo conseguiu um índice de acurácia de 90%, indicando que utilizando apenas o limite superior consegue detectar corretamente uma queda em aproximadamente 503 simulações do total de 559 analisadas no dataset. Já em relação a revocação, métrica relevante neste trabalho devido ao seu contexto, o algoritmo conseguiu índice de 96% na previsão correta de casos de queda classificados como verdadeiros.\
![alt text](https://github.com/GiseliSiqueira/projects/blob/main/Deteccao_de_quedas/Imagens/image.png)

* Na avaliação utilizando-se os conceitos de limite inferior, janela de tempo e contador, o algoritmo conseguiu um índice de acurácia de 91%, mostrandose melhor em 1% em relação a edição utilizando apenas o limite superior como critério de definição.\
![alt text](https://github.com/GiseliSiqueira/projects/blob/main/Deteccao_de_quedas/Imagens/image-1.png)

* Utilizando-se a abordagem de apenas o limite superior e também a abordagem utilizando todos os critérios de definição de queda como limite inferior, janela de tempo e contador, porém em relação a dados de outros acelerômetros que não o de pulso o algoritmo apresenta bom desempenho na detecção de quedas, podendo-se destacar os índices para o acelerômetro na cintura utilizando apenas o critério do limite superior e todos os critérios definidores de queda, e o acelerômetro no pescoço se utilizando todos os critérios definidores de queda. Em relação a métrica de revocação, o algoritmo mostrou-se bom em classificar situações de queda com índice satisfatório para todos os acelerômetros, destacando-se nos casos de acelerômetro instalado na cintura e levando-se em consideração apenas o limite superior como indicativo de ocorrência de queda.\
![alt text](https://github.com/GiseliSiqueira/projects/blob/main/Deteccao_de_quedas/Imagens/image-2.png)

---

#### 💡 Conclusões
Os resultados mostraram que a utilização apenas do limite superior para o pico da aceleração durante o evento de queda é relevante para caracterizar um evento como queda real, tendo revocação de 96%. O pior desempenho foi obtido na abordagem com todos os critérios de definição de queda aplicados e adicionando-se o critério do pico de aceleração entre os limites superior e inferior, com 65% de revocação. Observou-se ainda que a aplicação do algoritmo em dados de acelerômetro de dispositivos em outras partes do corpo diferentes do pulso obteve desempenho satisfatório, destacando-se os valores obtidos para os dispositivos localizados em regiões menos móveis como cintura e pescoço.

---
Você pode encontrar esse trabalho completo [aqui](https://repositorio.ifes.edu.br/handle/123456789/1803?show=full).

#### Referências
MARTÍNEZ-VILLASEÑOR, Lourdes et al. UP-fall detection dataset: a multimodal
approach. Sensors, v. 19, n. 9, p. 1988, 2019.

KOSTOPOULOS, P. et al. F2D: A fall detection system tested with real data from
daily life of elderly people. In: INTERNATIONAL CONFERENCE ON E-HEALTH
NETWORKING, APPLICATION & SERVICES (HealthCom). 17., 2015.
Proceedings… [S.l.]: IEEE, 2015. p. 397-403.
