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