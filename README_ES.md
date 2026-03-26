🌐 [Read in English](README.md)

# Sistema de Gestión de Stock de Cajas | Power Apps + SharePoint + Power Automate

Solución de conteo y reporte de stock diseñada para un entorno de fabricación de packaging.

Este proyecto digitaliza un proceso manual basado en papel y lo transforma en un flujo estructurado con validaciones, trazabilidad, almacenamiento centralizado y generación automática de reportes.

---

## Descripción general

El proceso original de conteo de stock se realizaba de forma manual, lo que generaba problemas como:

- errores en la carga de datos,
- falta de control sobre quién realizaba cada conteo,
- dificultad para consolidar información semanal,
- poca capacidad de filtrado por sector o producto,
- y demoras en la comunicación de resultados.

Para resolver esto, se desarrolló una solución basada en Power Platform compuesta por:

- **Power Apps** para la carga de datos y la interfaz de usuario  
- **SharePoint Lists** como base de datos estructurada  
- **Power Automate** para el envío automático de reportes por mail con Excel adjunto  

---

## Contexto de negocio

La solución fue implementada en un entorno productivo de fabricación de cajas, donde es clave tener visibilidad del stock según:

- sector (planta, expedición, etc.),
- estado del producto (zunchado, embolsado, etc.),
- tipo de empaque,
- y modelo de caja.

La aplicación permite a los operarios o responsables registrar el stock de forma ordenada, validada y trazable.

---

## Funcionalidades principales

### 1. Validación de responsable

La app no permite iniciar el proceso de conteo sin seleccionar un responsable.

El selector se alimenta de una lista de SharePoint (**MAESTRO_EMPLEADOS**) que contiene:

- nombre del empleado  
- estado activo/inactivo  
- email  
- roles o habilidades  

Solo se muestran empleados activos y habilitados para conteo de stock.

---

### 2. Flujo controlado de carga

Al iniciar, el usuario define:

- sector de trabajo  
- estado del producto  
- tipo de pack  
- responsable  

Esto estandariza la carga y mejora la trazabilidad.

---

### 3. Búsqueda de productos

Los productos pueden buscarse por:

- modelo  
- descripción  
- código  
- franquicia  

La app no permite cargar cantidades si no hay un producto seleccionado previamente.

---

### 4. Validaciones de entrada

Una vez seleccionado el producto:

- se resalta visualmente  
- se muestra el modelo elegido  
- se habilita la carga de cantidad  
- se pueden agregar observaciones  
- no se permite cargar si la cantidad está vacía  
- la cantidad solo acepta valores numéricos  

Esto reduce errores típicos de carga manual.

---

### 5. Resumen semanal de stock

La app incluye una vista de resumen donde se puede:

- consultar stock acumulado por semana  
- filtrar por fecha, sector, producto o área  
- ver totales por modelo  
- expandir detalles de cada registro  

Incluye información como:

- sector  
- responsable  
- cantidad  
- total acumulado  

---

### 6. Almacenamiento centralizado

Todos los registros se guardan en una lista de SharePoint con campos como:

- código de producto  
- descripción  
- sector  
- estado  
- pack  
- cantidad  
- responsable  
- fecha de conteo  
- semana (batch)  
- observaciones  

---

### 7. Envío automático de reportes

Al finalizar el conteo, el usuario puede enviar un reporte desde la app.

Un flujo de Power Automate:

- recibe el trigger desde Power Apps  
- procesa los datos  
- genera un archivo Excel  
- lo nombra automáticamente según la semana  
- y lo envía por mail a los responsables  

Esto permite visibilidad casi en tiempo real sin intervención manual.

---

## Flujo del proceso

1. Selección del responsable  
2. Validación de empleado activo  
3. Definición de sector, estado y pack  
4. Búsqueda y selección de producto  
5. Carga de cantidad y observaciones  
6. Registro en SharePoint  
7. Consulta de resumen semanal  
8. Envío de reporte por mail  
9. Generación automática de Excel  

---

## Capturas

### Selección de responsable
![Responsable](docs/screenshots/01-login-responsable.png)

### Responsable seleccionado
![Responsable seleccionado](docs/screenshots/02-responsable-seleccionado.png)

### Maestro de empleados
![Maestro empleados](docs/screenshots/03-maestro-empleados.png)

### Búsqueda de productos
![Busqueda](docs/screenshots/04-busqueda-productos.png)

### Carga de conteo
![Carga](docs/screenshots/05-carga-conteo.png)

### Resumen semanal
![Resumen](docs/screenshots/06-resumen-semanal.png)

### Lista en SharePoint
![SharePoint](docs/screenshots/07-sharepoint-lista-stock.png)

### Confirmación de envío
![Confirmacion](docs/screenshots/08-confirmacion-mail.png)

### Flujo de Power Automate
![Flow](docs/screenshots/09-power-automate-flow.png)

### Mail con reporte
![Mail](docs/screenshots/10-mail-reporte.png)

---

## Stack tecnológico

- Power Apps  
- Power Automate  
- SharePoint  
- Excel  
- Lógica de validación  
- Diseño de interfaz orientado a operación  

---

## Documentación adicional

Para más detalles sobre el sistema:

- [Modelo de datos](docs/data-model_ES.md)
- [Descripción del flujo](docs/flow-description_ES.md)
- [Arquitectura](docs/architecture_ES.md)

## Mejoras logradas

- Eliminación del registro manual en papel  
- Mejora en la trazabilidad  
- Estandarización del proceso de carga  
- Reducción de errores  
- Centralización de la información  
- Visibilidad semanal del stock  
- Automatización de reportes  
- Ahorro de tiempo operativo  

---

## Problemas resueltos

- Control de usuario responsable  
- Filtrado dinámico de empleados activos  
- Validación de datos incompletos  
- Organización del stock por semana  
- Automatización de envío de reportes  

---

## Próximas mejoras

- Permisos por sector  
- Dashboard en Power BI  
- Escaneo de códigos de barras  
- Historial de ajustes  
- Alertas de bajo stock  

---

## Notas

Este repositorio documenta la lógica funcional y la arquitectura de la solución.  
Los datos sensibles han sido anonimizados.

---

## 👤 Autor

**Gonzalo**  
Automatización de procesos y digitalización operativa con Power Platform
