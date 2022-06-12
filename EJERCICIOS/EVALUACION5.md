## Práctica 9.
### Operaciones en una base de datos.
Objetivo: Demostrar las operaciones que se realizan en una base de datos, aplicar el modelo relacional y el lenguaje SQL

Evaluación: Para poder tener correcto cada ejercicio deberán de mostrar el resultado que se da en cada respuesta.

Lista el nombre de todos los productos que hay en la tabla producto.


1. Lista los nombres y los precios de todos los productos de la tabla producto.
![image](https://user-images.githubusercontent.com/101912013/173214320-b4af95f0-dafb-49fb-90ba-3f466decc354.png)

SELECT producto, precio_en_dolares

FROM productos;


2. Lista todas las columnas de la tabla producto.

![image](https://user-images.githubusercontent.com/101912013/173214457-086f281b-cdf4-4696-a19c-2b9cc24a4676.png)

SELECT*

FROM productos;

3. Devuelve una lista con el nombre del producto, precio y nombre de fabricante de
todos los productos de la base de datos.


SELECT producto, precio_en_dolares, fabricante

FROM productos,fabricantes

WHERE productos.codigo_producto = fabricantes.codigo_producto2;

![image](https://user-images.githubusercontent.com/101912013/173214554-d3d4b033-b986-465e-bca1-dba981732d71.png)

Subconsultas (En la cláusula WHERE)
1. Devuelve todos los productos del fabricante Lenovo. (Sin utilizar INNER
JOIN).

SELECT producto, fabricante="lENOVO"

FROM productos, fabricantes

WHERE productos.codigo_producto=fabricantes.codigo_producto2
;
![image](https://user-images.githubusercontent.com/101912013/173215332-c57f056c-5686-4df0-8285-9db9754b584c.png)



2. Devuelve todos los datos de los productos que tienen el mismo precio que el
producto más caro del fabricante Lenovo. (Sin utilizar INNER JOIN).

SELECT precio_en_dolares=559, fabricante

FROM productos, fabricantes

WHERE productos.codigo_producto = fabricantes.codigo_producto2

;

![image](https://user-images.githubusercontent.com/101912013/173216988-da63650c-660d-47f1-8c98-2d8b44653131.png)



3. Lista el nombre del producto más caro del fabricante Lenovo.
SELECT MAX(precio_en_dolares), fabricante="LENOVO"
FROM productos, fabricantes
WHERE productos.codigo_producto = fabricantes.codigo_producto2
GROUP BY fabricantes.fabricante;
![image](https://user-images.githubusercontent.com/101912013/173215498-915a2cab-f728-4367-94f5-da046fa1916f.png)



