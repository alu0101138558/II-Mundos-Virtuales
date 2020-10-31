# II-Mundos-Virtuales

## 1. ¿Qué funciones se pueden usar en los scripts de Unity para llevar a cabo traslaciones, rotaciones y escalados? 

Las funciones que se pueden usar en los scripts de Unity realizar las siguientes acciones son: 

* Traslaciones: transform.traslation
* Rotaciones: transform.rotation 
* Escalados: transform.scale

## 2. ¿Cómo duplicarías el tamaño de un objeto en un script?

Lo que haría desde el script sería acceder a la propiedad transform.scale en la función Start y multiplicaría su tamaño al doble del actual, obteniendo así el resultado propuesto por el enunciado. Dejando la función así: 

```c#
transform.scale = new Vector3(transform.scale.x, transform.scale.y, transform.scale.z) * 2;
```

## 3. ¿Cómo situarías un objeto en la posición (3,5,1)?

Lo que haría para situar un objeto en la posición (3, 5, 1) sería:

* **Fuera del script:** Modificaría la propiedad Position y lo situaría en esas coordenadas.

* **Dentro del script:** Accedería a la propiedad transform.position en la función Start y le asignaría esas coordenadas. Dejando la función de esta manera:

```c#
transform.position = new Vector3(3, 5, 1);
```

## 4. ¿Como trasladarías 3 metros en cada uno de los ejes y luego lo rotas 30º alrededor del eje Y?

Lo que haría sería desarrollar un script con lo siguiente en la función Start: 

```c#
transform.position = new Vector3(transform.position.x + 3, transform.position.y + 3, transform.position.z + 3); 
transform.rotation = Quaternion.Euler(0, transform.rotation.y + 30, 0);
```

## ¿5. Como rotarías un objeto sobre el eje (1, 1, 1)?

Lo que haría para rotar un objeto en la sobre el eje (1, 1, 1) sería: 

* **Fuera del script:** Modificaría la propiedad Rotation y lo rotaría en esas coordenadas.

* **Dentro del script:** Accedería a la propiedad *transform.rotation* en la función Strart y le asignaría esas posiciones de rotación. Dejando la función de esta manera: 

```c#
transform.rotation = Quaternion.Euler(1, 1, 1);
```

## 6. Rota un objeto alrededor del eje Y 30ª y desplázalo 3 metros en cada uno de los ejes. ¿Obtendrías el mismo resultado que en 4?

```c#
transform.rotation = Quaternion.Euler(0, transform.rotation.y + 30, 0);
transform.position = new Vector3(transform.position.x + 3, transform.position.y + 3, transform.position.z + 3); 
```

Despues de probarlo concluyo que el resultado es el mismo.

## 7. ¿Como puedes obtener la distancia al plano cerca del volumen de vista desde la cámara?

## 8. ¿Como puedes aumentar el ángulo de la cámara?

## 9. ¿Qué efecto tiene disminuir el ángulo de la cámara?

## 10. Configura un volumen de vista que recorte objetos de la escena.