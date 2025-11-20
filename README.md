# Call-Center Operator Efficiency Analysis 📞📊

**Análisis de eficiencia operativa e identificación de operadores ineficaces para el servicio de telefonía virtual "CallMeMaybe".**

[![Status](https://img.shields.io/badge/status-active-success.svg)]()
[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Tableau](https://img.shields.io/badge/Tableau-Dashboard-orange.svg)](https://public.tableau.com/views/inef_ops/CallMeMaybe-Ops?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

## 📋 Tabla de Contenidos
- [Contexto del Proyecto](#-contexto-del-proyecto)
- [El Problema](#-el-problema)
- [Metodología](#-metodología)
- [Definición de Ineficacia](#-definición-de-ineficacia)
- [Resultados de Pruebas de Hipótesis](#-resultados-de-pruebas-de-hipótesis)
- [Conclusiones y Recomendaciones](#-conclusiones-y-recomendaciones)
- [Tecnologías Utilizadas](#-tecnologías-utilizadas)
- [Visualización](#-visualización)

---

## 🏢 Contexto del Proyecto
"CallMeMaybe" es un proveedor de servicios de telefonía virtual que busca optimizar su gestión de recursos humanos. La empresa necesita entender mejor el desempeño de sus operadores para mejorar la calidad del servicio al cliente y la eficiencia operativa.

El dataset contiene registros de llamadas (internas y externas), duración, tiempos de espera y estado de las llamadas (perdidas o atendidas) durante un periodo determinado.

## ❓ El Problema
La gerencia carece de un criterio objetivo y basado en datos para determinar qué operadores están teniendo un bajo rendimiento. El objetivo principal es:
1. Definir qué métricas constituyen a un operador "ineficaz".
2. Identificar a los operadores que cumplen con estas condiciones.
3. Proponer acciones de mejora basadas en pruebas estadísticas.

## ⚙️ Metodología
El análisis se llevó a cabo siguiendo estos pasos:

1.  **Preprocesamiento de Datos**: Limpieza de duplicados, tratamiento de valores nulos y conversión de tipos de datos (fechas, booleanos).
2.  **Análisis Exploratorio (EDA)**: Estudio de la distribución de llamadas entrantes vs. salientes, tiempos de espera y volúmenes diarios.
3.  **Definición de Umbrales (Data-Driven)**: Uso de percentiles (85, 90, 95) para establecer límites objetivos de rendimiento.
4.  **Pruebas de Hipótesis**: Validación estadística de las diferencias entre grupos (Test de Levene y T-Student).
5.  **Segmentación**: Clasificación binaria de operadores (Eficaz / Ineficaz).

## 📉 Definición de Ineficacia
Basado en el análisis de la distribución de los datos, se establecieron los siguientes KPIs críticos. Un operador se considera **ineficaz** si cumple cualquiera de estas condiciones:

* **Llamadas Entrantes**:
    * Tasa de llamadas perdidas > **10%** (Percentil 85+).
    * Tiempo de espera promedio > **80 segundos** (Percentil 90+).
* **Llamadas Salientes**:
    * Cantidad total de llamadas realizadas < **8** (Baja productividad).

## 🧪 Resultados de Pruebas de Hipótesis
Se realizaron pruebas estadísticas con un nivel de significancia de `alpha = 0.05` para validar los hallazgos:

| Hipótesis | Prueba Estadística | Resultado (Valor-p) | Conclusión |
| :--- | :--- | :--- | :--- |
| **1. Tiempos de Espera:** Internas < Externas | T-test (var. desiguales) | `0.000` | **Rechazada H0**. Los clientes externos esperan significativamente más. |
| **2. Tasa de Pérdida:** Ineficaces > Eficaces | T-test (var. desiguales) | `1.93e-06` | **Rechazada H0**. Los operadores marcados como ineficaces tienen un rendimiento estadísticamente inferior. |
| **3. Tasa de Pérdida:** Internas ≠ Externas | Z-test (proporciones) | `0.000` | **Rechazada H0**. Existe una diferencia significativa en la atención según el origen de la llamada. |

## 🚀 Conclusiones y Recomendaciones

1.  **Prioridad en Llamadas Externas**: Se demostró que el cuello de botella está en las llamadas externas (clientes reales). Se recomienda reasignar operadores internos a líneas externas durante horas pico.
2.  **Intervención Focalizada**: Se generó una lista de operadores ineficaces. No se recomienda el despido inmediato, sino **capacitación específica** en reducción de tiempos de espera.
3.  **Revisión de Infraestructura**: Los valores atípicos en tiempos de espera sugieren posibles fallos técnicos en el enrutamiento de llamadas, no solo error humano.

## 💻 Tecnologías Utilizadas
* **Python**: Lenguaje principal.
* **Pandas & NumPy**: Manipulación y agregación de datos.
* **SciPy Stats**: Pruebas de hipótesis (Levene, T-test, Z-test).
* **Matplotlib & Seaborn**: Visualización estática de distribuciones y boxplots.
* **Tableau**: Dashboard interactivo para la gerencia.

## 📊 Visualización
Puedes interactuar con el dashboard de resultados aquí:
👉 **[Ver Dashboard en Tableau Public](https://public.tableau.com/views/inef_ops/CallMeMaybe-Ops?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)**

---
*Autor: [Dagoberto Mares](https://github.com/DagoMares)*

*Contacto: [![Gmail Badge](https://img.shields.io/badge/-dagobertomares0@gmail.com-c14438?style=flat&logo=Gmail&logoColor=white&link=mailto:dagobertomares0@gmail.com)](mailto:dagobertomares0@gmail.com) - 
[![Linkedin Badge](https://img.shields.io/badge/-dagobertomares-0072b1?style=flat&logo=Linkedin&logoColor=white&link=https://www.linkedin.com/in/dagoberto-mares/)](https://www.linkedin.com/in/dagoberto-mares/)*
