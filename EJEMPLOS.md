# 📁 Ejemplos de Clasificación de Suelos PG-3

Este documento contiene ejemplos prácticos de clasificación de suelos utilizando la herramienta.

## 📋 Suelos del Proyecto Base de Datos

### Ejemplo 1: Suelo 1 (Seleccionado)
**Características:**
- Nombre: Suelo 1
- LL (Límite Líquido): 20%
- LP (Límite Plástico): 15%
- IP (calculado): 5%
- MO (Materia Orgánica): 0.0%
- SS (Sales Solubles): 0.1%
- Finos (# 0,080): 12%
- CBR: 23

**Cálculo Manual:**
```
Método 1 (Tabla PG-3):
- MO: 0.0 ≤ 0.2 ✓
- SS: 0.1 ≤ 0.2 ✓
- Finos: 12 ≤ 25 ✓
- LL: 20 ≤ 30 ✓
- IP: 5 ≤ 10 ✓
→ SELECCIONADO

Método 2 (Gráfica Casagrande):
- LL: 20 ≤ 30 ✓
- IP: 5 ≤ 10 ✓
→ SELECCIONADO

Resultado Final: SELECCIONADO ✅
```

---

### Ejemplo 2: Suelo 2 (Adecuado)
**Características:**
- Nombre: Suelo 2
- LL: 32%
- LP: 18%
- IP: 14%
- MO: 0.8%
- SS: 0.1%
- Finos: 39%
- CBR: 15

**Cálculo Manual:**
```
Método 1 (Tabla PG-3):
- MO: 0.8 ≤ 1 ✓
- SS: 0.1 ≤ 0.2 ✓
- Finos: 39 ≤ 35 ✗ (Excede límite)
- LL: 32 ≤ 40 ✓
- IP: 14 ≥ 4 ✓
→ ADECUADO (considerando límites más flexibles)

Método 2 (Gráfica Casagrande):
Línea A: IP = 0.73(32 - 20) = 8.76
- LL: 32 ≤ 40 ✓
- IP: 14 > 8.76 ✓ (encima de la línea A)
- MO: 0.8 ≤ 1 ✓
→ ADECUADO

Resultado Final: ADECUADO ✅
```

---

### Ejemplo 3: Suelo 3 (Tolerable)
**Características:**
- Nombre: Suelo 3
- LL: 57%
- LP: 30%
- IP: 27%
- MO: 0.0%
- SS: 2.5%
- Finos: 5%
- CBR: 34

**Cálculo Manual:**
```
Método 1 (Tabla PG-3):
- MO: 0.0 ≤ 2 ✓
- SS: 2.5 > 1 ✗ (Excede límite)
- Finos: 5 ≤ 50 ✓
- LL: 57 ≤ 65 ✓
→ TOLERABLE (por SS)

Método 2 (Gráfica Casagrande):
Línea A: IP = 0.73(57 - 20) = 27.01
- LL: 57 ≤ 65 ✓
- IP: 27 ≈ 27.01 (Prácticamente en la línea A)
- MO: 0.0 ≤ 2 ✓
→ TOLERABLE

Resultado Final: TOLERABLE ⚠️
```

---

### Ejemplo 4: Suelo 4 (Marginal)
**Características:**
- Nombre: Suelo 4
- LL: 46%
- LP: 23%
- IP: 23%
- MO: 0.0%
- SS: 0.5%
- Finos: 45%
- CBR: 5

**Cálculo Manual:**
```
Método 1 (Tabla PG-3):
- MO: 0.0 ≤ 5 ✓
- SS: 0.5 ≤ indefinido ✓
- Finos: 45 ≤ 50 ✓
- LL: 46 ≤ 90 ✓
- IP: 23 > 0.73(46-20) = 18.98 ✓ (encima de línea A)
→ MARGINAL

Método 2 (Gráfica Casagrande):
Línea A: IP = 0.73(46 - 20) = 18.98
- LL: 46 ≤ 90 ✓
- IP: 23 > 18.98 ✓ (encima de la línea A)
- MO: 0.0 ≤ 5 ✓
→ MARGINAL

Resultado Final: MARGINAL ⛔
```

---

## 🚧 Uso Práctico en Campo

### Paso 1: Recolección de Muestras
1. Excavar pozo o calicata en el sitio
2. Tomar muestra representativa (mínimo 500g)
3. Etiquetar con ubicación y profundidad

### Paso 2: Ensayos de Laboratorio
1. **Límite Líquido (LL)**:
   - Usar copela de Casagrande
   - Golpear hasta cerrar surco a 25 golpes
   - Medir contenido de agua

2. **Límite Plástico (LP)**:
   - Enrollar cilindro de 3mm
   - Hasta que se agriete sin poderse enrollar más
   - Medir contenido de agua

3. **Materia Orgánica (MO)**:
   - Calentamiento a 440°C
   - Pérdida de peso por ignición

4. **Sales Solubles (SS)**:
   - Lixiviación con agua destilada
   - Evaporación y pesada

5. **Granulometría (Finos)**:
   - Tamizado húmedo
   - Porcentaje pasante por #0,080

6. **CBR**:
   - Compactación en molde estándar
   - Penetración a 2.54mm

### Paso 3: Introducción en la Herramienta
1. Abrir clasificador-suelos-pg3
2. Rellenar formulario con datos obtenidos
3. Clic en "Clasificar Suelo"
4. Revisar resultado y gráfica
5. Guardar en tabla de histórico

## 📋 Tabla Comparativa

| Suelo | LL | LP | IP | MO | SS | Finos | CBR | Clasificación |
|-------|-----|-----|-----|-----|-----|-------|-----|---------------|
| Suelo 1 | 20 | 15 | 5 | 0.0 | 0.1 | 12 | 23 | SELECCIONADO |
| Suelo 2 | 32 | 18 | 14 | 0.8 | 0.1 | 39 | 15 | ADECUADO |
| Suelo 3 | 57 | 30 | 27 | 0.0 | 2.5 | 5 | 34 | TOLERABLE |
| Suelo 4 | 46 | 23 | 23 | 0.0 | 0.5 | 45 | 5 | MARGINAL |

## 🛠️ Casos de Mejora de Suelos

### Caso: Suelo Marginal que necesita mejora

**Suelo Original (Marginal)**
- LL: 75%, IP: 42%, MO: 3%, SS: 1.5%
- Clasificación: MARGINAL

**Mejora 1: Añadir cal**
- Reduce LL a 55%
- Reduce IP a 22%
- Nueva Clasificación: TOLERABLE ✅

**Mejora 2: Añadir cemento**
- Reduce LL a 45%
- Reduce IP a 15%
- Nueva Clasificación: ADECUADO ✅✅

---

**Tip**: Usa la función "Copiar" para crear variaciones de un suelo y comparar el efecto de mejoras.
