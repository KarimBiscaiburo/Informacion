# Clean Architecture

Este tipo de arquitectura se caracteriza por resolver el "Separation of Concerns" usando 4 capas llamadas "Dominio", "Casos de uso", "Adaptadores" y "Externa". A continuación se detallan sus características.

Hay que aclarar que aclarar que las capas siguientes no pueden afectar a las capas anteriores, es decir, el dominio no se puede ver afectado por los casos de uso, adaptadores o externa, los casos de uso no pueden verse afectado por los adaptadores o externa, y asi sucesivamente.

La información fluye desde adentro "Dominio" hacia afuera "Externa"

## DOMINIO: 

En el dominio se van a incluir las entiedades y lógicas de negocio, por lo cual es lo único que no puede cambiar y todas las demas capas van a depender de él. A su vez, serían todos aquellos requisitos del negocio que no estan tecnicamente limitados por nada, sino que estan porque la aplicación necesita que sea así.
> <br>

> [!NOTE]
> EJEMPLO:
> <hr>
> Supongamos que necesitamos crear una aplicación bancaria. Uno de los requisitos para que una persona pueda abrirse una cuenta en el banco es que tenga mas de 18 años. Este requerimiento es una lógica de negocio, porque no hay nada técnico que nos limite, a la hora de escribir codigo, que cuando creamos un usuario tenga que tener mas de 18 años. Siguiendo esta lógica, un usuario es una entidad, por lo cual es parte del dominio, así como tambien una cuenta de banco podría ser una entidad
> <br>

``` TypeScript
// Entidad Usuario
interface User {
    name: string;
    lastName: string;
    age: number;
}

// Entidad/lógica de negocio de la cuenta del banco
class BankAccount {
    user: User;
    minimumAge = 18;

    constructor(user: User) {
        if (this.checkMinimumAge(user)) {
            this.user = user;
        }
    }

    private checkMinimumAge(user: User) {
        return user.age >= this.minimumAge;
    }
}
```

> <br>

> [!IMPORTANT]
> Tambien existen lo que se llaman "Bussines Rules" o "Organization Rules", y estas son:
> <br>
> * Bussines Rules: aquellos requisitos que son única y exclusivamente del negocio. Ejemplo: tengo un lavadero de autos y siempre hay que usar un javon muy especifico para lavar.
> * Organization Rules: aquellos requisitos que se deben cumplir en todos los bussines rules: Ejemplo: tengo una empresa que tiene varios negocios y quiero que en todos esos negocios solo trabajen hombres.
> <br>

## CASOS DE USO:

Los casos de uso serian aquellas cosas que estan limitadas tecnicamente por algo. Tambien encapsula e implementa todos los casos de uso del sistema. Estos organizan el flujo de datos hacia y desde las entidades y dirigen a estas entidades para que utilicen sus reglas de negocio de toda la empresa para lograr los objetivos del caso de uso. Esta capa debería ser agnóstica a la tecnología y enfocarse únicamente en la lógica del negocio ya que aqui tambien va la lógica de aplicación.
> <br>

No esperamos que los cambios en esta capa afecten a las entidades. Tampoco esperamos que esta capa se vea afectada por cambios en externalidades como la base de datos, la interfaz de usuario o cualquiera de los marcos comunes.
> <br>

Sin embargo, esperamos que los cambios en el funcionamiento de la aplicación afecten a los casos de uso y, por lo tanto, al software de esta capa. Si cambian los detalles de un caso de uso, entonces, sin duda, se verá afectado algún código de esta capa.
> <br>


> [!NOTE]
> EJEMPLO:
> <hr>
> Tenemos un formulario que cuando se ingresan mal los datos, tiene que salir un "popup" de color rojo indicando que se ingresaron mal los campos. Esto está limitado tecnicamente porque hay que respetar algunas normas de UI o si se quiere, esta limitado psicológicamente ya que el color rojo indica advertencia/peligro, y si nosotros ponemos un popup de color verde generaría confusión.
> <br>

``` TypeScript
// Siguiendo con el ejemplo de las cuentas bancarias

// USE CASES -> Reglas de aplicación
class App {
    constructor(private readonly dbAdapter: DBBankAdapterInterface) { }

    // Utilizamos la entidad User del dominio para seguir con la lógica de negocio
    register(user: User) {
        try {
            this.dbAdapter.addOne(user);
            return { status: StatusStates.SUCCESS, message: "Usuario registrado correctamente" };
        } catch (e: any) {
            return { status: StatusStates.FAILED, message: "No se pudo registrar el usuario" };
        }
    }
}
```
> <br>

## ADAPTADORES:

Los adaptadores son los unicos que se comunican tanto con los casos de uso como con los externos. Basicamente lo que hacen es agarrar la información o datos que se reciban por la capa externa, adaptarlos a conveniencia y pasarselos a la capa de casos de uso. Tambien funciona a la inversa, es decir, tenemos unos datos que necesitan ser adaptados y enviados a traves de una capa externa. 
> <br>
Hay que tener en cuenta que tanto los casos de uso como la capa externa NUNCA deben comunicarse de manera directa, es decir, que por mas simple que sea el adaptador, siempre deben pasar por el para enviar o recibir información. De esta manera nos aseguramos que en caso de haber una modificación solo haya que cambiar el adaptador.
> <br>

> [!NOTE]
> EJEMPLO:
> <hr>
> Tenemos una base de datos que guarda usuarios mediante una función, esta recibe los argumentos (id: string, data: BankAccount(interfaz en la parte declarada en el dominio☝️)) pero esa id no esta dentro de ninguna entidad, por lo que debemos crear un nuevo objeto adaptado a los argumentos que recibe esa función.
> <br>

``` TypeScript
// ADAPTERS -> NEXO entre USE CASE y EXTERNA
// NUNCA ACCEDER DE MANERA DIRECTA A UNA CAPA EXTERNA

interface DBBankAdapterInterface {
    addOne(user: User): Status;
    getOne(id: string): Status;
}

class DBAdapter implements DBBankAdapterInterface {
    constructor(private readonly db: DBBank) { }

    addOne(user: User) {
        const newBankAccount = new BankAccount(user);
        const formattedData = {
            id: user.name,
            data: newBankAccount,
        };
        return this.db.addOne(formattedData);
    }

    getOne(id: string) {
        return this.db.getOne(id);
    }
}
```


## EXTERNA:

La capa externa o detalles de implementacion vendrian a ser todo lo que puede cambiarse y nunca va a afectar al proyecto, es decir, el front end, back end y hasta una base de datos son capas externas, porque se pueden desarrollar con diferentes tecnologías y nunca va a cambiar al proyecto o verse afectado.
> <br>

> [!NOTE]
> EJEMPLO:
> <hr>
> Nosotros podemos tener varios frameworks/tecnologías dentro de nuestra aplicación, como por ejemplo React.js para el FrontEnd y Express para el BackEnd, pero como estas no dejan de ser partes de la capa externa ¿Como hacemos para aplicar los caso de uso o dominio dentro de un framework, que a su vez es una capa externa?, bueno la solución es segmentar estos proyectos de manera que la lógica principal del proyecto no dependa del framework que estemos utilizando.
> <br>

``` TypeScript
// EXTERNA -> FRAMEWORK / DRIVER / UI -> Detalles de implementacion

interface DBBankAccount {
    id: string;
    data: BankAccount;
}

enum StatusStates {
    "SUCCESS" = "sucess",
    "FAILED" = "failed",
}

interface Status {
    status: StatusStates;
    message: string;
}

// Creamos la interfaz para un banco para abstraer la implementación
interface DBBankInterface {
    addOne: (bdUser: DBBankAccount) => Status;
    getOne: (id: string) => Status;
}

class DBBank implements DBBankInterface {
    listOfAccounts = new Map<string, BankAccount>();

    constructor() { }

    addOne(bdUser: DBBankAccount) {
        this.listOfAccounts.set(bdUser.id, bdUser.data);

        return {
            status: StatusStates.SUCCESS,
            message: "Se pudo guardar correctamente",
        };
    }

    getOne(id: string) {
        const user = this.listOfAccounts.get(id);

        if (!user) {
            return {
                status: StatusStates.FAILED,
                message: `couldn't find the bankAccount user`,
            };
        }

        return { status: StatusStates.SUCCESS, message: "bankAccount user found" };
    }
}

const bd = new DBBank();
```

> [!TIP]
> Esta es una manera mas sencilla de entender la capa externa:
> <br>
> En un proyecto FullStack es importante entender que Clean Architecture se aplica principalmente al back-end, donde reside la lógica de negocio central. El front-end, en este caso, actúa más como una capa de presentación que interactúa con el back-end para consumir datos y mostrar la interfaz al usuario.
> <br>

``` txt
/project-root
  /backend (Node.js - Capa de infraestructura y lógica de negocio)
    /src
      /core (o /domain)
      /application (o /usecases)
      /infrastructure
      /presentation (API o controladores para el front)
    package.json
    ...

  /frontend (React - Capa de presentación)
    /src
      /components
      /hooks
      /pages
      /services (interacciones con API o back-end)
    package.json
    ...
```