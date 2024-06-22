---
title: Medição e Cálculo de Erro com Folha de Árvore
date: 2024-06-22 16:00:00
cover: /img/mt.png
tags:
  - medição
  - métodos numéricos
  - cálculo
---

# Medição e Cálculo de Erro com Folha de Árvore

Para essa atividade, pegamos uma folha de árvore, marcamos cinco pontos e utilizamos métodos numéricos para calcular o erro na medição. O objetivo era aplicar os conhecimentos para entender a precisão das medições feitas manualmente.

## Medições e Cálculos

### Imagem da Folha com as Medições

![Folha com Medições](/img/folha.png)


### Código Utilizado

O código abaixo foi usado para calcular pela forma de Newton com os pontos medidos na folha:

```python
# Código de Interpolação Polinomial de Newton sem usar bibliotecas

def interpolacao_newton(x, y):
    n = len(x)
    coeficientes = [0] * n
    for i in range(n):
        coeficientes[i] = y[i]

    for j in range(1, n):
        for i in range(n-1, j-1, -1):
            coeficientes[i] = float(coeficientes[i] - coeficientes[i-1]) / (x[i] - x[i-j])

    return coeficientes

def calcular_polinomio(coeficientes, x, x_dados):
    n = len(coeficientes)
    p = coeficientes[-1]
    for k in range(1, n):
        p = coeficientes[n-1-k] + (x - x_dados[n-1-k]) * p
    return p

# Dados dos pontos medidos
x_dados = [1.5, 3.5, 6.3, 8.4, 10.5]
y_dados = [2.3, 3.0, 3.6, 2.8, 2.0]

# Calcula os coeficientes do polinômio de Newton
coeficientes = interpolacao_newton(x_dados, y_dados)

print("Coeficientes do polinômio interpolador de Newton:")
print(coeficientes)

# Calcula o valor do polinômio para vários pontos
x_teste = [min(x_dados) + i * (max(x_dados) - min(x_dados)) / 99 for i in range(100)]
y_teste = [calcular_polinomio(coeficientes, x, x_dados) for x in x_teste]

print("Valores do polinômio P(x) para os pontos de teste:")
print(y_teste)
```
### Resultado no codigo

![Resultado do codigo](/img/Refolha.png)