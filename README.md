# 📊 Tech Sales Analytics: Pipeline de ETL y Dashboard Interactivo

Este proyecto demuestra la implementación de un flujo completo de análisis de datos, abarcando desde la extracción y transformación de datos desestructurados (**ETL**) mediante **Power Query**, hasta la creación de un **Dashboard Ejecutivo Interactivo** en Excel para la toma de decisiones estratégicas.

---

## 🛠️ Arquitectura del Proyecto y Soluciones Aplicadas

### 1. Extracción y Transformación de Datos (ETL) con Power Query
Se procesó un set de datos local simulando un entorno de producción con múltiples anomalías de registro. Las fases de limpieza automatizadas incluyeron:
*   **Normalización de Texto:** Eliminación de espacios redundantes mediante funciones de recorte (`Trim`) y estandarización de registros de clientes a formato de nombre propio (`Capitalize Each Word`).
*   **Corrección de Encoding (Encoding Fix):** Identificación y reemplazo de caracteres especiales corruptos causados por codificación de texto dispar (ej. transmutación de `EspaÃ±a` a `ESPAÑA`).
*   **Deduplicación:** Depuración de registros e IDs de pedidos repetidos para garantizar la integridad analítica del volumen total de ventas.
*   **Tratamiento de Nulos (Imputación de Datos):** Reemplazo de valores faltantes (`null`) en la métrica de `Cantidad` bajo reglas lógicas de negocio (asumiendo un mínimo de 1 unidad por transacción).
*   **Tipado de Datos:** Aseguramiento y conversión estricta de formatos para columnas temporales (`Fecha`), numéricas continuas y discretas (`Precio_Unitario`, `Cantidad`).

### 2. Modelado y Análisis en el Dashboard
Una vez diseñado el pipeline automatizado, los datos limpios se conectaron directamente a un modelo de analítica descriptiva:
*   **Métricas de Rendimiento:** Transición de métricas de conteo plano a agregaciones financieras reales (`Suma` e impactos cruzados por precio unitario).
*   **Análisis de Pareto e Insights:** Identificación de los productos con mayor rendimiento económico frente a los de menor rotación (ej. análisis de margen en Zapatillas Run vs. Mouses Inalámbricos).
*   **Interactividad (UI/UX de Reportes):** Implementación de controles y **Segmentadores de Datos (Slicers)** dinámicos por `Pais` y `Producto`, permitiendo auditorías de mercado cruzadas y exploración de datos en tiempo real con un solo clic.

---

## 🚀 Impacto del Proyecto
El mayor valor de esta solución es su **escalabilidad**. Al haber programado la receta de limpieza dentro de Power Query, el reporte es 100% automatizable: ante cualquier actualización futura o inserción de miles de nuevas filas en el archivo de texto, el analista solo requiere pulsar un clic en **"Actualizar"** para que todo el Dashboard se reestructure e identifique las nuevas tendencias de inmediato.
