# Kata de divisibleCount
https://www.codewars.com/kata/55a5c82cd8e9baa49000004c/train/java

# Análisis

1. Identificar el primer y último número divisible: Encontrar el primer número mayor o igual a x y el último número menor o igual a y que sean divisibles por k. Esto se puede hacer usando operaciones de división y módulo.

2. Calcular la cantidad de números divisibles: Una vez identificados estos números, se calcula cuántos números divisibles hay entre ellos. Esto se puede hacer restando los cocientes de la división de y y x por k, y luego sumando 1 al resultado.

3. Manejar casos límite: Es importante considerar casos donde x o y sean ellos mismos divisibles por k.

## Consideración importante 1
La primera parte de la línea `long firstDivisible = x % k == 0`  `? x : x + (k - x % k);` es una comprobación para ver si el número `x` ya es divisible por `k`. 

Esto se hace mediante la operación módulo (`%`), que devuelve el residuo de la división de `x` por `k`. Si este residuo es cero (`x % k == 0`), significa que `x` es divisible por `k` sin dejar ningún residuo, y por lo tanto, `x` mismo es el primer número divisible por `k` en el rango. En este caso, `firstDivisible` se establece igual a `x`. Este es un paso importante para asegurarse de que empezamos a contar desde un número que cumple con el criterio de divisibilidad por `k`.

## Considerción importante 2

La segunda parte de la línea `long firstDivisible = x % k == 0 ? x :` `x + (k - x % k);` se ejecuta si `x` no es divisible por `k` (es decir, `x % k` no es igual a 0). Aquí, calculamos el primer número mayor que `x` que es divisible por `k`. 

- **`x % k`**: Esta parte calcula el residuo de dividir `x` por `k`.
- **`k - x % k`**: Esta resta determina cuánto falta para llegar al próximo múltiplo de `k`. Si `x` es 3 y `k` es 5, el residuo es 3 y `5 - 3` es 2, lo que significa que al sumar 2 a `x` llegamos al próximo múltiplo de 5.
- **`x + (k - x % k)`**: Finalmente, sumamos este valor a `x` para obtener el primer número divisible por `k` que es mayor que `x`.
