# Hexagonal Architecture

A diferencia con la clean architecture, esta no trabaja con capas, sino con hexagonos. Las ideas son muy similares a la clean architecture.
> <br>
![Grafico Hexagonal Architecture](./Hexagonal-Architecture.png)
> <br>

Esta arquitectura esta pensada de la siguiente manera:

* Como parte central y nucleo del hexagono vamos a tener el "Dominio", que es toda la lógica de la aplicación.
* Luego tenemos los adaptadores, que se van a encargar de enviar o recibir información. Ademas se encargan de implementar la interfaz 
* En tercer lugar tenemos los "Puertos", que se van a encargar de limitar las acciones que puede hacer nuestro hexagono. Estos tambien se pueden interpretar como interfaces que determinan un contrato que debe cumplir una entidad.



## Dominio








## Adaptadores






## Puertos







## Eventos

Si bien los eventos son parte de la idea, no forman parte de una manera de estructurar nuestros archivos, ya que es nada mas que un concepto para entender la comunicación en un hexagono o la comunicación entre hexagonos.





vamos a tener un punto central que va a ser el dominio, varios "adaptadores" que a su vez cada adaptador va a tener cosas que lo limiten, llamados "puertos" y por utlimo vamos a tener los eventos que van llegando a esos puertos

el dominio puede ser la cocina donde se preparan los productos
los adaptadores serian como los recepcionistas o cajeros que toman la orden y se la trasmiten a la cocina
los puertos pueden ser como un menu, donde estan cada una de las opciones que tengo para elegir
los eventos podriamos interpretarlos como los clientes que llegan a nuestro negocio para comprar

ahora, tambien tenemos un problema que surge cuando en la pizzeria nos quedamos sin materias primas para hacer las pizzas

entonces la cocina (el dominio) se debe comunicar con otro receptor (un adaptador) para que este le pida al proveedor (evento), a traves de un puerto, lo que necesitamos. Pero este proveedor es tambien un hexagono con sus respectivos adaptadores, puertos, eventos y dominio

Hay que tener en cuenta que la comunicacion entre hexagonos se realiza UNICAMENTE a travez de los adaptadores y sus puertos, es decir nunca un adaptadore de una pizzeria puede comunicarse directamente con la huerta(proveedor/dominio), sino que si o si tiene que hacerlo mediante el puerto y adaptador de la huerta

cada servicio se podria considerar como un hexagono

eventos izquierdos -> Triggers = son aquellos eventos que hacen que el hexagono empiece a funcionar, los gatillos o actores primarios
Puertos -> 
Adaptadores -> Si los adaptadores estan a la izquierda en el hexagono se van a llamar "Driver", son los que conducen a la accion primaria y si estan a la derecha se llaman "Driven", son conducidos. Pero para lo que un hexagono es un driven, para otro hexagono va a ser un driver que va a recibir, por lo tanto tambien seria el Trigger
Puertos
eventos derechos -> pueden ser otro hexagono o actores secundarios

* Servicios (servicios de aplicación - lógica de negocio)
* Puertos (limitar lo que entra o lo que sale de los servicios)
* Adapters (implementar los puertos)

### Ejemplo:

Supongamos que tenemos nuestro negocio que es un pizzeria
