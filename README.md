
# TITULO DEL DESIGN DOC
Aplicación de Recetas Basada en los Ingredientes de la Despensa

**Link:** [Link a este design doc]

**Author(s):** Charlie L

**Status:** [Draft]

**Última actualización:** 2025-03-06

---

### Contenido

1. **Goals**
2. **Non-Goals**
3. **Background**
4. **Overview**
5. **Detailed Design**
   - **Solución 1**
     - **Frontend**
     - **Backend**
   - **Solución 2**
     - **Frontend**
     - **Backend**
6. **Consideraciones**
7. **Métricas**
8. **Links**

---

### Objetivo
El objetivo de este proyecto es crear una **aplicación móvil** que ayude a las personas a **encontrar recetas de cocina basadas en los ingredientes** que tienen en su despensa, reduciendo el desperdicio de alimentos y ayudando a ahorrar tiempo y dinero. La aplicación permitirá a los usuarios ingresar ingredientes disponibles, recibir sugerencias de recetas, y planificar comidas.

---

### Goals

- Reducir el desperdicio de alimentos al proporcionar recetas basadas en los ingredientes disponibles.
- Facilitar la preparación de comidas al generar listas de recetas personalizadas y fáciles de seguir.
- Incluir filtros para preferencias dietéticas como veganas, sin gluten, bajas en calorías, etc.
- Implementar un sistema de escaneo de código de barras para agregar productos automáticamente a la despensa.
- Incluir un planificador de comidas semanal basado en recetas.

---

### Non-Goals

- No se incluirá la opción de realizar compras directamente a través de la app.
- No se buscará integrar la aplicación con supermercados locales inicialmente.
- No se permitirá la creación de recetas personalizadas por los usuarios en la versión inicial.

---

### Background

En muchas casas, el desperdicio de alimentos es un problema común debido a que las personas a menudo no saben qué cocinar con los ingredientes que tienen disponibles. Este proyecto surge con la necesidad de ayudar a las personas a aprovechar al máximo sus despensas y evitar compras innecesarias. Además, buscamos promover una alimentación más saludable y eficiente.

Este diseño está inspirado en aplicaciones de recetas existentes, pero con un enfoque particular en reducir el desperdicio de alimentos y ayudar a los usuarios a usar los ingredientes que ya tienen.

---

### Overview

La aplicación proporcionará una solución intuitiva donde los usuarios pueden ingresar los ingredientes disponibles en su despensa, ya sea mediante texto, códigos de barras o fotos, y recibir sugerencias de recetas. También podrá planificar las comidas semanales, generando listas de compras automáticas para los ingredientes faltantes.

**Características clave:**
1. Ingreso de ingredientes manualmente, por código de barras o foto.
2. Sugerencia de recetas basadas en los ingredientes disponibles.
3. Filtros de preferencias dietéticas y tipo de comida.
4. Planificador de comidas con generación de listas de compras.
5. Instrucciones detalladas para cada receta.

---

### Detailed Design

El diseño de la aplicación se divide en dos soluciones principales: una para el frontend y otra para el backend. Estas soluciones están interconectadas para crear una experiencia de usuario eficiente y sencilla.

#### **Solución 1:**

##### **Frontend**
1. **Pantalla de inicio**: Los usuarios podrán ver las recetas recomendadas y un botón para ingresar los ingredientes disponibles.
2. **Pantalla de ingredientes**: Los usuarios podrán agregar ingredientes de su despensa usando el teclado, escaneando códigos de barras o tomando fotos. 
3. **Pantalla de recetas**: Las recetas se mostrarán con imágenes, instrucciones paso a paso, y el tiempo estimado de preparación. Los usuarios podrán filtrar por tipo de comida (desayuno, almuerzo, etc.) y preferencias dietéticas.
4. **Pantalla de planificación**: Los usuarios podrán planificar sus comidas de la semana y generar listas de compras para los ingredientes faltantes.

##### **Backend**
1. **Base de datos de recetas**: Se necesitará una base de datos que contenga recetas con sus respectivos ingredientes y pasos. Se podría usar una API externa como Spoonacular para obtener recetas y datos nutricionales.
2. **Algoritmo de sugerencias**: Un algoritmo que sugiera recetas basadas en los ingredientes disponibles en la despensa del usuario. Este algoritmo deberá considerar las restricciones dietéticas y preferencias del usuario.
3. **Sistema de autenticación**: Implementar un sistema de autenticación para guardar las preferencias y recetas guardadas de cada usuario.

---

#### **Solución 2:**

##### **Frontend**
1. **Pantalla de escaneo de código de barras**: Los usuarios podrán escanear códigos de barras de productos que ya tienen para agregarlos automáticamente a la despensa. Esta función utilizará una API de escaneo de códigos de barras como ZXing.
2. **Pantalla de perfil**: Los usuarios podrán ajustar sus preferencias alimenticias (sin gluten, vegano, bajo en calorías) y su información personal.

##### **Backend**
1. **Reconocimiento de imágenes**: Usar una API de reconocimiento de imágenes, como Google Vision o TensorFlow, para identificar ingredientes a partir de fotos de los productos.
2. **Listas de compras**: El sistema deberá generar automáticamente una lista de compras basada en las recetas que el usuario desea cocinar y los ingredientes que le faltan.

---

### Consideraciones
- **Trade-offs**: El reconocimiento de imágenes puede no ser 100% preciso, lo que podría generar algunos errores al agregar ingredientes. 
- **Tech debt**: La integración con APIs externas para recetas puede generar dependencia de terceros.
- **Escalabilidad**: Necesitamos considerar cómo escalar la base de datos de recetas y los algoritmos de sugerencias si la aplicación crece significativamente.

---

### Métricas

- **Tasa de retención de usuarios**: Cuántos usuarios continúan utilizando la app después de la primera descarga.
- **Reducción de desperdicio de alimentos**: Evaluar a través de encuestas o feedback si los usuarios sienten que la aplicación les ayuda a reducir el desperdicio.
- **Uso de escaneo de código de barras**: Cuántos usuarios utilizan esta función para agregar productos a su despensa.
- **Número de recetas vistas por usuario**: Cuántas recetas el usuario consulta en promedio antes de cocinar.

---

### Links
