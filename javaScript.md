# Aspectos Basicos

## Concatenacion

- Tradicional:
    Es la utilizada tradicionalmente en los lenguajes de programacion, funciona utilizando el operador +. Ejemplo:

    'Jesus' + 'Millan'
    
    \>> 'Jesus Millan'

- Interpolacion:
    Es una forma nueva de concatenar texto, y para en lo personal me parece mas facil y clara de leer. Funciona utilizando el operador comillas invertidas (``). Ejemplo:

    var firstName = 'Jesus';
    var lastName  = 'Millan';

    \`${firstName} ${lastName}`;
    
    \>> 'Jesus Millan'
    
    **NOTA:** Dentro de las {} van codigo Js, el caracter para escapar texto es '\'.

## Depurar
En ocasiones nuestro código puede fallar por errores de syntaxis o errores lógicos. En caso de que quieras verificar tu código, debes utilizar la palabra clave 'debugger'. El código se detiene cada vez que lee esta palabra.

# Variables

## Strings 

Son cadenas de texto. Para indicar que estamos usando una cadena de texto debemos de colocar las comillas simples ('').

### Metodos

- toUpperCase:
    Sirve para transformar un String a mayúsculas.
- toLowerCase:
    Sirve para transformar el string a minúsculas.
- charAt(N):
    Retorna el caracter que esta en la posicion N.

### Atributo

- length:
    Nos indica la cantidad de caractéres que tiene un string.
Para concatenar dos strings se utiliza el símbolo (+)
var nombreCompleto = nombre + ’ ’ + apellido

# Funciones
Son fracciones de código reutilizable.

- Para definir una función utilizaremos la palabra reservada  *function*.
- Delimitamos el cuerpo de la función usando llaves { }.
- Los parámetros de la función son variables que se pasan a la función escribíendolos entre paréntesis ().

Ejemplo:

``` [javascript]
function nameFunction (var1, var2, ...,varn){
    code...
}
```
**Nota:** JavaScript es un lenguaje interpretado, esto quiere decir que intentará ejecutar el código sin importar si los parámetros que le pasemos a la función estén invertidos o incluso incompletos.

## ALcance
Si una variable no está definida dentro del cuerpo de una función hablamos de una variable *global*. Por el contrario, una variable definida dentro de una función es una variable *local*.

Para que la ejecución de una función no modifique una variable *global* usamos parámetros en lugar de pasar directamente la variable.

Es posible utilizar el mismo nombre para una variable global y para el parámetro de una función con un alcance local.

# Objetos (JSON: JavaScript Object Notation)
Un objeto nos permite la modelacion y abstracion de un "objeto" del mundo real.

**NOTA:** Un objeto también se puede pasar como atributo en una función.

## Definicion
Se definen delimitados mediante llaves( {} )

Un atributo se compone de una clave (key) y un valor (value), que se separan entre sí por dos puntos( : ). Los valores pueden ser de tipo *string*, *número*, *booleano*, etc. Cada atributo está separado del siguiente por una coma( , ). Un objeto puede tener todos los atributos que sean necesarios.

## Acceso

Existen al menos dos formas de acceder al valor de un atributo de un objeto:

1. Escribir el nombre de un objeto separado por un punto del nombre de un atributo.

**NOTA:** Las últimas versiones de JavaScript nos permiten desglosar el objeto para acceder únicamente al atributo que nos interesa. Esto se consigue encerrando el nombre del atributo entre llaves { }.

2. Es metodo de acceso es llamado *desestructurización*. Para no duplicar las variables se introduce el nombre de la variable como parámetro de la segunda variable. 
Ejemplo: Las dos lineas de codigo siguiente son completamente analogas

``` [javascript]
var nombre = persona.nombre;
var{ nombre } = persona;
```
***IMPORTANTE***
    Javascript se comporta de manera distinta cuando le pasamos un objeto como parámetro.

Cuando le pasamos un objeto a una funcion, este se pasan como una referencia del objeto, lo que significa que el objeto es modificado incluso fuera de la funciona.
Para solucionar esto se puede crear un objeto diferente o auxiliar. Esto lo podemos hacer colocando tres puntos antes del nombre del objeto(lo cual crea un desgloce del objeto).
Ejemplo:

```
aux = {
       …persona,
    }
```

## Arrow Function

Las Arrow Functions permiten una nomenclatura más corta para escribir expresiones de funciones. Este tipo de funciones deben definirse antes de ser utilizadas.

Al escribir las Arrow Functions no es necesario escribir la palabra function, y en algunos casos tampoco la palabra return, ni las llaves. Ejemplo:

``` [javascript]
const nameFunction = ( parameters ) => {
    code to executed ...
    return ...
}

const nameFunction = parameter => This is the value return
```


# Comparaciones

Existen varias maneras de comparar variables u objetos dentro de javascript.

Imaginemos que le asignamos a una variable *X* un valor numérico y a una variable *Y* un string. Para poder compararlos debemos agregar dos signos de igual (==). Esto los convierte al mismo tipo de valor y permite que se puedan comparar.

**NOTA:** Cuando realizamos operaciones es recomendable usar tres símbolos de igual (===). Esto permite que JavasScript no iguale las variables que son de distinto tipo. Es recomendado que se use el triple igual siempre que se estén comparando variables.

Recuerda existen cinco tipos de datos que son primitivos:

1. Boolean
2. Null
3. Undefined
4. Number
5. String

***MUY IMPORTANTE:*** Cuando comparamos objetos en Js, lo que hacemos es preguntar por la *referenacia en memoria RAM a la(s) variable(s)* que estamos consultando.

# Estructuras de Control

## Condicionales
Los condicionales nos permiten decidir si un código se ejecuta o no. Mediante un condicional (if) decidiremos si se ejecuta una parte de nuestro código cuando se cumpla o no cierta condición. Ejemplo

``` [javascript]
if (condition) {
    This code be executed if condition is true...
} else {
    This code be executed if confition is false...
}
```

## Bucles
Se utilizan para repetir una o más instrucciones un determinado número de veces o mientras/hasta que se cumpla una condicion.

### For
El bucle for, se utiliza para repetir una o más instrucciones un determinado número de veces.

Para escribir un bucle for se coloca la palabra for seguida de paréntesis y llaves.
Ej. for( ){ }. Dentro de los paréntesis irán las condiciones para ejecutar el bucle, y dentro las llaves irán las instrucciones que se deben repetir.
Ejemplo:
```
for (var i=0; i <N; i++) {
    code...
}
```

### While
While se ejecuta únicamente mientras la condición que se está evaluando es verdadera.

Ejemplo
``` [javascript]
while (condition) {
    code...
}
```

### Do...While
A diferencia de la instrucción while, un bucle do…while se ejecuta una vez antes de que se evalúe la expresión condicional.

Ejemplo
``` [javascript]
Do {
    code...
} while (condition)
```

## Switch
Switch se utiliza para realizar diferentes acciones basadas en múltiples condiciones.

Break, sirve para que el browser se salte un bucle.

``` [javascript]
switch (variable) {
    case value1:
        code...
        break;
    case value2:
        code...
        break;
    case valueN:
        code...
        break;
    default:
        code...
        break;
}
```

# Arrays
Los arrays son estructuras que nos permiten organizar elementos dentro de una collección. Estos elementos pueden ser números, strings, booleanos, objetos, etc.

## Declaracion

```
var nombres = ['juan','pedro','jesus','mario'];
```
## Metodos

### filter
Para filtrar siempre necesitamos establecer una condición.

El método filter ( ) crea una nueva matriz con todos los elementos que pasan la prueba implementada por la función proporcionada.

Recuerda que si no hay elementos que pasen la prueba, filter devuelve un array vacío.
Ejemplo:
```
newArray = array.filter(function (parameter) {
    filtering logic
    return boolean
})
```

### map
El método map() itera sobre los elementos de un array en el orden de inserción y devuelve un array nuevo con los elementos modificados.

```
newArray = array.map(function (parameters) {
    maping logic
})
```
### reduce
El método reduce() nos permite reducir, mediante una función que se aplica a cada uno de los elemento del array, todos los elementos de dicho array, a un valor único.

# Clases
## Bases del leguaje
Lo que se describe a continuacion es parte de las bases del lenguaje, dicha sintaxis ya no es muy utilizada, mas sin embargo es importante tener dichos conceptos claros.

Las clases(aunque en Js hablamos mas de "prototipos" y no mucho de "clases") son funciones cuya sintaxis tiene dos componentes:
- expresiones
- declaraciones

**Definicion**

Para definir un prototipo solo debemos definir una funcion. Ejemplo

``` [javascript]
function prototypeName (parameters) {
    // this is code of builder
    this.attribute1 = value1
    this.attribute2 = value2 
}

// this is a method of the prototype
prototypeName.prototype.methodName = function (parameters) {
    code..
}

var obj = new prototypeName(parameters)
```

## A partir de ECMAScript2015
A partir del 2015 las actualizaciones en l lenguaje trajeron consigo la palabra clave "class" y una forma mas sencilla de definir prototipos y de hacer "herencia" entre estos prototipo. 

**Importante:** Se debe tener en cuenta que Js no cuenta con *clases*. ELo que se hizo fue una "mascara", pero en el fondo el lenguaje sigue trabajando con prototipos.

``` [javascript]
class prototypeName extends prototypePather {
    constructor (parameters){        
        super(parametersPather);
        this.attribute1 = value1;
        this.attribute2 = value2; 
    }
}

// this is a method of the prototype
methodName (parameters) {
    code..
}

var obj = new prototypeName(parameters)
```
# Asincronismo
JavaScript sólo puede hacer una cosa a la vez, sin embargo; es capaz de delegar la ejecución de ciertas funciones a otros procesos. Este modelo de concurrencia se llama EventLoop.

JavaScript delega en el navegador ciertas tareas y les asocia funciones que deberán ser ejecutadas al estas tareas ser completadas. Estas funciones se llaman *callbacks*, y una vez que el navegador ha "regresado" con la respuesta(de las tareas), el callback asociado pasa a una cola de tareas para ser ejecutado una vez que JavaScript haya terminado todas las instrucciones que están en la pila de ejecución.

**IMPORTANTE**
    Si se acumulan funciones en la cola de tareas y JavaScript se encuentra ejecutando procesos muy pesados, el EventLoop quedará *bloqueado* y esas funciones pudieran tardar demasiado en ejecutarse.

En principio, cualquier tarea que se haya delegado al navegador a través de un *callback*, deberá esperar hasta que todas las instrucciones del programa principal se hayan ejecutado. Por esta razón el tiempo de espera definido en funciones como *setTimeout*, no garantizan que el callback se ejecute en ese tiempo exactamente, sino en cualquier momento a partir de allí, sólo cuando la cola de tareas se haya vaciado.

## Callback
Un callback es una función que se pasa a otra función como un argumento. Esta función se invoca, después, dentro de la función externa para completar alguna acción.

## Orden en el asincronismo
Una manera de asegurar que se respete la secuencia en que hemos realizado múltiples tareas es utilizando *callbacks*, con lo que se ejecutará luego, en cada llamada. Lo importante es que el llamado al callback se haga a través de una función anónima. Sin embargo, al hacerlo de esta manera generamos una situación poco deseada llamada CallbackHell. Ejemplo:

``` [javaScript]
const API_URL = "https://swapi.co/api/";
const PEOPLE_URL = "people/:id";
const opts = { crossDomain: true };

function obtener_personaje(id, callback) {
	consturl = `${API_URL}${PEOPLE_URL.replace(":id", id)}`;
	$.get(url, opts, function(persona) {
		console.log(`Hola yo soy ${persona.name}`);
		if (callback) {
			callback();
		}
	});
}

obtener_personaje(1, function() {
	obtener_personaje(2, function() {
		obtener_personaje(3, function() {
			obtener_personaje(4, function() {
				obtener_personaje(5, function() {
					obtener_personaje(6);
				});
			});
		});
	});
});
```

## Promesas
Son valores que aun no conocemos. Las promesas tienen tres estados:

- pending
- fullfilled
- rejected

Las promesas se invocan de la siguiente forma:

```[javaScript]
new Promise( ( resolve, reject ) => {
  // --- llamado asíncrono
  if( todoOK ) {
     // -- se ejecutó el llamado exitosamente
     resolve()
  } else {
     // -- hubo un error en el llamado
     reject()
  }
} )
```
### En Serie
A diferencia de los callbacks en el CallbackHell, que terminan estando anidados unos dentro de otros, cuando se usan Promesas la ejecución de las llamadas no se hacen de manera anidada sino de manera encadenada, al mismo nivel una debajo de la otra, lo que hace que el código sea mucho más legible y mantenible.

Ejemplo(replica del codigo anterior con los *callback*):

```[javaScript]
const API_URL = "https://swapi.co/api/";
const PEOPLE_URL = "people/:id";
const opts = { crossDomain: true };

function obtener_personaje(id) {
	return new Promise((resolve, reject) => {
		const url = `${API_URL}${PEOPLE_URL.replace(":id", id)}`;
		$.get(url, opts, function(data) {
			resolve(data);
		}).fail(() => reject(id));
	});
}

function on_error(id) {
    console.log(`Sucedio un error al obtener el personaje ${id}`)
}


obtener_personaje(1)
    .then(personaje => {console.log(`El personaje 1 es ${personaje.name}`)
    return obtener_personaje(2)
    })
    .then(personaje => {console.log(`El personaje 2 es ${personaje.name}`)
    return obtener_personaje(3)
    })
    .then(personaje => {console.log(`El personaje 3 es ${personaje.name}`)
    return obtener_personaje(4)
    })
    .then(personaje => {console.log(`El personaje 4 es ${personaje.name}`)
    return obtener_personaje(5)
    })
    .then(personaje => {console.log(`El personaje 5 es ${personaje.name}`)
    return obtener_personaje(6)
    })
    .then(personaje => {console.log(`El personaje 6 es ${personaje.name}`)
    })
    .catch(on_error)```
```

### En paralelo
Para hacer el llamado a múltiples promesas, nos apoyamos en un array de ids con el que luego construimos otro arreglo de Promesas, que pasaremos como parámetro a Promise.all( arregloDePromesas ), con las promesas podemos encadenar llamadas en paralelo, algo que no es posible usando callbacks.
Ejemplo:
```[javaScript]
const API_URL = 'https://swapi.co/api/'
const PEOPLE_URL = 'people/:id'
const opts = { crossDomain: true }

function obtenerPersonaje(id) {
  return new Promise((resolve, reject) => {
    const url = `${API_URL}${PEOPLE_URL.replace(':id', id)}`
    $
      .get(url, opts, function (data) {
        resolve(data)
      })
      .fail(() => reject(id))
  })
}

function onError(id) {
  console.log(`Sucedió un error al obtener el personaje ${id}`)
}

var ids = [1, 2, 3, 4, 5, 6, 7]
var promesas = ids.map(id => obtenerPersonaje(id))
Promise
  .all(promesas)
  .then(personajes => console.log(personajes))
  .catch(onError)
```

## Async-await
Es la manera más simple y clara de realizar tareas asíncronas. Await detiene la ejecución del programa hasta que todas las promesas sean resueltas. Para poder utilizar esta forma, hay que colocar async antes de la definición de la función, y encerrar el llamado a Promises.all() dentro de un bloque try … catch.
Ejemplo:
```[javaScript]
const API_URL = 'https://swapi.co/api/'
const PEOPLE_URL = 'people/:id'
const opts = { crossDomain: true }

function obtenerPersonaje(id) {
  return new Promise((resolve, reject) => {
    const url = `${API_URL}${PEOPLE_URL.replace(':id', id)}`
    $
      .get(url, opts, function (data) {
        resolve(data)
      })
      .fail(() => reject(id))
  })
}

function onError(id) {
  console.log(`Sucedió un error al obtener el personaje ${id}`)
}

async function obtenerPersonajes() {
  var ids = [1, 2, 3, 4, 5, 6, 7]
  var promesas = ids.map(id => obtenerPersonaje(id))
  try {
    var personajes = await Promise.all(promesas)
    console.log(personajes)
  } catch (id) {
    onError(id)
  }
}

obtenerPersonajes()
```