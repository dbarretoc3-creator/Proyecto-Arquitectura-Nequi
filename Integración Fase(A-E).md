UNIVERSIDAD CENTRAL

ARQUITECTURA DE SOFTWARE 2

PROYECTO DE ARQUITECTURA EMPRESARIAL:

INDEPENDENCIA TECNOLÓGICA DE NEQUI FRENTE A BANCOLOMBIA

Creadores / Autores:

Esteban Barreto
David Verdugo
Bryan Garavito

Bogotá D.C., Colombia
2026

# 1. Introducción y Contexto del Negocio

Pillá el asunto, parce: Nequi nació y creció como una línea de negocio digital operada bajo la sombrilla tecnológica, jurídica y bancaria de Bancolombia S.A. Sin embargo, el volumen masivo de usuarios (más de 18 millones) y la dinámica del mercado exigen la creación de Nequi S.A. Compañía de Financiamiento, una entidad financiera completamente independiente articulada bajo el Grupo Cibest.

El reto principal de este proyecto es lograr el desacople tecnológico y operacional total sin interrumpir la operación diaria ni degradar la experiencia de los usuarios. Para lograrlo, aplicamos el marco metodológico TOGAF (Fases Preliminar a la E), asegurando que la transición desde la arquitectura actual (AS-IS) hacia la arquitectura objetivo (TO-BE) garantice la continuidad del servicio, la integridad de los saldos y el cumplimiento estricto ante la Superintendencia Financiera de Colombia (SFC).

# 2. Impulsores, Necesidades y Limitaciones del Negocio

Para que la desvinculación sea un éxito total y no se caiga la plataforma en el intento, definimos los siguientes objetivos e indicadores clave de rendimiento (KPIs críticos):

## Impulsores Estratégicos e Indicadores Objetivo

Disponibilidad del Servicio: ≥ 99.9% en todos los canales digitales (App móvil, reintentos y servicios API).

Efectividad Transaccional: ≥ 99.5% de transacciones completadas exitosamente sin errores de plataforma.

Tiempo de Recuperación ante Fallos (RTO): ≤ 30 minutos en escenarios de contingencia o caída de nodo.

Pérdida Máxima de Datos (RPO): 0 pérdida de datos (RPO=0), garantizando consistencia transaccional absoluta en cuentas y depósitos.

Integraciones Seguras: 100% de los puntos de contacto con terceros y con Bancolombia asegurados mediante protocolos Zero Trust y llaves de encriptación dedicadas.

## Necesidades Operativas y Regulaciones

Licencia Financiera Propia: Operar formalmente bajo la figura de Compañía de Financiamiento aprobada por la SFC.

Autonomía en Infraestructura: Migrar los núcleos de procesamiento y bases de datos a un entorno multicloud propio independiente del centro de cómputo de Bancolombia.

## Limitaciones del Proyecto

Regulatorias: Cumplimiento estricto de los tiempos de autorización y reporte fijados por la Superintendencia Financiera.

Operativas: Prohibición absoluta de programar ventanas de mantenimiento extendidas (las migraciones deben ser invisibles para el usuario final).

Financieras: Presupuesto de ejecución (CAPEX) acotado a $37.375 M y un costo operativo anual objetivo (OPEX) de $38.800 M/año.

# 3. Definición del Alcance (Scope)

Para evitar desvíos en la ejecución, delimitamos con precisión qué componentes entran y cuáles quedan por fuera del esfuerzo de independización:

| Dentro del Alcance (In Scope) | Fuera del Alcance (Out of Scope) |
| --- | --- |
| App Móvil Nequi: Rediseño e independización de la capa de cliente. | Sistemas Core de Bancolombia: Operaciones bancarias tradicionales (cartera, leasing, sucursales físicas). |
| Core Financiero Propio: Motor de depósitos, cuentas de ahorro y billetera. | Red Física de Cajeros Automáticos: Se mantiene la integración pero tratada puramente como un servicio externo de red aliada vía API. |
| Motor de Crédito Independiente: Evaluación de riesgo y préstamos (Salvaavidas, Paracaídas). | Red de Sucursales de Bancolombia: Nequi opera como entidad 100% digital sin atención presencial física. |
| Capa de Integración y APIs: Despliegue de API Gateway propio para conectar con Bre-B, PSE, Wompi, Wenia y Visa. | Plataformas de Clientes Corporativos de Bancolombia: Portales empresariales no vinculados a Nequi. |
| Seguridad e Identidad: Auth0 independiente, biometría propia y plataforma de prevención de fraude (Feedzai). |  |
| Infraestructura Multicloud: Instancias independientes en AWS, Google Cloud y Azure. |  |

# 4. Principios de Arquitectura

El diseño arquitectónico se rige por 8 principios fundamentales que orientan cada decisión técnica:

1. Seguridad Integrada (Security by Design): La protección de los datos y las transacciones está presente desde la primera línea de código hasta el despliegue en producción.

2. Protección de Datos y Privacidad: Cumplimiento riguroso de la Ley Habeas Data y cifrado de punta a punta (AES-256) para información sensible.

3. Independencia Operativa: Cero dependencia de librerías, servidores o credenciales compartidas con el núcleo de Bancolombia.

4. Interoperabilidad Estandarizada: Exposición de servicios exclusivamente a través de APIs RESTful conectadas mediante estándares abiertos y microservicios.

5. Alta Disponibilidad y Resiliencia: Despliegue multizona activo-activo con tolerancia a fallos distribuida en la nube.

6. Escalabilidad Elástica: Capacidad de autoescalado automático para absorber picos de demanda (ej. quincenas, Días sin IVA, promociones).

7. Continuidad del Negocio: Planes de recuperación automatizados que garantizan la operación ante desastres naturales o tecnológicos.

8. Migración Progresiva y Controlada: Desacople por capas utilizando el patrón Strangler Fig para evitar cortes bruscos de servicio (Big Bang).

# Fase Preliminar

Punto de Inicio de la Fase: Esta fase arranca formalmente con la socialización del Acta de Constitución del Proyecto (Project Charter) y el establecimiento de la Mesa de Gobierno de Arquitectura entre el Grupo Cibest, Nequi y Bancolombia. En este punto inicial se adopta el marco TOGAF ADM adaptado a la regulación financiera colombiana y se aprueban los 8 principios arquitectónicos que rigen el proyecto.

## Actividades y Resultados

Definición del Marco de Trabajo: Configuración de herramientas de arquitectura (Enterprise Architect y ArchiMate) y repositorio centralizado en GitHub (dbarretoc3-creator/Proyecto-Arquitectura-Nequi).

Establecimiento de las Métricas de Éxito: Formalización del comité de arquitectura y criterios de aceptación regulatorios ante la SFC.

# Fase A: Visión de la Arquitectura

Punto de Inicio de la Fase: Comienza exactamente con la firma de la Declaración de Trabajo de Arquitectura (Architecture Statement of Work) por parte de la Vicepresidencia de Tecnología y la Gerencia General de Nequi. En esta actividad se define la propuesta de valor centrada en convertir a Nequi en la neobanca líder e independiente de Colombia.

## Propuesta de Valor Estratégica

Garantizar la inclusión financiera y la agilidad en los servicios digitales de más de 18 millones de colombianos mediante una plataforma nativa en la nube, ágil, segura y completamente autónoma de la banca tradicional.

## Mapa General de Actores

Usuarios Finales (Personas y Pequeños Negocios): Consumidores de la App Nequi para giros, pagos, recargas y créditos.

Operaciones e Ingeniería Nequi: Equipos internos encargados del monitoreo, desarrollo e infraestructura.

Superintendencia Financiera de Colombia (SFC): Entidad reguladora que audita el cumplimiento normativo.

Aliados y Ecosistema de Pagos: Redes interbancarias (Bre-B, PSE, Visa, Wompi, Wenia).

Bancolombia S.A. (Tercero Relacionado): Proveedor externo de red de cajeros y corresponsales bancarios.

# Fase B: Arquitectura de Negocio

Punto de Inicio de la Fase: Inicia con el levantamiento y diagramación del Estado Actual (AS-IS) de los procesos de negocio en Nequi, identificando los puntos de acoplamiento operativo con los sistemas centrales de Bancolombia.

## Arquitectura Base (AS-IS)

Actualmente, la operación de Nequi comparte componentes críticos con Bancolombia:

Capa de Presentación: App móvil conectada a través de un canal middleware administrado por Bancolombia.

Capa de Negocio: Lógica bancaria compartida en el Mainframe y servidores centrales de Bancolombia.

Capa de Datos: Bases de datos unificadas en Db2 y Oracle de la matriz bancaria.

## Arquitectura Destino (TO-BE)

Evolución hacia una estructura por capas totalmente desacoplada:

Capa de Presentación: App Nequi repotenciada con SDKs propios y comunicación segura por canal dedicado.

Capa de Servicios y Microservicios: Módulos de bolsillo, giros, préstamos y pagos alojados en contenedores Kubernetes (EKS) independientes.

Capa de Datos: Bases de datos nativas de la nube (Amazon Aurora PostgreSQL y DynamoDB) segregadas para Nequi.

## Mapa de Capacidades del Negocio

Capacidades Consolidadas: Gestión de billetera digital, transferencias P2P entre usuarios Nequi, pago de servicios públicos.

Capacidades Críticas en Transición: Originación y cobro de créditos de consumo, enrolamiento biométrico e integración con redes de pago interbancario.

Capacidades en Crecimiento: Servicios de adquirencia para comercios, billeteras multimoneda e interoperabilidad en tiempo real vía Bre-B.

# Fase C: Arquitectura de Sistemas de Información

Punto de Inicio de la Fase: Arranca con la matriz de catalogación de aplicaciones y datos, definiendo qué sistemas se van a construir desde cero (Build), cuáles se adquirirán como soluciones comerciales o SaaS (Buy) y cuáles se integrarán vía interfaces de API (Integrate).

## Estrategia de Portafolio: Build vs. Buy vs. Integrate

| Categoría | Enfoque de Solución | Componentes y Tecnologías Seleccionadas |
| --- | --- | --- |
| BUILD / (Desarrollo Propio) | Microservicios a medida en Go y Java para ventajas competitivas centrales. | • Motor de Pagos y Transferencias / • App Móvil Nequi (iOS / Android) / • Core de Billeteras y Bolsillos / • Microservicios de Crédito Expreso |
| BUY / (Comercial / SaaS) | Plataformas especializadas de clase mundial para ciberseguridad y observabilidad. | • Auth0 (Okta): Gestión de identidad y credenciales / • Datadog: Monitoreo APM y telemetría / • Cloudflare: Protección WAF y mitigación DDoS / • Splunk: Monitoreo SIEM y auditoría de logs / • Feedzai: Prevención de fraude con IA |
| INTEGRATE / (Integración por APIs) | Conectores estandarizados RESTful hacia el ecosistema financiero externo. | • Bancolombia: Servicio externo de cajeros y red física / • Red Bre-B / PSE: Transferencias interbancarias inmediatas / • Wompi / Wenia: Pasarelas de adquirencia y pagos digitales / • Franquicia Visa: Emisión y procesamiento de tarjetas débito |

# Fase D: Arquitectura Tecnológica

Punto de Inicio de la Fase: Inicia con la aprobación del diseño de arquitectura de infraestructura multicloud y la configuración de las redes virtuales privadas (VPCs y Subnets) en las regiones principales y secundarias de la nube.

## Infraestructura Objetivo (Multicloud & Edge)

Nube Principal (AWS): Clústeres de Amazon EKS para alojar microservicios, Amazon Aurora para persistencia relacional transaccional y Amazon DynamoDB para consultas no relacionales de alta velocidad.

Nube Secundaria / Contingencia (Google Cloud / Azure): Replicación asíncrona de datos y respaldo frío/tibio para garantizar la continuidad del negocio ante caídas de la región principal.

Capa de Borde (Edge & Ciberseguridad): Malla de servicio (Service Mesh con Istio) y API Gateway redundante protegido por reglas Zero Trust y cifrado TLS 1.3 en todos los puntos de comunicación.

# Fase E: Oportunidades y Soluciones

Punto de Inicio de la Fase: Esta fase arranca formalmente con la consolidación del Análisis de Brechas (Gap Analysis) y el cálculo detallado de la viabilidad financiera (CAPEX y OPEX) que sustentan la migración.

## Matriz de Brechas (Gap Analysis)

| Componente | Estado Actual (AS-IS) | Estado Objetivo (TO-BE) | Acción / Categoría |
| --- | --- | --- | --- |
| Core de Cuentas | Hospedado en el Mainframe de Bancolombia. | Core bancario propio en nube nativa. | Nuevo / Reemplazado |
| Autenticación | Servicio compartido de biometría y clave única. | Auth0 + Biometría en la nube de Nequi. | Nuevo |
| Canal de Cajeros | Conexión directa interna por red LAN/WAN. | Consumo de servicio externo vía API REST cifrada. | Modificado |
| App Móvil | Interfaz cliente dependiente de servicios matriz. | App cliente autónoma consumiendo API Gateway propio. | Modificado |
| Servidores Legados | Instancias locales en datacenters compartidos. | Retiro definitivo y desvinculación física. | Eliminado |
| Lógica de Bolsillos | Microservicios acoplados al bus de Bancolombia. | Contenedores EKS ejecutados independientemente. | Retenido / Migrado |

## Presupuesto e Inversión Financiera Detallada

El proyecto cuenta con una estructura de inversión dividida en costos de implementación (CAPEX) y costos recurrentes de operación (OPEX).

Inversión de Implementación (CAPEX): $37.375 M

Inversión Base Subtotal: $32.500 M

Contingencia Recomendada (15%): $4.875 M

Presupuesto Total CAPEX: $37.375 M

### Desglose del CAPEX por Fase del Roadmap:

Fase 0 (Fundación): $1.200 M (Diseño de arquitectura, licencias iniciales de modelamiento y asesoría legal de desvinculación).

Fase 1 (Legal y Gobierno): $4.500 M (Trámites ante la SFC, constitución de Nequi S.A. y auditorías normativas externas).

Fase 2 (Tecnología y Datos): $18.000 M (Representa el 55.3% del esfuerzo técnico):
• Plataforma y Nube: $7.000 M
• Desarrollo de Servicios Core: $6.500 M
• Identidad y Ciberseguridad: $2.700 M
• Integraciones y APIs: $1.800 M

Fase 3 (Cesión y Día 1): $6.000 M (Ensayos de corte, migración masiva de datos y campaña de cesión de contratos de usuarios).

Fase 4 (Estabilización): $2.800 M (Ajustes de desempeño, pruebas de estrés y optimización de cargas).

### Flujo de Caja Anual del CAPEX:

Año 2026: $15.870 M (42.5% de la inversión)

Año 2027: $18.285 M (48.9% de la inversión)

Año 2028: $3.220 M (8.6% de la inversión)

### Dimensión Económica del Proyecto:

La inversión total del CAPEX (37.375M) equivale a 0.94 veces el costo operativo anual de la plataforma.

Representa únicamente el 7.5% del Capital Inicial de Nequi S.A. (500.000M asignados para la creación de la Compañía de Financiamiento), diluido en un período de ejecución de 3 años.

### Presupuesto Operativo Anual (OPEX Target): $38.800 M/año

Para mantener la operación independiente corriendo al 100% en la nube, se distribuye el costo operativo en el siguiente esquema:

| Ítem | Componente Operativo | Costo Anual (COP) | Porcentaje (%) |
| --- | --- | --- | --- |
| 1 | Infraestructura Cloud (AWS, GCP, Azure) | $14.200 M | 36.6% |
| 2 | Ciberseguridad & Antifraude (Cloudflare, Feedzai) | $8.500 M | 21.9% |
| 3 | Licenciamiento SaaS (Auth0, Datadog, Splunk) | $6.800 M | 17.5% |
| 4 | Conectividad & Redes (APIs, Bre-B, Visa, PSE) | $5.100 M | 13.1% |
| 5 | Soporte Especializado & Mantenimiento | $4.200 M | 10.8% |
| TOTAL | Presupuesto Anual Estimado | $38.800 M | 100.0% |

# Estrategia y Pilares de Migración

La migración se basa en 4 Pilares Estratégicos:

Comprar / Construir / Reutilizar (Buy/Build/Reuse): Priorizar el desarrollo propio únicamente en lo que genera ventaja competitiva (core y billetera) y contratar SaaS para lo demás.

Cambio Evolutivo (Evitar el Big Bang): Desacoplar componentes paso a paso utilizando patrones de estratificación (Strangler Fig).

Ganancias Rápidas (Quick Wins): Independizar primero los servicios periféricos (notificaciones, consultas) antes de tocar el core de cuentas.

Prioridad por Valor e Impacto: Garantizar que cada fase entregue estabilidad tecnológica inmediata a los usuarios.

# Los 5 Proyectos Clave de Implementación

Proyecto 1: Gobierno, Regulación y Cumplimiento: Tramitación de la licencia ante la SFC, definición de estatutos jurídicos y constitución de la Compañía de Financiamiento.

Proyecto 2: Autonomía Financiera y Gestión del Riesgo: Creación de los modelos independientes de riesgo crediticio, tesorería y contabilidad separada.

Proyecto 3: Independencia Tecnológica e Infraestructura: Despliegue del entorno multicloud en AWS/GCP, aprovisionamiento de bases de datos Aurora y clústeres EKS.

Proyecto 4: Integración, Servicios y Ciberseguridad: Implementación de Auth0, Feedzai, Datadog y desarrollo del API Gateway para la red de aliados.

Proyecto 5: Migración de Datos y Puesta en Marcha (Día 1): Ejecución del plan de corte transaccional, cesión de contratos de usuarios y paso a producción independiente.

Hito de Separación Real (Fecha Efectiva): 1 de Septiembre de 2026 (Punto de inflexión donde la operación transaccional pasa a procesarse en los sistemas propios de Nequi).

# Herramientas de Seguimiento y Control

Microsoft Forms / Portales de Catastro: Levantamiento inicial de preparación e inventario de dependencias.

Jira Software / Confluence: Control de avance de sprints, gestión de backlog y matriz de riesgos en tiempo real.

Datadog & Grafana: Dashboards de monitoreo operacional, telemetría y verificación del cumplimiento de KPIs de disponibilidad.

Repositorio GitHub del Proyecto: dbarretoc3-creator/Proyecto-Arquitectura-Nequi

# Mapa de Valor y BPMN del Proceso Transaccional

A continuación se detalla la ejecución paso a paso de una transferencia monetaria dentro de la arquitectura objetivo (TO-BE):

| Paso | Actor / Componente | Acción Transaccional | Mecanismo de Control / Resultado |
| --- | --- | --- | --- |
| 1 | Usuario Nequi | Solicita envío de dinero desde la App Nequi. | Ingreso de monto, clave y destinatario. |
| 2 | App Móvil Nequi | Envía petición cifrada HTTPS / TLS 1.3. | Enrutamiento seguro hacia la nube propia. |
| 3 | API Gateway (Cloudflare WAF) | Inspecciona la petición y valida reglas de borde. | Filtrado de ataques DDoS y validación de DNS. |
| 4 | Auth0 / Identidad | Autentica el token JWT y la firma biométrica. | Verificación de identidad exitosa. |
| 5 | Feedzai AI Engine | Analiza la transacción en tiempo real (≤50ms). | Evaluación de riesgo e inspección antifraude. |
| 6 | Microservicio Cuentas (EKS) | Ejecuta el débito en el saldo del usuario emisor. | Aplicación de lógica de negocio desacoplada. |
| 7 | BD Aurora PostgreSQL | Registra el movimiento con consistencia ACID (RPO=0). | Actualización inmediata en base de datos. |
| 8A | Destino Nequi | Aplica el crédito en la cuenta receptora en Nequi. | Transmisión y abono instantáneo. |
| 8B | Destino Banco Externo | Transmite la instrucción por la red Bre-B / PSE. | Envío vía API REST sin tocar a Bancolombia. |

# Hoja de Ruta Estratégica (Roadmap 2026–2028)

## Fase 0: Fundación

Inicio de la Fase: Arranca el 1 de Enero de 2026 con la constitución oficial del Comité de Gobierno de la Transición y la asignación del equipo de arquitectura líder.

Período de Ejecución: Enero 2026 – Marzo 2026.

Actividades Principales: Definición de la estructura organizativa del programa, homologación de estándares de ingeniería y catastro de dependencias compartidas.

Hito de la Fase: Aprobación del Mapa Global de Dependencias e Inventario Tecnológico.

## Fase 1: Legal y Gobierno

Inicio de la Fase: Arranca el 1 de Abril de 2026 con el radicado formal del expediente de solicitud de constitución de Nequi S.A. Compañía de Financiamiento ante la Superintendencia Financiera de Colombia.

Período de Ejecución: Abril 2026 – Febrero 2027.

Actividades Principales: Tramitación de la autorización regulatoria, definición de estatutos de gobierno corporativo, estructuración del capital social de $500.000 M y montaje de las comisiones de riesgo.

Hito de la Fase: Obtención de la Licencia de Funcionamiento y Otorgamiento de Estatutos por la SFC.

## Fase 2: Tecnología y Datos

Inicio de la Fase: Arranca el 1 de Julio de 2026 con el aprovisionamiento de la cuenta máster de AWS y el despliegue de las primeras redes VPC para el entorno independiente de Nequi.

Período de Ejecución: Julio 2026 – Junio 2027.

Actividades Principales: Construcción del Core de cuentas en microservicios, despliegue de Auth0, configuración del motor antifraude Feedzai y migración de la capa de APIs de integración.

Hito de la Fase: Nequi Operando 100% en Nube Propia a través de APIs Desacopladas (Hito de Separación Real - 1 Sep 2026).

## Fase 3: Cesión y Día 1

Inicio de la Fase: Arranca el 1 de Abril de 2027 con la notificación pública a la base de usuarios y el inicio de la campaña de aceptación de la cesión de contratos de depósitos hacia Nequi S.A.

Período de Ejecución: Abril 2027 – Diciembre 2027.

Actividades Principales: Ejecución de pruebas de carga en producción (Dry Runs), corte transaccional simulado y apertura oficial del balance independiente.

Hito de la Fase: Celebración del "Día 1" de Nequi S.A. como Entidad Financiera Autónoma.

## Fase 4: Estabilización

Inicio de la Fase: Arranca el 1 de Enero de 2028 con la desconexión definitiva de los enlaces dedicados antiguos con el datacenter de Bancolombia.

Período de Ejecución: Enero 2028 – Junio 2028.

Actividades Principales: Desmantelamiento de servicios residuales compartidos, ajuste de reglas de autoescalado en la nube para optimización del OPEX anual ($38.800 M) y auditoría final post-implementación.

Hito de la Fase: Cierre Formal del Programa de Transición y Autonomía Operativa Absoluta.

# Proyectos Clave, Matriz de Riesgos & Mitigación y Herramientas

Para amortiguar cualquier imprevisto durante el desacople, se estructuró la siguiente matriz de riesgos operacionales y tecnológicos:

| Riesgo Identificado | Impacto / Probabilidad | Estrategia de Mitigación |
| --- | --- | --- |
| Falla en la Migración de Saldos: / Inconsistencia en saldos de usuarios durante la ventana de corte. | Crítico / Baja | Ejecución de replicación en doble vía con consistencia transaccional (RPO=0) y pruebas automatizadas de conciliación en tiempo real. |
| Ataques de Ciberseguridad (DDoS / Suplantación): / Intentos de vulneración durante el cambio de infraestructura. | Alto / Media | Despliegue de capa Cloudflare Magic Transit, inspección WAF de borde y autenticación robusta vía Auth0. |
| Demoras en Aprobación Regulatoria: / Retrasos en la obtención de la licencia de la SFC. | Alto / Media | Acompañamiento legal especializado y entregas de evidencia por fases anticipadas. |
| Degradación del Servicio (Latencias Altas): / Congestión en la comunicación entre microservicios. | Medio / Alta | Monitoreo sintético con Datadog APM, uso de bases de datos Aurora PostgreSQL con lectura replicada y mallas Istio. |
| Resistencia al Cambio en Usuarios: / Desconfianza ante el aviso de cesión de contrato. | Medio / Baja | Campaña omnicanal de comunicación pedagógica resaltando que los saldos y claves se mantienen intactos. |

## Resumen de Herramientas y Repositorios Oficiales

Control y Planificación de Tareas: Jira Software & Confluence.

Catastro de Preparación: Microsoft Forms.

Telemetría y Observabilidad: Datadog, Grafana & Splunk.

Repositorio Oficial de la Arquitectura: dbarretoc3-creator/Proyecto-Arquitectura-Nequi
