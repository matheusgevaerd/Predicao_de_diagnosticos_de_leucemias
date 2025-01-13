# Predição de diagnósticos de leucemias por meio da análise de lâminas de sangue periférico

#### Aluno: [Matheus Barbosa Gevaerd](https://github.com/matheusgevaerd)
#### Orientadora: [Professora Manoela Kohler](https://github.com/manoelakohler).
---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".


- [Link para o código](https://github.com/matheusgevaerd/Predicao_de_diagnosticos_de_leucemias_por_meio_da_analise_de_laminas_de_sangue_periferico/blob/main/Predic%CC%A7a%CC%83o_de_diagno%CC%81sticos_de_leucemias_por_meio_da_ana%CC%81lise_de_la%CC%82minas_de_sangue_perife%CC%81rico%20(1).ipynb)).

---

### Resumo

Introdução: o trabalho utiliza duas bases de dados abertas (subtypes_of_leukemia_blood_cell_microscopic_image e leukemia_dataset) com imagens de lâminas de sangue periférico de leucemias e de pacientes saudáveis. Em conjunto, as bases possuem 18.000 imagens agrupadas em cinco diferentes grupos: Leucemia Linfóide Aguda (LLA), Leucemia Mieloide Aguda (LMA), Leucemia Linfocítica Crônica (LLC), Leucemia Mieloide Crônica (LMC) e Imagens de Pacientes Saudáveis (Normal). Objetivo: desenvolver um modelo eficaz de deep learning para detecção de leucemias a partir de imagens de lâminas de sangue periférico. Para isso, pretende-se utilizar um modelo pré-treinado e por meio de transfer learning introduzir os parâmetros necessários para a correta identificação. Além disso, o Grad-CAM também será utilizado no trabalho e é uma ferramenta importante nesse caso pois indica quais partes da imagem estão sendo determinantes para a categorização. Dessa forma, os especialistas na área podem confirmar a correta análise do modelo e o que está sendo analisado na imagem da lâmina de sangue periférico. Modelagem: o projeto utiliza a rede convolucional MobileNetV2, escolhida pois trata-se de um problema multiclasse e com imagens complexas de microscopia. O modelo da rede neural foi elaborado de acordo com os parâmetros da rede citada após a adição de camadas personalizadas no processo de transfer learning. Resultados: 98,8% de acurácia e 3,6% de perdas no conjunto teste, 99,9% de acurácia e 0,3% de perdas no conjunto de treinamento, 99% de acurácia e 4,1% de perdas no conjunto de validação. Em relação aos dados específicos de cada categoria, o modelo testado teve 100% de precisão na identificação de lâminas com células normais.

### Abstract 

Introduction: This paper uses two open databases (subtypes_of_leukemia_blood_cell_microscopic_image and leukemia_dataset) with images of peripheral blood slides from leukemias and healthy patients. Together, the databases have 18,000 images grouped into five different classes: Acute Lymphoid Leukemia (ALL), Acute Myeloid Leukemia (AML), Chronic Lymphocytic Leukemia (CLL), Chronic Myeloid Leukemia (CML) and Images of Healthy Patients (Normal). Objective: to develop an effective deep learning model for detecting leukemias from images of peripheral blood smear. For this, we intend to use a pre-trained model and, through transfer learning, introduce the necessary parameters for correct identification. In addition, Grad-CAM will also be used in the project and is an important tool in this case because it indicates which parts of the image are being decisive for categorization. This way, experts in the field can confirm the correct analysis of the model and what is being analyzed in the peripheral blood smear image. Modeling: the project uses the MobileNetV2 convolutional network, chosen because it deals with a multiclass problem and complex microscopy images. The neural network model was developed according to the parameters of the aforementioned network after adding customized layers in the transfer learning process. Results: 98.8% accuracy and 3.6% losses in the test set, 99.9% accuracy and 0.3% losses in the training set, 99% accuracy and 4.1% losses in the validation set. Regarding the specific data of each category, the tested model had 100% accuracy in identifying slides with normal cells.

### 1. Introdução

O trabalho utiliza duas bases de dados abertas (subtypes_of_leukemia_blood_cell_microscopic_image e leukemia_dataset) com imagens de lâminas de sangue periférico de leucemias e de pacientes saudáveis. Em conjunto, as bases possuem 18.000 imagens agrupadas em cinco diferentes grupos: Leucemia Linfóide Aguda (LLA), Leucemia Mieloide Aguda (LMA), Leucemia Linfocítica Crônica (LLC), Leucemia Mieloide Crônica (LMC) e Imagens de Pacientes Saudáveis (Normal), conforme as imagens abaixo:

<img width="1045" alt="Captura de Tela 2025-01-12 às 20 22 49" src="https://github.com/user-attachments/assets/4d15df91-a977-49c6-a0f1-115a0ec121a2" />

Dessa forma, o objetivo desse projeto é desenvolver um modelo eficaz de deep learning para detecção de leucemias a partir de imagens de lâminas de sangue periférico. Para isso, pretende-se utilizar um modelo pré-treinado e por meio de transfer learning introduzir os parâmetros necessários para a correta identificação.

O Grad-CAM também será utilizado no trabalho e é uma ferramenta importante nesse caso pois indica quais partes da imagem estão sendo determinantes para a categorização. Dessa forma, os especialistas na área podem confirmar a correta análise do modelo e o que está sendo analisado na imagem da lâmina de sangue periférico.

### 2. Modelagem

Importante destacar que o projeto utiliza a rede convolucional MobileNetV2, escolhida pois trata-se de um problema multiclasse e com imagens complexas de microscopia. O modelo da rede neural foi elaborado de acordo com os parâmetros abaixo, após a adição de camadas personalizadas no processo de transfer learning.

Total de parâmetros: 18,315,845 (69.87 MB) / 
Parâmetros treináveis: 16,057,861 (61.26 MB) / 
Parâmetros não-treináveis: 2,257,984 (8.61 MB) /

### 3. Resultados

O conjunto de teste teve boa acurácia e perdas aceitáveis, apesar de desempenho um pouco inferior ao conjunto de treino.

Test score: 0.0369931235909462 /
Test accuracy: 0.9888888597488403

Analisando o histórico abaixo, há a evidencia do correto treinamento do modelo e os resultados aceitáveis no conjunto de testes. Futuramente, com uma quantidade maior de registros no conjunto teste o resultado pode ser ainda mais similar ao conjunto de treino.

<img width="601" alt="Captura de Tela 2025-01-12 às 20 31 37" src="https://github.com/user-attachments/assets/238eba0e-e6d1-47fa-a13f-8f5ab3b78299" />

<img width="598" alt="Captura de Tela 2025-01-12 às 20 31 45" src="https://github.com/user-attachments/assets/b80bb7f7-baf6-4b6f-be1e-87250f690db7" />

Em relação aos dados específicos de cada categoria, o modelo testado apresentou 100% de precisão na identificação de lâminas com células normais, conforme relatório abaixo:

    Classes    precision    recall   f1-score   support
    LLA       0.99      1.00      0.99       724
    LLC       1.00      0.97      0.98       732
    LMA       0.98      0.99      0.98       738
    LMC       0.99      0.99      0.99       718
    Normal    1.00      1.00      1.00       688
    accuracy                      0.99      3600
    macro avg 0.99      0.99      0.99      3600
    weighted avg 0.99   0.99      0.99      3600

Na matriz de confusão é possível destacar a precisão na categoria de indivíduos saudáveis e a baixa confusão no momento de classificação do modelo de maneira geral.

<img width="667" alt="Captura de Tela 2025-01-12 às 20 32 06" src="https://github.com/user-attachments/assets/503e521a-69ab-4672-86ce-1c52768a73d1" />

A análise do Grad-CAM aponta a correta classificação da imagem, destacando em vermelho os pontos principais para a indicação da categoria, cumprindo um dos objetivos do trabalho.

<img width="834" alt="Captura de Tela 2025-01-12 às 20 32 20" src="https://github.com/user-attachments/assets/d4fd5d2a-c8d6-4c78-9de2-54c8db87bb99" />

### 4. Conclusões

O modelo de predição de diagnósticos de leucemias por meio da análise de lâminas de sangue periférico com um conjunto de dados totais de 18.000 imagens apresenta resultados satisfatórios: 98,8% de acurácia e 3,6% de perdas no conjunto teste, 99,9% de acurácia e 0,3% de perdas no conjunto de treinamento, 99% de acurácia e 4,1% de perdas no conjunto de validação.

Importante destacar que o conjunto teste teve menos de 1.000 imagens por categoria, tendo um resultado satisfatório sem uma quantidade grande de imagens.

Trabalhos futuros podem utilizar o modelo em um conjunto de dados de diferentes tamanhos, além de estimar a capacidade de inferência para outras patologias hematológicas (anemias, síndromes mieloproliferativas, distúrbios dos plasmócitos e/ou alterações plaquetárias). Seria possível também subdividir o treinamento com imagens de diferentes aumentos e técnicas de coloração de lâminas (Panótico Rápido e a coloração Giemsa).

---

Matrícula: 222.100.023

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
