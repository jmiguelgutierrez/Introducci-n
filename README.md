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


