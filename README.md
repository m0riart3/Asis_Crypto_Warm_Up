# Asis_Crypto_Warm_Up
## Descripción
![Descripcion](https://github.com/m0riart3/Asis_Crypto_Warm_Up/blob/main/Descripcion.PNG)

## Análisis del cifrado

El código es un algoritmo por transposición, utiliza un número primo 'p' que obtiene usando la función getPrime() y genera una cadena de caracteres aleatorios imprimibles de longitud p - longitud de la flag. Para el algoritmo usa una congruencia lineal dada como ``` s**i mod(p)``` donde s es un entero random obtenido mediante la función getRandomNBitIntegrer(), i es una variable cuyo valor va desde 0 hasta p-1, tal y como se puede apreciar en el bucle for. 
Tal y como se puede ver en el código, la string enc, cuyo valor será la flag encriptada tiene como primera letra la 'A' puesto que al inicializarla le da el valor del primer elemento del array msg, es decir la flag sin encriptar cuyo formato era ASIS{}.

![Codigo](https://github.com/m0riart3/Asis_Crypto_Warm_Up/blob/main/codigo.PNG)

## Algoritmo de descifrado

El código que mi compañero "TonyTow3rs" y yo se basa en la forma en la que el algoritmo de cifrado funciona, sabemos que en ningun momento la flag llega a recibir un cambio de valor, solamente de posición y el orden en el que se desordena es posible de reversear. 
Sabemos que la longitud del texto dado es el valor de 'p', por lo que contamos carácteres y nos da el valor de 19489. Por lo tanto s tiene que tener de valor entre 0 y p-1.
Teniendo esas dos ideas ya podemos romper este cifrado, puesto que sabemos que la 2 letra del cifrado ha de ser 'S' y que sabemos las posiciones originales del formato de la flag. Podemos sacar todas las s posibles que den como resultado que las letras del formato de la flag en su posición original den como resultado la posición que tienen en el archivo 'output.txt'.

Para explicarlo mejor pondremos un ejemplo.
Si sabemos que la letra 'I' ocupaba en la flag original la posición 3. Podemos calcular todas las 's' que den como resultado que la I este en la posición actual del archivo. Al hacerlo con 1 letra solo al haber varias 'I' en el archivo pues las posibilidades serán muchas, pero al juntar esas posibles 's' para que también den como salida que '{' estuviera en la posición 5, se reducirán bastante, y así se repite con varios carácteres para que de solo una posible 's' la buena.
