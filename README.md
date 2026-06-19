# GlampSpace-mejorado
# ⛺ GlampSpace V2 - Optimización UX, Evaluación Heurística y Accesibilidad (WCAG 2.1)

[![UX/UI Compliance](https://img.shields.io/badge/UX%2FUI-Nielsen%20Heuristics-brightgreen)](#-evaluación-heurística-nielsen)
[![Accessibility AA](https://img.shields.io/badge/Accessibility-WCAG%202.1%20AA-blue)](#-auditoría-de-accesibilidad-wcag-21-aa)
[![Academic Status](https://img.shields.io/badge/Universidad-ECOTEC-darkblue)](https://ecotec.edu.ec/)

Este repositorio contiene la arquitectura de información, el código frontend y la documentación técnica del rediseño interactivo de **GlampSpace**, un marketplace especializado en el alquiler de campamentos de lujo y eco-lodges boutique[cite: 4]. El objetivo principal de este proyecto fue auditar el MVP Alpha para identificar fricciones críticas en el embudo transaccional y proponer una interfaz optimizada libre de barreras cognitivas y motrices[cite: 4].

## 📋 Tabla de Contenidos
* [Contexto y Diagnóstico](#-contexto-y-diagnóstico)
* [Evaluación Heurística (Nielsen)](#-evaluación-heurística-nielsen)
* [Propuesta de Rediseño: Antes vs. Después](#-propuesta-de-rediseño-antes-vs-después)
* [Justificación Técnica (Leyes de UX)](#-justificación-técnica-leyes-de-ux)
* [Auditoría de Accesibilidad (WCAG 2.1 AA)](#-auditoría-de-accesibilidad-wcag-21-aa)
* [Tablero de Control y Métricas de Impacto](#-tablero-de-control-y-métricas-de-impacto)

---

## 🔍 Contexto y Diagnóstico

El análisis de comportamiento digital inicial del MVP arrojó un abandono masivo de usuarios en las últimas fases del checkout[cite: 4]. A pesar de captar tráfico cualificado interesado en la propuesta de valor de turismo premium, la arquitectura de navegación obligaba al usuario a interactuar con múltiples interfaces redundantes antes de poder procesar una transacción económica[cite: 4]. 

Este estudio unifica el rigor del análisis heurístico tradicional y las directrices internacionales de accesibilidad para transformar deficiencias de diseño en ventajas competitivas cuantificables[cite: 4].

---

## 🛠️ Evaluación Heurística (Nielsen)

Se realizó un mapeo técnico de las fricciones interactivas utilizando las **10 Heurísticas de Usabilidad de Jakob Nielsen**[cite: 4]. La gravedad se cuantificó bajo la escala estandarizada de severidad (0: No es un problema, 4: Catástrofe de usabilidad)[cite: 4]:

| Heurística de Nielsen | Hallazgo Técnico y Fricción Detectada | Estado | Severidad |
| :--- | :--- | :---: | :---: |
| **1. Visibilidad del estado** | Al presionar "Confirmar Reserva", la interfaz no muestra un indicador de carga (*spinner*), induciendo a múltiples clics erróneos[cite: 4]. | Vulnerado | 2 (Menor) |
| **2. Relación sistema-mundo real** | El desglose utiliza nomenclatura técnica interna como `"ID_TAX_MUNICIPAL"` en lugar de `"Impuestos Locales"`[cite: 4]. | Vulnerado | 1 (Cosmético) |
| **3. Control y libertad** | El usuario no posee un botón explícito para retroceder de pantalla sin cancelar por completo la sesión transaccional[cite: 4]. | Vulnerado | 3 (Mayor) |
| **4. Consistencia y estándares** | Los botones de llamada a la acción (CTA) alteran su estilo visual, color y bordes de forma aleatoria entre pantallas móviles[cite: 4]. | Vulnerado | 1 (Cosmético) |
| **5. Prevención de errores** | El calendario de selección permite marcar de forma retroactiva fechas pasadas, gatillando un colapso del sistema al pagar[cite: 4]. | Vulnerado | 3 (Mayor) |
| **6. Reconocer antes que recordar** | Al avanzar al pago, el sistema oculta el precio por noche original, obligando al usuario a memorizarlo o abortar el flujo[cite: 4]. | Vulnerado | 2 (Menor) |
| **7. Flexibilidad y eficiencia** | **Falta absoluta de Guest Checkout.** Se obliga a registrar una cuenta con 15 campos obligatorios a usuarios nuevos[cite: 4]. | Vulnerado | 4 (Catástrofe) |
| **8. Estética y minimalismo** | La pantalla contiene banners promocionales masivos y textos legales extensos que sepultan el botón de pago[cite: 4]. | Vulnerado | 2 (Menor) |
| **9. Ayuda ante errores** | Cuando una tarjeta es rechazada, el sistema emite el mensaje genérico: `"Error de sistema HTTP 500"`[cite: 4]. | Vulnerado | 3 (Mayor) |
| **10. Ayuda y documentación** | No existe un centro de ayuda contextual ni preguntas frecuentes integradas durante la carga de datos bancarios[cite: 4]. | Vulnerado | 2 (Menor) |

---

## 📐 Propuesta de Rediseño: Antes vs. Después

Se procedió a re-arquitecturar el ecosistema de interacción transaccional eliminando los cuellos de botella mediante una reingeniería completa de flujos[cite: 4]:

* **Flujo Original (Antes - 6 Pantallas):** `Detalle de Habitación` ➔ `Creación Obligatoria de Cuenta` ➔ `Confirmación de Correo` ➔ `Datos Demográficos del Huésped` ➔ `Selección y Carga de Datos de Pago` ➔ `Confirmación de Términos Generales`[cite: 4]. Las analíticas evidenciaron un **abandono masivo en las pantallas 2 y 4** debido a la redundancia de los campos[cite: 4].
* **Flujo Optimizado (Después - 3 Pasos Críticos):** 
  1. **Paso 1:** Resumen de Reserva & Selección de Fechas (con bloqueo automático de días pasados e indicador visual de carga)[cite: 4].
  2. **Paso 2:** Formulario de Pago Simplificado con Opción de Compra como Invitado (*Guest Checkout*)[cite: 4].
  3. **Paso 3:** Pantalla de Éxito con Generación Automática de Credenciales Temporales para accesos futuros[cite: 4].

> 💡 *Nota: El mapa de flujo interactivo detallado con las zonas críticas de fricción cognitiva se encuentra documentado en el archivo `watermarked_img_3492769377484637118.png` adjunto en la raíz del repositorio.*

---

## 🧠 Justificación Técnica (Leyes de UX)

La toma de decisiones de diseño para el nuevo flujo se fundamentó científicamente en tres pilares de la psicología cognitiva[cite: 4]:

1. **Ley de Hick:** Al eliminar los 15 campos redundantes del registro tradicional e introducir la opción de pago como invitado, se redujo drásticamente el tiempo de procesamiento mental del usuario, mitigando la parálisis por análisis[cite: 4].
2. **Ley de Fitts:** En la interfaz móvil, los botones de confirmación principal (CTA) fueron expandidos en un **35% de su tamaño relativo** y relocalizados estratégicamente en la zona inferior de la pantalla (**área ergonómica del pulgar**), minimizando el esfuerzo motor necesario[cite: 4].
3. **Psicología de la Gestalt (Ley de Proximidad):** El rediseño agrupó visualmente mediante tarjetas contenedoras los datos de identidad (nombre y correo) de forma aislada a los datos de la tarjeta bancaria, agilizando la lectura visual predictiva del formulario[cite: 4].

---

## ♿ Auditoría de Accesibilidad (WCAG 2.1 AA)

Para garantizar una inclusión democrática, el rediseño subsanó deficiencias estructurales de accesibilidad bajo el estándar internacional **WCAG 2.1 Nivel AA**[cite: 4]:

* **Contraste de Color (Ratio 4.5:1):** El botón crítico original presentaba tipografía gris claro sobre fondo blanco (ratio deficiente de 2.1:1)[cite: 4]. Se ajustó la paleta cromática a **Azul Oscuro (#003366)** e Inclusión de **Verde Bosque (#1B3A24)**, superando un ratio de contraste de 5.1:1[cite: 4].
* **Legibilidad (Tamaño de Fuente):** Las cláusulas inferiores empleaban tipografías micro-textuales de 10px[cite: 4]. Se estandarizó la fuente base del sistema de checkout a **16px** para asegurar lectura universal[cite: 4].
* **Navegación por Teclado:** Al usar tabuladores no existía indicador del foco interactivo[cite: 4]. Se implementó un anillo de enfoque perimetral (**Focus Ring**) de alto contraste cromático azul brillante activo[cite: 4].
* **Etiquetas Alt (Imágenes):** Las fotografías de los glampings carecían de descripciones embebidas[cite: 4]. Se insertaron atributos HTML `alt` dinámicos y descriptivos *(ej: "Domo geodésico de lujo con jacuzzi exterior vista a la montaña")*[cite: 4].

---

## 📊 Tablero de Control y Métricas de Impacto

La efectividad del rediseño interactivo frente a las hipótesis comerciales se valida mediante el contraste empírico de indicadores de rendimiento clave (KPIs)[cite: 4]:

* **📈 Tasa de Éxito de la Tarea (Task Success Rate - TSR):**
  * *Situación Actual:* **65%** de completitud debido al desinterés por formularios extensos[cite: 4].
  * *Proyección Rediseño:* **92%** tras la implementación del flujo compacto y *Guest Checkout*[cite: 4].
* **⏱️ Tiempo Promedio en la Tarea (Time on Task - ToT):**
  * *Situación Actual:* **180 segundos** de navegación tortuosa[cite: 4].
  * *Proyección Rediseño:* Reducción a **95 segundos** netos eliminando pasos redundantes[cite: 4].
* **💰 Tasa de Conversión (Conversion Rate - CR):**
  * *Impacto Estimado en Negocio:* Se proyecta un **incremento nulo/neto del 15% en la conversión transaccional final** de la Landing Page al reducir la fricción cognitiva en el embudo de ventas[cite: 4].

---

## 👥 Equipo de Trabajo - Universidad ECOTEC
* **Asignatura:** Tópicos Especiales en Negocios Digitales[cite: 4]
* **Docente:** Giancarlo Molina[cite: 4]
* **Facultad:** Ciencias Económicas y Empresariales / Negocios Digitales[cite: 4]
