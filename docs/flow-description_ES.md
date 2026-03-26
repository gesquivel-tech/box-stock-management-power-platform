🌐 [Read in English](flow-description.md)

# Descripción del Flujo

Este documento describe el flujo funcional del Sistema de Gestión de Stock de Cajas.

---

## 1. Selección de Responsable

El usuario inicia la aplicación seleccionando un responsable.

### Validación
- La app no permite continuar sin seleccionar un responsable  
- La lista proviene del Maestro de Empleados en SharePoint  
- Solo se muestran empleados activos y autorizados  

---

## 2. Configuración del Contexto de Conteo

Una vez seleccionado el responsable, el usuario define:

- sector o ubicación  
- estado del producto  
- tipo de pack  

Esto permite estandarizar los registros y mejorar la trazabilidad.

---

## 3. Búsqueda de Producto

El usuario busca un producto utilizando:

- modelo  
- descripción  
- código  
- franquicia o referencia  

### Validación
- No se permite cargar cantidad si no hay un producto seleccionado  

---

## 4. Carga de Conteo

Una vez seleccionado el producto, la app:

- resalta el producto elegido  
- confirma visualmente la selección  
- habilita la carga de cantidad  
- permite agregar observaciones  

### Validación
- La cantidad es obligatoria  
- Solo se aceptan valores numéricos  
- No se permiten envíos vacíos  

---

## 5. Almacenamiento del Registro

Cuando el usuario confirma el conteo:

- el registro se guarda en la lista de SharePoint  
- se conserva el contexto seleccionado  
- se asocia el responsable al registro  

Esto genera datos centralizados y trazables.

---

## 6. Revisión de Resumen Semanal

La app incluye una vista de resumen donde se puede:

- filtrar por fecha  
- filtrar por sector o área  
- filtrar por producto o modelo  
- visualizar totales  
- expandir el detalle de cada agrupación  

Esto permite analizar el estado del stock de forma operativa.

---

## 7. Envío de Reporte por Email

Al finalizar el proceso, el usuario puede generar un reporte desde la app.

### Paso de confirmación
La aplicación solicita confirmación antes de enviar el reporte.

### Flujo de Power Automate
El flujo:

1. recibe la solicitud desde Power Apps  
2. obtiene los registros de stock necesarios  
3. estructura la información  
4. genera un archivo Excel  
5. lo nombra automáticamente según la semana  
6. envía el email a los responsables  

---

## 8. Resultado Final

El resultado es un proceso digitalizado de gestión de stock con:

- validación de responsables  
- registros estructurados y centralizados  
- visibilidad semanal  
- mejora en la trazabilidad  
- reducción del trabajo manual  
- comunicación automatizada  

---

## Notas

Este documento describe el proceso funcional a alto nivel.  
Los detalles de implementación pueden variar según la configuración de Power Apps y Power Automate.
