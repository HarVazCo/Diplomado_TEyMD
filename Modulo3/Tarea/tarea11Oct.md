## Parámetros $\beta$
---
- Modelo $\log - \log$:

  En este tipo de modelos $\log{(Y_i)} = \beta_1 + \beta_2 \log{(x_{i2})}+ u_i$ a $\beta_2$ se le conoce como *elasticidad* de *y* respecto a *x*, y mide el cambio porcentual de $Y_i$ respecto a un cambio porcentual de $x_{ik}.$

  **Ejemplo:** si $\beta_2 = 0.4$, un aumento del $1\%$ en $x_{ik}$ provoca un aumento del $0.4\%$ en $Y_i$.

- Modelo $\log - lineal$:
  
  Para un modelo $\log{(Y_i)} = \beta_1 + \beta_2 x_{i2} + u_i$ a $\beta_2$ se le conoce como *semielasticidad* y mide el cambio porcentual de $Y_i$ por una unidad de $x_{ik}$, es decir que para un aumento de una unidad de $x_{ik}$ cambia $Y_i$ en $100\times \beta_2 \%.$

  **Ejemplo:** si $\log{(salario)} = 1 + 0.01\ experiencia$, cada año de experiencia aumenta el salario en $1\%.$

- Modelo $lineal-\log$:
  
  Para un modelo $Y_i = \beta_1 + \beta_2 \log{(x_{i2})} + u_i$ a $\beta_2$ se le conoce como *semielasticidad* y mide el cambio por unidad absoluta en $Y_i$ por cambio porcentual de $x_{ik}$, es decir que para un aumento del $1\%$ de $x_{ik}$ cambia $Y_i$ en $ \beta_2/100$ unidades.

  **Ejemplo:** si $salario = 1 + 500\ \log{(experiencia)}$, cada $1\%$ de experiencia aumenta el salario en $5$ pesos.


## Prueba de multicolinealidad (Índice de condición)
---
Recordando que en notación matricial el MLRM se ve de la siguiente forma
$$\mathbf{Y} = \pmb{X\beta} + \mathbf{u}$$
y que el estimador de mínimos cuadrados es 
$$\pmb{\hat{\beta}} = (\pmb{X'X})^{-1} \pmb{X'Y}.$$

El índice de condición se obtiene a partir de calcular los valores propios de la matriz $\pmb{X'X}$, a partir de estos valores se deriva el *número de condición* $(k)$, el cual se define como
$$ k = \frac{\text{Valor propio máximo}}{\text{Valor propio mínimo}}$$
y el índice de condición 
$$IC = \sqrt{k}.$$

**Regla de dedo para $IC$:** Si el $IC$ es menor a $10$ no hay un problema grave de multicolinealidad, para valores entre 10 y 30, hay multicolinealidad entre moderada y fuerte, y si excede de 30, una multicolinealidad grave.

## Prueba de Chow
---



---
## Referencias 

- Wooldridge, J. M. (2009). *Introductory Econometrics: A Modern Approach* (4a ed.). Mason, Ohio: South Western Cengage Learning.
- Gujarati, D. N. (2015). *Econometría* (5a ed.). México, D.F.: McGraw-Hill/Interamericana Editores S.A. de C.V.