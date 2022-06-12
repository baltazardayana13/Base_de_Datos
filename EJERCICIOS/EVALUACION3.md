
## Práctica 4
### Data warehouse

Objetivo: Demostrar la identificación de los elementos que componen data warehouse y
su esquema

Ejercicio:

1. ¿Qué es un DataWarehouse?(valor 2)

Un repositorio central de datos, un data warehouse es un tipo de base de datos diseñado específicamente para consultas y análisis rápidos.
Data warehouse es un sistema que agrega y combina información de diferentes fuentes en un almacén de datos único y centralizado; consistente para respaldar el análisis empresarial, la minería de datos, inteligencia artificial y Machine Learning. Data warehouse permite a una organización o empresa ejecutar análisis potentes en grandes volúmenes petabytes y petabytes de datos históricos de formas que una base de datos estándar simplemente no puede.

2. Realiza un diseño del modelo en estrella (valor 2)


![MODELO EN ESTRELLA](https://user-images.githubusercontent.com/101912013/173212153-ab6822a7-4762-4a52-add5-b7e952c4225c.png)

3. Realiza un diseño del modelo copo de nieve (valor 2)

![MODELO COPO DE NIEVE](https://user-images.githubusercontent.com/101912013/173212161-3ff7f042-c4d7-4901-8d6c-2e14f9636cd3.png)

## Práctica 7

### Funciones en SQL
Objetivo: Demostrar el uso y aplicación en una base de datos para mejorar la gestión

Ejercicio:

1. Calcula el número total de productos que hay en la tabla productos. (valor 4.5)

USE empresa;

SELECT COUNT(producto)

FROM productos;


2. Muestra el número total de productos que tiene cada uno de los fabricantes. El listado
también debe incluir los fabricantes que no tienen ningún producto. El resultado
mostrará dos columnas, una con el nombre del fabricante y otra con el número de
productos que tiene. Ordene el resultado descendentemente por el número de
productos. (valor 4.5)


SELECT fabricante, COUNT(*) 

FROM fabricantes GROUP BY fabricante

ORDER BY COUNT(*) DESC;


3. Muestra el precio máximo, precio mínimo y precio medio de los productos de cada
uno de los fabricantes. El resultado mostrará el nombre del fabricante junto con los
datos que se solicitan. (valor 4.5)

SELECT AVG(precio_en_dolares),MAX(precio_en_dolares),MIN(precio_en_dolares), fabricantes.fabricante

FROM productos, fabricantes

WHERE productos.codigo_producto = fabricantes.codigo_producto2

GROUP BY fabricantes.fabricante;


4. Muestra el nombre de cada fabricante, junto con el precio máximo, precio mínimo,
precio medio y el número total de productos de los fabricantes que tienen un precio
medio superior a 200€. Es necesario mostrar el nombre del fabricante. (valor 4.5)


SELECT AVG(precio_en_dolares), MAX(precio_en_dolares),MIN(precio_en_dolares),fabricante

FROM productos, fabricantes

WHERE productos.codigo_producto = fabricantes.codigo_producto2

GROUP BY fabricantes.fabricante

HAVING AVG(precio_en_dolares) >= 200;

https://www.db-fiddle.com/f/ursVbfxatbDhYLScJcrRmn/5
