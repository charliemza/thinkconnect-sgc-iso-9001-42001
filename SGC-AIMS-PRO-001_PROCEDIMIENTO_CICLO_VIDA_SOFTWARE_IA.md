# PROCEDIMIENTO DE INGENIERÍA DE SOFTWARE Y AGENTES IA
**Organización:** ThinkConnect IA (`www.thinkconnect.com.ar`)  
**Código Documental:** `SGC-AIMS-PRO-001` | **Versión:** `1.0` | **Vigencia:** `15/10/2026` | **Estado:** `APROBADO Y VIGENTE`  
**Normas de Referencia:** ISO 9001:2015 • ISO/IEC 42001:2023 • ISO/IEC 29110 • NIST AI RMF 1.0

---

## 1. PROPÓSITO Y ESTÁNDAR DE REFERENCIA (ISO/IEC 29110 + ISO/IEC 5338)

Establecer el procedimiento estandarizado para la gestión de proyectos (PM) y la ingeniería de software y sistemas de Inteligencia Artificial (SI) en ThinkConnect IA, asegurando que todo producto o servicio cumpla con los requisitos funcionales, de seguridad, accesibilidad y gobernanza algorítmica antes de su puesta en producción.

## 2. FASES DEL CICLO DE VIDA DE INGENIERÍA (6 ETAPAS OBLIGATORIAS)

Todo desarrollo nuevo, módulo SaaS, automatización fiscal o agente autónomo atraviesa las siguientes 6 fases con sus respectivos registros de evidencia:

| Fase | Actividades Obligatorias | Controles Técnicos Aplicados | Evidencia / Entregable Registrado |
| --- | --- | --- | --- |
| F1. Relevamiento y Especificación | Análisis de requerimientos del cliente, alcance funcional, normativa aplicable (ARCA, Ley 25.326, pliegos) y evaluación preliminar de riesgo IA. | Candado de Alcance Estricto (Strict Scope Lock) y definición de criterios de aceptación. | Propuesta Técnica / Presupuesto Oficial / Especificación en PROJECT.md. |
| F2. Diseño y Arquitectura | Diseño de base de datos relacional (Piso 4), contratos de API/WebMCP, selección de modelos IA y diseño de interfaz (UX/UI). | Separación de datos transaccionales vs. contexto LLM; diseño con Cambio Mínimo (Minimal Diff). | Diagramas de arquitectura, esquemas SQL y configuración de entorno. |
| F3. Construcción y Codificación | Desarrollo en entorno controlado (Python Z:\.venv, FastAPI, Node.js, Flutter), integración de SDKs oficiales y sanitización de entradas. | Control de versiones en Git, prohibición de credenciales expuestas (.env protegidos) y tipado estricto. | Commits en repositorio Git y scripts modulares documentados. |
| F4. Verificación, QA y Auditoría Web/IA | Pruebas unitarias, validación de esquemas JSON, pruebas de regresión visual y auditoría de seguridad/accesibilidad (audit360 / OWASP / WCAG 2.2). | Pruebas de estrés contra alucinaciones, validación matemática determinística y verificación de cabeceras HTTP. | Reporte de QA, capturas de validación y logs de prueba exitosa. |
| F5. Despliegue y Documentación Espejo | Puesta en producción (VPS Linux vía systemd/Docker o Server_IA local) y actualización simultánea de la documentación técnica. | Sincronización obligatoria en espejo entre Z:\Proyectos\<Proyecto> y Z:\Documentacion\<Proyecto>. | Acta/Notificación de puesta en marcha y README/PROJECT.md actualizados. |
| F6. Operación, Monitoreo y Backup | Monitoreo de salud de contenedores, rotación de logs, atención de soporte y resguardo automatizado en almacenamiento dedicado. | Backups centralizados en \\Server_ia\e y verificación periódica de tareas programadas y Veeam. | Planillas de liquidación/soporte y registros de backup verificado. |

## 3. GESTIÓN DE CAMBIOS EN PRODUCCIÓN Y ROLLBACK

• Regla del Cambio Mínimo (Minimal Diff Rule): Toda modificación sobre sistemas productivos se limita estrictamente al componente afectado, prohibiéndose alteraciones colaterales en DNS, proxy inverso Nginx o esquemas de base de datos no solicitados.

• Respaldo Pre-Cambio: Antes de aplicar migraciones de esquema o actualizaciones críticas en bases SQLite/PostgreSQL, se genera una instantánea verificada para garantizar retorno inmediato (Rollback < 5 minutos) ante cualquier anomalía.


---
**Aprobado por:**  
Saludos cordiales,  
Carlos Ferro  
ThinkConnect IA — www.thinkconnect.com.ar  
carlos@thinkconnect.com.ar | Tel: 261 418-6751
