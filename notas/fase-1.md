# Fase 1: Fundamentos

## 1.1 Variables (25/11/2026)

**¿Qué podés hacer con shadowing que no podés hacer con mut?**
Hay 2 diferencias, una es que con shadowing podés cambiar de tipo la variable y en mut no. Por otro lado si querés "cambiar" el valor de una variable con shadowing si o si necesitas poner let, no como mut que te deja cambiarla sin declararla de nuevo. También son locales, por ejemplo si pongo un let x dentro de un if, fuera del if x tiene su valor original. La variable es inmutable en cada instancia declarada, se utiliza principalmente para usar el mismo nombre de variables pero cambiando el tipo. No voy a dar un ejemplo porque se me hace extenso, me parece que se entiende el punto.
**¿En qué se diferencia un const de un let sin mut?**
La principal diferencia radica en que const no es inmutable pordefecto, es inmutable por definición. Y además se pueden declarar constantes que abarquen todo el programa, como una especie de variable de entorno. Const también te obliga a declarar el tipo de dato
**¿Por qué Rust hace inmutable todo por defecto?**
Básicamente favorece al debug, la lectura del código y por ende su mantenimiento. Si una parte del código asume que es inmutable y otra no e intenta cambiarlo, produce errores muy dificiles de rastrear, eso en rust no pasa, porque directamente no compila
**¿Qué pasa si declarás `let x;` y lo usás sin asignarle un valor?**
Da un error de compilación. Rust no te deja usar una variable nula/vacía o que no tenga un valor
**Dudas:**
Por ahora todo claro

**Próximo paso:** cap. 3.2, tipos de datos.

## 1.1 Tipos de datos (26/11/2026)

**¿Qué pasa con un overflow de enteros en debug y qué pasa en release? ¿Por qué Rust los trata distinto?**
Un overflow de enteros es cuando un valor de un entero supera el límite que soporta la variable. En release lo que pasa es que rust realiza una envoltura, si el valor maximo es 255 y la variable recive 256 el valor que guarda es 0. Rust tiene métodos en la librería estandar, solo se mencionan por encima sin dar mucha profundidad. wrapping_*, checked_*, overflowing_*, saturating_* para manejar los overflow de enteros. En debug hace verificaciones de overflow ya que estando en debug el coste de la verificación es menos importante que que te diga si hay un error de overflow, te avisa con un panic.
**¿Por qué `'a'` y `"a"` son tipos diferentes?**
Lo que entendi es que las comillas simples son para un caracter, un char, que es una variable de 4 bytes que representa un valor escalar unicode. Y las comillas dobles son cadenas de caracteres, el cual no es unicode, no se profundiza mucho tampoco en este capitulo. Corrección luego de revición: la cadena de caracter si es unicode, solo que se trata de una variable con la cantidad de caracteres que se quiera cada uno de 1 a 4 bytes
**¿En qué se diferencia una tupla de un array? Pensá un caso donde usarías cada uno.**
se diferencian principalmente en que el array tiene todos los valores del mismo tipo, la tupla no; y la forma en que se acceden, la tupla es "x.1" y array "x[1]". Como caso de uso de una tupla, guardar un conjunto de valores de un perfil, por ejemplo, mail, contraseña, nombre, edad, fecha de nacimiento. Y para un array, guardar los meses del año.
**Si no anotás el tipo, ¿cuál elige Rust para `let x = 3;` y cuál para `let y = 3.0;`?**
para x rust elije i32 y para y rust elije f64
**Dudas:**
Imagino que las dudas que tengo las dejé en las preguntas respondidas, pero también imagino que mas adelante se aclaran
**Próximo paso:** cap. 3.3 (funciones) y Rustlings `functions1`–`5`.
