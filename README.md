# ⚽ Sporting Cristal: Medallion/Lakehouse Data Architecture & Analytics (Azure Databricks)

Este proyecto despliega una arquitectura de datos de extremo a extremo para transformar métricas crudas de fútbol extraídos del proveedor Skillcorner (eventos y GPS) en inteligencia táctica para **Sporting Cristal**, de la Liga 1 Profesional Peruana.

## 🏁 Arquitectura del Sistema
El ecosistema utiliza un enfoque Lakehouse sobre los servicios de la nube de Azure, garantizando escalabilidad y gobernanza de datos.

* **Nube:** Azure con autenticación basada en identidades administradas.
* **Procesamiento:** Azure **Databricks** con Unity Catalog para la gestión centralizada de metadatos y seguridad.
* **Orquestación:** Databricks **Workflows** configurado en el YAML para la ejecución de tareas en paralelo.
* **CI/CD:** Automatización de despliegue mediante **GitHub Actions** para la integración continua de notebooks y configuración de infraestructura.

## 💎 El Flujo Medallion
Los datos atraviesan tres capas de refinamiento para asegurar su calidad y disponibilidad:

1. **Capa Bronze (Ingesta):** Captura de archivos crudos (.csv) sobre competiciones, equipos, partidos y rendimiento físico.
2. **Capa Silver (Transformación):** Limpieza de valores nulos, estandarización de esquemas y enriquecimiento de datos, incluyendo el cálculo de dificultad de rivales.
3. **Capa Gold (Agregación):** Creación de tablas de alto rendimiento optimizadas para KPIs específicos como **xThreat (Amenaza Esperada)** y métricas físicas agregadas.

## 📊 Visualización e Insights
El producto final es un reporte en **Power BI** que permite analizar:

* **Distribución de Posesión:** Análisis de fases de ataque organizado y transiciones basado en la duración de los eventos.
* **Estructura Defensiva:** Monitoreo del tiempo efectivo del equipo en bloques alto, medio y bajo.
* **Progresión Física:** Visualización cronológica de distancias recorridas y sprints por jugador para la gestión de carga y prevención de lesiones.

<img width="1440" height="338" alt="image" src="https://github.com/user-attachments/assets/cbc53b50-4ff8-4f3a-8c35-983019140e7d" />

## 🚀 Stack Tecnológico
* **Lenguajes:** Python (PySpark), SQL.
* **Herramientas:** Azure, Databricks, GitHub Actions, Power BI, YAML.
* **Gobernanza:** Unity Catalog (External Locations, Volumes, Storage Credentials).
---
**Desarrollado por:** Enzo Villafuerte
* Durante el troubleshooting del CI/CD se detectó que los costos (Pay-as-you-go) del servicio de Azure, se estaban disparando. Opté por cancelar el servicio y me quedé imposibilitado de resolver el problema.
