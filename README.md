# 📊 SQL Data Analytics Project – Cohort, Segmentation & Retention Analysis

Este proyecto forma parte de mi aprendizaje en **Data Analytics con SQL**, siguiendo el tutorial  
**“SQL for Data Analytics – Intermediate Course + Project”** de **Luke Barousse**.

El objetivo principal es analizar el comportamiento de los clientes a través de:
- **Análisis de cohortes**
- **Segmentación de clientes por LTV**
- **Análisis de retención y churn**

Todo el análisis se realiza utilizando **SQL** y consultas analíticas avanzadas.

---

## 🗂️ Estructura del Proyecto
│   ├── cohort_analysis_view.sql
│   ├── customer_segmentation.sql
│   ├── cohort_analysis.sql
│   └── retention_analysis.sql

---

## 🧱 Fuente de Datos

El proyecto utiliza la base de datos **`contoso_100k`**, un dataset de ejemplo ampliamente usado para análisis de negocio y prácticas de Data Analytics.
Tablas principales utilizadas:

- **sales**
  - Información de ventas
  - Campos clave:  
    `orderkey`, `customerkey`, `orderdate`, `quantity`, `netprice`, `exchangerate`

- **customer**
  - Información de clientes
  - Campos clave:  
    `customerkey`, `givenname`, `surname`, `age`, `countryfull`

La base **contoso_100k** simula datos reales de una empresa de retail, permitiendo realizar análisis de ingresos, comportamiento de clientes y retención.

---

## 📌 Descripción de los Archivos

### 1️⃣ `cohort_analysis_view.sql`

Crea la vista `cohort_analysis`, que sirve como base para todo el análisis posterior.

**Características principales:**
- Calcula ingresos netos por cliente y fecha.
- Agrega métricas de ventas (`total_net_revenue`, `num_orders`).
- Limpia y concatena nombres de clientes.
- Identifica la **fecha de primera compra**.
- Asigna el **año de cohorte** según la primera compra.

📍 Esta vista es reutilizada por todos los análisis siguientes.

---

### 2️⃣ `cohort_analysis.sql`

Realiza un **análisis de cohortes** basado en la primera compra de cada cliente.

**Métricas calculadas:**
- Ingresos totales por cohorte
- Cantidad total de clientes
- Ingreso promedio por cliente

📊 Permite comparar el valor inicial de los clientes a lo largo del tiempo.

---

### 3️⃣ `customer_segmentation.sql`

Segmenta a los clientes según su **Lifetime Value (LTV)**.

**Proceso:**
1. Calcula el LTV total por cliente.
2. Obtiene percentiles 25 y 75.
3. Clasifica a los clientes en:
   - 🟢 **Low Value**
   - 🟡 **Mid Value**
   - 🔵 **High Value**

📈 Ideal para estrategias de marketing y priorización de clientes.

---

### 4️⃣ `retention_analysis.sql`

Analiza **retención y churn de clientes** por cohorte.

**Definiciones clave:**
- Un cliente se considera **churned** si no realizó compras en los últimos **6 meses**.
- Se identifica la última compra de cada cliente mediante funciones de ventana.

**Resultados:**
- Clientes activos vs churned por cohorte
- Porcentaje de estado por cohorte

🔍 Permite evaluar la fidelización de clientes a lo largo del tiempo.

---

## 🛠️ Tecnologías Utilizadas

- **SQL**
  - CTEs (`WITH`)
  - Window Functions
  - Agregaciones
  - Percentiles
- Base de datos: **contoso_100k**
- Motor SQL compatible con sintaxis tipo **PostgreSQL**

---

## 🎯 Objetivos del Proyecto

- Practicar SQL intermedio aplicado a análisis de negocio.
- Trabajar con cohortes, segmentación y churn.
- Preparar análisis reutilizables mediante vistas.
- Simular un flujo de trabajo real de Data Analytics.

---

## 📚 Referencia

Curso:  
**SQL for Data Analytics – Intermediate Course + Project**  
Instructor: **Luke Barousse**
