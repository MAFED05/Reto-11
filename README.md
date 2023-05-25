# Reto 11

## Punto 1

Desarrolle un programa que permita realizar la suma/resta de matrices. El programa debe validar las condiciones necesarias para ejecutar la operación.

### Código

``` python
def crearMatriz(filas,columnas): # Definimos la primera función para lograr crear las matrices
    matrizFinal=[] #Para lograr hacer la metriz primero debemos colocar una lista vacía
    for X in range (0,filas): # Declaro que para x en el rango de 0 hasta las filas que halla colocado el usuario
        fila= [] # Ingreso otra variable vacia para ingresar cada elemento de las filas
        for j in range(0, columnas): # Ahora declaro que para j en el rango de 0 hasta la cantidad de columnas necesarias
            elemento =float(input("Ingrese los valores de cada matriz:")) # Se solicita un entero como valor
            fila. append(elemento) # el anterior entero se adiciona a la lista vacia llamada fila que declaramos antes para ir creando la matriz. 
        matrizFinal.append(fila) # Ahora pido que la fila se adicione a la matriz vacia antes declarada.
    return(matrizFinal) # Pido que retorne la matriz creada

def suma_matrices(columnas,filas,MatrizUno, MatrizDos): # Defino la funcion para la suma de matrices y sus argumentos
    Matriz =[] 
    for i in range (0,filas): 
        fila=[] 
        for j in range (0,columnas):
            sumaMatriz = MatrizUno[x][j]+ MatrizDos [x][j] # Aqui hago la suma de matrices donde digo que sume x que recorrio filas y j que reccorrio columnas de ambas matrices ya antes creadas
            fila.append(sumaMatriz) # Aqui se adiciona a la lista vacia de fila el resultado anterior
        Matriz.append(fila) # En este adiciono fila a la lista vacia suma ya antes declarada
    return(Matriz) # Al final retorno suma de matrices

if __name__ =="__main__": #Definimos la función principal
    filas=int(input( "Introduzca la cantidad de filas: (Recuerde que la matriz debe tener la misma cantidad de filas y columnas) ")) # Se solicita la cantidad de filas
    columnas=int(input( "Introduzca la cantidad de columnas:  (Recuerde que la matriz debe tener la misma cantidad de filas y columnas) ")) # Se solicita la cantidad de columnas

    print("Matriz 1")
    MatrizUno=crearMatriz(columnas,filas) # Se define la primera función
    for x in range(0,filas): # Recorro desde 0, hasta los elementos que ingrese el usuario
        print(MatrizUno[x]) # Imprimo la primera matriz

    print("Matriz 2")
    MatrizDos=crearMatriz(columnas,filas) #Se define la segunda función
    for x in range (0,filas): # Recorro desde 0, hasta los elementos que ingrese el usuario
        print(MatrizDos[x]) # Imprimo la Segunda matriz
    
    print("Matriz 3")
    MatrizTres=suma_matrices(columnas,filas,MatrizUno, MatrizDos) # Aqui ya realizamos la suma de funciones
    print("La suma de las matrices 1 y 2 es: ")
    for x in range(0,filas): # Realizo lo mismo que con las dos matrices anteriores
        print (MatrizTres[x]) #Se imprime la tercera matriz
```

## Punto 2

Desarrolle un programa que permita realizar el producto de matrices. El programa debe validar las condiciones necesarias para ejecutar la operación.

### Código

``` python
# Para el producto/punto de matrices el número de columnas de la primera matriz debe coincidir con el número de filas de la segunda matriz

def crearMatriz(filas,columnas): # Defino la primera función para crear las matrices, junto con sus argumentos
    """
    permite crear una matriz

    Argumentos:
       filas: los digitos horizontales
       columnas: los digitos verticales

    Return:
        matriz
    """
    matriz=[] 
    for i in range (0,filas): # 
        fila= [] 
        for j in range(0, columnas): 
            valor=float(input()) 
            fila.append(valor)
        matriz.append(fila) 
    return(matriz)

def productoPuntoMatrices (filas1,filas2,columnas2,matriz1, matriz2): # Definimos la funcion y sus argumentos
    productoPunto = [] # Agregamos una variable en forma de lista que estara vacia
    for i in range(0,filas1): # Primer range que recorrera las primeras filas
        fila = [] # Agregamos variable en forma de lista que estara vacia
        for j in range(0,columnas2): # Segundo range que recorrera las columnas 2
            lista1 = matriz1[i] # Definimos una lista que es igual a el recorrido de filas de la primera matriz
            lista2 = [] # Declaro segunda lista que estara vacia
            producto = 0 # Declaro variable producto la cual es 0 y la que utilizaremos mas adelante para operar
            for m in range(0,filas2): # Ahora con este tercer range se recorrera las filas 2
                lista2.append(matriz2[m][j]) # A la lista dos se le agregara o adiconara la matrizB[m][j] sabemos que m representa un valor desde 0 hasta la cantidad de filas de B y J tiene un valors desde 0 hasta la cantidad de columnas de B
            for n in range(len(lista1)): # Declaro un 4 for donde recorrera la lista 1 
                producto = producto + lista1[n]*lista2[n] #Realizamos la operación para el producto punto
            fila.append(producto) # La operacion anterior se agregara a la fila vacia 
        productoPunto.append(fila) # Y la fila que ya no esta vacia se adiciona al producto punto que era una lista vacia
    return(productoPunto) # Retornamos producto punto


if __name__ == "__main__": #Definimos la función principal
    # Creo la primera matriz 1   
    print("MATRIZ 1")
    filas1 = int(input("Especifique el numero de filas de la primera matriz: ")) #Solicitamos cantidad de filas
    columnas1 = int(input("Especifique el numero de columnas de la primera matriz: ")) # Solicitamos cantidad de columnas
    matriz1 = crearMatriz(filas1,columnas1) # Llamo a la función crear matriz
    for j in range (0,filas1): 
        print(matriz1[j]) # Se imprime la matriz
    
    # En la segunda matriz se realiza lo mismo, la diferencia es que la condicion es que las filas son igual que las columnas de la anterior matriz por ende no le pedimos filas al usuario
    print("MATRIZ 2")
    filas2 = columnas1 #Le indicamos la condicion para que pueda ser producto punto
    columnas2 = int(input("Especifique el numero de columnas de la segunda matriz: ")) #Se solicita el numero de columnas de la segunda matriz
    matriz2 = crearMatriz(filas2,columnas2) #Se crea la segunda matriz
    for j in range (0,filas2):
        print(matriz2[j]) #Imprimimos la segunda matriz
    
    matriz3 = productoPuntoMatrices(filas1,filas2,columnas2,matriz1, matriz2) # Llamo a la funcion de producto punto matrices
    print("El producto punto de las matrices es: ")
    for j in range (0,filas1):
        print(matriz3[j]) # imprimimos la matriz
```

## Punto 3

Desarrolle un programa que permita obtener la matriz transpuesta de una matriz ingresada. El programa debe validar las condiciones necesarias para ejecutar la operación.

### Código

``` python
```

## Punto 4

Desarrollar un programa que sume los elementos de una columna dada de una matriz.

### Código

``` python
```

## Punto 5

Desarrollar un programa que sume los elementos de una fila dada de una matriz.

### Código

``` python
```
