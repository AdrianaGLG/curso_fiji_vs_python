# Segmentación y cuantificación reproducible de puncta de Tau oligomérica

**Comparación entre Fiji y Python sobre las mismas imágenes confocales**

📄 **Sitio del proyecto:** https://adrianaglg.github.io/curso_fiji_vs_python/

---

## De qué se trata

Dos personas analizan la misma imagen de microscopía confocal. Una usa Fiji, otra usa
Python. Aplican los pasos conceptuales de cada herramienta: elegir el canal, proyectar el z-stack,
umbralizar, etiquetar objetos y medir. ¿Obtienen el mismo resultado?

Este repositorio implementa un flujo clásico de segmentación **dos veces** sobre las
mismas imágenes, para medir cuánto concuerdan ambas herramientas y dónde se separan.

### Pregunta principal

> ¿En qué medida dos implementaciones equivalentes de un mismo flujo clásico, una en
> Fiji y otra en Python, producen segmentaciones y cuantificaciones concordantes de los
> puncta intracelulares reconocidos por el anticuerpo T22 en las mismas imágenes
> confocales?

El objetivo **no** es evaluar el efecto biológico del tratamiento. Las imágenes
funcionan como caso de estudio para enseñar segmentación, cuantificación,
automatización y comparación entre herramientas de análisis de bioimágenes.

## Alcance

- El análisis se realiza en **2D**, sobre la proyección de máxima intensidad del z-stack.
- Se trabaja sobre el **canal verde** (Alexa Fluor 488 / T22).
- Los objetos se describen como *puncta segmentados en la proyección*, sin asumir que
  cada uno corresponda a un agregado individual en tres dimensiones.
- Sin una máscara manual de referencia, lo que se mide es **concordancia entre
  métodos**, no exactitud.

### Precisión sobre el marcador

El anticuerpo T22 reconoce principalmente **Tau oligomérica**. No constituye por sí solo
un marcador de fosforilación, por lo que la señal no se describe como "Tau fosforilada"
en ninguna parte de este trabajo.

## Estructura del repositorio

```
curso_fiji_vs_python/
├── _quarto.yml          Configuración del sitio (menú, tema, formato)
├── custom.scss          Paleta, tipografía y estilos
├── index.qmd            Portada
├── contexto.qmd         Contexto y pregunta
├── datos.qmd            Imágenes, canales y calibración
├── flujo.qmd            Flujo común: la tabla de equivalencias
├── fiji.qmd             Implementación en Fiji / ImageJ
├── python.qmd           Implementación en Python
├── comparacion.qmd      Concordancia entre ambas máscaras
├── presentacion.qmd     Diapositivas
├── integrantes.qmd      Autores y agradecimientos
└── media/               Figuras del tutorial
```

## Cómo trabajar sobre el sitio

Requiere [Quarto](https://quarto.org/docs/get-started/) instalado.

```bash
git clone https://github.com/AdrianaGLG/curso_fiji_vs_python.git
cd curso_fiji_vs_python
quarto preview
```

`quarto preview` abre el sitio en el navegador y lo actualiza con cada archivo guardado.

Para publicar los cambios:

```bash
git add .
git commit -m "Descripción del cambio"
git push
quarto publish gh-pages
```

## Autores

| | Filiación |
|---|---|
| **Pablo Pomato** | Servicio de Microscopía, IBYME – CONICET |
| **Rodrigo Tomás Grau** | Investigador Asistente CONICET, IMMCA |
| **María José Godás Willems** | IFIBA – CONICET |
| **Adriana Gabriela López Guerra** | Lab. de Biología Celular y Molecular, Instituto de Investigaciones Biomédicas (UCA – CONICET) |

## Agradecimientos

Trabajo desarrollado en el marco del **Taller de Fundamentos en Análisis de Bioimágenes
(Formación de Formadores)**, Buenos Aires, agosto de 2026.

Al **Centro de Microscopía Avanzada (CMA)** y a la **Facultad de Ciencias Exactas y
Naturales de la Universidad de Buenos Aires** por la organización del taller y el acceso
a la infraestructura. Al comité organizador y al equipo de instructores por el marco
conceptual y metodológico. A **FUNDACEN** por el apoyo que permitió la participación de
asistentes de distintos puntos del país y de la región.

## Licencia

Este material se distribuye bajo licencia
[CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/deed.es):
puede reutilizarse y adaptarse con atribución, para fines no comerciales.
