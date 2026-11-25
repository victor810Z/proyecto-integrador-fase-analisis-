# SRS -- Especificación de Requisitos de Software

## Proyecto: Miko -- Sistema POS multisucursal

**Versión:** 1.0\
**Fecha:** 25 de noviembre de 2026

------------------------------------------------------------------------

## 1. Introducción

### 1.1 Propósito

Este documento define los requisitos de software del sistema **Miko**,
una aplicación de punto de venta (POS) diseñada para administrar las
operaciones de uno o varios establecimientos desde una misma plataforma.
Su objetivo es establecer de forma clara las funciones que deberá
ofrecer el sistema y las condiciones de calidad que deberá cumplir.

### 1.2 Alcance

Miko permitirá iniciar sesión según el rol del usuario, consultar un
panel principal, administrar productos e inventario, registrar ventas y
consultar el historial de transacciones. El sistema está pensado para
trabajar con varias sucursales y manejar distintos permisos para
administradores, gerentes y cajeros.

### 1.3 Público al que va dirigido

Este documento está dirigido al equipo de desarrollo, responsables del
proyecto y personas encargadas de revisar y validar el funcionamiento
del sistema.

## 2. Descripción general

### 2.1 Perspectiva del producto

Miko es un sistema de gestión comercial tipo POS. Reúne en una sola
aplicación las tareas principales de operación de una tienda: control de
acceso, consulta de información, administración de inventario, cobro de
productos y revisión de ventas.

### 2.2 Funciones principales

-   Inicio de sesión y acceso de acuerdo con el rol del usuario.
-   Panel principal con resumen de ventas y estadísticas.
-   Administración de productos y existencias.
-   Registro de ventas mediante un punto de venta con carrito y cobro.
-   Consulta del historial de ventas y sus métodos de pago.
-   Organización de la operación por sucursales.

### 2.3 Tipos de usuario

-   **Administrador:** administra la configuración general y puede
    supervisar la operación del sistema.
-   **Gerente:** consulta información y supervisa las operaciones de la
    sucursal que tiene asignada.
-   **Cajero:** utiliza el punto de venta para registrar y cobrar las
    compras.

### 2.4 Suposiciones y restricciones

-   Los usuarios deben contar con una cuenta autorizada para acceder.
-   Las funciones disponibles dependerán del rol asignado.
-   Para registrar y consultar información, el sistema requiere una
    conexión y una base de datos disponibles.
-   La información de productos y ventas debe asociarse con la sucursal
    correspondiente.

## 3. Requisitos funcionales

### RF-01. Inicio de sesión

-   **Descripción:** El sistema deberá permitir que los usuarios
    ingresen mediante sus credenciales y validar que la cuenta sea
    correcta. Después del acceso, mostrará las opciones permitidas según
    el rol asignado.
-   **Prioridad:** Alta.
-   **Criterio de aceptación:** Dado un usuario registrado, cuando
    introduzca credenciales válidas, el sistema permitirá el acceso y
    mostrará las funciones correspondientes a su rol. Si los datos son
    incorrectos, mostrará un mensaje de error y no permitirá entrar.

### RF-02. Panel principal y estadísticas

-   **Descripción:** El sistema deberá mostrar un panel principal con un
    resumen de la actividad comercial, incluyendo información de ventas
    y estadísticas relevantes de la sucursal o ámbito autorizado.
-   **Prioridad:** Alta.
-   **Criterio de aceptación:** Cuando un usuario con acceso al panel
    inicie sesión, podrá visualizar los indicadores disponibles. La
    información mostrada deberá corresponder a los registros existentes
    y al alcance de permisos del usuario.

### RF-03. Administración de inventario

-   **Descripción:** El sistema deberá permitir consultar y administrar
    el catálogo de productos, sus existencias y las alertas relacionadas
    con niveles bajos de inventario.
-   **Prioridad:** Alta.
-   **Criterio de aceptación:** Un usuario autorizado podrá consultar
    los productos y sus cantidades. Cuando la existencia de un producto
    alcance el nivel configurado como bajo, el sistema mostrará una
    alerta identificable para ese producto.

### RF-04. Registro y cobro de ventas

-   **Descripción:** El sistema deberá proporcionar un punto de venta
    donde el cajero pueda seleccionar productos, agregarlos a un
    carrito, revisar la compra y registrar el cobro.
-   **Prioridad:** Alta.
-   **Criterio de aceptación:** Al agregar productos al carrito, el
    sistema mostrará los artículos y el total correspondiente. Cuando el
    cajero confirme el cobro con los datos requeridos, la venta quedará
    registrada y podrá consultarse posteriormente.

### RF-05. Historial de ventas

-   **Descripción:** El sistema deberá permitir consultar las
    transacciones realizadas, mostrando la información disponible de
    cada venta, como productos, total, fecha y método de pago.
-   **Prioridad:** Media.
-   **Criterio de aceptación:** Un usuario autorizado podrá abrir el
    historial y visualizar las ventas registradas. Al seleccionar una
    transacción, el sistema mostrará sus datos y el método de pago
    asociado cuando exista esa información.

### RF-06. Gestión por sucursal y roles

-   **Descripción:** El sistema deberá asociar la información operativa
    con la sucursal correspondiente y limitar las acciones y los datos
    visibles de acuerdo con los permisos de administrador, gerente o
    cajero.
-   **Prioridad:** Alta.
-   **Criterio de aceptación:** Al ingresar, cada usuario solo podrá
    ejecutar las acciones permitidas para su rol y consultar la
    información de las sucursales a las que tenga acceso. Un usuario sin
    permiso no podrá acceder a funciones restringidas.

## 4. Requisitos no funcionales

### RNF-01. Seguridad

-   **Descripción:** El sistema deberá proteger el acceso mediante
    autenticación y control de permisos por rol. Las credenciales y la
    información de las operaciones deberán manejarse de forma segura.
-   **Prioridad:** Alta.
-   **Criterio de aceptación:** Un usuario no autenticado no podrá
    acceder a las funciones internas. Las cuentas con distintos roles
    deberán recibir únicamente los permisos asignados.

### RNF-02. Rendimiento

-   **Descripción:** Las pantallas y operaciones comunes, como abrir el
    panel, consultar productos y agregar artículos al carrito, deberán
    responder en un tiempo adecuado para no interrumpir la atención en
    caja.
-   **Prioridad:** Media.
-   **Criterio de aceptación:** En condiciones normales de operación y
    con una conexión estable, las operaciones comunes deberán mostrar
    una respuesta en un máximo objetivo de 3 segundos.

### RNF-03. Usabilidad y compatibilidad

-   **Descripción:** La interfaz deberá ser clara, consistente y fácil
    de utilizar. Los elementos principales deberán mantener una
    presentación ordenada y adaptarse a los tamaños de pantalla
    compatibles con la aplicación.
-   **Prioridad:** Media.
-   **Criterio de aceptación:** Un usuario podrá identificar las
    secciones principales (panel, inventario, punto de venta e
    historial) desde la navegación de la aplicación, y el contenido
    deberá permanecer legible y utilizable en los tamaños de pantalla
    contemplados por el proyecto.

## 5. Criterios generales de validación

El sistema se considerará aceptable cuando: 1. Los usuarios puedan
iniciar sesión y reciban permisos según su rol. 2. El panel muestre
información correspondiente a los registros disponibles. 3. El
inventario permita consultar productos, existencias y alertas. 4. El
punto de venta permita formar un carrito y registrar una venta. 5. El
historial muestre las transacciones registradas. 6. La información y las
operaciones respeten la separación por sucursal. 7. Se cumplan los
criterios de seguridad, rendimiento y usabilidad descritos en este
documento.

------------------------------------------------------------------------

**Nota:** Esta especificación se elaboró con base en el alcance descrito
para Miko: un sistema POS multisucursal con inicio de sesión, panel de
estadísticas, inventario, punto de venta e historial de ventas, y con
roles de administrador, gerente y cajero. Los detalles técnicos no
definidos aquí deberán precisarse durante el desarrollo.
