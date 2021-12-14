# Estrella_Regular
Mi dirección de Github para este repositorio es la siguiente: [Github: https://github.com/paulaanb/Estrella_Regular]


El reto consiste en programar una función que dibuje estrellas como la que aparece a continuación con un número de puntas dado.

Estrella

<img width="254" alt="Captura de pantalla 2021-12-14 a las 16 09 00" src="https://user-images.githubusercontent.com/91721496/146024688-d2eb2567-5787-48ad-a0cc-88f769d1943a.png">


Para ello hay que utilizar el módulo de Python Turtle que permite realizar trazos sencillos en una ventana gráfica.

El código que vamos a utilizar para esta tarea es el siguiente:

```
#Creamos un código resolver el reto

#Creamos una función para dibujar una estrella regular de 150 puntas utilizando el módulo de Phyton Turtle

def star(tips, side=150):
    import turtle
    
    #Ahora creamos una función para calcular el máximo común divisor de 2 números enteros mediante el algoritmo de euclides
    #Necesitamos esto para calcular el ángulo de rotación de la estrella
    def mcd(a,b):
        while b !=0:
            a,b = b, a % b
        return a
    
    #A continuación utilizamos un condicional para saber si el número de puntas debe ser mayor que 4, porque en caso contrario no podemos dibujar la estrella
    if tips <= 4:
        print("El número de puntas no llega al número mínimo. Por favor introduzca un número mayor par poder continuar.")
        return
    
    #Vamos a calcular el ángulo de rotación en los vertices de la estrella en función del primer número entero coprimo con el número de puntas.
    #Para ello utilizamos un bucle iterativo para buscar el mayor coprimo con el número de puntas.
    for i in range(tips // 2,1,-1):
        if mcd(tips,i) == 1:
            angle =360.00 / tips * i
            break
        #Hemos creado otro bucle para comprobar si i y el número de puntas son números coprimos
        
        #Creamos otro para dibujar los trazos de cada punta
        for _ in range (tips):
            turtle.forward(side)
            turtlr.left(angle)
            
        return
    star(20)
