# Reto-no.3
_El siguiente repositorio muestra el pseudo código y diagrama de flujo del algoritmo para para hallar los números primos hasta un número natural n y del algoritmo para obtener raíces cuadradas_
## Tabla de contenido
1. [Algoritmo para hallar los números primos hasta un número natural n](#algoritmo-para-hallar-los-números-primos-hasta-un-número-natural-n)
	- [Pseudocódigo 1](#pseudocódigo-1)
	- [Diagrama de flujo 1](#diagrama-de-flujo-1)
2. [Algoritmo para sacar raiz cuadrada a un número n](#algoritmo-para-sacar-raiz-cuadrada-a-un-número-n)
	- [Pseudocódigo 2](#pseudocódigo-2)
	- [Diagrama de flujo 2](#diagrama-de-flujo-2)

### Algoritmo para hallar los números primos hasta un número natural n
#### Pseudocódigo 1
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
#### Diagrama de flujo 1
```mermaid
flowchart TD;
    A(Inicio) --> B[n : entero];
    B-->C;
    C[i : entero] -->D[primos : arreglo];
    D-->E;
    E[arraySize : entero]-->F[x : índice de primos];
    F --> G;
    G[i = 2]--> H{i **menor que** n} -- Sí --> I[Descartar todos los múltiplos de i excepto i];
    I-->J;
    J[Escribir ''i es primo'']-->K[Guardar i en primos];
    K-->L;
    L[arraySize += 1]-->M[i += 1];
    M-->H;
    H-- NO -->N[i==n];
    N -->O[Para x = 0 Hasta x **menor o igual que** arraySize Con Paso x = x +1];
    O -->P{n mod primosₓ == 0}-- Sí -->Q[Escribrir n, ''no es primo''];
    P-- No -->R[Guardar n en primos];
    R-->S;
    S[Escribir ''n es primo''];
    Q-->T;
    S-->T;
    T(Fin)
```
### Algoritmo para sacar raiz cuadrada a un número n
#### Pseudocódigo 2
```pseudocode
n : radicando
b : raiz
c : primeras dos cifras de n
r : residuo de las dos cifras de n - b^2 junto con siguientes dos cifras de n
y : 1

Inicio
  Si b^2 == n Entonces
  	escribir (b^2, ''es raiz de'', n)
  Sino
  	separar n en dos cifras de derecha a izquierda
  	buscar un número b tales que b^2 sea el número más cercano a c ∧ b^2 ≤ c
  	restar c - b^2
  	multiplicar b*2
  	bajar siguientes dos cifras de n
		Si en las siguientes dos cifras de n una de ellas es decimal Entonces
			poner punto decimal a la derecha de b
		Sino
			dejar a b como está
  	Multiplicar (b*2)y*y
	Mientras (b*2)y*y no sea el número más cercano a r ∧ (b*2)y*y ≤ r Entonces
		y +=1 siempre y cuando y < 10
	Fin Mientras
	Si (b*2)y*y es el número más cercano a r ∧ (b*2)y*y ≤ r Entonces
		restar r - (b*2)y*y
	Fin Si
	Si b tiene un punto decimal Entonces
		sumar b + 0.y
	Sino
		sumar b + y
	Mientras r - (b*2)y*y tenga residuo Hacer
		(b*2)y*y = b
		repetir desde (Multiplicar b*2)
	Fin mientras
	Si r - (b*2)y*y no tiene residuo Entonces
            escribir(b + y, ''es raiz de'' n)
	Fin si
  Fin si           
```
#### Diagrama de flujo 2
```mermaid
flowchart TD;
    A(Inicio) --> B[n : radicando];
    B-->C;
    C[b : raiz] --> D[ R : conjunto de números reales];
    D-->E;
    E[Z : conjunto de números enteros]--> F[r : residuo junto con siguientes dos cifras de n];
    F --> G;
    G{b^2 == n}-- Sí --> H[Escribir ''b^2 es raiz de n''];
    G-- No --> I[Separar n en dos cifras de derecha a izquierda];
    I-->J;
    J[Buscar un número b tales que b^2 sea el número más cercano a n y b^2 sea menor o igual a n]--> K[Restar n - b^2];
    K-->L;
    L[Multiplicar b*2]--> M[Bajar siguientes dos cifras de n];
    M-->N;
    N[Multiplicar b*2+y*y tales que b*2+y*y sea el número más cercano a r y b*2+y*y sea menor o igual a r]-->O[Sumar b + y];
    O-->P;
    P[Restar r - b*2+y*y]-->Q{r - b*2+y*y tiene residuo}--> Sí --> S[b*2+y*y = b];
    Q--> No --> T[Escribir''b +y es raiz de n''];
    S-->L
    T-->V;
    H-->V;
    V(Fin);
```
```mermaid
flowchart TD;
    A(Inicio) --> B[n : radicando];
    B-->C;
    C[b : raiz] --> D[ c : primeras dos cifras de n];
    D-->E;
    E[r : residuo de las dos cifras de n - b^2 junto con siguientes dos cifras de n]--> F[y : 1];
    F --> G;
    G{b^2 == n}-- Sí --> H[Escribir b^2, ''es raiz de'', n];
    G-- No --> I[Separar n en dos cifras de derecha a izquierda];
    I-->J;
    J[Buscar un número b tales que b^2 sea el número más cercano a c y b^2 sea menor o igual a c]-->K[Restar c - b^2]
    K-->L;
    L[Multiplicar b*2]--> M[Bajar siguientes dos cifras de n];
    M-->N;
    N{En las siguientes dos cifras de n una de ellas es decimal}-- Sí -->O[poner punto decimal a la derecha de b];
    N-- No --> P[Dejar a b como está];
    O-->R;
    P-->R;
    R[Multiplicar b*2+y*y]--> S{b*2y*y no es el número más cercano a r y b*2y*y es menor o igual a r}-- Sí -->T[y +=1 siempre y cuando y menor a 10];
    S-- No-->U[Restar r - b*2*y*y]
    T--> S;
    U-->V{b tiene un punto decimal}--Sí -->W[Sumar b + 0.y];
    V--No-->X[Sumar b + y];
    X-->Y{r - b*2y*y tiene residuo}--Sí -->Z[b*2y*y = b];
    Z-->L;
    Y--No -->AB[escribir b + y, ''es raiz de'', n]
```

