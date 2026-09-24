# Checklist de Cumplimiento Normativo — GobData

## 1. Introducción

GobData es una plataforma estatal de trámites ciudadanos que gestiona información relacionada con identidad, salud, impuestos y derechos civiles. Debido a la naturaleza de la información procesada, el sistema maneja datos personales y datos sensibles que requieren controles específicos de privacidad, seguridad y trazabilidad.

El presente análisis busca evaluar el nivel de cumplimiento normativo de GobData, identificar las principales brechas y establecer recomendaciones priorizadas para reducir los riesgos asociados al tratamiento de información.

---

## 2. Marcos normativos de referencia

| Marco / Norma | Qué exige | Aplicación en GobData |
|---|---|---|
| Ley 1581 de 2012 — Habeas Data | Consentimiento informado, finalidad del tratamiento y protección de los derechos de los titulares de los datos. | Aplica porque GobData procesa datos personales de ciudadanos colombianos. |
| ISO/IEC 27001 | Gestión de seguridad de la información, controles de acceso, gestión de incidentes y continuidad. | Aplica porque GobData almacena y procesa información que requiere protección sistemática. |
| Protección contra fugas de datos | Cifrado, monitoreo y respuesta frente a exposición o pérdida de información. | Aplica porque el sistema almacena y transmite información sensible. |
| Consentimiento, auditoría y roles de acceso | Registro y control de quién accede a la información y bajo qué autorización. | Aplica porque el sistema maneja diferentes usuarios y niveles de acceso. |

---

## 3. Datos y procesos sensibles identificados

| Dato / Proceso | Sensibilidad | Normativa aplicable |
|---|---|---|
| Número de identificación (cédula) | Dato personal | Ley 1581 de 2012 |
| Historial clínico | Dato sensible de salud | Ley 1581 de 2012 |
| Dirección de residencia | Dato personal | Ley 1581 de 2012 |
| Certificados digitales | Dato de identidad / autenticación | ISO/IEC 27001 |
| Trámites y peticiones ciudadanas | Trazabilidad de gestión pública | ISO/IEC 27001 |

---

## 4. Metodología

La evaluación de cumplimiento se desarrolló mediante cinco pasos:

1. Identificación de datos y procesos sensibles.
2. Construcción del checklist de requisitos.
3. Evaluación de cada requisito como `Cumple` o `Parcial`.
4. Identificación y análisis de las brechas asociadas a los controles parciales.
5. Priorización de las brechas y definición de recomendaciones correctivas.

Cada evaluación debe estar respaldada por una evidencia o justificación concreta.

---

## 5. Checklist General

| N° | Categoría | Criterio de Cumplimiento | Nivel | Evidencia / Justificación | Recomendación |
|---:|---|---|---|---|---|
| 1 | Consentimiento | Se solicita consentimiento informado al ciudadano antes del tratamiento de datos. | Cumple | Casilla de aceptación de términos en el registro de usuario. | Detallar fines específicos del tratamiento. |
| 2 | Consentimiento | Mecanismo para revocar el consentimiento disponible. | Parcial | Solo mediante solicitud escrita. | Implementar botón o formulario en línea. |
| 3 | Seguridad (ISO 27001) | Existe política formal de seguridad. | Cumple | Política de TI estatal basada en ISO/IEC 27001. | Mantenerla actualizada conforme a la versión vigente. |
| 4 | Seguridad (ISO 27001) | Cifrado de datos en tránsito y reposo. | Cumple | HTTPS/TLS y cifrado de campos sensibles. | Revisar certificados y algoritmos periódicamente. |
| 5 | Seguridad (ISO 27001) | Plan de continuidad y recuperación. | Parcial | Respaldos diarios sin un plan BCP/DRP formal. | Diseñar, documentar, probar e implementar un plan de continuidad. |
| 6 | Protección de Datos | Se cuenta con un Oficial de Protección de Datos (DPO). | Cumple | Existe un funcionario encargado de las funciones de protección de datos. | Reforzar su participación en auditorías y reportes. |
| 7 | Protección de Datos | Logs de acceso a información personal. | Cumple | El sistema registra y permite auditar consultas a información personal. | Revisar integridad y retención de logs. |
| 8 | Prevención de Fugas | Se controlan exportaciones manuales. | Parcial | No existen controles DLP específicos. | Implementar políticas y herramientas DLP. |
| 9 | Retención | Política formal de retención de datos. | Cumple | Existen políticas de conservación de información. | Automatizar procesos de eliminación. |
| 10 | Retención | Datos sensibles se anonimizarán cuando dejen de ser necesarios. | Parcial | No existe proceso automatizado de anonimización o eliminación. | Implementar política y mecanismos de anonimización. |
| 11 | Roles y Responsabilidades | Roles y permisos documentados. | Cumple | El modelo de seguridad establece diferentes roles y responsabilidades. | Revisar y actualizar periódicamente los permisos. |
| 12 | Roles y Responsabilidades | Formación del personal en protección de datos. | Parcial | Existe capacitación, pero no evaluación de su efectividad. | Aplicar evaluaciones posteriores a las capacitaciones. |

---

## 6. Brechas Identificadas

Los controles evaluados como `Parcial` generan las siguientes brechas:

| Categoría | Brecha | Riesgo | Recomendación Prioritaria | Prioridad |
|---|---|---|---|---|
| Consentimiento | No existe mecanismo automático de revocatoria. | Medio | Crear funcionalidad de eliminación y revocatoria digital. | Alta |
| Seguridad | No hay plan formal de continuidad (BCP/DRP). | Alto | Diseñar, probar e implementar un plan de continuidad. | Alta |
| Prevención de Fugas | Exportación manual no controlada. | Alto | Implementar DLP para controlar descargas y exportaciones. | Alta |
| Retención | No existe eliminación automatizada. | Medio | Configurar reglas de caducidad y anonimización en base de datos. | Media |
| Formación | No existe evaluación de efectividad de las capacitaciones. | Bajo | Aplicar pruebas posteriores a las capacitaciones. | Media |

---

## 7. Priorización

Las principales brechas que requieren atención son las relacionadas con:

- continuidad y recuperación del servicio;
- prevención de fugas de información;
- gestión de la revocatoria del consentimiento.

Las brechas relacionadas con continuidad y prevención de fugas presentan un riesgo alto debido al impacto que podría tener una interrupción del servicio o una exposición no autorizada de información sensible.

También se considera prioritaria la implementación de mecanismos digitales para gestionar la revocatoria del consentimiento de los ciudadanos.

---

## 8. Conclusiones

El análisis muestra que GobData cuenta con diversos controles orientados a la protección de datos y seguridad de la información. Sin embargo, todavía existen controles implementados parcialmente que requieren acciones de mejora.

Las principales oportunidades de fortalecimiento se concentran en la continuidad del servicio, prevención de fugas de información, revocatoria digital del consentimiento, anonimización de datos y evaluación de las capacitaciones del personal.

La implementación de las recomendaciones propuestas permitiría disminuir los riesgos identificados y fortalecer el cumplimiento de los requisitos asociados a protección de datos y seguridad de la información.

---

## 9. Fuentes

- Ley 1581 de 2012 — Régimen General de Protección de Datos Personales en Colombia.
- Decreto 1377 de 2013 — Reglamentación parcial de la Ley 1581 de 2012.
- Superintendencia de Industria y Comercio — Protección de Datos Personales.
- ISO/IEC 27001 — Sistemas de Gestión de Seguridad de la Información.
- Guía Paso a Paso — Taller 6 de Checklist de Cumplimiento Normativo.
