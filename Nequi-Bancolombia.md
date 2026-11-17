# Arquitectura Empresarial TOGAF ADM para la independencia tecnológica y operativa de Nequi

![Universidad Central](assets/image1.png)

**Asignatura:** Arquitectura de Sistemas II  
**Integrantes:** Esteban Barreto · David Verdugo · Bryan Garavito  
**Profesor:** Oscar Darío Sánchez Pérez  
**Universidad:** Universidad Central  
**Ubicación:** Bogotá D. C.  
**Año:** 2026

---

## Tabla de contenido

- [Síntesis del problema](#sintesis-del-problema)
- [Hallazgo principal y alcance de visibilidad del arquitecto](#hallazgo-principal-y-alcance-de-visibilidad-del-arquitecto)
- [Cifras de contexto verificadas](#cifras-de-contexto-verificadas)
- [1. Fase Preliminar: preparar la capacidad de arquitectura](#1-fase-preliminar-preparar-la-capacidad-de-arquitectura)
- [1.1 Contexto y motivadores](#11-contexto-y-motivadores)
- [1.2 Alcance de la empresa sujeta a arquitectura](#12-alcance-de-la-empresa-sujeta-a-arquitectura)
- [1.3 Principios de arquitectura](#13-principios-de-arquitectura)
- [1.4 Organización de arquitectura y gobierno [P]](#14-organizacion-de-arquitectura-y-gobierno-)
- [1.5 Marco, repositorio y herramientas](#15-marco-repositorio-y-herramientas)
- [1.6 Madurez de partida [P]](#16-madurez-de-partida-)
- [1.7 Entregables de la fase](#17-entregables-de-la-fase)
- [2. Fase A: visión de arquitectura](#2-fase-a-vision-de-arquitectura)
- [2.1 Declaración de visión](#21-declaracion-de-vision)
- [2.2 Interesados y preocupaciones](#22-interesados-y-preocupaciones)
- [2.3 Objetivos medibles](#23-objetivos-medibles)
- [2.4 Restricciones y riesgos iniciales](#24-restricciones-y-riesgos-iniciales)
- [2.5 Solicitud de trabajo de arquitectura (resumen)](#25-solicitud-de-trabajo-de-arquitectura-resumen)
- [3. Fase B: arquitectura de negocio](#3-fase-b-arquitectura-de-negocio)
- [3.1 Línea base y objetivo](#31-linea-base-y-objetivo)
- [3.4 Procesos críticos y su dueño](#34-procesos-criticos-y-su-dueno)
- [3.5 Análisis de brechas de negocio](#35-analisis-de-brechas-de-negocio)
- [4. Fase C: arquitectura de sistemas de información](#4-fase-c-arquitectura-de-sistemas-de-informacion)
- [4.1 Arquitectura de datos](#41-arquitectura-de-datos)
- [4.2 Arquitectura de aplicaciones](#42-arquitectura-de-aplicaciones)
- [4.3 Matriz de integraciones](#43-matriz-de-integraciones)
- [5. Fase D: arquitectura tecnológica](#5-fase-d-arquitectura-tecnologica)
- [5.2 Requisitos de resiliencia](#52-requisitos-de-resiliencia)
- [5.3 Seguridad y cumplimiento tecnológico](#53-seguridad-y-cumplimiento-tecnologico)
- [5.4 Costo de operar la plataforma](#54-costo-de-operar-la-plataforma)
- [6. Fase E: oportunidades y soluciones](#6-fase-e-oportunidades-y-soluciones)
- [6.1 Alternativas evaluadas](#61-alternativas-evaluadas)
- [6.2 Paquetes de trabajo y estado](#62-paquetes-de-trabajo-y-estado)
- [Ajuste de Alcance sobre el Paquete 6](#ajuste-de-alcance-sobre-el-paquete-6)
- [6.3 Costo de implementación](#63-costo-de-implementacion)
- [6.4 Beneficios y riesgos de la decisión](#64-beneficios-y-riesgos-de-la-decision)
- [7. Fase F: planificación de la migración](#7-fase-f-planificacion-de-la-migracion)
- [7.1 Línea de tiempo real frente a la planeada](#71-linea-de-tiempo-real-frente-a-la-planeada)
- [7.2 Arquitecturas de transición](#72-arquitecturas-de-transicion)
- [7.3 Priorización (valor y riesgo)](#73-priorizacion-valor-y-riesgo)
- [7.4 Estrategia de migración de lo que falte](#74-estrategia-de-migracion-de-lo-que-falte)
- [7.5 Recursos](#75-recursos)
- [7.6 Riesgos de implementación](#76-riesgos-de-implementacion)
- [8. Fase G: gobierno de la implementación](#8-fase-g-gobierno-de-la-implementacion)
- [8.1 Contrato de arquitectura](#81-contrato-de-arquitectura)
- [8.2 Building blocks (Bloques de construcción)](#82-building-blocks-bloques-de-construccion)
- [8.3 Niveles de conformidad](#83-niveles-de-conformidad)
- [8.4 Integración con el desarrollo](#84-integracion-con-el-desarrollo)
- [8.5 Gobierno de la relación con Bancolombia](#85-gobierno-de-la-relacion-con-bancolombia)
- [8.6 Artefactos clave de gobierno](#86-artefactos-clave-de-gobierno)
- [9. Fase H: gestión del cambio de la arquitectura](#9-fase-h-gestion-del-cambio-de-la-arquitectura)
- [9.1 Motores de cambio a vigilar](#91-motores-de-cambio-a-vigilar)
- [9.2 Clasificación de los cambios](#92-clasificacion-de-los-cambios)
- [9.4 Indicadores de seguimiento](#94-indicadores-de-seguimiento)
- [9.5 Cuándo iniciar un nuevo ciclo del ADM](#95-cuando-iniciar-un-nuevo-ciclo-del-adm)
- [10. Gestión de requerimientos](#10-gestion-de-requerimientos)
- [11. Diferencias entre la planificación inicial y los datos públicos](#11-diferencias-entre-la-planificacion-inicial-y-los-datos-publicos)
- [12. Fuentes](#12-fuentes)
- [Nota de Validación Técnica Pendiente con Nequi](#nota-de-validacion-tecnica-pendiente-con-nequi)

---

Caso de estudio:Arquitectura Empresarial TOGAF para la Independencia Tecnológica y Operativa de Nequi


## Síntesis del problema

Nequi dio un salto histórico en el sistema financiero colombiano: dejó de operar como una línea de negocio dentro de Bancolombia para constituirse como Nequi S.A. Compañía de Financiamiento, una entidad autónoma vigilada directamente por la Superintendencia Financiera de Colombia (SFC) y propiedad 100 % de Grupo Cibest. La autorización regulatoria llegó mediante la Resolución 2002 del 31 de octubre de 2025 [V], y la operación independiente arrancó oficialmente el 1 de septiembre de 2026 [V], fecha en la cual Bancolombia cedió a Nequi los activos, pasivos y contratos vinculados a su operación digital.

Como Arquitecto Empresarial del proyecto, he estructurado este entregable siguiendo el ciclo completo del Método de Desarrollo de Arquitectura (ADM) de TOGAF. Para garantizar rigor técnico y transparencia académica, cada afirmación, cifra o decisión lleva una etiqueta explícita según su nivel de evidencia:


| [V] Verificado en fuente pública<br>Datos respaldados por reportes regulatorios (6-K), llamadas de resultados y prensa especializada (ver Sección 12). | [D] Diseño base del proyecto<br>Estimaciones de costos, cronogramas preliminares y parámetros técnicos definidos en nuestra línea base de arquitectura. | [P] Propuesta del arquitecto<br>Lineamientos de gobierno, resiliencia y operación formulados desde la arquitectura empresarial para validación con Nequi. |
| --- | --- | --- |


## Hallazgo principal y alcance de visibilidad del arquitecto

Hallazgo principal: En nuestra planificación inicial del proyecto se proyectaba la cesión y el Día 1 entre abril y diciembre de 2027, con independencia total en junio de 2028 [D]. Sin embargo, la realidad pública demuestra que el Día 1 ocurrió el 1 de septiembre de 2026 [V], aproximadamente un año antes de lo proyectado. Por ello, este estudio aborda las Fases A a D como el diseño de la arquitectura objetivo y las Fases E a H como la hoja de ruta ajustada a los hechos ya ejecutados: nuestra prioridad actual es estabilizar, gobernar y evolucionar la plataforma. La Sección 11 detalla cada diferencia entre la planificación inicial y los datos públicos.

Alcance de visibilidad: Dado que la información operativa confidencial de Nequi no es de dominio público, esta arquitectura integra rigurosamente lo que Nequi y Grupo Cibest han divulgado oficialmente [V], nuestra línea base de diseño técnico-financiero [D] y mis propuestas como arquitecto del proyecto [P], manteniendo cada elemento claramente identificado


## Cifras de contexto verificadas


| Indicador | Valor | Fuente |
| --- | --- | --- |
| Autorización SFC | Resolución 2002 del 31-oct-2025 [V] | Semana / Nequi |
| Inicio de operación independiente | 1-sep-2026 [V] | Cibest 6-K |
| Cuentas Nequi (30-sep-2026) | 29,3 millones; 23,8 millones activas [V] | Cibest 6-K |
| Cartera de crédito (3T26) | COP 2,469 billones [V] | La República |
| Depósitos (3T26) | COP 6,9 billones, +24 % anual [V] | Llamada de resultados Cibest 3T26 |
| Capital asignado por Cibest | COP 600.000 millones; solvencia total 13 % [V] | Llamada de resultados Cibest 3T26 |
| Peso en la utilidad de Cibest | Cerca de 2 % [V] | Llamada de resultados Cibest 3T26 |
| Punto de equilibrio | Primera vez en sep-2025 [V] | Cibest 3T25 / El Colombiano |


## 1. Fase Preliminar: preparar la capacidad de arquitectura

Antes de trazar planos tecnológicos, todo arquitecto empresarial debe preparar el terreno organizacional. En TOGAF, la Fase Preliminar responde cuatro preguntas fundamentales para este proyecto: qué abarca la separación, quién tomará las decisiones, bajo qué principios técnicos operaremos y con qué herramientas gobernaremos el cambio.


## 1.1 Contexto y motivadores

Estructura corporativa: Grupo Bancolombia se reorganizó bajo la matriz Grupo Cibest, un holding financiero que agrupa a Bancolombia, Nequi, Wenia, Wompi y otras filiales estratégicas .

Motivador regulatorio: Operar con licencia propia otorga a Nequi supervisión directa de la SFC, respaldo del seguro de depósitos de Fogafín y habilitación para actuar como Intermediario del Mercado Cambiario.

Motivador de negocio: Nequi alcanzó su punto de equilibrio financiero por primera vez en septiembre de 2025 y su cartera de crédito creció de COP 1,6 billones (marzo de 2026) a COP 2,469 billones en el tercer trimestre de 2026 . Según explicó su CEO, Andrés Vásquez, la separación busca que los inversionistas y el mercado valoren a Nequi de forma independiente.

Motivador tecnológico: Nequi culminó en noviembre de 2025 un proyecto de 18 meses para trasladar su core bancario a la nube y, de acuerdo con su CEO, hoy el 100 % de su tecnología opera en la nube].


## 1.2 Alcance de la empresa sujeta a arquitectura


| Dentro del alcance | Fuera del alcance |
| --- | --- |
| App Nequi (móvil y web), servicios de usuarios, transacciones, pagos y seguridad | Productos y estrategia comercial de Bancolombia |
| Base de datos propia y ledger central de saldos | Cambios de producto visibles al usuario final durante la cesión |
| Integraciones: Bancolombia (cajeros y corresponsales), Bre-B, PSE, redes de tarjetas, Puntored y PTM | Estrategia corporativa de otras filiales de Cibest (Banistmo, Wompi, Wenia), salvo sus interfaces con Nequi |
| Gobierno corporativo, riesgos, tesorería, contabilidad y cumplimiento propios | Decisiones de salida a bolsa (IPO) u otras alternativas del holding (Cibest señaló que no la considera en el corto plazo) [V] |


## 1.3 Principios de arquitectura

Cada principio rector sigue estrictamente la estructura de TOGAF: enunciado, justificación de negocio/técnica e implicación operativa.


| # | Principio | Justificación | Implicación |
| --- | --- | --- | --- |
| P1 | El dinero y los datos del usuario van primero | Nequi custodia depósitos por COP 6,9 billones [V] | Ningún cambio se despliega sin plan de reversa y conciliación de saldos |
| P2 | Independiente pero conectada | Nequi es una entidad con licencia propia, pero depende de la red de cajeros de Bancolombia [V] | Bancolombia es una integración más, con contrato, SLA y canal cifrado |
| P3 | Cambio evolutivo, por etapas | El servicio no puede detenerse; hubo caídas en la migración a la nube [V] | Migraciones por cohortes, ventanas de baja demanda y vuelta atrás |
| P4 | Comprar lo estándar, construir lo propio | Presupuesto acotado y regulación exigente | Se construye solo lo que diferencia a Nequi (crédito, experiencia, antifraude propio) |
| P5 | Seguridad y cumplimiento por diseño | Nequi es vigilada directamente por la SFC | Controles, trazabilidad y evidencia para el regulador desde el diseño |
| P6 | Resiliencia sin concentración [P] | La caída de AWS de octubre de 2025 afectó a Bancolombia y Nequi [V] | Evitar un único punto de falla en nube, región o proveedor crítico |
| P7 | Datos con un solo dueño y acceso por API | Evita saldos inconsistentes entre servicios | Ningún servicio lee la base de datos de otro directamente |
| P8 | Transparencia con el usuario | Las comunicaciones oficiales solo salen por canales propios [V] | Estado de servicios público y comunicación proactiva en incidentes |


## 1.4 Organización de arquitectura y gobierno [P]


| Rol | Responsabilidad |
| --- | --- |
| Patrocinador ejecutivo (CEO de Nequi) | Mandato institucional, asignación de presupuesto y resolución de conflictos estratégicos |
| Junta de Revisión de Arquitectura (ARB) | Aprueba desviaciones y excepciones; la integran CTO, CISO, riesgos, cumplimiento, operaciones y producto |
| Arquitecto empresarial | Custodia la coherencia integral entre negocio, datos, aplicaciones y tecnología |
| Arquitectos de dominio | Lideran los frentes especializados de datos, aplicaciones, seguridad e integraciones |
| Oficina del programa de separación | Gestiona el plan maestro, hitos, riesgos y coordinación operativa con Bancolombia y Cibest |
| Cumplimiento y riesgo | Dueño de los requisitos regulatorios y de la evidencia formal ante la SFC |


## 1.5 Marco, repositorio y herramientas

Marco metodológico: TOGAF ADM adaptado a una ejecución ágil: ciclo corto por etapas, un entregable obligatorio por fase y sesiones ordinarias de la ARB cada dos semanas.

Repositorio de arquitectura: Un repositorio único y versionado que centraliza los catálogos de principios, capacidades, aplicaciones, interfaces y datos, junto con los Registros de Decisiones de Arquitectura (ADR) y el Contrato de Arquitectura.

Herramientas de ingeniería y observabilidad: En nuestra línea base de diseño contemplamos GitHub Enterprise y Datadog ; como arquitecto propongo que los ADR vivan versionados junto al código fuente y que el repositorio de arquitectura esté enlazado directamente al backlog de desarrollo.


## 1.6 Madurez de partida [P]


| Dimensión | Nivel de partida | Evidencia |
| --- | --- | --- |
| Capacidad técnica propia | Alto | Nequi cuenta con áreas propias de tecnología, operaciones, riesgos y cumplimiento desde hace unos dos años [V] |
| Resiliencia operativa | Medio-bajo | Caídas registradas el 24-oct-2025, fin de noviembre y 1-dic-2025, 3-feb-2026 y 27-oct-2026 [V] |
| Gobierno de arquitectura formal | Por confirmar | No existe divulgación pública sobre su estructura interna de ARB |
| Cumplimiento como entidad autónoma | En construcción | La transición de normas locales a NIIF registró un efecto único en provisiones durante el 3T26 [V] |


## 1.7 Entregables de la fase

1. Modelo organizacional de arquitectura: Definición de roles, responsabilidades y gobierno de la ARB (sección 1.4).

2. Catálogo de principios de arquitectura: Reglas no negociables P1 a P8 (sección 1.3).

3. Repositorio inicial de arquitectura: Estructura base para catálogos, ADR y contratos (sección 1.5).

4. Petición de trabajo de arquitectura: Documento ejecutivo que autoriza formalmente el inicio de la Fase A, con el alcance definido en 1.2, el patrocinio del CEO y el presupuesto del programa.


## 2. Fase A: visión de arquitectura

Con la capacidad de gobierno preparada, en la Fase A alineamos a todos los actores clave alrededor de una meta compartida: lograr una separación jurídica y tecnológica limpia sin fricciones para los millones de colombianos que usan la aplicación a diario.


## 2.1 Declaración de visión

Declaración de Visión del Proyecto

Que Nequi opere con plataforma, datos y gobierno propios como Compañía de Financiamiento autónoma, manteniendo una conexión segura y controlada con la red de Bancolombia para cajeros y corresponsales, sin que el usuario perciba interrupciones ni su dinero corra riesgo.


## 2.2 Interesados y preocupaciones


| Interesado | Preocupación principal | Qué le aporta la arquitectura |
| --- | --- | --- |
| Usuarios (29,3 millones de cuentas) [V] | Que su dinero esté seguro y la aplicación no se caiga | Alta disponibilidad, recuperación rápida y comunicación transparente |
| Nequi S.A. y su junta directiva | Decidir y evolucionar productos sin depender de terceros | Plataforma, gobierno de datos y accesos 100 % propios |
| Grupo Cibest (accionista) | Rentabilidad, eficiencia de capital y valor del activo | Estructura corporativa que habilita alternativas estratégicas |
| Bancolombia | Seguir prestando su red de cajeros y retiros sin riesgo operativo | Integración segura, delimitada y gobernada por contrato |
| SFC y Fogafín | Solvencia, gestión de riesgo operativo y protección del depósito | Controles auditables y trazabilidad regulatoria documentada |
| Aliados y redes (Bre-B, PSE, Visa, Puntored, PTM, Wompi) | Continuidad y estabilidad de las interfaces | APIs estables y estandarizadas tras un Gateway único |
| Empleados y socios tecnológicos (AWS, Infosys, Pragma) [V] | Claridad en roles, contratos y responsabilidades técnicas | Gobierno definido y hoja de ruta compartida |


## 2.3 Objetivos medibles


| Meta | Indicador | Qué significa en la práctica | Estado público |
| --- | --- | --- | --- |
| Disponibilidad | [D] | Hasta 43 minutos de indisponibilidad máxima al mes | No hay SLA publicado; hubo incidentes en 2025 y 2026 [V] |
| Transacciones exitosas | [D] | Pagos y envíos que culminan exitosamente al primer intento | Sin dato público divulgado |
| Recuperación | [D] | Tiempo máximo de restablecimiento ante una falla grave | Sin dato público divulgado |
| Integraciones seguras | 100 % [D] | Toda conexión externa mutuamente autenticada y cifrada | Sin dato público divulgado |
| Pérdida de datos | 0 [D] | Ningún saldo o registro se pierde durante la migración | No se reportó pérdida de saldos en el corte del 1-sep-2026 [V] |


## 2.4 Restricciones y riesgos iniciales

Restricciones del entorno: Exigencias regulatorias estrictas de la SFC, continuidad de servicio 24/7, presupuesto acotado y dependencia operativa de la red física de cajeros de Bancolombia.

Riesgos iniciales identificados: (1) Saldos que no concilian entre sistemas durante la cesión.  Caídas de plataforma durante picos transaccionales de quincena y diciembre. (3) Escasez de talento especializado en nube, datos y ciberseguridad. Dependencia contractual con Bancolombia para retiros en efectivo.Concentración tecnológica en un solo proveedor de nube.


## 2.5 Solicitud de trabajo de arquitectura (resumen)

Alcance: Ejecución integral de las Fases B a H del ciclo TOGAF ADM. Entregables clave: Arquitectura objetivo (negocio, datos, aplicaciones y tecnología), análisis de brechas, hoja de ruta de migración, Contrato de Arquitectura y marco de gestión del cambio. Aprobación: CEO de Nequi y Junta de Revisión de Arquitectura (ARB).


## 3. Fase B: arquitectura de negocio

La Fase B traduce la visión estratégica en la nueva realidad jurídica, financiera y operativa de Nequi S.A. Aquí contrastamos cómo operaba la entidad antes del 1 de septiembre de 2026 frente a su estructura actual como Compañía de Financiamiento independiente.


## 3.1 Línea base y objetivo


| Dimensión | Antes del 1-sep-2026 (Línea base) | Después (Nequi S.A. Objetivo) |
| --- | --- | --- |
| Figura legal | Línea de negocio dentro de Bancolombia | Compañía de financiamiento con licencia propia, 100 % de Cibest [V] |
| Supervisión | Bajo la licencia bancaria de Bancolombia | Vigilada directamente por la SFC [V] |
|  |  |  |
| Depósitos | Contabilizados dentro del balance de Bancolombia | Cedidos a Nequi, con seguro de depósitos de Fogafín [V] |
| Información financiera | Consolidada dentro de los estados de Bancolombia | Estados financieros y reportes regulatorios propios [V] |
| Procesos de soporte | Compartidos con la estructura central del banco | Áreas propias de tecnología, operaciones, riesgos y cumplimiento [V] |
| Capital | Respaldado por el patrimonio del banco | COP 600.000 millones asignados; solvencia total del 13 % [V] |
| Mercado cambiario | Dependía de la autorización del banco | Habilitada para actuar como Intermediario del Mercado Cambiario [V] |

3.2 Cadena de valor

El flujo operativo extremo a extremo que sostiene la propuesta de valor de Nequi S.A. se articula en seis eslabones secuenciales:


| 1. Captar usuarios<br>Onboarding digital y validación KYC | 2. Custodiar y mover<br>Cuentas, bolsillos, envíos, recargas, Bre-B y PSE | 3. Retirar efectivo<br>Red de cajeros y corresponsales aliados | 4. Prestar<br>Colocación de crédito preaprobado | 5. Servir y resolver<br>Atención al usuario, disputas y antifraude | 6. Rendir cuentas<br>Reportería a SFC, contabilidad NIIF y tesorería |
| --- | --- | --- | --- | --- | --- |

3.3 Mapa de capacidades


| Estado de madurez | Capacidades de negocio |
| --- | --- |
| Consolidadas | Cuentas de ahorro de trámite simplificado y bolsillos, envíos y pagos P2P, recargas y experiencia móvil de la app |
| Críticas para separarse | Gestión de identidad y accesos, seguridad y ciberseguridad, tesorería y riesgo de liquidez, cumplimiento regulatorio y reportería a la SFC, contabilidad autónoma bajo NIIF |
| En crecimiento | Crédito digital (más de 3 millones de clientes con crédito preaprobado y más de COP 10 billones disponibles) [V], pagos inmediatos Bre-B, remesas y divisas, ecosistema cripto con Wenia y servicios a comercios |


## 3.4 Procesos críticos y su dueño


| Proceso de negocio | Dueño funcional | Dependencia con Bancolombia |
| --- | --- | --- |
| Abrir cuenta (KYC/AML) | Cumplimiento y producto | Ninguna (autónomo) |
| Enviar y pagar | Operaciones | Interoperabilidad bancaria vía Bre-B y PSE |
| Retirar en cajero o corresponsal | Operaciones | Alta: uso continuo de la red física de Bancolombia |
| Otorgar crédito | Riesgos | Cartera histórica cedida en el corte |
| Atender y resolver | Servicio al cliente | Ninguna (autónomo) |
| Reportar al regulador | Cumplimiento y finanzas | Ninguna; anteriormente lo consolidaba el banco |


## 3.5 Análisis de brechas de negocio


| Área | Estado base | Objetivo | Mecanismo de cierre | Estado actual |
| --- | --- | --- | --- | --- |
| Gobierno y legal | Bajo licencia del banco | Nequi S.A. autorizada | Resolución SFC 2002 y cesión de activos, pasivos y contratos | Cerrada [V] |
| Identidad y accesos | Directorio del grupo | Identidad propia | Servicio independiente de identidad y seguridad | Parcial [P] |
| Datos | Con sistemas del banco | Base de datos propia | Migración controlada con conciliación de saldos | Cerrada jurídicamente; detalle técnico no público |
| Plataforma | Infraestructura compartida | Plataforma independiente | Nube y API Gateway propios | Avanzada [V] |
| Integraciones | Conexiones internas | APIs seguras y auditadas | Contratos formales con Bancolombia, Bre-B, PSE y redes | En operación [V] |
| Contabilidad | Normas locales consolidadas | Contabilidad NIIF propia | Transición contable a estándares NIIF | En curso; efecto único en 3T26 [V] |


## 4. Fase C: arquitectura de sistemas de información

En la Fase C descendemos del modelo de negocio al diseño de los sistemas de información. El reto técnico más sensible de toda la separación reside aquí: transferir la custodia de millones de saldos sin detener el servicio ni perder un solo centavo, desacoplando los sistemas internos mediante interfaces estandarizadas.


## 4.1 Arquitectura de datos

Entidades principales del modelo: Usuario, Cuenta y saldo, Transacción, Crédito, Contrato de cesión y Registro de auditoría.


| Dominio de dato | Dueño | Clasificación | Control arquitectónico clave |
| --- | --- | --- | --- |
| Identidad y KYC | Cumplimiento | Personal sensible | Cifrado fuerte, principio de mínimo privilegio y trazabilidad |
| Saldo y ledger | Operaciones financieras | Crítico | Patrón de un solo escritor, conciliación diaria y respaldo replicado |
| Transacciones | Operaciones | Crítico | Registro inmutable con identificador único de idempotencia |
| Crédito y scoring | Riesgos | Personal y financiero | Gobierno del modelo analítico y explicabilidad |
| Auditoría | Cumplimiento | Regulatorio | Retención inalterable y consulta directa para el regulador |

Principios de gobierno de datos: (1) Un dato, un único dueño. (2) Acceso exclusivo a través de APIs autorizadas. (3) Cifrado obligatorio tanto en tránsito como en reposo. (4) Trazabilidad completa de cada movimiento financiero para auditoría de la SFC. (5) Cumplimiento estricto de la Ley 1581 de 2012 (protección de datos personales) y de la Ley 1266 de 2008 (habeas data financiero), a validar formalmente con Cumplimiento.

Estrategia de migración y cesión de datos: Ejecución estructurada por lotes bajo cuatro pasos: *copia, conciliación, corte y verificación posterior*. Dado que el servicio digital no podía detenerse, la ventana crítica de transición se ejecutó entre la noche del 31 de agosto y la madrugada del 1 de septiembre de 2026, con suspensión temporal de Bre-B entre las 10:00 p. m. y la 1:30 a. m. [V]. Todo el proceso fue transparente y los clientes no tuvieron que realizar ningún trámite [V].


## 4.2 Arquitectura de aplicaciones


| Componente | Función principal | Decisión | Nota arquitectónica |
| --- | --- | --- | --- |
| App Nequi (móvil y web) | Canal de interacción del usuario | Reutilizar | La experiencia de usuario se mantuvo intacta [V] |
| API Gateway | Punto de entrada único y control de acceso | Comprar | Gestiona autenticación, límites de tráfico y observabilidad |
| Servicios de usuarios, transacciones y pagos | Lógica de negocio central de Nequi | Construir | Constituye el núcleo diferencial del producto |
| Servicio de crédito y riesgo | Originación de preaprobados y scoring | Construir | Principal motor de crecimiento y rentabilidad |
| Seguridad e identidad | Autenticación, autorización y antifraude | Comprar | Auth0, Feedzai y Splunk según nuestra línea base de diseño [D]; no verificado públicamente |
| Servicio de retiros | Orquestación con cajeros de Bancolombia | Construir | Generación dinámica de código de retiro en la app [V] |
| Core bancario | Gestión de cuentas, movimientos y contabilidad | Comprar / integrar | Operando 100 % en la nube [V] |
| Reportería regulatoria | Generación de informes para la SFC y Fogafín | Construir / comprar [P] | Anteriormente era generada por Bancolombia |


## 4.3 Matriz de integraciones


| Integración | Qué intercambia | Criticidad | Estado |
| --- | --- | --- | --- |
| Bancolombia: cajeros y corresponsales | Retiros e ingresos en efectivo; límite de retiro diario en cajero de COP 2,7 millones [V] | Alta | Mantiene retiros sin costo para el usuario [V] |
| Bancolombia: transferencias | Movimientos financieros entre cuentas Nequi y Bancolombia | Alta | Interrumpida únicamente durante la ventana de cambio [V] |
| Bre-B | Pagos inmediatos interbancarios del sistema financiero | Alta | Operando normalmente [V] |
| PSE | Pagos en comercios y recargas desde otros bancos | Alta | Operando normalmente [V] |
| Redes de tarjetas (Visa) | Autorización y compensación de pagos con tarjeta | Media | Definido en diseño base [D] |
| Puntored y PTM | Red de corresponsales físicos aliados | Media | Operando normalmente [V] |
| Wompi y Wenia | Pasarela de pagos para comercios y servicios cripto | Media | Son compañías filiales de Grupo Cibest [V] |
| Remesas y divisas | Operaciones cambiarias e ingreso de remesas | Media | Nueva capacidad habilitada por la licencia propia <br> |


## 5. Fase D: arquitectura tecnológica

La Fase D define la infraestructura física y lógica en la nube sobre la cual corren las aplicaciones y bases de datos. En un biobanco que atiende a más de 29 millones de usuarios, la disponibilidad y la capacidad de recuperación son atributos críticos de supervivencia.

5.1 Pila tecnológica


| Capa | Tecnología / Especificación | Confianza |
| --- | --- | --- |
| Canales | Flutter (aplicación móvil) y React (portal web) | [D] |
| Aplicaciones | Microservicios Java / Spring desplegados sobre Kubernetes, tras un API Gateway | [D] |
| Datos | PostgreSQL con respaldo automatizado y recuperación ante desastres (AWS Backup) | [D] |
| Seguridad | Auth0, Splunk, Cloudflare; Feedzai y motores KYC/AML contra fraude | [D] |
| Nube y operación | AWS, GitHub Enterprise y Datadog | [D] |
| Nube (declaración pública) | Core bancario desplegado en Google, Microsoft y AWS; aliados estratégicos AWS, Infosys y Pragma | [V] |
| Capacidad transaccional | Arquitectura diseñada para soportar hasta 80 millones de transacciones diarias | [V] |


## 5.2 Requisitos de resiliencia


| Requisito | Meta arquitectónica |
| --- | --- |
| Disponibilidad | Despliegue multi-zona; rutas críticas (login, consulta de saldo, envío y retiro) con degradación controlada |
| RTO (Tiempo de recuperación) |  |
| RPO (Pérdida de datos aceptable) | Cercano a cero para el ledger transaccional de saldos |
| Capacidad y desempeño | Pruebas de carga y estrés obligatorias previas a cada quincena y a la temporada de diciembre |
| Gestión de dependencias | Si falla un proveedor externo, el servicio degrada grácilmente sin detenerse (Bre-B, PSE y retiros con modo contingencia) |

Justificación empírica: El 24 de octubre de 2025, una falla de comunicación entre centros de datos dejó sin servicio digital tanto a Bancolombia como a Nequi, pocos días después de la caída global de AWS . Posteriormente, entre el 28 de noviembre y el 1 de diciembre de 2025, se registraron nuevas intermitencias en plena migración a la nube . Durante 2026 se documentaron incidentes el 3 de febrero, el 17 de septiembre (parcial), el 26 de septiembre (falla en reconocimiento facial en dispositivos iPhone) y el 27 de octubre .


## 5.3 Seguridad y cumplimiento tecnológico

Controles preventivos y detectivos: Autenticación fuerte mediante biometría y vinculación de dispositivo, monitoreo antifraude en tiempo real y cifrado extremo a extremo en canales e integraciones.

Higiene de infraestructura: Gestión centralizada de llaves criptográficas y secretos, junto con segregación estricta entre ambientes de desarrollo, pruebas y producción.

Marco normativo a validar con Cumplimiento: Circular Externa 007 de 2018 de la SFC (requerimientos de ciberseguridad), Circular Externa 005 de 2019 de la SFC (servicios de computación en la nube) y normativa SARLAFT para prevención de lavado de activos y financiación del terrorismo.

Observabilidad: Monitoreo técnico con Datadog y Splunk , complementado con una página pública de estado de servicios para transparencia con los usuarios .


## 5.4 Costo de operar la plataforma


| Rubro operativo anual | COP millones / año |
| --- | --- |
| Nube e infraestructura | 11.147 |
| Plataforma y equipo de operación | 8.154 |
| Seguridad y antifraude | 7.914 |
| Integraciones | 5.300 |
| Total anual estimado de operación | 32.515 (aprox. USD 10,2 M con TRM 3.175) |

Verificación financiera del arquitecto: La suma aritmética de los rubros es exacta (11.147 + 8.154 + 7.914 + 5.300 = 32.515). La TRM de referencia utilizada en nuestra estimación inicial (COP 3.175) es inferior a la TRM oficial del 1 de octubre de 2026 (COP 3.312,84) [V]; aplicando esta tasa actualizada, el costo operativo anual equivale a USD 9,8 millones. En la estimación base se proyectó que este monto representa el 2 % de la inversión tecnológica de Grupo Cibest en 2026 (COP 1,6 billones), dato que permanece pendiente de verificación pública.


## 6. Fase E: oportunidades y soluciones

En la Fase E evaluamos los caminos posibles para materializar la separación, estructuramos los paquetes de trabajo técnicos y auditamos la consistencia financiera de la inversión requerida.


## 6.1 Alternativas evaluadas


| Opción | Descripción | Ventajas | Desventajas | Decisión |
| --- | --- | --- | --- | --- |
| A. Seguir como línea de negocio | Mantener a Nequi dentro de Bancolombia | Cero esfuerzo de separación técnica o legal | Sin autonomía de producto, finanzas consolidadas y límites del banco | Descartada |
| B. Entidad propia, tecnología compartida | Licencia propia pero operando sobre la plataforma del banco | Menor inversión inicial de infraestructura | Dependencia operativa continua y fallas compartidas (como el 24-oct-2025) | Descartada |
| C. Separación legal y tecnológica con integración al banco | Licencia, datos y plataforma propios; Bancolombia como proveedor de red física | Autonomía total, visibilidad independiente para inversionistas y productos propios | Mayor esfuerzo y riesgo controlado de migración | Elegida [V]: es lo que se ejecutó |


## 6.2 Paquetes de trabajo y estado


| # | Paquete de trabajo | Estado según información pública |
| --- | --- | --- |
| 1 | Nube propia y API Gateway | Avanzado: core bancario operando en la nube desde nov-2025; hoy 100 % en la nube [V] |
| 2 | Monitoreo y seguridad | Parcial: página de estado pública activa; se registraron incidentes en sep y oct de 2026 [V] |
| 3 | Pagos directos (Bre-B, PSE, Visa) | Operando en producción [V] |
| 4 | Identidad y servicios propios | Áreas propias conformadas hace unos dos años [V]; detalle técnico interno no público |
| 5 | Base de datos de saldos | Depósitos reportados en el balance propio de Nequi tras la cesión [V]; corte técnico no público |
| 6 | Retiro de servicios del banco | No aplica por completo: los retiros en efectivo seguirán usando la red de Bancolombia [V] |


### Ajuste de Alcance sobre el Paquete 6

En la concepción inicial del proyecto se asumía una desconexión total respecto a los servicios de Bancolombia. Sin embargo, la decisión estratégica ejecutada fue más eficiente: convertir la red de cajeros y corresponsales físicos de Bancolombia en una integración permanente respaldada por contrato .


## 6.3 Costo de implementación


| Etapa de implementación | Alcance de equipo y actividades | COP millones |
| --- | --- | --- |
| 0. Fundación | 5 personas + consultoría especializada | 1.200 |
| 1. Legal y gobierno | Firma legal y certificaciones regulatorias | 4.500 |
| 2. Tecnología y datos | 60 personas durante 12 meses | 18.000 |
| 3. Cesión y Día 1 | 25 personas durante 9 meses | 6.000 |
| 4. Estabilización | 12 personas durante 6 meses | 2.800 |
| Subtotal | Inversión base estimada de ejecución | 32.500 |
| Contingencia (15 %) | Reserva para riesgos de migración | 4.875 |
| Total inversión estimada | Presupuesto integral del programa | 37.375 (aprox. USD 11,8 M) |

Verificación de consistencia financiera: Las sumas de nuestra estimación base cuadran con exactitud: 32.500 + 4.875 = 37.375 millones; el desglose interno de tecnología (7.000 + 6.500 + 2.700 + 1.800) suma 18.000 millones; y la distribución plurianual (15.870 + 18.285 + 3.220) totaliza igualmente 37.375 millones. Como arquitecto señalo dos precisiones clave:

1. Desglose laboral vs. no laboral: Aplicando el costo unitario de COP 20 millones por persona al mes, la etapa 2 equivale a COP 14.400 millones (60 × 12 × 20), la etapa 3 a COP 4.500 millones y la etapa 4 a COP 1.440 millones. La diferencia respecto a los totales del cuadro corresponde a rubros no laborales (licencias de software, ambientes de nube en paralelo y consultoría externa), los cuales conviene desglosar en el presupuesto detallado.

2. Relación frente al capital asignado: En la proyección preliminar se calculó que la inversión representaba el 7,5 % sobre un capital inicial esperado de COP 500.000 millones. Dado que Grupo Cibest asignó finalmente COP 600.000 millones [V], dicha proporción se reduce al 6,2 %. Esta cifra constituye una referencia de contexto arquitectónico, pues ni Nequi ni Cibest han divulgado el costo real ejecutado en la separación.


## 6.4 Beneficios y riesgos de la decisión


| Qué se gana (Beneficios) | Qué puede salir mal (Riesgos) | Estrategia de mitigación |
| --- | --- | --- |
| Autonomía en decisiones y velocidad de evolución de producto | Fallas o intermitencias de servicio durante la transición | Despliegues en ventanas de baja demanda y planes de reversa |
| Información financiera separada y alternativas estratégicas para Cibest [V] | Dependencia operativa de Bancolombia para retiros en efectivo | Contrato formal con SLA y rutas alternas (Puntored y PTM) |
| Nuevas líneas de negocio: mercado cambiario y remesas (cerca de un millón de remesas al mes) [V] | Sobrecostos en nube paralela o integración | Reserva de contingencia del 15 % [D] |
| Respaldo directo del seguro de depósitos de Fogafín [V] | Mayores costos operativos de cumplimiento regulatorio | Automatización de controles y reportería regulada |


## 7. Fase F: planificación de la migración

En la Fase F contrastamos nuestra línea base de planificación con los hitos reales ya ejecutados por Nequi, definimos las arquitecturas de transición hacia la estabilización plena y establecemos los protocolos para desplegar los ajustes pendientes sin afectar la operación.


## 7.1 Línea de tiempo real frente a la planeada


| Hito estratégico | Planificación inicial [D] | Realidad pública verificada [V] |
| --- | --- | --- |
| Fundación y gobierno | Enero – Marzo 2026 | Separación técnica y operativa iniciada hace unos dos años |
| Autorización de la SFC | Hasta febrero 2027 | 31 de octubre de 2025 (Resolución 2002) |
| Core bancario en la nube | Julio 2026 – Junio 2027 | Proyecto de 18 meses finalizado en noviembre de 2025 |
| Cesión de contratos y cuentas (Día 1) | Abril – Diciembre 2027 | 1 de septiembre de 2026 |
| Estabilización operativa | Enero – Junio 2028 | En curso desde septiembre de 2026 |


## 7.2 Arquitecturas de transición


| Estado de arquitectura | Horizonte temporal | Descripción operativa y técnica |
| --- | --- | --- |
| Línea base | Hasta oct-2025 | Nequi opera como línea de negocio de Bancolombia mientras su core migra a la nube |
| TA1: Licencia y nube | Nov-2025 a ago-2026 | Licencia SFC otorgada, core 100 % en la nube y áreas propias conformadas; la entidad legal aún no inicia operación |
| TA2: Día 1 | 1-sep-2026 | Cesión jurídica de activos, pasivos y contratos; Bancolombia queda como integración externa tras una ventana de cambio de pocas horas |
| TA3: Estabilización | Nov-2026 a jun-2027 | Cierre de incidentes de disponibilidad, retiro de servicios transitorios y culminación de contabilidad NIIF y reportería |
| Arquitectura Objetivo | Desde jul-2027 | Operación estable cumpliendo las cinco metas de servicio y aceleración de nuevos productos |


## 7.3 Priorización (valor y riesgo)

Orden de ejecución recomendado para la etapa actual ]: priorizamos primero las iniciativas que generan alto valor de estabilidad con bajo riesgo operativo.


| Prioridad | Iniciativa | Valor | Riesgo | Justificación del orden |
| --- | --- | --- | --- | --- |
| 1 | Observabilidad y SLO por servicio crítico | Alto | Bajo | No toca saldos y reduce drásticamente el tiempo de detección |
| 2 | Pruebas de carga y simulacros de recuperación antes de picos | Alto | Bajo | Ataca directamente las caídas de quincena y diciembre |
| 3 | Resiliencia multi-región y modo contingencia de integraciones | Alto | Medio | Mitiga el riesgo de concentración tecnológica |
| 4 | Reportería regulatoria y NIIF automatizadas | Medio | Bajo | Cumplimiento obligatorio frente a la SFC |
| 5 | Retiro de servicios transitorios con Bancolombia | Medio | Medio | Se ejecuta solo tras acumular meses de estabilidad probada |
| 6 | Nuevos productos (cambiario, ahorro e inversión) | Alto | Medio | Se despliegan sobre una plataforma plenamente estabilizada |


## 7.4 Estrategia de migración de lo que falte

Despliegue gradual por cohortes: Liberación controlada al 1 %, 10 %, 50 % y 100 % de los usuarios, con auditoría nocturna de saldos y capacidad de reversa total en menos de 30 minutos.

Ventanas de mantenimiento protegidas: Ejecución de cambios estructurales únicamente entre la 1:00 a. m. y las 4:00 a. m., prohibiendo despliegues críticos en días de quincena o durante diciembre.

Integridad transaccional estricta: Mantenimiento de un solo escritor activo de saldos en todo momento y conciliación obligatoria previa a cada corte.

Compuertas de calidad (Quality Gates): Exigencia de 30 días consecutivos sin incidentes críticos antes de promover una cohorte a la siguiente etapa.


## 7.5 Recursos

En nuestra planificación base proyectamos un pico de 60 especialistas en tecnología y datos (ingeniería Java, arquitectura nube, ingeniería de datos, ciberseguridad y QA), 25 personas en cesión y estabilización y 11 en fundación y legal . Para la etapa actual de estabilización propongo consolidar un núcleo dedicado de 12 personas  respaldado por un socio externo bajo acuerdos de nivel de servicio (SLA), aprovechando el ecosistema tecnológico con el que Nequi ya trabaja (AWS, Infosys y Pragma ).


## 7.6 Riesgos de implementación


| Riesgo | Descripción | Plan de mitigación |
| --- | --- | --- |
| Saldos que no cuadran | Diferencias contables o transaccionales al migrar o conciliar | Respaldo completo previo, revisión nocturna y despliegue por cohortes |
| Caída del servicio | Ocurrió en oct-2025 y nov-dic 2025 durante la migración; en 2026 se reportaron cinco incidentes [V] | Ventanas de baja demanda, reversa automática y pruebas de carga |
| Falta de personal especializado | Escasez de expertos en arquitecturas nube, datos y seguridad | Contratación anticipada y apoyo de socios tecnológicos |
| Dependencia contractual de Bancolombia | Modificación unilateral de condiciones o tarifas de retiro | Contrato formal con SLA y canales alternos operativos |
| Fraude y suplantación | Delincuentes usan la separación como excusa para engañar usuarios | Nequi comunicó oficialmente que no pedirá claves ni trámites por la separación [V] |


## 8. Fase G: gobierno de la implementación

En la Fase G asumo el rol de interventor técnico del proyecto: vigilo que cada componente construido por los equipos de ingeniería respete fielmente los principios, estándares y metas aprobados en la arquitectura objetivo.


## 8.1 Contrato de arquitectura


| Contrato de Arquitectura (Especificación de Conformidad en formato JSON)<br>{<br>  "Plataforma": "Nube con despliegue multi-zona; sin punto único de falla",<br>  "Aplicaciones": "Java/Spring sobre Kubernetes, tras API Gateway",<br>  "Datos": "PostgreSQL; un solo escritor de saldos; acceso solo por API",<br>  "Seguridad": "Autenticación fuerte, cifrado en tránsito y reposo, mTLS en integraciones",<br>  "Disponibilidad": ">= 99,9 %",<br>  "Recuperación": "RTO <= 30 min; RPO cercano a cero en ledger",<br>  "Integraciones": "100 % autenticadas, cifradas y auditadas",<br>  "Cumplimiento": "SFC, Fogafín, Ley 1581/2012, SARLAFT"<br>} |
| --- |

Cuando un equipo técnico requiere apartarse de alguno de estos parámetros, se activa formalmente el flujo de excepciones ante la ARB. Los valores de pila tecnológica reflejan nuestra línea base de diseño .


## 8.2 Building blocks (Bloques de construcción)


| ABB (Bloque abstracto) | SBB (Bloque de solución real) | Confianza |
| --- | --- | --- |
| Persistencia transaccional relacional | PostgreSQL con respaldo replicado | [D] |
| Autenticación y autorización | Auth0 | [D] |
| Antifraude en tiempo real | Feedzai | [D] |
| Gateway de APIs | Gateway gestionado propio | [D] |
| Computación y nube | AWS, Google Cloud y Microsoft Azure | [V] |
| Retiros físicos | Cajeros y corresponsales de Bancolombia, Puntored y PTM | [V] |


## 8.3 Niveles de conformidad


| Nivel de conformidad | Significado técnico | Acción de gobierno |
| --- | --- | --- |
| Conforme | La solución cumple el 100 % del Contrato de Arquitectura | Aprobar el pase a producción |
| Excepción | Se adopta una alternativa tecnológica con justificación válida | La ARB analiza y aprueba por escrito con fecha de vencimiento |
| No conforme | Introduce riesgo técnico, operativo o regulatorio inaceptable | Detener el despliegue y exigir refactorización |

Ejemplo práctico de interventoría: Si un equipo propone incorporar un motor de base de datos fuera del catálogo oficial para gestionar el *ledger* de saldos, el dictamen inmediato es No conforme hasta que demuestre replicación síncrona, auditoría regulatoria y soporte empresarial; en cambio, si se plantea para un microservicio satélite de baja criticidad, puede tramitarse como una Excepción temporal respaldada por un ADR aprobado.


## 8.4 Integración con el desarrollo

Planeación del sprint: El arquitecto participa en el refinamiento para delimitar fronteras de dominio e integraciones.

Revisión de código: Auditoría ligera de conformidad arquitectónica sobre cambios críticos.

Pipeline CI/CD: Validación automatizada mediante análisis estático, escaneo de vulnerabilidades, pruebas de carga y verificación de contrato de API.

Definición de terminado (DoD): Ninguna historia se cierra sin código probado, documentación actualizada, ADR registrado y conformidad verificada.


## 8.5 Gobierno de la relación con Bancolombia


| Elemento de gobierno | Contenido contractual y operativo |
| --- | --- |
| Acuerdo de servicio (SLA) | Disponibilidad garantizada del canal de retiros, tiempos máximos de respuesta y ventanas coordinadas de mantenimiento |
| Seguridad de canal | Conexión cifrada con autenticación mutua (mTLS) y rotación periódica de credenciales |
| Continuidad operativa | Activación inmediata de rutas alternas por Puntored y PTM ante indisponibilidad de la red del banco |
| Gestión de cambios | Protocolo de aviso previo obligatorio y pruebas conjuntas antes de modificar interfaces |
| Revisión ejecutiva | Comité trimestral de seguimiento con tablero de indicadores y esquema de penalidades |


## 8.6 Artefactos clave de gobierno

Contrato de arquitectura vigente, evaluaciones de conformidad por entrega, catálogo actualizado de SBB, registro histórico de ADR y registro de excepciones con fechas de caducidad.


## 9. Fase H: gestión del cambio de la arquitectura

La arquitectura empresarial no termina cuando sale a producción; en la Fase H aseguramos que la plataforma de Nequi S.A. evolucione de manera ordenada frente a nuevas presiones regulatorias, de mercado o de crecimiento, evitando que la deuda técnica degrade la estabilidad alcanzada.


## 9.1 Motores de cambio a vigilar


| Motor de cambio | Señal de alerta | Origen |
| --- | --- | --- |
| Regulatorio | Nuevas circulares de la SFC, ajustes NIIF, exigencias de capital y liquidez | SFC y Fogafín |
| Negocio | Expansión agresiva de crédito (meta de COP 5 billones en desembolsos) [V], ahorro, inversión y divisas | Nequi |
| Accionista | Nuevas alternativas estratégicas de holding; Cibest indicó que no contempla una IPO a corto plazo [V] | Grupo Cibest |
| Tecnológico | Concentración en proveedores nube, actualizaciones mayores y obsolescencia | Operaciones |
| Operación | Recurrencia de incidentes durante picos de quincena o temporada decembrina | Operaciones |
| Mercado | Evolución del ecosistema Bre-B, nuevos competidores y redes de pago | Mercado |
| Terceros | Renegociación o cambios técnicos en el contrato con Bancolombia | Bancolombia |


## 9.2 Clasificación de los cambios


| Tipo de cambio | Ejemplo práctico | Tratamiento de gobierno |
| --- | --- | --- |
| Simplificación | Sustituir un proveedor de antifraude por otro equivalente | Ajuste en catálogo SBB y ADR; aprueba el arquitecto de dominio |
| Incremental | Lanzar un nuevo producto de ahorro sobre servicios existentes | Solicitud formal de cambio; revisa y aprueba la ARB |
| Rearquitectura | Migrar de proveedor de nube o rediseñar la topología multi-región | Inicia un nuevo ciclo completo del ADM desde la Fase A |

9.3 Proceso de gestión del cambio

1. Detectar: El requerimiento o evento ingresa desde operación, riesgos, negocio o el regulador.

2. Evaluar: Se analiza su impacto sobre los principios (P1–P8), el Contrato de Arquitectura y las metas de nivel de servicio.

3. Clasificar: Se tipifica como cambio de simplificación, incremental o rearquitectura.

4. Decidir: La ARB aprueba, rechaza o devuelve la iniciativa, documentando la resolución en un ADR.

5. Ejecutar: El cambio avanza bajo gobierno de las Fases G y H; si es rearquitectura, se reinicia el ciclo ADM.

6. Medir: Se actualizan los indicadores operativos y el repositorio de arquitectura.


## 9.4 Indicadores de seguimiento


| Indicador clave (KPI) | Meta objetivo | Frecuencia |
| --- | --- | --- |
| Disponibilidad mensual de plataforma | [D] | Mensual |
| Tasa de transacciones exitosas | [D] | Mensual |
| Tiempo de recuperación en incidentes graves (MTTR) | [D] | Por incidente |
| Incidentes con impacto masivo | 0 en quincenas y diciembre [P] | Por quincena |
| Conciliación diaria de saldos sin diferencias | 100 % [P] | Diaria |
| Excepciones de arquitectura abiertas | Tendencia sostenida a la baja [P] | Trimestral |
| Disponibilidad del canal de retiros de Bancolombia | Cumplimiento estricto según SLA [P] | Mensual |


## 9.5 Cuándo iniciar un nuevo ciclo del ADM

Cuando se decida cambiar de proveedor principal de nube o reemplazar el core bancario.

Cuando el regulador (SFC) emita una exigencia estructural que altere el modelo de capital o continuidad.

Cuando el accionista (Grupo Cibest) active una operación estratégica que transforme el perfil societario de Nequi.

Cuando tres incidentes operativos graves consecutivos apunten a una falla estructural de diseño.


## 10. Gestión de requerimientos

En el corazón del ciclo ADM reside la Gestión de Requerimientos, que asegura trazabilidad continua desde las metas de negocio y regulación hasta la operación diaria:


| ID | Requerimiento arquitectónico | Fase | Estado actual |
| --- | --- | --- | --- |
| R1 | Operar con licencia propia vigilada por la SFC | B | Cumplido [V] |
| R2 | Depósitos protegidos por el seguro de Fogafín | B | Cumplido [V] |
| R3 | Mantener retiros sin costo en cajeros y corresponsales | C | Cumplido [V] |
| R4 | Interoperar con Bre-B, PSE y demás entidades financieras | C | Cumplido [V] |
| R5 | Cero pérdida de datos en el corte de cesión | C | Sin reportes de pérdida [V] |
| R6 |  | D | No demostrado: hubo incidentes [V] |
| R7 | Arquitectura sin punto único de falla de nube | D | Por confirmar [P] |
| R8 | Reportería regulatoria y contabilidad NIIF propias | B/C | En curso [V] |
| R9 | Contrato formal con SLA con Bancolombia | G | Por confirmar [P] |
| R10 | Gobierno de arquitectura formal con ARB y ADR | Prel./G | Propuesto [P] |


## 11. Diferencias entre la planificación inicial y los datos públicos

Como ejercicio de rigor arquitectónico, consolidamos los diez puntos donde la ejecución real divulgada públicamente superó o modificó los supuestos de nuestra planificación inicial del proyecto:


| # | Tema | Planificación inicial [D] | Dato público verificado [V] | Recomendación arquitectónica |
| --- | --- | --- | --- | --- |
| 1 | Fecha del Día 1 | Abr-Dic 2027; independencia total en jun-2028 | 1 de septiembre de 2026 | Actualizar la línea de tiempo maestra tomando sep-2026 como corte real |
| 2 | Autorización de la SFC | Abril 2026 – Febrero 2027 | 31 de octubre de 2025 (Res. 2002) | Registrar como hito regulatorio cumplido |
| 3 | Capital inicial | COP 500.000 millones | 500.000 millones anunciados en marzo; 600.000 millones asignados | Adoptar COP 600.000 millones como base financiera |
| 4 | Caída por migración a nube | Diciembre de 2024 | Caídas reportadas el 24-oct-2025 y entre nov y dic de 2025 | Corregir la cronología histórica de incidentes |
| 5 | Custodia de saldos | Transición con saldos en el banco hasta jun-2027 | Depósitos cedidos a Nequi el 1 de septiembre de 2026 | Reemplazar la arquitectura de transición de saldos |
| 6 | Retiro de servicios del banco | Desconexión total como meta final | Bancolombia sigue prestando cajeros y corresponsales | Reformular como integración permanente gobernada por SLA |
| 7 | Relación con Wompi | Tratado como aliado externo | Es filial corporativa de Grupo Cibest | Ajustar el modelo contractual y de gobierno intercompañía |
| 8 | Estrategia de nube | AWS como nube única | Google, Microsoft y AWS según declaración del CEO | Auditar y confirmar la topología multinube productiva |
| 9 | TRM de referencia | COP 3.175 | COP 3.312,84 (1 de octubre de 2026) | Actualizar indicadores financieros a la TRM vigente |
| 10 | Cifras de costos y herramientas | Proyectadas como línea base | No divulgadas públicamente por Nequi | Mantener explícitamente como estimaciones de diseño [D] |


## 12. Fuentes

Documentos primarios y regulatorios

Grupo Cibest, Formulario 6-K (31-jul-2026): Anuncio oficial de la fecha de inicio de operaciones de Nequi S.A. https://www.sec.gov/Archives/edgar/data/0002058897/000205889726000263/grupocibestsaannouncesthed.htm

Grupo Cibest, Formulario 6-K (9-nov-2026, resultados del 3T26): Confirmación de la cesión del 1-sep-2026 y métricas de cuentas de Nequi. https://www.sec.gov/Archives/edgar/data/0002058897/000205889726000335/grupocibestsa6-kpr3q26.htm

Nequi, Centro de Ayuda Oficial: Nequi S.A. Compañía de Financiamiento. https://ayuda.nequi.com.co/hc/es/articles/47777570492557-Nequi-S-A-Compa%C3%B1%C3%ADa-de-Financiamiento-lo-que-necesitas-saber

Semana: Resolución 2002 del 31-oct-2025. https://www.semana.com/economia/banca-y-bolsa/articulo/oficial-nequi-se-separa-de-bancolombia-ya-hay-fecha-definitiva-cuales-seran-los-principales-detalles/202618/

Transcripción de la llamada de resultados 3T26 de Grupo Cibest: Capital de COP 600.000 millones, solvencia del 13 % y aporte del 2 % a la utilidad. https://finance.yahoo.com/markets/stocks/articles/grupo-cibest-cib-q3-2026-224950300.html

TipRanks: Resumen ejecutivo de la llamada 3T26 (depósitos de COP 6,9 billones, margen y provisiones). https://www.tipranks.com/news/company-announcements/grupo-cibest-earnings-call-signals-stronger-growth-ahead

La República: Cartera de crédito de COP 2,469 billones en el 3T26. https://www.larepublica.co/finanzas/el-grupo-cibest-ajusta-sus-proyecciones-para-2027-impulsado-por-el-motor-de-nequi-4521320

El Espectador: Capitalización anunciada en marzo de 2026. https://www.elespectador.com/economia/empresas/nequi-sera-compania-de-financiamiento-independiente-desde-septiembre/

Infobae (31-ago-2026): Áreas propias, habilitación como Intermediario del Mercado Cambiario y continuidad sin trámites para usuarios. https://www.infobae.com/colombia/2026/08/31/nequi-dejara-de-ser-una-billetera-virtual-desde-el-1-de-septiembre-esto-pasara-con-los-29-millones-de-usuarios-tras-la-migracion-a-neobanco/

Valora Analitik: Entrevista al CEO de Nequi (operación 100 % en la nube; aliados AWS, Infosys y Pragma). https://www.valoraanalitik.com/?p=609252

Infobae y Portafolio: Migración del core bancario a la nube (proyecto de 18 meses; Google, Microsoft y AWS; capacidad de 80 millones de transacciones diarias). https://www.infobae.com/colombia/2025/11/21/nequi-refuerza-su-infraestructura-tecnologica-para-evitar-nuevas-caidas-de-su-plataforma/ y https://www.portafolio.co/economia/finanzas/caida-de-nequi-en-plena-temporada-decembrina-genera-inquietud-entre-usuarios-mientras-avanza-migracion-a-la-nube-484078

El Colombiano: Caída del 24-oct-2025 de Bancolombia y Nequi. https://www.elcolombiano.com/negocios/por-que-se-cayo-bancolombia-II30293759

La República: Caídas de fin de noviembre y diciembre de 2025 y del 3-feb-2026. https://www.larepublica.co/finanzas/las-razones-detras-de-las-caidas-en-los-servicios-de-nequi-4283299 y https://www.larepublica.co/finanzas/caida-generalizada-de-nequi-impacta-pagos-transferencias-y-retiros-de-los-usuarios-4318527

Semana: Incidentes operativos del 17-sep y 27-oct-2026. https://www.semana.com/tecnologia/articulo/reportan-caida-de-nequi-este-martes-27-de-octubre-estos-son-los-servicios-afectados/202640/

Noticias RCN: Puntos de retiro y ventana de cambio del 1 de septiembre. https://www.noticiasrcn.com/economia/nequi-separacion-bancolombia-1046294 y https://www.noticiasrcn.com/economia/nequi-separacion-bancolombia-como-sacar-dinero-1056387

La FM: Suspensión programada de servicios entre el 31-ago y el 1-sep-2026. https://www.lafm.com.co/economia/nequi-dejara-de-funcionar-fechas-horarios-agosto-septiembre-408854

El Colombiano: Punto de equilibrio y utilidades de Cibest (3T25). https://www.elcolombiano.com/negocios/nequi-independiza-bancolombia-opera-compania-financiamiento-colombia-AC30672266


## Nota de Validación Técnica Pendiente con Nequi

Permanecen sujetos a verificación directa con los equipos internos de Nequi S.A.: el detalle presupuestal de implementación y operación [D], las herramientas específicas de ciberseguridad y observabilidad [D], la topología exacta de distribución multinube, las cláusulas técnicas del contrato de servicios con Bancolombia [P] y la validación jurídica de aplicabilidad normativa (Circulares Externas 007 de 2018 y 005 de 2019 de la SFC; Leyes 1581 de 2012 y 1266 de 2008).
