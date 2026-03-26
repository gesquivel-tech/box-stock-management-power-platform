🌐 [Read in English](data-model.md)

# Modelo de Datos

Este documento describe las principales fuentes de datos utilizadas en el Sistema de Gestión de Stock de Cajas.

---

## 1. Lista de SharePoint: Maestro de Empleados

Esta lista se utiliza para validar qué empleados pueden realizar conteos de stock.

### Propósito
Proveer a la aplicación una lista controlada de empleados disponibles para el conteo de stock.

### Campos de ejemplo
- **Nombre**: Nombre completo del empleado  
- **Activo**: Campo Sí/No que indica si el empleado está activo  
- **Email**: Dirección de correo electrónico  
- **Roles**: Roles o habilidades operativas asignadas  

### Uso en la aplicación
- Filtra únicamente empleados activos  
- Muestra solo empleados asignados a tareas de stock  
- Define el responsable seleccionado al inicio del flujo  

---

## 2. Lista de SharePoint: Registros de Stock de Cajas

Esta lista almacena todos los registros de conteo ingresados desde Power Apps.

### Propósito
Centralizar la información de stock y permitir trazabilidad, filtrado, reporting y análisis semanal.

### Campos de ejemplo
- **CodigoProducto**: Código interno del modelo de caja  
- **Descripcion**: Descripción del producto  
- **Sector**: Área donde se realizó el conteo  
- **Estado**: Estado del producto (por ejemplo, zunchado o embolsado)  
- **Pack**: Tamaño del empaque (por ejemplo, x100)  
- **Cantidad**: Cantidad contabilizada  
- **Responsable**: Usuario que realizó el conteo  
- **FechaConteo**: Fecha del conteo  
- **SemanaBatch**: Agrupación semanal para reporting  
- **Observaciones**: Notas opcionales ingresadas por el usuario  

### Uso en la aplicación
- Almacena cada registro de stock  
- Permite visualización de resúmenes semanales  
- Permite filtrado por producto, sector, área y fecha  
- Alimenta el proceso de reportes en Power Automate  

---

## 3. Salida de Reportes

El proceso de reporting genera un archivo Excel basado en los registros semanales de stock.

### Propósito
Distribuir la información actualizada de stock a los responsables de producción.

### Contenido
El reporte puede incluir:
- Código de producto  
- Descripción  
- Sector  
- Estado  
- Pack  
- Cantidad  
- Responsable  
- Fecha  
- Semana  

### Canal de salida
- Enviado por email mediante Power Automate  
- Puede visualizarse online o descargarse para análisis  

---

## Notas

Este repositorio contiene una representación funcional anonimizada del modelo de datos.  
La información sensible del negocio ha sido removida o generalizada.
