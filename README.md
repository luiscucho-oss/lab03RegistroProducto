# Registro de Producto

## Alumno
Luis Cucho

## Descripción
Aplicación desarrollada con Kotlin y Jetpack Compose que permite registrar un producto ingresando su nombre, precio y cantidad.

Al presionar el botón "AGREGAR PRODUCTO", la aplicación muestra una tarjeta con el resumen del producto y calcula el importe multiplicando el precio por la cantidad.

## Capturas

### Pantalla inicial

<img width="261" height="563" alt="Captura de pantalla 2026-09-02 a las 5 23 57 p  m" src="https://github.com/user-attachments/assets/35e4e7e4-770e-4185-b7eb-713aeda86227" />


### Producto registrado

<img width="261" height="563" alt="Captura de pantalla 2026-09-02 a las 5 24 26 p  m" src="https://github.com/user-attachments/assets/cc676832-f152-47a0-8fa8-116795ccd510" />


## ¿Qué pasa si las variables se declaran sin remember?

Al quitar `remember`, Compose no conserva correctamente el valor del estado durante las recomposiciones. Por eso, cuando la interfaz se vuelve a dibujar, el valor puede volver a su estado inicial y el TextField no se comporta correctamente.

`remember` permite que Compose recuerde el valor mientras el composable permanece en la composición.

## Mejora con IA

Para la mejora del laboratorio se utilizó ChatGPT en la rama `mejora-ia`.

| Prompt que usé | Qué generó la IA | Qué acepté o corregí y por qué |
|---|---|---|
| Agrega una validación en `PantallaRegistro` para que, si el usuario deja algún campo vacío y presiona AGREGAR PRODUCTO, se muestre un mensaje de error en rojo en lugar de la Card. También agrega un botón LIMPIAR que vacíe nombre, precio y cantidad, oculte la Card y elimine cualquier mensaje de error. No cambies el diseño principal de la pantalla. | Se agregó la variable `mensajeError`, la validación con `isBlank()`, un mensaje de error usando el color de error del tema y un botón LIMPIAR que reinicia los estados del formulario. | La funcionalidad principal se mantuvo porque cumplía con lo solicitado. Después de probarla, detecté que permitía ingresar letras en precio y cantidad. |
| Corrige la validación para que el precio solo acepte un número válido y la cantidad solo acepte un número entero válido. | Se agregó una validación usando `precio.toDoubleOrNull()` y `cantidad.toIntOrNull()` antes de mostrar la Card. | Acepté esta corrección porque evita que un precio con letras se convierta en 0.0 y permite mostrar al usuario un mensaje de error más claro. |

### Pruebas realizadas

- Campos vacíos: se muestra `Completa todos los campos`.
- Precio con letras: se muestra `El precio debe ser un número válido`.
- Cantidad con letras: se muestra `La cantidad debe ser un número entero válido`.
- Datos válidos: se muestra correctamente la Card.
- Botón LIMPIAR: vacía los campos y oculta el resumen.
