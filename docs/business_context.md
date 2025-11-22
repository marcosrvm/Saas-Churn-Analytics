# Business Context — RavenStack SaaS Churn Analytics

## Table of Contents

1. Business Objective
2. Stakeholders & Business Needs
3. Definitions & Scope
4. SaaS Model Overview
5. What “Churn” Means in This Dataset
6. Key Business Questions
7. Initial Hypotheses (Placeholders)
8. Risks & Constraints
9. Expected Business Decisions Enabled
10. Alignment with CS + Product Strategy

---

## 1. Business Objective

Identificar los factores clave que explican el churn (pérdida) de clientes en RavenStack con el fin de reducir la pérdida de cuentas y mejorar la retención en las primeras etapas del ciclo de vida.

---

## 2. Stakeholders & Business Needs

**Primary Stakeholders:**

* Head of Customer Success: identificarle las cuentas en riesgo y priorizar intervenciones.
* Product Manager: entender qué aspectos del uso del producto contribuyen a la retención o abandono.

**Business Needs:**

* Mejorar retención del cliente en los primeros 90 días.
* Detectar patrones de uso, soporte o plan que anticipen churn.
* Orientar iniciativas de producto y experiencia de cliente.

---

## 3. Definitions & Scope

**Scope:**

* Analizar el comportamiento de cuentas activas y churned.
* Realizar métricas de producto, soporte y revenue.
* Construir base de datos analítica vía SQL.
* Entrenar modelo explicativo (logística / árboles) orientado a interpretabilidad.

**Out of Scope:**

* Modelos black-box sin interpretabilidad.
* Optimización de campañas de marketing.
* Predicción de MRR a largo plazo.

---

## 4. SaaS Model Overview

RavenStack opera como un SaaS B2B centrado en cuentas (empresas cliente) con ingresos recurrentes mediante suscripciones.

**Componentes clave (5 BBDD):**

* *Accounts:* información base, plan inicial, seats, industria.
* *Subscriptions:* ingresos recurrentes (MRR/ARR), upgrades, downgrades.
* *Feature Usage:* actividad granular del producto.
* *Support Tickets:* interacción con soporte y calidad del servicio.
* *Churn Events:* fecha y motivo de abandono, reactivaciones.

---

## 5. What “Churn” Means in This Dataset

Para este proyecto, entendemos churn como el evento en que una cuenta finaliza su relación con RavenStack, reflejado por un registro en la tabla **churn_events**.

Este dataset también incluye un campo `churn_flag` en *accounts*, pero el evento oficial será determinado mediante `churn_events`.

---

## 6. Key Business Questions

1. ¿Qué cohortes muestran mayores tasas de churn?
2. ¿Qué patrones de uso del producto son más predictivos para el abandono?
3. ¿Cómo influye el soporte (tickets, tiempos de respuesta) en el churn?
4. ¿Existe relación entre upgrades/downgrades y churn posterior?
5. ¿Qué clientes o segmentos(industria, país, plan) están más predispuestos al churn?
6. ¿Cuáles son las señales tempranas (entre 30-90 días) de riesgo?

---

## 7. Initial Hypotheses (Placeholders — to be validated)

* Las cuentas con baja actividad desde el inicio tienen mayor propensión a churn.
* Las cuentas con tickets urgentes o tiempos largos de resolución presentan mayor riesgo de abandono.
* Los downgrades en los 90 días previos aumentan la probabilidad de churn.
* La insatisfacción con soporte es un indicador crítico.
* Clientes en planes básicos retienen peor que los de planes superiores.

Estas hipótesis serán refinadas y validadas mediante SQL y el EDA.

---

## 8. Risks & Constraints

* Posible data leakage si se usan variables posteriores al churn.
* Campos con nulos que pueden sesgar análisis (ej. satisfacción).
* Diferencias entre churn de suscripción vs churn de cuenta.
* Reactivaciones complican medición del lifetime.
* Sesgos entre heavy users y cuentas de nulo uso.

---

## 9. Expected Business Decisions Enabled

* Priorización de cuentas en riesgo para Customer Success.
* Identificación de features o comportamientos que conducen a la retención.
* Optimización del onboarding y la experiencia inicial(30-90 días).
* Diseñar estrategias de producto basadas en señales tempranas de riesgo.

---

## 10. Alignment with CS + Product Strategy

Este análisis proporciona una visión integral del churn combinando:

* Drivers operacionales (soporte).
* Drivers de producto (uso, adopción, errores).
* Drivers comerciales (planes, upgrades, downgrades).

Esta perspectiva híbrida permite coordinar decisiones entre Customer Success y Product, maximizando impacto en retención y experiencia del cliente.
