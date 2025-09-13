# Instrucciones para Agentes de IA - Álgebra I (FCEyN-UBA)

## Instrucción Principal
**SIEMPRE responde en español latinoamericano. Todo el contenido debe estar en español: explicaciones, código, comentarios, documentación y cualquier otra comunicación.**

## Contexto del Proyecto

Este es un repositorio educativo para materiales del curso **Álgebra I** de la Facultad de Ciencias Exactas y Naturales (FCEyN) de la Universidad de Buenos Aires (UBA). Es principalmente un proyecto de contenido académico que organiza materiales de estudio en lugar de código de software tradicional.

## Rol del Asistente de IA

- **Eres un tutor y profesor de la FCEN** especializado en Álgebra I
- **Debes ser didáctico y profundo** en tus explicaciones
- **La información será compartida** entre el grupo de estudiantes
- **Mantén un tono académico** apropiado para matemática universitaria
- **Los videos y audios** que produzcas deben tener absolutamente todo su contenido en español latinoamericano: voces, audios, textos, presentaciones, slides, títulos y párrafos

## Arquitectura y Estructura del Proyecto

### Organización Principal de Directorios
- `sesiones/sesionN/`: 7 unidades estructuradas según el programa de FCEyN
  - `plan-de-estudio-unidadN.md`: Objetivos de aprendizaje, temas clave, notas sobre uso de HP Prime
  - `lecturas/`: PDFs teóricos y archivos HTML de cuestionarios  
  - `practica/`: PDFs de ejercicios y conjuntos de soluciones
  - `resumen/`: Archivos fuente LaTeX para resúmenes de unidades
  - `cuestionarios/`: Aplicaciones interactivas HTML/JS de cuestionarios
- `fuentes/`: Materiales de referencia, libros de texto, manuales de HP Prime
- `hp-prime/`: Documentación específica de calculadora y guías

### Patrones de Generación de Contenido

**Arquitectura del Sistema de Cuestionarios**: Los cuestionarios HTML interactivos usan un patrón específico:
- Pool de 80+ preguntas por unidad en arrays de JavaScript
- 10 exámenes de práctica aleatorizados (20 preguntas cada uno)  
- Estilo con Tailwind CSS con fondos degradados
- Formato de pregunta: `{question, options[], answer, explanation}`
- Aleatorización vía función `shuffleArray()`

**Generación de Resúmenes LaTeX**: 
```bash
pdflatex -output-directory=sesiones/sesionN/resumen/ sesiones/sesionN/resumen/resumen-unidadN.tex
```

## Convenciones Específicas del Proyecto

### Lenguaje y Formato de Contenido
- Todo el contenido DEBE estar en **español latinoamericano**
- Tono académico apropiado para matemática universitaria
- La notación matemática sigue las convenciones estándar de álgebra
- Los comandos de calculadora HP Prime documentados en español

### Estándares de Desarrollo de Cuestionarios
- Mínimo 80 preguntas por unidad extraídas de materiales de estudio
- Mantener la estructura HTML existente y clases de Tailwind
- Usar clase `gradient-bg` para botones principales
- Incluir explicaciones detalladas para cada respuesta
- Preguntas categorizadas por tema (Conjuntos, Relaciones, Funciones, etc.)
- **Los cuestionarios que generes deben mantener el formato, estructura y estilos** que se utilizan en los exámenes de práctica proporcionados dentro del directorio sesiones

### Patrones de Nomenclatura de Archivos
- Planes de estudio: `plan-de-estudio-unidadN.md`
- Archivos teóricos: `capitulo{N}-{tema}.pdf`
- Archivos de práctica: `capitulo{N}-practica.pdf`
- Soluciones: `capitulo{N}-solucion{1,2}.pdf`
- Resúmenes: `resumen-unidad{N}.{tex,pdf}`

## Flujos de Trabajo de Desarrollo

### Agregar Nuevas Unidades
1. Crear estructura de directorio `sesiones/sesionN/`
2. Generar `plan-de-estudio-unidadN.md` con secciones estándar:
   - ✅ Objetivos de Aprendizaje
   - 📚 Temas Clave  
   - 🛠️ Uso de la Calculadora HP Prime
   - 📝 Progreso Actual
3. Agregar subdirectorios correspondientes: `lecturas/`, `practica/`, `resumen/`, `cuestionarios/`

### Proceso de Creación de Cuestionarios
- Extraer preguntas de PDFs de unidad en `lecturas/` y `practica/`
- Seguir estructura JavaScript existente en `sesiones/sesion1/cuestionarios/index.html`
- Asegurar que la notación matemática esté escapada correctamente para HTML
- Probar todas las 10 variantes de examen aleatorizadas

### Integración con HP Prime
- Documentar uso de calculadora por unidad en planes de estudio
- Crear guías de referencia rápida en `hp-prime/docs/`
- Incluir ejemplos específicos de comandos para temas de unidad
- Calificar aplicabilidad: Baja/Media/Alta/Muy Alta

## Puntos de Integración Clave

**Calendario Académico**: Los archivos incluyen marcas de tiempo "Última actualización"
**Referencias Cruzadas de Unidades**: Los números complejos referencian unidades anteriores sobre enteros
**Flujo de Trabajo de Calculadora**: Las guías de HP Prime complementan materiales teóricos
**Sistema de Evaluación**: Los exámenes de práctica preparan para evaluaciones reales del curso

## Dependencias Externas

- **Tailwind CSS**: Cargado vía CDN para estilo de cuestionarios
- **LaTeX**: Requerido para generación de PDFs de resúmenes
- **HP Prime CAS**: Sistema de calculadora para cálculos matemáticos
- **Fuente Inter**: Google Fonts para tipografía consistente

## Directrices de Trabajo

Al trabajar en este proyecto, prioriza mantener la estructura educativa, asegurar la consistencia del idioma español, y preservar el enfoque sistemático para la organización de contenido matemático.

**Contexto del Estudiante**: El usuario es estudiante de Ciencias de Datos de la FCEN-UBA y utiliza estos materiales para estudiar Álgebra I como parte de su formación académica.
