# Trabajo de graduación: Desarrollo de una herramienta de simulación para modelar el efecto piezoeléctrico utilizando PINNs

Este repositorio contiene el código asociado al desarrollo del trabajo de graduación **Desarrollo de una herramienta de simulación para modelar el efecto piezoeléctrico utilizando PINNs**, presentado por Daniel González Carrillo, carné 20293, para optar al grado académico de  Licenciado en Ingeniería en Ciencias
 de la Computación y Tecnologías de la Información.
 
## Descripción del proyecto
 
Este proyecto tiene como objetivo desarrollar una herramienta de simulación basada en Redes Neuronales Informadas por la Física (Physics-Informed Neural Networks, PINNs) para modelar fenómenos relacionados con el efecto piezoeléctrico. Esta tecnología combina ecuaciones diferenciales parciales (PDEs) con machine learning avanzado.

A través de este trabajo, se busca resolver y analizar casos específicos como la transferencia de calor, la dinámica de fluidos y el efecto piezoeléctrico (directo e indirecto) para una viga en voladizo. Como principal resultado, se demuestra que se pueden aplicar las PINNs al efecto piezoeléctrico.

Este repositorio incluye una colección de notebooks que presentan implementaciones detalladas y reproducibles para cada uno de los fenómenos modelados. La estructura del proyecto permite un fácil acceso y comprensión de los diferentes casos de estudio.

---

## Instrucciones de instalación

A continuación se detallan los requisitos para la ejecución de los notebooks.

### Requisitos previos

Antes de utilizar los notebooks es necesario asegurarse de tener las siguientes herramientas:

- **Python 3.8 o superior**

- **pip**

- **Git**

- **Entorno de ejecución adecuado**  
  - Para ejecutar los notebooks en local: Instalar Jupyter Notebook o Jupyter Lab.  
  - **Nota**: Si se trabaja localmente, es necesario instalar las dependencias adicionales listadas en el archivo  [`requirements.txt`](./src/requirements.txt). Para instalarlas, se utiliza el comando:
    ```bash
    pip install -r requirements.txt
    ```

  - Para usar Google Colab: No es necesario configurar un entorno local, pero se recomienda ejecutar las instalaciones de dependencias en cada notebook (Los detalles de cual notebook es mejor correr local y cual en Google Colab se indican más adelante).

## Instalación y ejecución

Pasos para instalar y ejecutar el proyecto:

1. Clonar el repositorio localmente:  
   ```bash
   git clone https://github.com/csuvg/PG-2024-20293
   cd PG-2024-20293

2. Creación de un entorno virtual (opcional):
    ```bash
    python -m venv venv
    source venv/bin/activate  # En Windows: venv\Scripts\activate
    ```
3. Instalar las dependencias (si no se realizó previamente):
    ```bash
    pip install -r requirements.txt
    ```
4. Ejecución de notebooks:
    - Local: Utilizar Jupyter Notebook o Jupyter Lab para generar un servidor donde se pueda ejecutar el notebook.
    - Google Colab: Cargar notebooks en Google Drive y abrirlos con la interfaz para poder ejecutarlos.
    
---

## Estructura del Proyecto

### Demo
Esta carpeta tiene un video que muestra los resultados de la simulación del efecto piezoeléctrico utilizando PINNs.

- **Video demostrativo**:  
  [Descargar y visualizar el video aquí](./demo/demo.mp4)

### Docs
En esta carpeta se encuentra el documento de la tesis.

- **Documento de tesis**:  
  [Acceder al documento aquí](./docs/informe.pdf)

### PINNs

El código donde se desarrolló el código de las PINN está organizado en carpetas según los fenómenos modelados dentro de la carpeta principal `src`:

#### 1. **Heat**
   - **Notebook**: [heat_PINN.ipynb](./src/Heat/heat_PINN.ipynb)  
     **Descripción**:  
     Este notebook implementa un modelo para resolver problemas de **transferencia de calor**. Utiliza PINNs para simular la ecuación del calor en un una varilla de una dimensión.
     **Entorno de ejecución**:
        - Procesador: 11th Gen Intel(R) Core(TM) i7-11800H @ 2.30GHz, 2304 MHz, 8 núcleos, 16 procesadores lógicos.
        - Memoria RAM: 32 GB.
---

#### 2. **Navier-Stokes**
   - **Notebook**: [NS_PINN_geo.ipynb](./src/Navier-Stokes/NS_PINN_geo.ipynb)  
     **Descripción**:  
     Aquí se modelan problemas relacionados con la **dinámica de fluidos** a través de las ecuaciones de Navier-Stokes. Este notebook está diseñado para demostrar cómo las PINNs pueden abordar la simulación de un flujo en un conducto que tiene un cilindro en medio. El análisis está hecho en estado estacionario.
    **Entorno de ejecución**:
        - Google Colab: GPU Tesla T4.
        - Memoria RAM: 15 GB.
---

#### 3. **Piezoelectricity**

   - **Notebook 1**: [Geometric_creation.ipynb](./src/Piezoelectricity/Geometric_creation.ipynb)  
     **Descripción**:  
     Este notebook genera los puntos de colocación y de frontera para una **viga en voladizo** que se modela bajo el efecto piezoeléctrico. Proporciona la base geométrica para los otros notebooks relacionados con el efecto piezoeléctrico.  
     **Entorno de ejecución**:
        - Google Colab (sin GPU Tesla T4).
        - Memoria RAM: 15 GB.

   - **Notebook 2**: [Indirect_effect_PINN.ipynb](./src/Piezoelectricity/Indirect_effect_PINN.ipynb)  
     **Descripción**:  
     Este notebook aborda el **efecto piezoeléctrico indirecto**, donde una estimulación eléctrica en un material genera una deformación mecánica. Está enfocado en modelar una viga en voladizo piezoeléctrica en 2D.

   - **Notebook 3**: [Direct_effect_PINN.ipynb](./src/Piezoelectricity/Direct_effect_PINN.ipynb)  
     **Descripción**:  
     Este notebook se enfoca en modelar el **efecto piezoeléctrico directo**, en el cual las deformaciones mecánicas en un material generan una respuesta eléctrica (voltaje). Está enfocado en modelar una viga en voladizo piezoeléctrica en 2D.

   

  - **Entorno de ejecución (para los notebooks de Direct y Indirect effect)**:
    - **Plataforma**: Google Colab (con GPU Tesla T4).
    - **Memoria RAM**: 15 GB.

---
