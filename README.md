# 🚧 Clasificador de Suelos PG-3

Herramienta web interactiva para clasificar suelos según la **Normativa PG-3 de Carreteras (España)**.

![License](https://img.shields.io/badge/license-MIT-blue)
![Version](https://img.shields.io/badge/version-1.0.0-green)

## ✨ Características

- 📋 **Entrada de datos simple**: Introducción de parámetros de un suelo a la vez
- 🧮 **Cálculo automático**: IP se calcula automáticamente (LL - LP)
- 📊 **Gráfica de Casagrande interactiva**: Visualización de la posición del suelo
- ⚙️ **Doble clasificación**:
  - **Método 1**: Tabla de características PG-3
  - **Método 2**: Gráfica de Casagrande
  - **Resultado final**: Aplica el peor resultado (más restrictivo)
- 📈 **Tabla de histórico completo** con opciones:
  - ✏️ **Editar**: Modifica los datos del suelo
  - 📋 **Copiar**: Duplica un suelo para crear variaciones
  - 🗑️ **Eliminar**: Borra de la lista
- 🎨 **Interfaz clara y profesional**:
  - Diseño responsivo (móvil y desktop)
  - Códigos de color según clasificación
  - Todo en español

## 🚀 Uso Rápido

### En línea (GitHub Pages)
1. Accede a: [https://tsu7007.github.io/clasificador-suelos-pg3/](https://tsu7007.github.io/clasificador-suelos-pg3/)
2. Rellena los parámetros del suelo
3. Haz clic en "Clasificar Suelo"
4. Visualiza la clasificación y la posición en la gráfica

### Local
1. Descarga o clona el repositorio:
   ```bash
   git clone https://github.com/tsu7007/clasificador-suelos-pg3.git
   cd clasificador-suelos-pg3
   ```

2. Abre `index.html` en tu navegador (no requiere servidor)

## 📋 Parámetros de Entrada

| Parámetro | Símbolo | Unidad | Descripción |
|-----------|---------|--------|-------------|
| Límite Líquido | LL | % | Contenido de agua en el límite entre estado plástico y líquido |
| Límite Plástico | LP | % | Contenido de agua en el límite entre estado sólido y plástico |
| Índice Plasticidad | IP | % | Calculado automáticamente: LL - LP |
| Materia Orgánica | MO | % | Contenido de materia orgánica del suelo |
| Sales Solubles | SS | % | Contenido de sales solubles |
| Finos | Finos | % | Porcentaje que pasa por el tamiz #0,080 (0,080 mm) |
| Índice Portante | CBR | — | California Bearing Ratio (valor de resistencia) |

## 🎯 Clasificaciones PG-3

La herramienta clasifica en 4 categorías:

### 1. ✅ **Seleccionados**
- Suelos de máxima calidad
- Mínima restricción en el uso
- **Límites estrictos**: MO < 0.2%, SS < 0.2%, Finos < 25%, LL < 30%, IP < 10%

### 2. ✅ **Adecuados**
- Suelos de buena calidad
- Pocas restricciones
- **Límites moderados**: MO < 1%, SS < 0.2%, Finos < 35%, LL < 40%, IP > 4%

### 3. ⚠️ **Tolerables**
- Suelos aceptables con restricciones
- Requieren control de calidad
- **Límites flexibles**: MO < 2%, SS < 1%, Finos < 50%, LL < 65%

### 4. ⛔ **Marginales**
- Suelos con limitaciones significativas
- Requieren mejora o tratamiento
- **Límites permisivos**: MO < 5%, LL < 90%

## 📊 Método de Casagrande

La gráfica utiliza la **Línea A** según la ecuación:

```
IP = 0.73 (LL - 20)
```

Esta línea separa:
- **Arcillas inorgánicas** (arriba de la línea)
- **Limos inorgánicos** (abajo de la línea)

## 🔧 Lógica de Clasificación

La herramienta evalúa ambos métodos y aplica **el peor resultado**:

1. **Método 1**: Verifica contra la tabla de características PG-3
2. **Método 2**: Verifica la posición en la gráfica de Casagrande
3. **Resultado final**: Toma la clasificación más restrictiva

```
Si Método 1 = Adecuado y Método 2 = Tolerable → Resultado = Tolerable
```

## 📁 Estructura del Proyecto

```
clasificador-suelos-pg3/
├── index.html          # Aplicación completa (HTML + CSS + JS)
├── README.md           # Este archivo
└── .gitignore          # Configuración de Git
```

## 💻 Requisitos

- Navegador web moderno (Chrome, Firefox, Safari, Edge)
- **No requiere** instalación ni dependencias externas
- Funciona completamente offline

## 🛠️ Desarrollo

Para modificar la herramienta:

1. **Fork del repositorio**:
   ```bash
   git clone https://github.com/tsu7007/clasificador-suelos-pg3.git
   ```

2. **Editar `index.html`**:
   - CSS en la sección `<style>`
   - JavaScript en la sección `<script>`

3. **Hacer push de cambios**:
   ```bash
   git add .
   git commit -m "Descripción de cambios"
   git push
   ```

## 📝 Ejemplos de Clasificación

### Ejemplo 1: Suelo Seleccionado
```
LL: 25%    LP: 15%    IP: 10%
MO: 0.1%   SS: 0.1%   Finos: 20%   CBR: 40
→ Clasificación: SELECCIONADO ✅
```

### Ejemplo 2: Suelo Tolerable
```
LL: 45%    LP: 25%    IP: 20%
MO: 1.5%   SS: 0.8%   Finos: 40%   CBR: 15
→ Clasificación: TOLERABLE ⚠️
```

### Ejemplo 3: Suelo Marginal
```
LL: 80%    LP: 35%    IP: 45%
MO: 4.0%   SS: 2.0%   Finos: 45%   CBR: 5
→ Clasificación: MARGINAL ⛔
```

## 🌐 Referencias Normativas

- **PG-3**: Pliego de Prescripciones Técnicas Generales para obras de carreteras (España)
- **AASHTO**: American Association of State Highway and Transportation Officials
- **Sistema Unificado**: USCS (Unified Soil Classification System)
- **Método Casagrande**: Clasificación de suelos arcillosos y limosos

## 📚 Bibliografía

1. Ministerio de Fomento (2016). *PG-3: Pliego de Prescripciones Técnicas Generales para obras de carreteras*
2. Casagrande, A. (1948). *Classification and Identification of Soils*
3. Das, B.M. (2016). *Principios de Ingeniería de Cimentaciones*

## 🐛 Reportar Problemas

Si encuentras algún error o tienes sugerencias:

1. Abre un **Issue** en GitHub
2. Describe el problema claramente
3. Incluye datos de ejemplo si es posible

## 📄 Licencia

MIT License - Libre para usar, modificar y distribuir

## 👨‍💻 Autor

Desarrollado como herramienta educativa para estudiantes de Ingeniería Civil.

---

**Última actualización**: Enero 2026
**Versión**: 1.0.0
