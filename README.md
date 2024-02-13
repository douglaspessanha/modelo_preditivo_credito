# Modelo Preditivo de Crédito

O presente projeto tem como objetivo criar um modelo preditivo do dataset "German Credit Data". Buscou-se prever o perfil "mau pagador" com base nas informações contidas nos dados. O notebook presente neste repositório contém o código comentado com explicação detalhada de cada passo.  

## 1. Problema de Negócio

Saber se um cliente é bom ou mau pagador é importante para minimizar riscos ao oferecer serviços bancários aos clientes. Pode-se aumentar a oferta de crédito ao bom pagador, bem como diminuir as taxas de juros, o oposto pode ser feito ao mau pagador. Também é possível correr mais riscos com os bons pagadores. 


## 2. Características do Dataset

O dataset pode ser encontrado na seguinte localização: <https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data>. Possui 21 atributos e 1000 linhas. A varíavel alvo é chamada "Class" e possuí o valor 1 para "Good" e 2 para "Bad". Das 20 variáveis utilizadas na previsão 11 são categóricas, 6 inteiras e 2 binarias.


| **Variable Name** | **Description**                                          | **Type**    |
| ----------------- | -------------------------------------------------------- | ----------- |
| Attribute1        | Status of existing checking account                      | Categorical |
| Attribute2        | Duration                                                 | Integer     |
| Attribute3        | Credit history                                           | Categorical |
| Attribute4        | Purpose                                                  | Categorical |
| Attribute5        | Credit amount                                            | Integer     |
| Attribute6        | Savings account/bonds                                    | Categorical |
| Attribute7        | Present employment since                                 | Categorical |
| Attribute8        | Installment rate in percentage of disposable income      | Integer     |
| Attribute9        | Personal status and sex                                  | Categorical |
| Attribute10       | Other debtors / guarantors                               | Categorical |
| Attribute11       | Present residence since                                  | Integer     |
| Attribute12       | Property                                                 | Categorical |
| Attribute13       | Age                                                      | Integer     |
| Attribute14       | Other installment plans                                  | Categorical |
| Attribute15       | Housing                                                  | Categorical |
| Attribute16       | Number of existing credits at this bank                  | Integer     |
| Attribute17       | Job                                                      | Categorical |
| Attribute18       | Number of people being liable to provide maintenance for | Integer     |
| Attribute19       | Telephone                                                | Binary      |
| Attribute20       | foreign worker                                           | Binary      |
| Class             | 1 = Good, 2 = Bad                                        | Binary      |


## 3. Extração e Transformação dos Dados

O projeto foi todo desenvolvido em linguagem Python. As bibliotecas pandas e numpy foram utilizadas para extração e transformação dos dados. 

## 4. Aplicação de Machine Learning

As bibliotecas scikitlearn e scipy foram utilizadas para aplicação dos modelos de Machine Learning. Três modelos de classificação foram escolhidos: Regressão Logística, Random Forest Classifier e o Multi-layer Perceptron Classifier, uma rede neural. Os dados foram dividos entre treinamento e teste com 70% dos dados para treinamento e 30% para teste nos três classificadores. O argumento "random_state" possui o mesmo valor nos 3 classificadores, para aplicação dos modelos nos mesmo dados.

## 5. Avaliação dos Modelos

Foi avaliada a acurácia, precisão, revocação e F1-score dos três modelos. Na Regressão Logística foi determinado os coeficientes das variáveis e no Random Forest a importância das características, ambos com o intuíto de dar interpretabilidade aos modelos.  


| **Avaliação do Modelo** | **Regressão Logística** | **Random Forest** | **Multi-layer Perceptron** |
|-------------------------|:-----------------------:|:-----------------:|:--------------------------:|
| Acurácia                | 0.72                    | 0.73              | 0.55   
| Precisão                | 0.76                    | 0.74              | 0.77
| Revocação               | 0.85                    | 0.94              | 0.45
| F1-score                | 0.80                    | 0.83              | 0.82

## 6. Resultados

A rede neural apresentou os piores resultados dos três modelos. Regressão Logística e Random Forest apresentaram resultados bastante parecidos, entretanto, Random Forest se saiu melhor na revocação. Esta métrica penaliza os falso negativos. No nosso modelo o alvo é "mau pagador", assim, o falso negativo ocorrerá quando o algorítimo classificar um cliente como sendo "bom pagador", enquanto ele não o é. 
O falso negativo é uma situação bastante ruim no caso estudado. Classificar erroneamente alguém como "bom pagador" pode fazer o banco correr riscos desnecessário. A métrica revocação acaba por ser bastante importante.
Apesar da acurácia não ser tão alta, como a revocação é bastante precisa, o Random Forest pode ser usado para ajudar a instituição a tomar decisões com base no perfis bom/mau pagador.