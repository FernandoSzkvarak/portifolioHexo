---
title: Interpolação de Lagrange
date: 2024-06-22 15:00:00
cover: /img/lagrange.png
tags:
  - interpolação
  - métodos numéricos
  - cálculo
---


# Código de Interpolação de Lagrange

#### O Mesmo codigo foi utilizado pra realização dos exercicios da Lista a imagem é meramente ilustrativa apenas para exemplificar como o codigo é estruturado.

## Código em Python

```python
#Codigo em Python que resolve os exercicios na Forma de Lagrange
# Aluno: Fernando Szkvarak Desengrini


def interpolacao_lagrange(x_valores, y_valores, x):
    n = len(x_valores)
    resultado = 0.0
    for i in range(n):
        termo = y_valores[i]
        for j in range(n):
            if i != j:
                termo *= (x - x_valores[j]) / (x_valores[i] - x_valores[j])
        resultado += termo
    return resultado

# Exercício 1
x_valores_1 = [-1, 0, 1, 2]
y_valores_1 = [1, 3, 1, 1]
x_interpolar_1 = 1.5
y_interpolado_1 = interpolacao_lagrange(x_valores_1, y_valores_1, x_interpolar_1)
print(f"Exercício 1: Valor interpolado em x = {x_interpolar_1} é {y_interpolado_1:.2f}")

# Exercício 2
x_valores_2 = [1, 3, 5, 7, 13]
y_valores_2 = [800, 1310, 2090, 2340, 3180]
x_interpolar_2 = 10
y_interpolado_2 = interpolacao_lagrange(x_valores_2, y_valores_2, x_interpolar_2)
print(f"Exercício 2: Valor interpolado em t = {x_interpolar_2}s é {y_interpolado_2:.2f}")

# Exercício 3
x_valores_3 = [11, 12, 13, 14, 15]
y_valores_3 = [2.397895, 2.484907, 2.564949, 2.639057, 2.708050]
x_interpolar_3 = 12.3
y_interpolado_3 = interpolacao_lagrange(x_valores_3, y_valores_3, x_interpolar_3)
print(f"Exercício 3: Valor interpolado em x = {x_interpolar_3} é {y_interpolado_3:.6f}")

```
## Resultado do codigo acima


![Codigo em Python que Resolve no metodo de Lagrange](/img/rela.png)
