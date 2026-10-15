# FICHAS DE TRANSPARENCIA ALGORÍTMICA (AI SYSTEM CARDS)
**Organización:** ThinkConnect IA (`www.thinkconnect.com.ar`)  
**Código Documental:** `SGC-AIMS-FIC-001` | **Versión:** `1.0` | **Vigencia:** `15/10/2026` | **Estado:** `APROBADO Y VIGENTE`  
**Normas de Referencia:** ISO 9001:2015 • ISO/IEC 42001:2023 • ISO/IEC 29110 • NIST AI RMF 1.0

---

## 1. REGISTRO OFICIAL DE SISTEMAS DE IA EN PRODUCCIÓN (ISO/IEC 42001 Cl. 6.1.3 / NIST MAP)

En cumplimiento de los requisitos de transparencia, inventario de activos algorítmicos y evaluación de impacto del sistema (AI System Impact Assessment), se documentan las Fichas Técnicas (AI System Cards) de las plataformas operativas de ThinkConnect IA:

| ID Sistema | Nombre de la Solución | Modelos / Motor IA | Nivel de Riesgo (UE AI Act / NIST) | Barreras de Seguridad y Control Humano (Guardrails) |
| --- | --- | --- | --- | --- |
| AI-SYS-01 | ThinkConnect Core Agentic Workspace (Arquitectura 4 Pisos) | Gemini 2.5 Pro/Flash + Google ADK + Vertex AI Memory Bank + Ollama Local (Server_IA) | Limitado / Controlado | Ejecución confinada a entorno virtual único; separación en 4 pisos; prohibición de SQL libre desde LLM; logs JSONL completos de cada paso y herramienta invocada. |
| AI-SYS-02 | EstudioConta Pro & Asistente Contable ARCA/ATM (Proyecto 5) | Gemini 2.5 + Motor Determinístico Python de Liquidación Tributaria (F.2051 / F.5111) | Alto (Dominio Fiscal/Contable) -> Mitigado a Bajo | El cálculo impositivo (IVA, IIBB, Ganancias) es 100% ejecutado por algoritmos determinísticos en Python/Excel; la IA asiste en clasificación, doctrina y generación de reportes bajo revisión profesional. |
| AI-SYS-03 | UrbanAgent OS & EcoCívica / TerraVolt DePIN (Proyecto 16) | Agentes Multimodales + Visión Computacional Edge + Oráculos IoT/Blockchain | Limitado (Infraestructura Cívica Smart City) | Validación cruzada por telemetría física (básculas IoT, sensores, GPS), trazabilidad criptográfica de activos RWA y panel de supervisión municipal en tiempo real. |
| AI-SYS-04 | Sistema de Gestión, Cotización y Facturación Electrónica (Proyectos 4 y 17) | Motor WSAA/WSFEv1 ARCA + SQLite WAL + Asistente de Cotización Multiproveedor | Moderado (Transaccional Comercial) | Fórmula comercial determinística inmutable (Costo / 0.70), validación de CUIT contra padrón oficial y emisión con Código de Autorización Electrónico (CAE) oficial de ARCA. |

## 2. POLÍTICA DE PROTECCIÓN DE DATOS Y ANTI-CONTAMINACIÓN DE CONTEXTO

• Aislamiento Multi-Cliente: Los datos fiscales, contables y comerciales de cada cliente (Hormimac, clientes de facturación, etc.) residen en estructuras aisladas y jamás se utilizan para entrenar modelos públicos de terceros.

• Sanitización contra Prompt Injection: Todo contenido externo (correos entrantes, sitios web auditados, respuestas de APIs de terceros) es tratado como dato no confiable (Untrusted Input) y procesado mediante parsers estructurados antes de interactuar con herramientas del sistema.


---
**Aprobado por:**  
Saludos cordiales,  
Carlos Ferro  
ThinkConnect IA — www.thinkconnect.com.ar  
carlos@thinkconnect.com.ar | Tel: 261 418-6751
