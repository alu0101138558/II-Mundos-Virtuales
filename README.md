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
transform.rotation = Quaternion.Euler(tranform.rotation.x, transform.rotation.y + 30, transform.rotation.z);
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
transform.rotation = Quaternion.Euler(tranform.rotation.x, transform.rotation.y + 30, transform.rotation.z);
transform.position = new Vector3(transform.position.x + 3, transform.position.y + 3, transform.position.z + 3); 
```

Después de comprobarlo concluyo que el resultado es el mismo.

## 7. ¿Como puedes obtener la distancia al plano cerca del volumen de vista desde la cámara?

Se puede obtener en los siguientes opciones:

![eje7.jpg](/images/eje7.jpg)

## 8. ¿Como puedes aumentar el ángulo de la cámara?

Este puede ser aumentado desde la propiedad de la cámara denominada **Field of View**.

## 9. ¿Qué efecto tiene disminuir el ángulo de la cámara?

El efecto que tiene es que se pierde visión perisférica de los elementos de la escena.

## 10. Configura un volumen de vista que recorte objetos de la escena.

![eje10.jpg](/images/eje10.jpg)

![eje10.2.jpg](/images/eje10.2.jpg)

## 11. ¿Como puedes realizar la proyección al espacio 2D?

Puede ser realizado gracias a la matriz de proyecciones que se encargan de pasar a 2D los objetos 3D. Las librerías de gráficos que permiten proyección son:

* **Ortogonal:** Conservan las medidas, no se alamacena la información de distancias.

* **Prespectiva:** Los objetos más cercanos al observador son más grandes y los más alejados son pequeños.

## 12. Especifica la rotación de los apartados 4 y 6 con la utilidad quaternion.

Ya en los apartados 4 y 6 la especifiqué con quaternion, pero quedaría de la siguiente manera:

```c#
transform.rotation = Quaternion.Euler(tranform.rotation.x, transform.rotation.y + 30, transform.rotation.z);
```

## 13. ¿Como puedes averiguar la matriz de proyección en perspectiva que se ha usado para proyectar la escena al último frame renderizado?

Puede ser hallada de la siguiente manera en la función Update: 

```c#
public class ExampleClass : MonoBehaviour {
    public Matrix4x4 originalProjection;
    Camera camera;
    
    void Start() {
    	camera = GetComponent<Camera>();
    }
    
    void Update() {
        Matrix4x4 p = originalProjection;
        p.m01 += Mathf.Sin(Time.time * 1.2F) * 0.1F;
        p.m10 += Mathf.Sin(Time.time * 1.5F) * 0.1F;
        camera.projectionMatrix = p;
    }
}
```
*p* representa a la matriz de proyección en el último frame renderizado.

## 14. ¿Como puedes averiguar la matriz de proyección en perspectiva ortográfica que se ha usado para proyectar la escena al último frame renderizado?

Se puede obtener a traves del método:

```c#
public static Matrix4x4 CreateOrthographic (float width, float height, float zNearPlane, float zFarPlane);
```
Los parámetros que se le deben pasar referentes a la cámara, significando cada uno:

* **width:** Ancho del volumen de vista.
* **height:** Alto del volumen de vista. 
* **zNearPlane:** Valor Z mínimo del volumen de vista.
* **zFarPlane:** Valor Z máximo del volumen de vista.

## 15. ¿Cómo puedes obtener la matriz de transformación entre el sistema de coordenadas local y el mundial?


## 16. ¿Cómo puedes obtener la matriz para cambiar al sistema de referencia de vista?

## 17. Especifica la matriz de la proyección usado en un instante de la ejecución del ejercicio 1 de la práctica 1.

## 18. Especifica la matriz de modelo y vista de la escena del ejercicio 1 de la práctica 1.

## 19. Aplica una rotación en el start de uno de los objetos de la escena y muestra la matriz de cambio al sistema de referencias mundial.

## 20. ¿Como puedes calcular las coordenadas del sistema de referencia de un objeto con las siguientes propiedades del Transform:?: Position (3, 1, 1), Rotation (45, 0, 45)