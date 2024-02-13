# Modelo Preditivo de Crédito

O presente projeto tem como objetivo criar um modelo preditivo do dataset "German Credit Data". Buscou-se prever o perfil "mau pagador" com base nas informações contidas nos dados.

## Características do dataset

O dataset pode ser encontrado na seguinte localização: <https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data>. Possui 21 atributos e 1000 linhas. A varíavel alvo é chamada "Class" e possuí o valor "1" para "Good" e 2 para "Bad". Das 20 variáveis utilizadas na previsão 11 são categóricas, 6 inteiras e 2 binarias;

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

## Modelos preditivos do perfil "mau pagador" do dataset "German Credit Data"

Foi utilizada a linguagem Python na realização do trabalho. Para limpeza dos dados e preparação do dataset, a biblioteca pandas foi escolhida. Os modelos foram empregados através da biblioteca scikit learn. Os três modelos de classificação escolhidos foram: Regressão Logistica, Random Forest Classifier e o Multi-layer Perceptron Classifier, uma rede neural. Os dados foram dividos entre treinamento e teste com 70% dos dados para treinamento e 30% para teste nos três classificadores. O argumento "random_state" possui o mesmo valor nos 3 classificadores, para que tratassem dos mesmo dados. Também foi avaliada a acurácia, precisão, revocação e F1-score dos modelos. Por fim, na Regressão Logística foi avaliado os coeficientes das variáveis e no Random Forest a importância das caracteristicas. 


