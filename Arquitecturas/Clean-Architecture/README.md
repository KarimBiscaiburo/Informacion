# Clean Architecture

Este tipo de arquitectura se caracteriza por resolver el "Separation of Concerns" usando 4 capas llamadas "Dominio", "Casos de uso", "Adaptadores" y "Externa". A continuación se detallan sus características.

> <br>

* DOMINIO: 

En el dominio se van a incluir las entiedades y lógicas de negocio, por lo cual es lo único que no puede cambiar y todas las demas capas van a depender de él. A su vez, serían todos aquellos requisitos del negocio que no estan tecnicamente limitados por nada, sino que estan porque la aplicación necesita que sea así.

> <br>

> [!NOTE]
> EJEMPLO:
> <br>
> Supongamos que necesitamos crear una aplicación bancaria. Uno de los requisitos para que una persona pueda abrirse una cuenta en el banco es que tenga mas de 18 años. Este requerimiento es una logica de negocio, porque no hay nada técnico que nos limite, a la hora de escribir codigo, que cuando creamos un usuario tenga que tener mas de 18 años. Siguiendo esta logica, un usuario es una entidad, por lo cual es parte del dominio, así como tambien una cuenta de banco podría ser una entidad

> <br>

``` TypeScript
// Entidad Usuario
interface User {
    name: string;
    lastName: string;
    age: number;
}

// Entidad/Logica de negocio de la cuenta del banco
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

* CASOS DE USO:

Los casos de uso serian aquellas cosas que estan limitadas tecnicamente por algo


> [!NOTE]
> EJEMPLO:
> <hr>
> 



* ADAPTADORES:

Los adaptadores son los unicos que se comunican tanto con los casos de uso como con los externos. Basicamente lo que hacen es agarrar la informacion o datos que se reciban por la capa externa, adaptarlos a conveniencia y pasarselos a la capa de casos de uso. Tambien funciona a la inversa, es decir, tenemos unos datos que necesitan ser adaptados y enviados a traves de una capa externa. Un ejemplo claro podria ser una api que reciba y envie información. Otro ejemplo mas claro sería, en nuetras aplicación utilizamos un objeto que tenga "nombre" y "apellido", pero estos datos son recibidos por la capa externa como "name" y "lastname", por lo que la capa adaptador se encarga de mapear estos datos a como se utilizan en la aplicacion.

> [!NOTE]
> EJEMPLO:
> <hr>
> 


* EXTERNA:

La capa externa o detalles de implementacion vendrian   a ser todo lo que puede cambiarse y nunca va a afectar al proyecto, es decir, el front end, back end y hasta una base de datos son capas externas, porque se pueden desarrollar con diferentes tecnologías y nunca va a cambiar al proyecto

> [!NOTE]
> EJEMPLO:
> <hr>
> 


* Dominio (lógica de negocio, entidades)
* Casos de uso (lógica funcional)
* Adapters
* Externa (ej: api)


## Ejemplo

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

// ADAPTERS -> NEXO entre USE CASE y EXTERNA
// NUNCA ACCEDER DE MANERA DIRECTA A UNA CAPA EXTERNA
// Creamos la interfaz para un el adaptador de la DB para abstraer la implementación

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
        return this.getOne(id);
    }
}

// USE CASES -> Reglas de aplicación

class App {
    constructor(private readonly dbAdapter: DBBankAdapterInterface) { }

    register(user: User) {
        try {
            this.dbAdapter.addOne(user);
            return { status: StatusStates.SUCCESS, message: "anduvo papaaaaaa" };
        } catch (e: any) {
            return { status: StatusStates.FAILED, message: "no anduvo naaaa" };
        }
    }
}

