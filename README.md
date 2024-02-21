# Reto-no.3
_El siguiente repositorio muestra el pseudo código y diagrama de flujo del algoritmo para para hallar los números primos hasta un número natural n y del algoritmo para obtener raíces cuadradas_

## Algoritmo para hallar los números primos hasta un número natural n
### Pseudocódigo
```pseudocode
n : entero
i : entero
primos : arreglo
arraySize : entero

Inicio
  i := 2
  Mientras (i < n) hacer
     descartar todos los múltiplos de i excepto i
	 escribir ("i es primo")
	 Guardar i en primos
	 arraySize += 1
      i := i + 1
	Fin mientras
	Si i==n entonces 
	    para x = 0 hasta x <= arraySize Con Paso x = x +1
			Si (n mod primosₓ == 0) Entonces:
			 	escribrir ("n no es primo")
			Fin si
		Fin para
	    Guardar n en primos
	Fin si
Fin
```
### Diagrama de flujo
```mermaid
flowchart TD;
    A(Inicio) --> B[n : entero]
    B-->C;
    C[i : entero] -->D[primos : arreglo]
    D-->E;
    E[arraySize : entero]-->F[x : índice de primos]
    F --> G;
    G[i = 2]--> H{i<n} -- Sí --> I[Descartar todos los múltiplos de i excepto i]
    I-->J;
    J[Escribir ''i es primo'']-->K[Guardar i en primos]
    K-->L;
    L[arraySize += 1]-->M[i += 1]
    H-- NO -->N{i==n}-- Sí -->O[Para x = 0 Hasta x <= arraySize Con Paso x = x +1]
    N-- No -->H;
    O -->P{n mod primosₓ == 0}-- Sí -->Q[Escribrir ''n no es primo'']
    P-- No -->R[Guardar n en primos]
    R-->S;
    S[Escribir n es primo]
```
