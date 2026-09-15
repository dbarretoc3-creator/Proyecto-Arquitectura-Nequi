# Proyecto de Arquitectura Empresarial y Tecnológica
## Independencia Tecnológica y Operativa de Nequi

**Integrantes:** Esteban Barreto • Bryan Camilo Garavito • David Verdugo

---

## 1. Contexto de la noticia: independencia de Nequi

Nequi nació como una iniciativa de innovación de Bancolombia y evolucionó hasta convertirse en una plataforma financiera digital de gran alcance. El proceso de separación jurídica comenzó previamente y culminó con el inicio de operaciones independientes de **Nequi S.A. Compañía de Financiamiento el 1 de septiembre de 2026**.

Esta transformación debe entenderse como una **independencia jurídica y operativa**, no como una salida completa del ecosistema empresarial. Nequi y Bancolombia continúan vinculados dentro de **Grupo Cibest**, pero funcionan como entidades jurídicas independientes.

### Línea de tiempo

| Periodo | Hito |
|---|---|
| **2015** | Nequi nace como proyecto de innovación de Bancolombia. |
| **2021-2022** | Avanza el proceso de separación y se autoriza la creación de Nequi S.A. Compañía de Financiamiento. |
| **2025** | Grupo Cibest se constituye como matriz de Bancolombia, Nequi y otras compañías. |
| **1 de septiembre de 2026** | Nequi inicia operaciones como entidad independiente de Bancolombia S.A. |

> **Aclaración:** independencia no significa que Nequi deje de pertenecer al mismo grupo empresarial. Significa que Nequi cuenta con una entidad jurídica propia y una operación financiera independiente, manteniendo relaciones e integraciones necesarias con otras empresas del grupo.

---

## 2. Antes y después de la transformación

| Aspecto | Situación anterior | Situación actual / objetivo |
|---|---|---|
| **Estructura empresarial** | Nequi estaba asociado a Bancolombia como línea de negocio. | Nequi opera como **Nequi S.A. Compañía de Financiamiento**. |
| **Relación jurídica** | Existía una relación directa dentro de la estructura de Bancolombia. | Nequi y Bancolombia son entidades jurídicas independientes dentro de Grupo Cibest. |
| **Operación financiera** | La operación se encontraba vinculada a la estructura anterior. | Nequi desarrolla directamente su operación financiera como entidad propia. |
| **Servicios digitales** | Existían dependencias estructurales y tecnológicas que debían evolucionar. | Los servicios críticos deben estar bajo mayor control de Nequi. |
| **Tecnología** | Existían dependencias y componentes compartidos. | Se busca una arquitectura propia, modular y desacoplada. |
| **Datos** | Parte de los datos y procesos requerían separación y migración. | Los datos críticos deben ser administrados bajo el entorno controlado por Nequi. |
| **Bancolombia** | Tenía un papel estructural dentro de la operación. | Pasa a ser principalmente un sistema externo con integraciones puntuales cuando sean necesarias. |
| **Grupo Cibest** | No existía como matriz actual. | Es la casa matriz que agrupa a Nequi, Bancolombia y otras compañías. |

---

## 3. Ejemplo sencillo

La transformación puede entenderse como una división de una empresa que inicialmente funcionaba como un área interna y posteriormente se convierte en una empresa propia.

Puede conservar:
- la marca;
- los clientes;
- determinadas alianzas;
- algunas integraciones y servicios compartidos.

Pero ahora cuenta con:
- estructura jurídica propia;
- responsabilidades empresariales propias;
- mayor autonomía operativa;
- mayor control sobre sus servicios y tecnología.

---

# 4. Proyecto de Arquitectura

El propósito del proyecto es diseñar una arquitectura tecnológica que permita a Nequi consolidar su independencia tecnológica y operativa después de su separación jurídica de Bancolombia.

La arquitectura **no busca eliminar todas las relaciones con Bancolombia**, sino transformar las dependencias estructurales en integraciones puntuales, documentadas, seguras y controladas.

### Necesidades principales

- Fortalecer la autonomía tecnológica y operativa.
- Proteger usuarios, datos y transacciones.
- Mantener alta disponibilidad.
- Reducir dependencias tecnológicas estructurales.
- Conservar integraciones seguras con Bancolombia y terceros.
- Preparar la plataforma para el crecimiento de usuarios y transacciones.

---

# 5. Partes interesadas

| Parte interesada | Necesidad principal |
|---|---|
| **Clientes** | Seguridad, disponibilidad, facilidad de uso y continuidad. |
| **Nequi** | Autonomía tecnológica, crecimiento y control de sus sistemas. |
| **Área de tecnología** | Estabilidad, escalabilidad, mantenibilidad e interoperabilidad. |
| **Seguridad** | Protección de datos, monitoreo y control de accesos. |
| **Bancolombia** | Integraciones seguras y continuidad de los servicios que todavía requieran interoperabilidad. |
| **Grupo Cibest** | Continuidad, control y transformación organizada. |
| **Reguladores** | Cumplimiento de las normas aplicables al sector financiero. |
| **Comercios y aliados** | Continuidad de pagos e integraciones confiables. |

---

# 6. Objetivos del negocio

1. Consolidar la independencia tecnológica de Nequi.
2. Proteger datos, cuentas y transacciones.
3. Mantener alta disponibilidad de los servicios.
4. Garantizar la continuidad del negocio durante la transición.
5. Reducir dependencias tecnológicas estructurales.
6. Mantener interoperabilidad segura con Bancolombia y terceros.
7. Soportar el crecimiento de usuarios y transacciones.
8. Facilitar innovación y nuevos servicios financieros.
9. Aumentar la autonomía operativa y la capacidad de decisión.
10. Mantener una experiencia de usuario estable durante la transformación.

---

# 7. Capacidades del negocio: AS-IS y TO-BE

> **AS-IS** representa la situación de referencia anterior a la consolidación de la independencia.  
> **TO-BE** representa la capacidad objetivo que la arquitectura debe permitir consolidar.

| Capacidad | AS-IS | TO-BE |
|---|---|---|
| **Operación financiera** | Operación vinculada a la estructura histórica de Bancolombia. | Operación financiera gestionada directamente por Nequi S.A. Compañía de Financiamiento. |
| **Gestión de usuarios** | Gestión digital existente, con dependencias estructurales que debían evolucionar. | Nequi controla directamente sus servicios de usuarios. |
| **Transacciones y pagos** | Capacidad digital existente, con integraciones y dependencias que debían desacoplarse. | Servicios propios y controlados por Nequi, con integraciones externas definidas. |
| **Gestión de datos** | Datos y procesos que requerían separación y migración controlada. | Datos críticos administrados bajo el control del entorno de Nequi. |
| **Seguridad** | Controles existentes, pero la transformación exige fortalecerlos y adaptarlos. | Seguridad incorporada desde el diseño, con monitoreo, auditoría y gestión de accesos. |
| **Integraciones** | Existencia de dependencias e integraciones con Bancolombia y terceros. | APIs e integraciones puntuales, seguras, documentadas y desacopladas. |
| **Disponibilidad** | Los servicios deben permanecer activos durante la transformación. | Arquitectura redundante con objetivo de disponibilidad de al menos 99,9 %. |
| **Escalabilidad** | La plataforma debe responder al crecimiento de usuarios y transacciones. | Componentes modulares y escalables preparados para crecimiento futuro. |
| **Continuidad** | Una transformación incorrecta podría afectar servicios existentes. | Migración gradual, respaldos, recuperación y mecanismos de reversión. |
| **Arquitectura de servicios** | Capacidades digitales existentes que deben evolucionar hacia mayor autonomía. | Servicios propios para usuarios, transacciones, pagos, seguridad y datos. |
| **Gobierno tecnológico** | Decisiones que requieren coordinación entre negocio, tecnología y seguridad. | Mayor autonomía y control sobre decisiones, activos y políticas tecnológicas. |

---

# 8. Arquitectura objetivo

La arquitectura objetivo plantea que Nequi disponga de una plataforma tecnológica propia, modular, segura, escalable y altamente disponible.

### Componentes principales

- **Aplicación / canales digitales**
- **API Gateway**
- **Servicios de usuarios**
- **Servicios de transacciones**
- **Servicios de pagos**
- **Servicios de seguridad**
- **Gestión de datos**
- **Monitoreo y observabilidad**
- **Sistemas externos**
- **Integraciones controladas con Bancolombia**
- **Integraciones con terceros**

### Principio central

Bancolombia deja de considerarse una dependencia estructural dentro de la arquitectura objetivo y pasa a representarse como un **sistema externo**, conectado mediante interfaces e integraciones controladas cuando el negocio lo requiera.

Los servicios y datos críticos deben quedar bajo el entorno controlado por Nequi.

---

# 9. Análisis de brechas

| # | Brecha | Explicación | Prioridad |
|---|---|---|---|
| **1** | **Independencia tecnológica** | Deben reducirse las dependencias estructurales heredadas de la relación con Bancolombia. | Alta |
| **2** | **Gestión de datos** | Se requiere garantizar que los datos críticos puedan administrarse directamente por Nequi. | Alta |
| **3** | **Seguridad** | La separación exige mantener y fortalecer controles de acceso, monitoreo y protección. | Alta |
| **4** | **Disponibilidad** | Las migraciones y cambios no deben interrumpir los servicios financieros. | Alta |
| **5** | **Interoperabilidad** | Las relaciones necesarias con Bancolombia y terceros deben convertirse en integraciones controladas. | Alta |
| **6** | **Continuidad del negocio** | Se requieren mecanismos de respaldo, recuperación, contingencia y reversión. | Alta |
| **7** | **Migración tecnológica** | Los sistemas y dependencias deben migrarse progresivamente hacia componentes bajo control de Nequi. | Alta |
| **8** | **Escalabilidad** | La arquitectura debe soportar el crecimiento futuro de usuarios y transacciones. | Media/Alta |
| **9** | **Arquitectura de servicios** | Las capacidades críticas deben separarse y modularizarse. | Alta |
| **10** | **Gobierno tecnológico** | Se deben fortalecer responsables, políticas, indicadores y mecanismos de seguimiento. | Media/Alta |

---

# 10. Propuesta de solución

La solución arquitectónica se basa en una estrategia progresiva:

```text
SITUACIÓN ANTERIOR
        │
        ▼
Dependencias estructurales
con Bancolombia
        │
        ▼
Identificación de dependencias
        │
        ▼
Desacoplamiento progresivo
        │
        ▼
Migración de datos y servicios
        │
        ▼
Servicios propios de Nequi
        │
        ├──────────────► Bancolombia
        │                 (integraciones puntuales)
        │
        ├──────────────► Terceros
        │                 (APIs seguras)
        ▼
ARQUITECTURA OBJETIVO
Nequi autónomo, modular,
seguro y escalable
```

---

# 11. Principios de arquitectura

- **Independencia tecnológica:** los componentes críticos deben poder administrarse sin dependencia estructural de Bancolombia.
- **Seguridad desde el diseño:** la protección de datos y transacciones debe incorporarse desde la arquitectura.
- **Continuidad del servicio:** ningún cambio debe comprometer innecesariamente los servicios actuales.
- **Datos bajo control de Nequi:** los datos críticos deben administrarse dentro del entorno controlado por Nequi.
- **Interoperabilidad:** las integraciones deben utilizar interfaces definidas, seguras y controladas.
- **Escalabilidad:** la arquitectura debe soportar incrementos de usuarios y transacciones.
- **Modularidad:** los servicios deben poder evolucionar y migrarse progresivamente.
- **Observabilidad:** las operaciones críticas deben monitorearse y auditarse.
- **Cumplimiento:** la arquitectura debe considerar las obligaciones aplicables al sector financiero.
- **Experiencia del usuario:** la transformación debe ser transparente para el cliente siempre que sea posible.

---

# 12. KPI propuestos

| Indicador | Meta propuesta | Propósito |
|---|---:|---|
| Disponibilidad | ≥ 99,9 % | Garantizar continuidad del servicio. |
| Transacciones exitosas | ≥ 99,5 % | Reducir fallos en operaciones. |
| Recuperación ante fallos | ≤ 30 min | Restablecer servicios críticos rápidamente. |
| Integraciones seguras | 100 % | Garantizar controles en conexiones externas. |
| Pérdida de datos | 0 | Proteger la integridad de la información. |

---

# 13. Riesgos y mitigación

| Riesgo | Impacto | Mitigación |
|---|---|---|
| Pérdida de información | Alto | Copias de seguridad, validación y reconciliación. |
| Caída del servicio | Alto | Redundancia, despliegues graduales y recuperación. |
| Ataques informáticos | Alto | Seguridad, monitoreo y gestión de accesos. |
| Error de migración | Alto | Pilotos, pruebas, validación y reversión. |
| Problemas de integración | Medio/Alto | APIs independientes, documentación y contingencia. |
| Incumplimiento regulatorio | Alto | Auditorías y validación de requisitos. |
| Resistencia al cambio | Medio | Gestión del cambio y capacitación. |
| Sobrecostos o retrasos | Medio | Implementación por fases y seguimiento de hitos. |

---

# 14. Conclusión

La independencia de Nequi frente a Bancolombia debe interpretarse como una transformación jurídica, operativa y tecnológica progresiva. Desde el **1 de septiembre de 2026**, Nequi opera como **Nequi S.A. Compañía de Financiamiento**, mientras continúa formando parte del ecosistema empresarial de Grupo Cibest.

Por esta razón, la arquitectura propuesta no plantea eliminar todas las relaciones con Bancolombia. El objetivo es transformar las dependencias estructurales en integraciones puntuales y controladas.

La arquitectura objetivo se fundamenta en servicios propios, control de datos, seguridad, alta disponibilidad, escalabilidad, modularidad e interoperabilidad. La transición debe realizarse mediante migraciones progresivas, respaldos, pruebas, monitoreo y mecanismos de recuperación.

De esta manera, el proyecto de arquitectura queda alineado con la nueva realidad empresarial de Nequi: **una entidad jurídicamente independiente de Bancolombia, pero integrada dentro de Grupo Cibest y conectada con otros sistemas mediante relaciones tecnológicas controladas.**

---

## 15. Fuentes de contexto

- Bancolombia / Grupo Cibest. Información corporativa sobre la nueva estructura del grupo.
- Grupo Cibest. Resultados corporativos 2026, donde se informa que Nequi operaría de forma independiente a partir del 1 de septiembre de 2026.
- Documento base del proyecto: *Proyecto de Arquitectura Empresarial y Tecnológica — Independencia Tecnológica y Operativa de Nequi*.

> **Nota:** Las metas KPI y la arquitectura objetivo son propuestas académicas del proyecto; no representan necesariamente indicadores o arquitectura interna publicada oficialmente por Nequi.
