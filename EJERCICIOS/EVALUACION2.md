## Práctica 3.
### Introducción a SQL
Objetivo: Demostrar la correcta identificación de los conceptos del lenguaje SQL
Ejercicio:

1. Menciona los comandos DMl: (valor .85)
SELECT
INSERT
UPDATE
DELETE



2. Menciona 3 tipos de datos que existen: (valor .85)
varchar(n)
int
smallint


3. ¿Qué diferencia existe entre TRUNCATE y DELETE?(valor .85)

El TRUNCATE  no permietr el borrado selectivo por lo que elimina todo el contenido de la tabla, el DELETE si acepta el borrado selescrtivo.
4. ¿Para qué se utiliza el atributo UNIQUE?(valor .85)
Se utiliza para garantizar que no se inserten valores duplicados.

5. ¿Qué diferencia hay entre los tipos de datos VARCHAR y CHAR? (valor .85)

char es de longitud fija que es especificada por el usuario y varchar es una cadena de caracteres de longitud variable especificada por el usuario

6. Defina brevemente el significado de las siglas SQL(valor .85)

SQL (Structured Query Language) 
Es un lenguaje de consulta con estructura
7. Defina brevemente qué es MySQL WorkBench (valor .85)
Es un editor visual de base de datos.
## Práctica 5.
### Gestores de base de datos

Objetivo: Categorizar los distintos gestores de base de datos que existen y señalar las
ventajas y desventajas

Evaluación: Conoce los tipos de gestores de base de datos 3 puntos.

Domina sus diferencias de los gestores de base de datos mencionados 3 puntos

Ejercicio:

En un mapa conceptual presenta 3 gestores de bases de datos, sus características
principales, las ventajas y desventajas. (valor 6)

![image](https://user-images.githubusercontent.com/91554777/170415427-e2b7321b-a97f-43b0-ac24-6e506c307e6b.png)

## Práctica 6.
### Herramienta en línea y ejercicio necesarios para realizar las prácticas

Creación de base de datos.

Objetivo: Demostrar mediante la creación de una base de datos el uso y la aplicación de
las funciones

Ejercicio: Creación de la base de datos (valor 18 puntos)

Tienda de informática

![image](https://user-images.githubusercontent.com/91554777/170415101-717bca19-3644-46a9-8a57-8d5940c5d283.png)




Modelo entidad/relación

![image](https://user-images.githubusercontent.com/101912013/173202498-1b89a2cb-aa71-4bf3-aec9-aa8db1474e58.png)



Base de datos para MySQL

https://www.db-fiddle.com/f/ursVbfxatbDhYLScJcrRmn/0


CREATE DATABASE empresa;

USE empresa;


CREATE TABLE productos(

	codigo_producto CHAR(100) NOT NULL PRIMARY KEY,
	
    producto CHAR(100) NOT NULL,
    
    precio_en_dolares float NOT NULL
    
);


INSERT INTO productos VALUES('DD-23','Disco duro SATA 1TB',86.99);

 INSERT INTO productos VALUES('MM-34','Memoria RAM DDR4 8GB',120);
 
 INSERT INTO productos VALUES('DD-98','Disco SSD 1 TB',150.99);
 
 INSERT INTO productos VALUES('MM-98','GeForce GTX 1050Ti',185);
 
 INSERT INTO productos VALUES('MM-23','GEForce GTX 1080 Xtreme',755);
 
 INSERT INTO productos VALUES('MT-12','Monitor 24 LED Full HD',202);
 
 INSERT INTO productos VALUES('MT-08','Monitor 27 LED Full HD',245.99);
 
 INSERT INTO productos VALUES('LP-19','Portatil yoga 520',559);
 
 INSERT INTO productos VALUES('LP-11','Portatil Ideapd 320',444);
 
 INSERT INTO productos VALUES('IM-56','Impresora HP Deskjet 3720',59.99);
 
 INSERT INTO productos VALUES('IP-54','Imprfesora HP Laserjet Pro M26nw',180);

--CREANOS LA TABLA fabricantes

CREATE TABLE fabricantes(

    fabricante CHAR(100) NOT NULL,
    
    id_fabricante CHAR(100) PRIMARY KEY,
    
   codigo_producto2 CHAR(100),
   
   FOREIGN KEY (codigo_producto2) REFERENCES productos (codigo_producto)
);
 INSERT INTO fabricantes VALUES('SEAGATE','fab_1','DD-23');
 
INSERT INTO fabricantes VALUES('CRUCIAL','fab_2','MM-34');

INSERT INTO fabricantes VALUES('SAMMSUNG','fab_3','DD-98');

INSERT INTO fabricantes VALUES('GYGABYTE','fab_4','MM-98');

INSERT INTO fabricantes VALUES('CRUCIAL','fab_5','MM-23');

INSERT INTO fabricantes VALUES('ASUS','fab_6','MT-12');

INSERT INTO fabricantes VALUES('ASUS','fab_7','MT-08');

INSERT INTO fabricantes VALUES('LENOVO','fab_8','LP-19');

INSERT INTO fabricantes VALUES('LENOVO','fab_9','LP-11');

INSERT INTO fabricantes VALUES('HP','fab_10','IM-56');

INSERT INTO fabricantes VALUES('HP','fab_11','IP-54');



