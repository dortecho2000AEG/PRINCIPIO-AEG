# 🧪 Guía de Replicación: Prototipo AEG v1.0

**Versión:** 1.0  
**Fecha:** Febrero 2026  
**Autor:** Daniel Rolando Ortecho Acosta, Ing. Químico  
**Ubicación:** Lima, Perú  
**Licencia:** CC BY 4.0  
**Patente Pendiente:** N° 2590-2023

---

## 📋 Resumen

Este documento describe paso a paso cómo construir y probar el prototipo AEG (Acceso a Energía Geométrica). El sistema convierte energía interna del aire en energía cinética útil mediante restricción geométrica (R≈7) y reducción de entropía configuracional (honeycomb), generando ~13V DC estables.

**Resultado esperado:** ~13V DC estables, suficiente para alimentar múltiples LEDs.

⚠️ **ADVERTENCIA DE SEGURIDAD:** Este experimento involucra corriente eléctrica (220V AC en el transformador). Si no tienes experiencia trabajando con electricidad, busca supervisión de un electricista calificado.

---

## 💡 NOTA SOBRE LA VISIÓN DEL PROYECTO

**La idea original del sistema AEG es ser autónomo:** una batería alimenta el ventilador, el generador recarga la batería mientras produce excedente para cargas externas. El sistema no debería depender de la red eléctrica.

**Para estas pruebas de laboratorio** usamos un transformador de 220V a 12V por conveniencia y estabilidad de medición, pero el diseño final apunta a un sistema cerrado autoalimentado con batería + supercondensadores.

---

## 🛠️ Lista de Materiales (Qué Comprar)

### Componentes Principales

#### 1. Ventilador Axial 12V (Doble Aspa, Área 8x8 cm)
- **Buscar en AliExpress:** "axial fan 12V 8x8cm dual blade" o "12V DC fan 80x80mm double impeller"
- **Especificaciones:**
  - Voltaje: 12V DC
  - Corriente nominal: 9A (según fabricante)
  - **Corriente real medida:** ~5.6A máximo en operación
  - Área de entrada: 8 cm × 8 cm = 64 cm²
  - Tipo: Doble aspa (mayor presión estática)
- **Precio aproximado:** $25-40 USD
- **Nota:** El área del ventilador (8x8 cm) coincide exactamente con el área de entrada de la tobera, lo que permite acoplamiento directo sin pérdidas.

#### 2. Tobera Convergente de Acrílico (R≈7)
- **Material:** Acrílico transparente de 5mm de espesor
- **Dimensiones:**
  - Entrada: 8 cm × 8 cm = 64 cm² (coincide con el ventilador)
  - Salida: 1.5 cm × 6 cm = 9 cm²
  - Relación de áreas: R = 64/9 ≈ 7.1
  - Longitud total: ~25-30 cm
  - Ángulo de convergencia: ~15° (suave)
- **Dónde comprar:** Ferreterías, tiendas de plásticos, Amazon
- **Qué buscar:** "lámina acrílico transparente 5mm"
- **Costo:** $10-20 USD
- **Nota:** Puedes pedir que te lo corten a medida o fabricarlo tú mismo.

#### 3. Honeycomb (Elemento de Ordenamiento)
- **Opción A (Económica - La que usamos):**
  - Pajillas de plástico de 5mm de diámetro
  - Cortadas a 7 cm de largo
  - Pegadas juntas formando un bloque de 8×8 cm
  - **Costo:** ~$5 USD
  
- **Opción B (Profesional):**
  - Buscar en AliExpress: "aluminum honeycomb 5mm cell" o "honeycomb structure plastic"
  - **Costo:** $10-20 USD

#### 4. Turbina Pelton de 10 cm
- **Buscar en AliExpress:** "pelton turbine wheel 100mm" o "micro hydro turbine 10cm"
- **Especificaciones:**
  - Diámetro: 10 cm (100 mm)
  - Número de cucharas: 8-12
  - Material: Plástico ABS o aluminio
- **Precio aproximado:** $15-30 USD
- **Nota:** Aunque es para agua, funciona perfectamente con aire si el chorro es coherente (gracias al honeycomb).

#### 5. Motor DC (usado como generador)
- **Buscar en AliExpress:** "DC motor 14V 150W 4000RPM permanent magnet" o "PMDC motor 12-24V"
- **Especificaciones:**
  - Voltaje nominal: 14V DC
  - Potencia nominal: 150W
  - Velocidad nominal: 4000 RPM
  - Tipo: Motor de imanes permanentes (PMDC)
  - **Voltaje generado en prueba:** 10.6V - 13.2V DC estables
- **Precio aproximado:** $20-35 USD

#### 6. Fuente de Alimentación (para pruebas de laboratorio)
- **Buscar:** "power supply 12V 10A 120W" o "fuente conmutada 12V 10A"
- **Especificaciones:**
  - Entrada: 220V AC, 50/60 Hz
  - Salida: 12V DC, mínimo 10A (120W)
- **Precio aproximado:** $15-25 USD
- **Nota:** Para la versión autónoma final, reemplazar por batería de 12V (ej: batería de moto o litio) + circuito de carga.

#### 7. Componentes Adicionales
| Componente | Dónde comprar | Cantidad | Costo aprox. |
|------------|---------------|----------|--------------|
| Multímetro digital | Tiendas de electrónica | 1 | $10-15 |
| LEDs (rojos, azules, blancos) | AliExpress, Amazon | 10-20 | $5 |
| Resistencias 220Ω-470Ω | Tiendas de electrónica | 10-20 | $2 |
| Cables de conexión | Tiendas de electrónica | 2m | $5 |
| Silicona/pegamento acrílico | Ferretería | 1 tubo | $5 |
| Cinta aislante | Ferretería | 1 rollo | $3 |
| Batería 12V (opcional, versión autónoma) | Tiendas de autopartes | 1 | $30-50 |

---

### 💰 **COSTO TOTAL ESTIMADO**

| Versión | Costo |
|---------|-------|
| **Laboratorio (con transformador)** | $120-195 USD |
| **Autónoma (con batería)** | $150-245 USD |

---

##  Protocolo de Ensamblaje

### Paso 1: Preparación de la Fuente de Alimentación
1. Conecta el transformador a la red eléctrica (220V) con el interruptor en OFF
2. Verifica con multímetro que la salida sea 12V DC
3. Conecta un fusible de 10A en serie con el positivo (protección)
4. Prepara cables de 12V con conectores apropiados

### Paso 2: Montaje del Ventilador
1. Fija el ventilador en un soporte estable
2. Conecta los cables de 12V al ventilador (respeta polaridad)
3. Instala la rejilla protectora si viene incluida
4. **NO enciendas aún**

### Paso 3: Fabricación de la Tobera
1. Corta el acrílico según las dimensiones:
   - Panel frontal (entrada): 8×8 cm con abertura cuadrada completa
   - Panel trasero (salida): abertura rectangular de 1.5×6 cm
   - 4 paneles laterales trapezoidales (convergentes, ~25-30 cm de largo)
2. Ensambla con adhesivo acrílico o silicona
3. Verifica que no haya fugas de aire en las uniones
4. Deja secar 24 horas

### Paso 4: Instalación del Honeycomb
1. Corta las pajillas a 7cm de largo
2. Pégalas juntas formando un bloque compacto de 8×8 cm
3. Inserta el bloque en la tobera a **2 cm de la entrada**
4. Asegúrate de que las celdas estén alineadas paralelas al flujo
5. Fija con cinta adhesiva o silicona

### Paso 5: Montaje de la Turbina y Generador
1. Fija la turbina Pelton en un soporte rígido
2. Conecta el eje de la turbina al eje del motor/generador (acoplamiento directo)
3. Alinea perfectamente para evitar vibraciones
4. Verifica que la turbina gire libremente sin rozamiento

### Paso 6: Alineación del Sistema Completo
1. Coloca la tobera **pegada o a 2-5 cm** del ventilador (entrada de tobera alineada con salida de ventilador)
2. Coloca la turbina **a 1-2 cm** de la salida de la tobera
3. Verifica que el chorro de aire impacte directamente las cucharas de la turbina
4. Asegura todo el conjunto para que no se mueva durante la prueba

### Paso 7: Conexión del Circuito Eléctrico
1. Conecta los cables del generador al multímetro (para medir voltaje)
2. Conecta los LEDs en paralelo, cada uno con su resistencia de 220Ω-470Ω
3. Verifica polaridad correcta
4. **NO conectes aún los LEDs** (primero prueba sin carga)

---

## 🧪 Protocolo de Prueba

### Prueba 1: Verificación SIN Geometría (Control)
1. Enciende el ventilador **SIN la tobera instalada**
2. Observa la turbina: debe girar débilmente o no girar
3. Mide voltaje en el generador: debe ser ~0V o muy bajo (<1V)
4. **Documenta:** Foto/video de la turbina quieta o girando débilmente

### Prueba 2: Activación CON Geometría AEG
1. Instala la tobera con honeycomb frente al ventilador
2. Enciende el ventilador
3. Observa la turbina: debe **acelerar inmediatamente**
4. Mide voltaje en el generador: debe subir a **~10-13V DC**
5. **Documenta:** Foto/video de la turbina girando + multímetro mostrando voltaje

### Prueba 3: Conexión de Carga (LEDs)
1. Conecta los LEDs al circuito (con resistencias)
2. Verifica que se enciendan con brillo estable
3. Mide voltaje con carga conectada: debe mantenerse ~10-12V
4. **Documenta:** Foto/video de LEDs encendidos

### Prueba 4: Prueba de Causalidad (ON/OFF)
1. Con el sistema funcionando, **retira la tobera**
2. Observa: turbina frena, LEDs se apagan, voltaje cae
3. **Vuelve a instalar la tobera**
4. Observa: turbina acelera, LEDs se encienden, voltaje sube
5. **Documenta:** Video mostrando el efecto ON/OFF (esto demuestra que la geometría es la causa)

### Prueba 5: Visualización de Flujo (Pita/Hilo)
1. Ata un hilo ligero (pita) a un palillo
2. Acerca el hilo a la salida de la tobera (con sistema encendido)
3. Observa: el hilo debe ser **succionado hacia el chorro** (flujo coherente)
4. **Documenta:** Foto/video del hilo alineado con el flujo

### Prueba 6: Firma Acústica (Opcional pero recomendado)
1. Descarga una app de análisis espectral en tu celular (ej: Spectroid, Spectral Analyzer)
2. Coloca el celular a 10-20 cm de la salida de la tobera, a 90° del chorro
3. Graba el sonido con el sistema encendido
4. Observa el espectro: debe aparecer un **pico tonal definido (~600-700 Hz)**
5. Compara con el sonido del ventilador solo (sin tobera): debe ser ruido de banda ancha
6. **Documenta:** Captura de pantalla del espectro

---

## 📊 Mediciones Esperadas

| Parámetro | Valor Esperado | Instrumento |
|-----------|---------------|-------------|
| **Voltaje en circuito abierto** | 10.6 - 13.2 V DC | Multímetro digital |
| **Voltaje con carga (LEDs)** | 10.0 - 12.0 V DC | Multímetro digital |
| **Corriente estimada** | ~2.5 - 3.0 A | Multímetro (opcional) |
| **Potencia eléctrica** | ~30 - 40 W | Calculado (V × I) |
| **Firma acústica** | Pico tonal ~635 Hz | App espectro celular |
| **Consumo real del ventilador** | ~5.6 A máximo | Multímetro en serie |

---

## ⚠️ Solución de Problemas

### Problema: La turbina no gira o gira muy lento
**Causas posibles:**
- Alineación incorrecta entre tobera y turbina
- Honeycomb mal instalado o celdas obstruidas
- Fugas de aire en la tobera
- Ventilador demasiado lejos de la tobera

**Soluciones:**
- Revisa alineación: el chorro debe impactar directamente las cucharas
- Verifica que el honeycomb esté bien colocado y las celdas estén limpias
- Sella todas las uniones de la tobera con silicona
- Acerca el ventilador a 2-5 cm de la entrada de la tobera

### Problema: Voltaje muy bajo (<5V)
**Causas posibles:**
- Generador/motor con imanes débiles
- Acoplamiento turbina-generador con pérdidas
- Turbina mal diseñada (cucharas muy pequeñas)

**Soluciones:**
- Prueba con otro motor DC de imanes permanentes
- Usa acoplamiento directo (sin correa) para minimizar pérdidas
- Aumenta el tamaño de las cucharas de la turbina

### Problema: Los LEDs parpadean o se apagan
**Causas posibles:**
- Voltaje inestable
- Resistencias incorrectas
- Conexiones sueltas

**Soluciones:**
- Verifica que el voltaje se mantenga estable (>10V)
- Usa resistencias de 220Ω-470Ω para cada LED
- Revisa todas las conexiones del circuito

### Problema: No se observa el pico espectral en el sonido
**Causas posibles:**
- Honeycomb no está ordenando el flujo efectivamente
- Tobera muy corta o ángulo de convergencia muy agresivo
- Micrófono del celular mal posicionado

**Soluciones:**
- Verifica que las celdas del honeycomb estén alineadas con el flujo
- Asegúrate de que R ≈ 7 (no mayor)
- Coloca el celular a 10-20 cm de la salida, a 90° del chorro

---

