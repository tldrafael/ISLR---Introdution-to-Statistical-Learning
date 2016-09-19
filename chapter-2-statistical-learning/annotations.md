# Capítulo 2 - Aprendizado Estatístico

Esse capítulo busca dar a compreensão do que é aprendizado estatístico, ele começa distinguindo dois tipos de variáveis, as variáveis independentes do sistema (os estímulos), representadas como **X**,  e as variáveis dependentes ou resposta, representadas como **Y**. A partir disso, temos a seguinte relação:

```
Y = f(X) + e
```

```
Y =  valor da resposta
f(X) = representação de uma informação sistemática de X por Y.
e = termo de erro.
```

Aprendizado Estatístico é um conjunto de técnicas para estipulação de *f*, e assume dois papéis: a Predição e a Inferência. 


## Predição

Predição preocupa-se especialmente com a acurácia da resposta especulada, o foco não é entender o quanto e como uma variável se relaciona com a resposta, e sim criar respostas precisas. Por isso, muitas vezes são adotados modelos de difícil interpretabilidade, como SVM, mas que detém grande poder de precisão. **F^** é tratada frequentemente como uma caixa preta.

```
Ŷ = f^(x)

f^ = função especulada.
Ŷ = resposta especulada.
``` 

O erro entre `|Y - Ŷ|` é dividido em duas partes: `erro reduzível e erro irreduzível`. O **erro reduzível** pode ser diminuído a cada melhora da estimativa de *f*. O **erro irreduzível** - apresentado como *e* acima - não pode ser estimado por **X** , porque esse erro está relacionalado a alguma variável não-observada ou aleatoriedades. 

## Inferência

O papel principal da inferência é entender como variáveis distintas relacionam-se, como a alteração no valor de uma afeta o valor de uma segunda variável. Se essa relação é positiva ou negativa, se é uma relação linear ou não. Para a inferência, são priorizados modelos que favoreçam a interpretalidade como regressão linear.

## Overfitting

Acontece quando a função especulada segue muito estreitamento os padrões do dataset de treinamento, seguindo inclusive seus 'ruídos' e 'erros' (*erro irredutível*), ruídos que não estarão presente em outros datasets.

---
---

## Bias-Variance Trade-Off

### Bias

Taxa de erro da função `|Y - Ŷ|`, o quanto a função falha em *encaixar* os dados do dataset de treinamento.

### Variância

O quanto a função especulada é sensível a mudança na alteração do dataset de treinamento. Modelos de alta flexibilidade, acabam por encaixar perfeitamente todos os dados dentro da imagem da função, contudo, caso o dataset de treinamento mude, a imagem da função mudará o quanto for necessário para assumir a forma dos novos dados.

### Trade-Off

Modelos com muita flexibilidade tendem a ter low-bias e high-variance, podendo causar overfitting nos datasets de treinamento. Modelos inflexíveis como regressão linear costumam apresentar high-bias e low-variance, se o número de dados for grande o suficiente, a reta apresentada será robusta ao dataset de treinamento.

---
---


## Classificação

Classificação trabalha com respostas qualitativas, categorias, classes.

### The Bayes Classifier 

The Bayes Classifier é uma probabilidade condicional, que prediz a classe de acordo com a probabilidade que esse apresente dado o vetor X.

```
Pr(Y=j|X=xo)
```
Como o classificador Bayes produz o menor test-error-rate, seu erro é análogo ao error irreduzível.

Como nem sempre sabemos a distribuição condicional de Y dado X, o classificador Bayes serve como um padrão ouro inalcançável, comparando-o com outros métodos.

### K-Nearest Neighbors

Os outros métodos buscam usar probabilidade condicional. KNN é um desses. Calcula a probabilidade de uma classe *j* para dado vetor **X**  a partir da média dos N-vizinhos mais próximos que sejam da classe *j*.

Quanto maior *N* número de vizinhos, mais flexível é o modelo e maior chance de overfitting.

