# Proyecto final 2 — Informe de Inferencia Estadística

Dashboard de Quarto con motor Python. Todo el análisis se ejecuta al renderizar:
no hay cifras escritas a mano en el texto, cada número del informe sale del código.

---

## 1. Qué poner en la carpeta

```
Proyecto_final_2/
├── informe.qmd              <- el informe (único archivo que se edita)
├── requirements.txt
├── README.md
├── logo_universidad.png     <- FALTA: pon aquí el logo institucional
└── datos/
    ├── Evaluaciones_Agropecuarias_Municipales_EVA_20260920.csv
    └── Evaluaciones_Agropecuarias_Municipales_–_EVA._2019_-_2025._Base_Agrícola_20260920.csv
```

Si la carpeta `datos/` está vacía, el informe descarga los dos CSV desde datos.gov.co
la primera vez que se renderiza (unos 68 MB, tarda un par de minutos).

---

## 2. Requisitos, una sola vez

**Quarto:** descargar de <https://quarto.org/docs/get-started/> e instalar. Se necesita
la versión 1.4 o superior; el formato `dashboard` no existe en versiones anteriores.

**Extensiones de VS Code:**

- `quarto.quarto` (Quarto)
- `ms-python.python` (Python)
- `ms-toolsai.jupyter` (Jupyter)

**Paquetes de Python**, desde la terminal de VS Code y dentro de la carpeta del proyecto:

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

Después, en VS Code: `Ctrl+Shift+P` → *Python: Select Interpreter* → elegir `.venv`.

---

## 3. Cómo trabajar

**Ver el resultado:** abrir `informe.qmd` y pulsar el botón **Preview** de la barra
superior, o `Ctrl+Shift+K`. Se abre el dashboard al lado y se actualiza al guardar.

**Generar el archivo final:**

```powershell
quarto render informe.qmd
```

Produce `informe.html`, autocontenido en un solo archivo: se puede subir tal cual a la
plataforma o enviar por correo, sin carpetas adicionales.

**Ejecutar un bloque suelto** mientras se edita: clic en *Run Cell* sobre el bloque, o
`Ctrl+Shift+Enter`.

---

## 4. Lo que hay que completar antes de entregar

Busca estas marcas en `informe.qmd` (`Ctrl+F`):

| Marca | Qué reemplazar |
|---|---|
| `INTEGRANTE 1 · INTEGRANTE 2 · INTEGRANTE 3` | Nombres reales, en el YAML de arriba y en la página de Presentación |
| `NRC_DEL_CURSO` | Número de NRC |
| `logo_universidad.png` | Colocar el archivo del logo en la carpeta |
| Ciudad | Dice Cartagena de Indias; cambiar si corresponde |

---

## 5. Estructura del informe

Cada página del dashboard corresponde a una sección de la rúbrica:

| Página | Sección de la rúbrica | Peso |
|---|---|---|
| Presentación | Presentation | 0,15 |
| Introducción | Introduction | 0,25 |
| Marco teórico | Marco teórico | 0,30 |
| Datos y EDA + Descriptivas + Distribuciones | Dataset | 1,00 |
| Métodos | Materials and Methods | 0,45 |
| Normalidad, Muestreo, Intervalos, Hipótesis 1 y 2 muestras, Independencia, Regresión | Result | 2,20 |
| Discusión | Discusión de resultados | 0,25 |
| Conclusiones | Conclusiones | 0,20 |
| Referencias | Referencias | 0,20 |

---

## 6. Diseño estadístico, en corto

- **Unidad de análisis:** municipio × cultivo (pareado).
- **Pareamiento:** la misma unidad medida en 2018 (base 2006-2018) y en 2024 (base 2019-2025).
- **Población de estudio:** 10.815 unidades con registro válido en ambos años.
- **Muestra:** 968 unidades, estratificada por región natural, con margen de error del 2 % y
  confianza del 95 %.
- **Semilla:** 2026. Renderizar dos veces da exactamente las mismas cifras.
- **Hallazgo principal:** El rendimiento agrícola mejoró en promedio 1,7 t/ha (2018–2024);
  la mejora está asociada al tipo de cultivo, no a la región.

---

## 7. Si algo falla

| Síntoma | Causa y solución |
|---|---|
| `quarto: command not found` | Quarto no está instalado o falta reiniciar VS Code |
| `Unknown format: dashboard` | Versión de Quarto anterior a la 1.4; actualizar |
| `ModuleNotFoundError` | El intérprete seleccionado no es el del entorno virtual |
| El render tarda muchísimo la primera vez | Está descargando los CSV; colocarlos en `datos/` lo evita |
| Las fórmulas se ven como `$...$` | Falta conexión a internet: MathJax se carga desde la red |
