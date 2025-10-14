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
La prueba de Chow nos dice si los coeficientes de una regresión son los mismos para un conjunto de datos dividido. 
Considerando el modelo general con $k$ variables explicativas y una constante, y una muestra con dos grupos: $g=1,2$.
$$ Y_{g} = \beta_{1,g} + \beta_{2,g}x_{2,g} + \dots + \beta_{k,g} x_{k,g} + u_g $$
La prueba de Chow busca probar si los coeficientes y las constantes son iguales en los dos, es decir,
$$H_0 : \beta_{1,1} = \beta_{1,2}, \beta_{2,1} = \beta_{2,2}, \dots, \beta_{k,1} = \beta_{k,2},$$
esta hipótesis incluye $k+1$ restricciones.

La prueba consiste en realizar tres estimaciones con el modelo general, una para cada grupo ($Y_1$ y $Y_2$) y la tercera para el conjunto de datos completo $(Y)$. Ya que se tienen las estimaciones, se calcula la suma de residuales cuadrados de cada uno de los modelos:
$$\begin{align*} SRC_1 &= \sum \hat{u}_1^2 \\  SRC_2 &= \sum \hat{u}_2^2 \\ SRC &= \sum \hat{u}^2 \end{align*}.$$

Ya que se tienen las sumas, se calcula el estadístico $F$ de la siguiente manera:
$$ F = \frac{\frac{(SRC - (SRC_1 + SRC_2))}{k+1} }{\frac{SRC_1 + SRC_2}{(n_1 + n_2 - 2(k+1))} } $$
donde $n_1$ y $n_2$ son el número de observaciones del grupo $1$ y del grupo $2$ respectivamente. 

Si no hay un cambio estructural, es decir, $Y_1$ y $Y_2$ son las mismas, $SCR$ y $SCR_1+SCR_2$ no deben ser estadísticamente diferentes. Por lo tanto:
$$ F \sim F_{[k+1,(n_1+n_2-2(k+1))]}. $$

De esta manera, cuando $F$ no excede el valor crítico $ F_{[k+1,(n_1+n_2-2(k+1))]} $, no se rechaza la hipótesis nula de *estabilidad paramétrica*. Caso contrario cuando $F$ es mayor que el valor crítico $ F__{[k+1,(n_1+n_2-2(k+1))]} $, se rechaza la hipótesis nula y se concluye que $Y_1$ y $Y_2$ son diferentes.

Observaciones de la prueba de Chow:
- Se generaliza fácilmente para casos de más de un cambio estructural.
- Dado que la prueba de Chow es simplemente una prueba F, sólo es válida bajo homocedasticidad. Primero se debe asegurar que las varianzas de los residuos de $Y_1$ y $Y_2$ son las mismas.
- Solo dice si las regresiones son las mismas, pero no dice si difieren en las constantes o en los coeficientes.
- Supone que se conocen los puntos de cambio estructural.

---
## Referencias 

- Wooldridge, J. M. (2009). *Introductory Econometrics: A Modern Approach* (4a ed.). Mason, Ohio: South Western Cengage Learning.
- Gujarati, D. N. (2015). *Econometría* (5a ed.). México, D.F.: McGraw-Hill/Interamericana Editores S.A. de C.V.