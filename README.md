# RETO.7
## Imprimir un listado con los números del 1 al 100 cada uno con su respectivo cuadrado
````python
#se define una variable en 1 para empezar la cuenta
x = 1

#mientras x sea menor o igual a 100 procede a operar la varIable cuadrado 
while x <= 100:
  cuadrado = x**2
  print(x, cuadrado,sep =" , ")
#suma uno al valor de x hasta que llegue a 100
  x += 1

````
### Diagrama de flujo 

````mermaid
flowchart TD
    A[Inicio]--> B
    B[x =1] --> D
    D --> |falso| E[fin del codigo]
    D{mientras x <= 100} 
    D --> |verdadero| F[funcion x^2]
    F --> G[imprimir x y x^2]
    G --> H[suma 1 ala valor de x] --> D

````

## Imprimir un listado con los números impares desde 1 hasta 999 y seguidamente otro listado con los números pares desde 2 hasta 1000

````python
#se declaran variables para cada uno de los listados
x = 0
y = 0

#mientras x sea menor o igual a 1000 
while x <= 1000 :
  x += 1
  #analiza si este numero no es multiplo de 2
  if x%2 != 0:
    continue
  #continua hasta que la condicion del ´while´ acabe
  print(x)

while y <= 999 :
  y += 1
  #analiza si este numero es multiplo de 2
  if y%2 == 0:
    continue
  #continua hasta que la condicion del ´while´ acabe
  print(y)
````
### Diagrama de flujo 

````mermaid
flowchart TD
    A[Inicio]
    A --> B[x = 0]
    A --> C[y = 0]
    B --> D{mientras x <= 1000} 
    D --> |Verdadero|E[sumar +1 a x]
    E --> F{si x % 2 != 0}
    F --> |continuar|G[emprimir x] -->D
    C --> I{mientras y <= 999} 
    D --> |Falso|H[Fin]
    I --> |Verdadero|J[sumar +1 a y]
    J --> K{si y % 2 = 0}
    K --> |continuar|L[imprimir y] --> I
    I --> |Falso|H 
````

## Imprimir los números pares en forma descendente hasta 2 que son menores o iguales a un número natural n ≥ 2 dado

````python
#se difine una variable float
x = float(input("ingrese un numero: "))

#mientras x sea mayor a 2
print(x)
while x > 2:
  x -= 1
  #analiza si el modulo sea 0 para determinar si es par
  if x%2 != 0:
    continue
    #continua hasta que la condicion del ´while´ acabe
  print(x)
````
### Diagrama de flujo 

````mermaid
flowchart TD
    A[Inicio]
    A --> B[ingrese un numero = x]
    B --> C[imprimir el numero x]
    C --> D{mientras x > 2}
    D --> |Falso|Z[fin]
    D --> |Verdadero|E[Restar -1 a x]
    E --> F{si x % 2 != 0}
    F --> |continuar|G[imprimir x] --> D
````

## En 2022 el país A tendrá una población de 25 millones de habitantes y el país B de 18.9 millones. Las tasas de crecimiento anual de la población serán de 2% y 3% respectivamente. Desarrollar un algoritmo para informar en que año la población del país B superará a la de A

````python
#se definen las variables de la poblacion y el año de inicio
A = float(25)
B = float(18.5)
C = 2022

#mientras la poblacion de A sea mayor a la de B
while A > B:
  #se define las variables del porcentaje de crecimiento 
  porcentajeA = (1 + 0.02)
  porcentajeB = (1 + 0.03)
  #se multiplica la poblacion por su respectivo porcentaje
  A *= porcentajeA
  B *= porcentajeB
  C +=1
#continua hasta que la condicion del ´while´ acabe
print(C)

````

## Imprimir el factorial de un número natural n dado

````python
#se declara que factorial es 1
factorial = 1

#se declara la variable para introducir un numero
x = int(input("Introduzca el número: "))

#se declara i para generar el conteo
i = 1

#mientras i sea menor que x 
while (i <= x):
    #se realiza la operacion respectiva del factorial
    factorial = factorial * i
    #y se suma 1 a i
    i = i + 1
#cuando se completa el while se imprime elresultado
print ("El factorial de " + str(x) + " es " + str(factorial))
    
````

## Implementar un algoritmo que permita adivinar un número dado de 1 a 100, preguntando en cada caso si el número es mayor, menor o igual

````python
#se importa la funcion ramdom
import random

#se define la funcion de adivinar
def adivina():
    print("Piensa en un número entre 1 y 100 :D")
    minimo = 1
    maximo = 100
    
    #se declara un ciclo verdadero
    while True:
        #se declara una variable aleatoria 
        x = random.randint(minimo, maximo)
        
        #se le pide al usuario que reponda segundo 
        print("tu número es " + str(x))
        print("( responde 'igual' si es correcto, 'menor' si es menor, 'mayor' si es mayor):")
        respuesta = input()
        
        #dependiendo de la respuesta del usuario hacer algunos de los condicionales
        if respuesta == 'igual':
            print("Adiviné tu número :D")
            break
        elif respuesta == 'menor':
            maximo = x - 1
        elif respuesta == 'mayor':
            minimo = x + 1
        else:
            print("Por favor, responde 'igual', 'menor' o 'mayor'.")

#se termina el ciclo
adivina()

````
## Implementar un programa que ingrese un número de 2 a 50 y muestre sus divisores

````python
#se decaclara la variable para ingresar un numero
x = int(input("Ingresa un número entre 2 y 50: "))

#si x esta entre 2 y 50 permite continuar
if 2 <= x <= 50:
    print("Los divisores de son:" + str(x))
    
    divisor = 1
    
    # mietras la variable divisor sea menor o igual a x 
    while divisor <= x:
        if x % divisor == 0:
            print(divisor)
        #suma uno a la cuenta
        divisor += 1

#termina si el numero no cumple las condiciones
else:
    print("El número debe estar en el rango de 2 a 50.")

````
## Implementar el algoritmo que muestre los números primos del 1 al 100

````python
#hacemos una funcion para definir cuando es primo un numero
def primos(x):
  if x <= 1:
    return False
  elif x <= 3:
    return True
  elif x % 2 == 0 or x % 3 == 0:
    return False
  
  #define i para hacer el conteo
  i = 5

  #mientras i multiplicado por si mismo sea menor x
  while i * i <= x:
        if x % i == 0 or x % (i + 2) == 0:
            return False
        #se le suma 6 a la cuenta
        i += 6
  return True

#imprima todo el los numeros en la lista que coincidan
print("Números primos del 1 al 100:")
for n in range(1, 101):
    if primos(n):
        print(n)
````

