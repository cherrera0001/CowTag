
# 🐄 Cow Tag: Dispositivo IoT para Monitoreo Ganadero en Zonas Rurales de Chile

**Responsable:** Cristóbal Herrera Jara (C4A SpA)  
**Fecha:** 6 de mayo de 2025

---

## 📘 Índice

- [Resumen Ejecutivo](#resumen-ejecutivo)
- [Estado del Arte y Benchmark Global](#estado-del-arte-y-benchmark-global)
- [Cercas Virtuales – Enfoque Técnico](#cercas-virtuales--enfoque-técnico)
- [Tecnologías Emergentes](#tecnologías-emergentes)
- [Comparativa de Hardware](#comparativa-de-hardware)
- [Infraestructura de Datos y Plataforma](#infraestructura-de-datos-y-plataforma)
- [Propuesta MVP Técnica](#propuesta-mvp-técnica)
- [Evaluación de Costos Iniciales](#evaluación-de-costos-iniciales)
- [Conclusiones y Recomendaciones](#conclusiones-y-recomendaciones)
- [📎 Archivos Adjuntos](#archivos-adjuntos)

---

## 🧭 Resumen Ejecutivo

¿Cómo nació la idea de Cow Tag?
La idea de Cow Tag nació en un momento de introspección y conexión con la naturaleza. Recuerdo que, tras una situación difícil en mi vida personal, decidí pasar unos días en el sur de Chile. Durante esa estadía, tuve la oportunidad de conocer a mi familia paterna, la familia Palacios, especialmente a mi tío Queño y a mi primo Jaime. Queño ha sido veterinario toda su vida, y juntos se dedican a la crianza de ganado. Fue ahí, en su predio, donde observé una práctica que me llamó profundamente la atención: antes de ir a una feria a vender su ganado, ellos perforaban la oreja de las vacas para colocarles una etiqueta, un "tag" simple exigido por el SAG (Servicio Agrícola y Ganadero).

Aquella escena, aparentemente rutinaria, despertó en mí una pregunta: ¿Qué más se podría controlar en el ganado? ¿Qué información adicional se podría obtener para ayudar realmente a los ganaderos? No se trataba solo de identificarlos, sino de ofrecerles datos útiles para su gestión diaria.

Poco después, conocí a Gabriel, un hombre mayor que también trabajaba con ganado. Una tarde, su esposa le pidió que fuera a buscar a su buey, un animal viejo que solía pastar libremente. Gabriel miró al horizonte y, con una certeza impresionante, dijo: "A esta hora el animal está echado, no lo voy a encontrar". Esa escena me dejó pensando. ¿Y si él pudiera saber con precisión dónde estaba su buey, sin depender solo de su intuición?

Fue entonces cuando me di cuenta de una necesidad profunda y común entre los ganaderos: conocer el estado, ubicación y comportamiento de sus animales, especialmente en terrenos amplios y sin conectividad móvil. Sin embargo, el primer desafío era evidente: la falta de conexión en esas zonas rurales.

Cow Tag nació como una respuesta a esta necesidad, una solución tecnológica que va más allá del simple control visual del ganado. No se trata solo de una etiqueta identificadora, sino de un sistema integral para monitorear ubicación, salud y comportamiento, incluso en zonas remotas. Es una solución que busca transformar la ganadería rural, haciéndola más eficiente, segura y rentable.

### Solución:

📍 Seguimiento por GPS en tiempo real, para conocer la ubicación del animal en todo momento.

🚨 Alertas de comportamiento anómalo, como inactividad prolongada o posible escape.

🧭 Geocercas configurables (cercas virtuales) para definir límites sin necesidad de vallado físico (fase futura).

☀️ Operación autónoma con panel solar y batería, sin necesidad de intervención humana frecuente.

📡 Comunicación por LoRaWAN, que no depende de cobertura celular.

📲 Plataforma de monitoreo vía app web/móvil, accesible, simple y pensada para usuarios no técnicos.



🌱 Etapa futura (visión a corto/mediano plazo)

  - Sensores de temperatura corporal o frecuencia cardíaca.
  - Detección de alimentación o falta de movimiento por tiempo excesivo.
  - Rutas frecuentes y mapas de calor de comportamiento.
  - Estado energético del collar y alertas por bajo nivel de batería.
  - Estimaciones predictivas: ¿Está preñada? ¿Se enfermó? ¿Está rumiando correctamente?
  - Generación de reportes trazables para el SAG o exportación.
   
---

## 🌎 Estado del Arte y Benchmark Global

| Producto     | Empresa    | Tecnología                           | Precio        | Región               | Limitaciones                      |
|--------------|------------|---------------------------------------|----------------|------------------------|-----------------------------------|
| Nofence      | Noruega    | GPS, App, Panel solar, descarga       | USD 289 + subs.| Europa/USA             | Requiere señal celular            |
| eShepherd    | Gallagher  | GPS, estación base, solar             | USD 250–350    | USA, Canadá            | Mínimo 20 collares, base LTE      |
| Halter       | NZ/USA     | GPS, base inteligente, energía solar  | USD 60/año     | NZ, USA                | Requiere infraestructura compleja |
| Vence        | Merck      | GPS + base fija                       | USD 40/año     | USA                   | Limitada autonomía energética     |

Cow Tag busca posicionarse como una alternativa más económica, con independencia celular (gracias a LoRa) y adaptable al terreno rural latinoamericano.

---

## 🚧 Cercas Virtuales – Enfoque Técnico

### ¿Cómo funcionan?
1. Se configura una cerca virtual desde una app o plataforma web.
2. El collar Cow Tag monitorea la ubicación del animal vía GPS.
3. Si el animal se acerca a la zona límite:
   - Se emite una alerta sonora.
   - (Fase futura) Se aplicaría un impulso leve.

### Consideraciones técnicas:
- GPS convencional (~2–10 m precisión).
- Posible evolución a GPS RTK para mayor exactitud.
- Cercas dinámicas posibles según estaciones o calidad del forraje.

---

## 📡 Tecnologías Emergentes

| Tecnología     | Alcance         | Energía       | Costo      | Observación                    |
|----------------|------------------|---------------|------------|-------------------------------|
| **LoRaWAN**    | 2–15 km           | Muy bajo      | Bajo/Medio | Ideal para zonas rurales      |
| Sigfox         | 10–40 km          | Bajo          | Bajo       | Cobertura limitada            |
| Satelital NB-IoT| Global           | Alto          | Alto       | Ideal en lugares extremos     |

- **MQTT** será el protocolo base (por su bajo overhead y soporte en IoT).
- **Energía solar** + batería Li-Ion/LiFePO4 permitirá operación continua.
- El firmware utilizará *deep sleep* y eventos por movimiento.

---

## 🧱 Comparativa de Hardware

| Componente       | Modelo                 | Precio CLP | Justificación breve                                  |
|------------------|------------------------|------------|------------------------------------------------------|
| Microcontrolador | LilyGO TTGO T-Beam     | $18.000    | GPS + LoRa integrados, ideal para MVP                |
| GPS              | u-blox Neo-6M          | $4.000     | Precisión aceptable, bajo consumo                    |
| LoRa             | SX1276 integrado       | Incluido   | Probado y eficiente para redes privadas              |
| Panel solar      | 5V 1.2W genérico       | $2.500     | Recarga básica en días soleados                     |
| Batería          | 18650 Li-Ion 2600mAh   | $2.000     | Alta densidad energética                             |
| Cargador         | TP4056 con BMS         | $1.200     | Control de carga básico y económico                  |
| Caja estanca     | IP65 ABS               | $2.500     | Protección contra polvo y agua                       |
| Gateway LoRaWAN  | RAK7246 / Dragino      | $70k–$120k | Necesario para pruebas reales, posible TTN gratuito  |

---

## ☁️ Infraestructura de Datos y Plataforma

### Arquitectura:

```
Cow Tag (GPS+LoRa)
     ↓
LoRa Gateway
     ↓
MQTT Broker
     ↓
Firebase/Supabase (Backend + DB)
     ↓
App Web o Móvil
```

### Tecnologías:
- **Backend:** Firebase (rápido), Supabase (open-source).
- **Frontend:** React / Vue.js (web), Flutter / React Native (móvil).
- **Seguridad:** MQTT + TLS, validación JWT, cifrado en tránsito y en reposo.

---

## ⚙️ Propuesta MVP Técnica

### Lista de materiales (estimado):

- MCU + GPS + LoRa: ~$18.000
- Panel solar: ~$2.500
- Batería + cargador: ~$4.000
- Caja, conectores, extras: ~$3.000

**Costo total por unidad MVP:** ~$28.000–34.000 CLP

### Ciclo de operación:
1. Ciclo de lectura GPS cada 30–60 minutos.
2. Detección de eventos: cruce, inactividad.
3. Envío LoRa → almacenamiento → visualización.

---

## 💰 Evaluación de Costos Iniciales

| Cantidad | Precio unitario estimado | Costo total aprox. |
|----------|---------------------------|---------------------|
| 1        | $34.000 CLP               | $34.000 CLP         |
| 10       | $31.000 CLP               | $310.000 CLP        |
| 100      | $28.000 CLP               | $2.800.000 CLP      |

---

## ✅ Conclusiones y Recomendaciones

- El diseño del MVP es **viable técnica y financieramente**.
- LoRa y energía solar ofrecen autonomía y bajo costo.
- Se sugiere iniciar con pruebas de campo usando gateways comunitarios (TTN).
- La evolución futura incluirá cercas virtuales activas.

**Próximos pasos:**
- Fabricación de prototipos.
- Validación funcional (campo real).
- Iteración de firmware y estructura.
- Preparación de pitch para incubadora/inversionistas.

---

## 📎 Archivos Adjuntos

- [Nofence](https://www.nofence.no/en-us/what-is-nofence)
- [eShepherd (Gallagher)](https://am.gallagher.com/en-US/new-products/eShepherd)
- [Sateliot – IoT Satelital](https://sateliot.space/es/ganaderia/)
- [Basto.io (startup argentina)](https://basto.io)
- [Virtual fencing PDF – Southwest Beef](https://southwestbeef.org/wp-content/uploads/virtual_fencing_spanish_v3.pdf)
