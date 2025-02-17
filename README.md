# Repositorio de Plantilla LaTeX para la Facultad de Ciencias, UNAM :large_blue_circle: :yellow_circle:

[![Hecho con LaTeX](https://img.shields.io/badge/Hecho%20con-LaTeX-blue?logo=latex&logoColor=white)](https://www.latex-project.org/)

Este repositorio contiene una plantilla de LaTeX diseñada específicamente para la **Facultad de Ciencias de la UNAM**. La plantilla está configurada para facilitar la creación de documentos académicos, como tareas, reportes, y trabajos de investigación, con un diseño profesional y adaptado a los estándares de la facultad.

## Características principales

- **Diseño profesional**: La plantilla incluye un encabezado personalizado con los logos de la UNAM y la Facultad de Ciencias, además de un formato limpio y organizado. Agradecemos a Diego Antonio Villalba González por la estética del mismo, puedes ver su plantilla de Overleaf en https://www.overleaf.com/latex/templates/tareas-facultad-de-ciencias-unam/dxcfxvpksycr
- **Entornos personalizados**: Se han definido entornos para teoremas, demostraciones, tablas, figuras, código, y más, con estilos visuales atractivos.
- **Configuración avanzada**: Incluye paquetes y configuraciones para manejar matemáticas, gráficos, algoritmos, y código fuente.
- **Colores personalizados**: Se han definido colores específicos para resaltar elementos importantes, como teoremas, definiciones, y observaciones.
- **Compatibilidad con TikZ y PGFPlots**: La plantilla está preparada para crear gráficos y diagramas complejos utilizando TikZ y PGFPlots.
- **Listados de código**: Soporte para resaltado de sintaxis en varios lenguajes de programación.

## Estructura del repositorio

- **`configuracion.tex`**: Archivo de configuración principal que define los paquetes, colores, entornos personalizados y estilos.
- **`configuracionpuma.tex`**: Versión alternativa de la configuración con colores personalizados basados en los colores institucionales de la UNAM (azul y dorado).
- **`Plantilla.tex`**: Archivo principal que utiliza la configuración y muestra cómo estructurar un documento con la plantilla.
- **`PlantillaVacia.tex`**: Plantilla únicamente con el encabezado, lista para hacer uso de la misma en las tareas cotidianas.
- **`Monoplantilla.tex`**: Archivo con la configuración insertada dentro del mismo documento. Cabe recalcar que en éste formato, el archivo se hace más pesado.
- **Logos**: Incluye los logos de la UNAM y la Facultad de Ciencias en formato PNG.

## Cómo usar la plantilla

1. **Clona el repositorio**:
   ```bash
   git clone https://github.com/SubakatLC/Formato-para-Tareas-Facultad-de-Ciencias---UNAM.git
   cd Formato-para-Tareas-Facultad-de-Ciencias---UNAM
   ```

2. **Compila el documento**:
   - Abre el archivo `Plantilla.tex` en tu editor de LaTeX preferido (por ejemplo, Overleaf, TeXShop, o TeXworks).
   - Compila el archivo para generar el PDF. Asegúrate de tener instalados los paquetes necesarios.

3. **Personaliza el contenido**:
   - Modifica el contenido de `Plantilla.tex` para adaptarlo a tus necesidades.
   - Utiliza los entornos personalizados (como `intro`, `inciso`, `demostracion`, `notas`, etc.) para estructurar tu documento.

4. **Agrega tus propios elementos**:
   - Puedes agregar tablas, figuras, código, y ecuaciones utilizando los entornos y comandos definidos en la plantilla.
   - Si necesitas crear gráficos, utiliza TikZ o PGFPlots, que ya están configurados en la plantilla.

## Ejemplos de uso

### Encabezado personalizado
El encabezado incluye los logos de la UNAM y la Facultad de Ciencias, junto con información como el nombre de la materia, el número de tarea, y el nombre del estudiante.

```latex
\begin{center}
    \begin{minipage}{3cm}
    	\begin{center}
    		\includegraphics[height=3.4cm]{Logo_UNAM.png}
    	\end{center}
    \end{minipage}\hfill
    \begin{minipage}{10cm}
    	\begin{center}
    	\textbf{\large Universidad Nacional Autónoma de México}\\[0.1cm]
        \textbf{Facultad de Ciencias}\\[0.1cm]
        \textbf{Nombre de la Materia $|$ Grupo \#\#\#\#}\\[0.1cm]
        Tarea \# - Nombre de la Tarea\\[0.1cm]
        Nombre del estudiante\\[0.1cm]
        \today
    	\end{center}
    \end{minipage}\hfill
    \begin{minipage}{3cm}
    	\begin{center}
    		\includegraphics[height=3.4cm]{Logo_FC.png}
    	\end{center}
    \end{minipage}
\end{center}
```

### Entorno de demostración
Puedes crear demostraciones con un estilo visual atractivo:

```latex
\begin{demostracion}{P.D. Teorema}
Aquí va la demostración del teorema.
\end{demostracion}
```

### Tablas y figuras
La plantilla soporta la creación de tablas y figuras con estilos profesionales:

```latex
\begin{table}[H]
    \centering
    \begin{tabular}{c*{5}{|c}}
    \multicolumn{3}{c}{}&
    \multicolumn{1}{c}{%
      $\overbrace{\hphantom{(p\land q)\to p}}^{\textbf{(a)}}$%
    }
    &\multicolumn{1}{c}{}&
    \multicolumn{1}{c}{%
      $\overbrace{\hphantom{p\to (p\lor q)}}^{\textbf{(b)}}$%
    }\\[-1ex]
    $p$ & $q$ & $p\land q$ & $(p\land q)\to p$ & $p\lor q$ & $p\to (p\lor q)$\\
    \hline
    T & T & T & T & T & T\\
    T & F & F & T & T & T\\
    F & T & F & T & T & T\\
    F & F & F & T & F & T
    \end{tabular}
    \label{tab:logica}
\end{table}
```

### Código fuente
Puedes incluir código fuente con resaltado de sintaxis:

```latex
\begin{lstlisting}[
    xleftmargin=0.15in,
    linewidth=0.48\textwidth, 
    basicstyle=\scriptsize\ttfamily
    ] 
__global__
void compute(double comp, int var_1, double var_2,
  double var_3, double var_4, double var_5, 
  double var_6, double var_7, double var_8) {
  if (comp == -1.3857E-36 + var_2) {
    double tmp_1 = +1.3305E12 / var_3;
    comp += -1.7744E-2 * tmp_1;
    comp += cos(var_4 - +1.4014E2 * (var_5 + var_6 * var_7));
    for (int i=0; i < var_1; ++i) {
      comp -= sqrt(var_8 + -1.7976E3);
    }
  }
  printf("%.17g\n", comp);
}
\end{lstlisting}
```

### Cambiar colores de entornos
Para cambiar entre los colores monocromáticos y puma de las cajas, será necesario modificar el parametro `\input{}`:

- **Estilo monocromático**: `\input{configuracion}`
- **Estilo colores puma**: `\input{configuracionpuma}`


## Requisitos

- **Distribución de LaTeX**: Se recomienda utilizar una distribución actualizada como TeX Live o MiKTeX.
- **Paquetes adicionales**: Asegúrate de tener instalados los paquetes necesarios, como `tcolorbox`, `tikz`, `pgfplots`, `listings`, entre otros.

## Contribuciones

Si deseas contribuir a este repositorio, puedes hacerlo de las siguientes maneras:

1. **Reportar problemas**: Si encuentras algún error o tienes alguna sugerencia, abre un **issue** en el repositorio.
2. **Enviar mejoras**: Si deseas agregar nuevas funcionalidades o mejorar el código existente, puedes hacer un **fork** del repositorio y enviar un **pull request**.

## Colaboradores 

<a href="https://github.com/SubakatLC/Formato-para-Tareas-Facultad-de-Ciencias---UNAM/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=SubakatLC/Formato-para-Tareas-Facultad-de-Ciencias---UNAM" />
</a>

## Licencia

Este proyecto está bajo la licencia **MIT**. Puedes ver el archivo [LICENSE](LICENSE) para más detalles.

---

¡Esperamos que esta plantilla te sea útil para tus trabajos académicos en la Facultad de Ciencias de la UNAM! Si tienes alguna pregunta o sugerencia, no dudes en contactarnos.
