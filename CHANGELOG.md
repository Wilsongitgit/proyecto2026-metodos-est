# Changelog — Proyecto Metodología Estadística

Todos los cambios notables en este proyecto se documentan en este archivo.

---

## [2026-09-24] — Mejoras de redacción, visualización y documentación

### Agregado
- **Subtítulos descriptivos** a todas las figuras (7 figuras) con `fig-cap:` en Quarto
- **Subtítulos descriptivos** a todas las tablas (15 tablas) con `tbl-cap:` en Quarto
- **Nombres descriptivos** a cada tabla mostrada en los bloques estadísticos (chi-cuadrado, regresión, diagnóstico)
- **Conclusiones resumidas y acertivas** después de cada gráfica principal (5 conclusiones en total):
  - Gráfico circular: concentración regional (Andina 58,8%)
  - Gráfico de barras: variabilidad de rendimiento (3-16 t/ha)
  - Histograma: no normalidad y asimetría positiva
  - Diagrama caja/Q-Q: diferencias entre ciclos de cultivo
  - Regresión: heterocedasticidad y elasticidad 0,88

### Mejorado
- **Redacción metodológica:** Clarificación sobre clave de emparejamiento y ciclo de cultivo
- **Justificación inferencial:** Ampliación sobre validez de inferencia con EVA como estimaciones
- **Documentación de limitaciones:** Detalles cuantitativos sobre cambio de estructura (1.062 unidades con ciclo "anual")
- **Multiplicidad de contrastes:** Cuantificación de riesgo de falso positivo (~40% con 10+ pruebas)
- **README.md:** Actualización de cifras (población 10.815, muestra 968) y resumen de hallazgo principal

### Corregido
- **Error de sintaxis:** Eliminación de carácter "w" extra en línea de merge
- **Referencias bibliográficas:** Limpieza de 7 referencias BibTeX no citadas
- **Hipervincilación de referencias:** Conversión de referencias DOI/URL a formato Markdown clickeable

### Cambios técnicos
- Configuración VS Code: `.vscode/settings.json` con intérprete automático `.venv`
- Manejo de CSV con saltos de línea en nombres de columnas (función `_norm_col()`)
- Glob patterns actualizados para priorizar archivos locales sobre descargas
- Restricción pandas: `>=2.0,<3.0` por cambios incompatibles en v3.x

---

## Commits realizados en esta sesión

```
a1919ac Mover conclusiones al interior de los bloques de gráficas
e9b3486 Agregar conclusiones resumidas a las gráficas principales
60fe427 Agregar nombres descriptivos a las tablas
a6e29fd Agregar subtítulos descriptivos a todas las figuras y tablas
6ce9912 Mejoras de redacción y precisión metodológica
44716fa Limpiar referencias bibliográficas innecesarias y mejorar hipervincilación
c562ad5 Limpiar YAML frontmatter y eliminar referencias innecesarias
456dd24 Arreglar bug en carga de datos: CSV con saltos de línea en nombres de columnas
c76493f Configurar VS Code y entorno para Quarto dashboard
```

---

## Estado actual del documento

✅ **Documento renderizado:** `informe.html` (6.3 MB, autocontenido)  
✅ **Código Python:** Ejecutable, sin errores de sintaxis  
✅ **Referencias:** 12 referencias APA 7, todas citadas e hipervinciladas  
✅ **Figuras:** 7 figuras con subtítulos y conclusiones  
✅ **Tablas:** 15 tablas con subtítulos y nombres descriptivos  
✅ **Repositorio:** Sincronizado con GitHub (`Wilsongitgit/proyecto2026-metodos-est`)

---

## Notas para futuras sesiones

- El documento es completamente reproducible: renderizar dos veces con semilla 2026 produce idénticas cifras
- Los CSV se descargan automáticamente de datos.gov.co si no están en `datos/`
- Las conclusiones se muestran dentro de los cards (dentro del mismo cuadro que la figura)
- Todas las pruebas estadísticas están documentadas con hipótesis, supuestos y decisiones
