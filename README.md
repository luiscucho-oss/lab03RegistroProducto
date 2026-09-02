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
