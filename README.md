# Introducci-n
Introduccion en MONGO DB

Curso basado en la Base de Datos Mongo DB.
Mongo DB es multiplataforma es decir puede montarse en varios S.Operativos

CLOUD COMPUTING
Se puede hacer también en CPD's

El Corte Inglés utiliza MONGO

GitHub  es una Nube (Programa de control de versiones)

MONGO DB esta escrito en C++
Palabra MONGO significa enorme

Colección y documento en lugar de tabla y tupla utilizados en base de datos relacionales.
Cada registro lo llamamos documento
El registro suele tener más datos que el formulario

Hoy en día hay poca diferencia entre ADMINISTRADOR y DESARROLLADOR.
Hoy en día quien inyecta datos en BIG DATA es MONGO DB
MONGO DB utiliza base de datos tipo NoSQL.

Documentos en MONGODB poseen formato JSON (Javascript Object Notation)
{
  email:"pedro@gmail.com",
  "password":"pedro1234"
}

Es un lenguaje de ALTO NIVEL
MULTIHILO

Son almacenados en BSON (Binary JSON)
Mongo DB comenzo en 2007. Se llamaba 10g
Licencia GNU AGPL de la versión Community de Mongo DB

Diferencias entre NoSQL y SQL
______________________________

NoSQL no soportan operaciones JOIN

El Teorema CAP

NoSQL
_____
Base de Datos de grafos
Base de Datos de columnares
Base de Datos orientada a documentos                                            API's

                                                             ________
                                                             ________             REPLICA SETS
                                                             ________
                                              10 seg                      10 seg             
                                                             
                                         ________                                _________
                                         ________               10 seg           _________ 
                                         ________                                _________  
                                         
MONGO DB permite el escalado horizontal  -->  SHARDING
es decir en lugar de tener 1 de 32 por 2 de 16.
Datos geográficos

No hay posibilidad de inyecciones SQL en MOngo DB
MONGO DB se integra bien con Javascript y JSON

                                         _____Servidor____________________________
                                         |                                        |
                                         |            Repositorio                 |
                                         |                                        |
                                         |                ______________          |
                                         |                |__images_____|         |
                                         |                                        |
                                         |                                        |
                                         __________________________________________
                                         
                                         DB <16 Mbytes>
                                         
                                         producto
                                           name
                                           ------
                                           ------
                                           ------
                                           ------
                                           imagenes; "http://..../.....jpg
                                           
MONGO DB no permite realizar operaciones JOIN como en B.D. Relacionales

                                                            CPU
                           ______________________________________________________                                 
                                          ___________  Memoria RAM
                                          |
                                          |
                                          | I/O
                                          |                                In-memory       
                                      ___________   
                                      | Disco    |
                                      ____________
                                          
                          ________________________________________________________                                          

Es costoso migrar una B.D SQL a B.D MONGO

LISTADO DE BASES DE DATOS MAS UTILIZADAS EN EL MUNDO
____________________________________________________

1. ORACLE
2. MySQL
3. Microsoft SQL
4. MONGO DB


Trabajar y comprobar al desarrollar
MONGO trae un servidor local para utilizar la BASE DE DATOS.

Windows      Ejecutable msi
Para descargarte 

Introducción
Documentación Oficial
MongoDB Docs

MongoDB es útil para desarrollos rápidos.

Intsalación en Windows
La instalación de MongoDB en Windows esta en la siguiente ubicación:

Archivos de Programas/MongoDB/Server/4.2/bin

En esta carpeta tenemos los archivos:

mongod: Ejecuta el servidor de MongoDB
mongo: Ejecuta el shell de Mongo
Desde el terminal verificamos la versión instalada de Mongo:

$ mongo --version
MongoDB shell version v4.2.2


El almacenamiento fisico de las bases de datos en MongoDB se hace en la carpeta:

C:\data\db

Si copio esa carpeta y la copio en otro ordenador no funcionará, debe hacerse la importación de las bases de datos a través de herramientas.

Concepto de Documento en MongoDB
Tres ventajas:

Correspondencia con tipos nativos (Objetos JS)
Los arrays o documentos embebidos reducen las necesidades de joins.
Esquemas dinámicos permiten polimorfismo
La base de datos ya no tiene la estructura de la base de datos, se hace desde las clases (Mongoos).

La velocidad de lectura es muy rápida.

BSON (JSON Binario)
Velocidad de lectura.
Amplía tipos de JSON BSON Types
BSON es transparente para el administrador. No comprime tanto comparado con JSON.

Si solo usas JS todos los tipos de BSON sobrarán, pero para entornos como JAVA u otros si son muy útiles.

Limites:

Documento BSON menor a 16 megabytes.
Documentos anidados o embebidos menor de 100 niveles.
Documentos, Colecciones y Bases de Datos
BD Relacional	MongoDB
Registro	Documento
Tabla	Colección
BD	BD
Ademas tenenos:

Vistas de sólo lectura
Vistas On-demand
Campo _id
Todos los documentos tendrán el campo _id t será único a nivel de colección.

Si el campo _id no es especificado cuando se inserta un documento MongoDB lo añade como un tipo ObjectId.



La mayoría de los drivers crean el _id de tipo ObjectId si no se especifica. 

Restricciones del _id:

Puede ser de cualquier tipo incluso un documento, excepto de tipo array. 
El _id es único a nivel de colección
¿Permite Objetos con arrays? Vamos a comprobarlo

> use foo
switched to db foo

> db.clientes.insert({_id: {a:1, b:1}})
WriteResult({ "nInserted" : 1 })

PERMITIDO

> db.clientes.insert({ _id: [1, 2, 3] })
WriteResult({
	"nInserted" : 0,
	"writeError" : {
		"code" : 2,
		"errmsg" : "can't use an array for _id"
	}
})

ERROR DE EJECUCIÓN

> db.clientes.insert({ _id: {[1, 2, 3]} })
2020-02-09T20:44:04.777+0100 E  QUERY    [js] uncaught exception: SyntaxError: missing ] in computed property name :
@(shell):1:29

