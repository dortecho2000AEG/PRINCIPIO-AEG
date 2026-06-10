# PRINCIPIO-AEG
# 🔬 Principio-AEG: Acceso a Energía Geométrica mediante Reducción de Entropía de Flujo

Validación experimental de código abierto de un mecanismo termodinámico para extracción de energía cinética a partir de flujo relativo de fluidos mediante convergencia geométrica y gestión de entropía.

**Licencia:** CC BY 4.0 | **Estado:** Prototipo Experimental | **Documentación:** [Informe Técnico Completo](./docs/Principio_AEG_Informe_Tecnico.pdf)

---

## 📋 Resumen

El **Principio AEG (Acceso a Energía Geométrica)** describe un mecanismo físico validado experimentalmente: la conversión de energía interna de un fluido en energía cinética dirigida mediante **restricción geométrica forzada** y **reducción de entropía configuracional** (Δs < 0).

A diferencia de los sistemas convencionales de energía de flujo que dependen de gradientes de presión externos o combustión, AEG demuestra que una geometría convergente combinada con un elemento de ordenamiento de flujo (honeycomb) puede imponer una reducción local de entropía del flujo. Este ordenamiento libera energía interna como energía cinética dirigida, manifestándose como aumento de velocidad de salida y una consecuente caída de presión estática.

**Estado actual:** Prototipo a escala de laboratorio validado cualitativa y cuantitativamente con instrumentación de consumo. Eficiencia ≈ 5.6% (límite de prototipo). Las proyecciones teóricas de escalabilidad indican potencial para movilidad autónoma y generación distribuida, pendiente de validación metrológica independiente.

> ⚠️ **Nota importante:** Este no es un dispositivo de movimiento perpetuo. AEG requiere flujo relativo (v₁ > 0), respeta la Segunda Ley de la Termodinámica mediante exportación de entropía al entorno, y opera estrictamente dentro de límites de coherencia observados experimentalmente (R ≤ 7).

---

## 🔑 Mecanismo Fundamental

| Concepto | Visión Tradicional | Visión AEG |
|----------|-------------------|------------|
| **Motor** | Gradiente de presión externo (ΔP < 0 empuja el flujo) | Restricción geométrica + ordenamiento entrópico (Δs < 0 habilita aceleración) |
| **Continuidad** | Restricción de balance de masa | Expresión matemática de restricción volumétrica → reducción de entropía |
| **Caída de Presión** | Causa de la aceleración | Consecuencia termodinámica del aumento de energía cinética |
| **Fuente de Energía** | Potencial almacenado o combustión | Energía interna del fluido accesada mediante ordenamiento configuracional |

### Relación Gobernante (Ecuación de Gibbs para Flujo)

Para un sistema abierto en régimen estacionario con intercambio térmico despreciable:
Δe_c = -TΔs - vΔP

Donde:
- **-TΔs (Término de Ordenamiento):** Positivo cuando Δs < 0. Inyecta energía cinética al suprimir turbulencia transversal.
- **-vΔP (Término de Expansión):** Positivo cuando ΔP < 0. Contribución convencional impulsada por presión.
- **Límite de Coherencia:** R = A₁/A₂ ≈ 7. Más allá de este valor, la separación de capa límite destruye el ordenamiento (Δs → 0 o >0), colapsando la eficiencia.

La derivación completa, condiciones de contorno y pruebas de consistencia termodinámica se encuentran en el [Informe Técnico](./docs/Principio_AEG_Informe_Tecnico.pdf).

---

## 🧪 Validación Experimental

| Prueba | Observación | Interpretación |
|--------|-------------|----------------|
| **Causalidad ON/OFF** | La turbina se detiene sin geometría; acelera instantáneamente con AEG | El efecto está habilitado geométricamente, no es ambiental |
| **Firma Acústica** | Ruido de banda ancha → pico tonal definido (~630–690 Hz) | Entropía configuracional exportada como señal coherente |
| **Visualización de Flujo** | Hilo succionado alineado (R≤7) vs rechazo caótico (R>7) | El límite de coherencia coincide con el límite teórico |
| **Salida Eléctrica** | ~13.0 V DC estable, ~35 W entregados a LEDs/generador | Trabajo útil extraído del flujo ordenado |

📹 Videos brutos, capturas espectrales y registros de medición disponibles en: [`/data/experimental/`](./data/experimental/)

> 🔍 **Nota de Instrumentación:** Las mediciones se realizaron con multímetros de consumo y aplicaciones de espectrometría móvil. La propagación de incertidumbre y metrología calibrada están pendientes. Consulte la [Declaración de Transparencia](./docs/TRANSPARENCIA.md).

---

## 🌍 Precedente de Ingeniería: Efecto Suelo en Fórmula 1

El mecanismo físico subyacente a AEG es directamente análogo a la **aerodinámica de efecto suelo en Fórmula 1** (reintroducida en 2022):

- Ambos utilizan geometrías convergentes para acelerar flujo relativo sin potencia externa.
- Ambos dependen de mantener flujo adherido y de baja entropía para maximizar el resultado útil (downforce en F1; trabajo cinético/eléctrico en AEG).
- Ambos colapsan cuando ocurre separación de flujo (stall del difusor en F1; R > 7 en AEG).

Los equipos de F1 invierten >USD 500 millones/año validando esta física a escala. AEG aplica los mismos principios fluidodinámicos a la extracción de energía y propulsión, documentado abiertamente para verificación independiente.

**Referencias técnicas:**
- SAE Technical Paper 2021-01-0935: "Diffuser Aerodynamics in Formula 1 Ground Effect"
- Reglamento Técnico FIA 2022-2026, Artículo 3.5.8: Especificaciones de difusores de efecto suelo

---

## 📐 Proyecciones Teóricas de Escalabilidad

*Nota: Estas son proyecciones matemáticas basadas en P ∝ v₁³ y validación de prototipo. La implementación real requiere optimización aerodinámica, selección de materiales e ingeniería de sistemas.*

| Aplicación | v₁ (m/s) | A₁ (m²) | P_flujo (kW) | η (est.) | P_neta (kW) |
|------------|----------|---------|--------------|----------|-------------|
| Terrestre (90 km/h) | 25 | 0.5 | 225 | 20–40% | 45–90 |
| Aviación (crucero) | 250 | 2.0 | 38,400 | 15–30% | 5,760–11,520 |
| Marítimo (10 m/s) | 10 | 1.0 | 7,500 | 20–40% | 1,500–3,000 |
| Micro-red estacionaria | 20 | 0.25 | 57.6 | 20–30% | 7.5–15.3* |

*Neto tras consumo del soplador. Asume arquitectura de generación AC de alta frecuencia y almacenamiento con supercondensadores.

---

## 📁 Estructura del Repositorio
Principio-AEG/
├── README.md # Este archivo
├── docs/
│ ├── Principio_AEG_Informe_Tecnico.pdf # Informe técnico completo
│ └── TRANSPARENCIA.md # Declaración de limitaciones
├── data/
│ └── experimental/ # Videos, espectros, mediciones
├── cad/
│ ├── tobera_R7.step # Geometría convergente (R≈7)
│ ├── honeycomb_5mm.step # Elemento de ordenamiento
│ └── guia_ensamblaje.md # Instrucciones de construcción
└── LICENSE # CC BY 4.0

---

## 🔧 Cómo Replicar y Contribuir

Invitamos a ingenieros, físicos y makers a validar o refinar independientemente este principio.

### 1. Construir el Prototipo

- Utilice los archivos CAD en `/cad/` o fabrique en acrílico/PLA.
- **Dimensiones recomendadas:**
  - A₁ = 64 cm² (8×8 cm)
  - A₂ = 9 cm² (3×3 cm)
  - Relación R ≈ 7
  - Honeycomb: celdas Ø ≈ 2.5–5 mm, longitud ≥ 70 mm
- Alinear: fuente de flujo → honeycomb → tobera → turbina/generador en eje rígido.

### 2. Medir y Reportar

- Registrar voltaje/corriente con multímetro calibrado.
- Capturar espectros acústicos con micrófono calibrado + analizador FFT.
- Visualizar flujo con hilo/humo cerca de la salida.
- Documentar condiciones ambientales (T, P, humedad).

### 3. Compartir Resultados

- Haga fork de este repositorio o abra un Issue/Discussion con su conjunto de datos.
- Reportar incertidumbre (Tipo A/B) conforme a ISO/IEC Guide 98-3 (GUM).
- Consolidaremos conjuntos de datos validados en un benchmark público.

📩 **Contacto:** [Su correo o enlace a GitHub Discussions]  
🤝 **Colaboración:** Abierto a coautoría en validaciones revisadas por pares, optimización CFD o iteración de hardware.

---

## 📜 Transparencia y Limitaciones

### ✅ Lo que este repositorio proporciona:

- Protocolo experimental completo y datos brutos
- Derivación termodinámica (formulación de Gibbs para sistemas abiertos)
- Archivos CAD, lista de materiales y guía de ensamblaje
- Declaración explícita de límites del prototipo

### ❌ Lo que aún no está incluido:

- Metrología calibrada o propagación de incertidumbre
- Pruebas de durabilidad a largo plazo o en condiciones ambientales reales
- Optimización de eficiencia a grado comercial
- Publicación en revista revisada por pares (en preparación)

**Priorizamos la reproducibilidad sobre las afirmaciones.** Si encuentra errores, limitaciones o mejoras, por favor envíe un Pull Request o abra un Issue. La ciencia avanza mediante crítica rigurosa y abierta.

---

## 📄 Licencia y Citación

**Licencia:** [Creative Commons Attribution 4.0 Internacional](https://creativecommons.org/licenses/by/4.0/deed.es)

Puede compartir y adaptar este material, incluso comercialmente, bajo la condición de atribución adecuada.

**Patente de referencia:** Solicitud Pendiente N° 2590-2023 (protección legal complementaria; no restringe la replicación abierta)

### Citación sugerida (BibTeX):

```bibtex
@misc{ortecho2026aeg,
  author = {Ortecho Acosta, Daniel Rolando},
  title = {Principio-AEG: Acceso a Energía Geométrica mediante Reducción de Entropía de Flujo},
  year = {2026},
  publisher = {GitHub},
  url = {https://github.com/[SU_USUARIO]/Principio-AEG},
  license = {CC-BY-4.0},
  language = {es}
}
"La geometría es libre. El flujo es universal. Los datos están abiertos. Valide, refine, comparta."
— Daniel Rolando Ortecho Acosta, Ing. Químico | Lima, Perú
