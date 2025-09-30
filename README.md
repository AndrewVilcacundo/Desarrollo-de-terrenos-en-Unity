# Desarrollo de Terrenos en Unity

## Descripción del Proyecto
Este proyecto fue desarrollado como parte de la tarea de creación de escenas en Unity.  
El objetivo fue diseñar un **terreno**, colocar **cubos**, y personalizar la escena con **texturas, rocas y un río**, demostrando creatividad y habilidades básicas de Unity.

---

## Contenido de la Escena

### Terreno
- Creado con la herramienta **Terrain** de Unity.
- Modificado con **colinas y áreas planas** para dar variedad al paisaje.
- Pintado con **texturas del paquete Terrain Textures Pack Free**: césped, tierra y piedra.

### Cubos
- Se colocaron al menos **10 cubos** en distintas posiciones.
- Representan estructuras, rocas o elementos de la escena.
- Se les aplicaron **materiales personalizados** para color y variedad.
- Algunos se generaron automáticamente con un **script en C#** que coloca cubos en posiciones aleatorias.


using UnityEngine;

public class CubesGenerator : MonoBehaviour
{
    public GameObject cubePrefab; // Asigna un Cube prefab desde Unity
    public int numberOfCubes = 10;
    public float terrainSize = 100f; // tamaño aproximado del terreno

    void Start()
    {
        for (int i = 0; i < numberOfCubes; i++)
        {
            Vector3 position = new Vector3(
                Random.Range(0, terrainSize), 
                0, 
                Random.Range(0, terrainSize)
            );

            // Crea un cubo en la posición
            Instantiate(cubePrefab, position, Quaternion.identity);
        }
    }
}


### Rocas
- Se agregaron rocas usando **objetos 3D deformados (cubes y spheres)** con materiales grises, y también se pueden usar prefabs de la Asset Store.
- Se distribuyeron en puntos estratégicos como cerca del río o en colinas para dar realismo.

### Río
- Creado simulando un cauce bajando el terreno.
- Se añadió un **plane con material transparente azul** para representar agua.
- Opcional: se puede usar un **prefab de agua animada de la Asset Store** para un efecto más realista.

### Iluminación y Ambientación
- Se utilizó **Directional Light** para simular el sol y generar sombras realistas.
- La escena está organizada para mostrar un **paisaje natural coherente**.

---

## Cómo ejecutar el proyecto

1. Clona este repositorio en tu computadora:

```bash
git clone https://github.com/TUUSUARIO/TUREPO.git
