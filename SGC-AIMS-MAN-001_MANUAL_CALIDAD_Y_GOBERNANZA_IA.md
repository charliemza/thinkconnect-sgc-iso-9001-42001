# MANUAL INTEGRADO DE CALIDAD Y GOBERNANZA DE IA
**Organización:** ThinkConnect IA (`www.thinkconnect.com.ar`)  
**Código Documental:** `SGC-AIMS-MAN-001` | **Versión:** `1.0` | **Vigencia:** `15/10/2026` | **Estado:** `APROBADO Y VIGENTE`  
**Normas de Referencia:** ISO 9001:2015 • ISO/IEC 42001:2023 • ISO/IEC 29110 • NIST AI RMF 1.0

---

## 1. OBJETO Y ALCANCE DEL SISTEMA INTEGRADO (ISO 9001 Cl. 4.3 / ISO 42001 Cl. 4.3)

El presente Manual establece la arquitectura, políticas y controles del Sistema Integrado de Gestión de Calidad y Gobernanza de Inteligencia Artificial (SGC-AIMS) de ThinkConnect IA, con sede operativa en Godoy Cruz, Provincia de Mendoza, República Argentina.

ALCANCE CERTIFICABLE DECLARADO:

• «Diseño, desarrollo, implementación, operación y soporte técnico de software a medida, plataformas SaaS, integraciones con servicios web fiscales/gubernamentales (ARCA/ATM), infraestructura DePIN/GovTech y sistemas multi-agente autónomos basados en Inteligencia Artificial.»

Este Sistema integra en un cuerpo normativo único los requisitos de:

• ISO 9001:2015 (Sistemas de Gestión de la Calidad — Requisitos).

• ISO/IEC 42001:2023 (Tecnología de la Información — Inteligencia Artificial — Sistema de Gestión AIMS).

• ISO/IEC 29110-4-1 (Ingeniería de Sistemas y Software — Perfiles de Ciclo de Vida para PyMEs).

• NIST AI Risk Management Framework (AI RMF 1.0 & Generative AI Profile NIST AI 600-1).

## 2. POLÍTICA INTEGRADA DE CALIDAD Y ÉTICA EN INTELIGENCIA ARTIFICIAL (Cl. 5.2)

La Dirección de ThinkConnect IA establece como compromisos innegociables de su operatoria tecnológica:

• Determinismo y Cero Alucinación Transaccional: Ningún modelo fundacional (LLM) tiene permiso de escritura libre sobre bases de datos relacionales o sistemas fiscales. Toda mutación de estado se ejecuta mediante contratos de herramientas tipados (Function Calling), validaciones de esquema y registros de auditoría inmutables (SQLite WAL / PostgreSQL / BigQuery).

• Supervisión Humana Efectiva (Human-in-the-Loop - HITL): Las decisiones críticas de índole fiscal, contable, patrimonial o de infraestructura cuentan con verificación criptográfica externa (CAE ARCA, hashes SHA-256) o confirmación del operador autorizado.

• Privacidad, Soberanía de Datos y Seguridad por Diseño: Separación estricta de entornos, ejecución de modelos locales cuando la confidencialidad lo requiere (Server_IA con Ollama/OpenVINO) y resguardo automatizado e inmutable de copias de seguridad mediante Veeam.

• Mejora Continua y Cumplimiento Normativo: Cumplimiento estricto de la Ley 25.326 de Protección de Datos Personales, normativas técnicas de ARCA (ex AFIP), estándares de accesibilidad W3C WCAG 2.2 AA y lineamientos de la Ley 27.506 de Régimen de Promoción de la Economía del Conocimiento.

## 3. ARQUITECTURA DE GOBERNANZA DE IA: LA MÁQUINA DE 4 PISOS (ISO 42001 Anexo A)

Para garantizar la trazabilidad, explicabilidad y ausencia de deriva semántica en sistemas agénticos, ThinkConnect IA implementa de forma obligatoria la arquitectura de memoria y estado de 4 niveles (The Archive / Google ADK Architecture):

| Nivel / Piso | Ámbito Técnico | Regla de Gobernanza ISO/IEC 42001 | Mecanismo de Control y Auditoría |
| --- | --- | --- | --- |
| Piso 1: Estado de Sesión | session.state (Volátil) | Controlado exclusivamente por código Python determinístico; prohibida la alteración por texto libre del LLM. | Validación de tipos en tiempo de ejecución y sanitización de entradas. |
| Piso 2: Identidad y Reglas | user:state (Persistente) | Almacena reglas de negocio inmutables, firmas institucionales y políticas de seguridad del cliente. | Bloqueo de alcance (Strict Scope Lock) y control de versiones en Git. |
| Piso 3: Memoria Semántica | Vertex AI Memory Bank / Chronicle | Destilación curada de lecciones aprendidas y contexto técnico; separación estricta respecto de hechos contables. | Revisión asíncrona y trazabilidad de fuentes documentales (RAG Grounding). |
| Piso 4: Hechos Duros (ACID) | SQLite WAL / PostgreSQL / BigQuery | Única fuente de verdad para comprobantes fiscales, cuentas corrientes, remitos y series de hardware. | Integridad referencial ACID, recibos criptográficos CAE y backups Veeam en Server_IA. |

## 4. OBJETIVOS DE CALIDAD E INDICADORES CLAVE (KPIs 2026-2027)

La Dirección monitorea trimestralmente el desempeño del SGC-AIMS a través de métricas cuantitativas verificables:

| Indicador (KPI) | Fórmula / Métrica de Medición | Meta Objetiva | Frecuencia |
| --- | --- | --- | --- |
| Exactitud en Emisión Electrónica e Integraciones | (Transacciones exitosas validadas con CAE o API / Total emitidas) x 100 | 100,0% | Mensual |
| Tasa de Éxito de Backups en Infraestructura (Server_IA) | (Ejecuciones Veeam exitosas sin error / Total programadas) x 100 | >= 99,5% | Semanal |
| Cumplimiento de SLA en Soporte IT Corporativo | Tickets resueltos dentro de la ventana acordada (Remoto / En Sitio) | >= 98,0% | Quincenal |
| Incidencia de Fugas o Escrituras No Autorizadas por IA | Eventos de corrupción de datos o violación de frontera Piso 3 -> Piso 4 | 0 Eventos | Continuo |
| Satisfacción del Cliente y Conformidad de Entregas | Entregas de software/sistemas aprobadas sin rechazo crítico en producción | >= 95,0% | Trimestral |


---
**Aprobado por:**  
Saludos cordiales,  
Carlos Ferro  
ThinkConnect IA — www.thinkconnect.com.ar  
carlos@thinkconnect.com.ar | Tel: 261 418-6751
