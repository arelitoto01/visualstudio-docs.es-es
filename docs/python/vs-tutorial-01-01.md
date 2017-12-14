---
title: Trabajar con Python en Visual Studio, paso 1 | Microsoft Docs
ms.custom: 
ms.date: 09/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: get-started-article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: d6c5cd4395ea0251027edbc94019637b72a630a8
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="working-with-python-in-visual-studio"></a>Trabajo con Python en Visual Studio

Python es un lenguaje de programación popular confiable, flexible, fácil de aprender, de uso libre en todos los sistemas operativos y admitido por una gran comunidad de desarrolladores y muchas bibliotecas gratuitas. El lenguaje es compatible con todos los modos de desarrollo, lo que incluye aplicaciones web, servicios web, aplicaciones de escritorio, scripting e informática científica, y lo usan muchas universidades, científicos, programadores ocasionales y desarrolladores profesionales.

Visual Studio proporciona compatibilidad de primera clase con el lenguaje Python. Este tutorial le guiará a través de los pasos siguientes:

- [Paso 0: Instalación](vs-tutorial-01-00.md)
- [Paso 1: Crear un proyecto de Python (en este tema)](#step-1-create-a-new-python-project)
- [Paso 2: Escribir y ejecutar código para ver IntelliSense de Visual Studio en funcionamiento](vs-tutorial-01-02.md)
- [Paso 3: Crear más código en la ventana interactiva de REPL](vs-tutorial-01-03.md)
- [Paso 4: Ejecutar el programa completado en el depurador de Visual Studio](vs-tutorial-01-04.md)
- [Paso 5: Instalar paquetes y administrar entornos de Python](vs-tutorial-01-05.md)
- [Paso 6: Trabajar con Git](vs-tutorial-01-06.md)

## <a name="prerequisites"></a>Requisitos previos

- Visual Studio 2017 con la carga de trabajo de Python instalada. Vea las instrucciones en el [Paso 0](vs-tutorial-01-00.md).

## <a name="step-1-create-a-new-python-project"></a>Paso 1: Crear un proyecto de Python

Visual Studio usa los *proyectos* para administrar todos los archivos que se combinan para generar una aplicación, incluido el código fuente, los recursos, las configuraciones, etc. Un proyecto formaliza y mantiene la relación entre todos los archivos del proyecto, así como los recursos externos que se comparten entre varios proyectos. Por lo tanto, un proyecto permite que la aplicación se expanda sin esfuerzo y crezca mucho más fácilmente que mediante la administración de las relaciones de un proyecto en carpetas, scripts y archivos de texto ad hoc, o incluso su propia mente.

En este tutorial, empezará con un proyecto simple que contiene un único archivo de código vacío.

1. En Visual Studio, seleccione **Archivo > Nuevo proyecto** (CTRL+Mayús+N). Se abrirá el cuadro de diálogo **Nuevo proyecto**. Aquí puede examinar plantillas de diferentes lenguajes. Seleccione una para el proyecto y especifique dónde colocará los archivos Visual Studio.

1. Para ver las plantillas de Python, seleccione **Plantillas > Otros lenguajes > Python** en el lado izquierdo, o busque "Python". Si no recuerda la ubicación de una plantilla en el árbol de lenguajes, lo mejor es que use la búsqueda.

    ![Cuadro de diálogo Nuevo proyecto con los proyectos de Python](media/vs-getting-started-python-01-new-project.png)

1. Observe que la compatibilidad de Python con Visual Studio incluye una serie de plantillas de proyecto, incluidas aplicaciones web que usan los marcos Bottle, Flask y Django. Para los fines de este tutorial, en cambio, comenzaremos con un proyecto vacío. 

1. Elija la plantilla **Aplicación de Python**, especifique un nombre para el proyecto y seleccione **Aceptar**. 

1. Después de unos minutos, Visual Studio muestra la estructura del proyecto en la ventana del **Explorador de soluciones** (1). El archivo de código predeterminado se abre en el editor (2). También aparece la ventana de propiedades (3), en la que se muestra información adicional sobre los elementos seleccionados en el Explorador de soluciones, incluida su ubicación exacta en el disco.
 
    ![Explorador de soluciones con un proyecto de Python](media/vs-getting-started-python-02-windows.png)
 
1. Tómese su tiempo para familiarizarse con el Explorador de soluciones, que es donde examinará los archivos y las carpetas del proyecto.
    
    ![El Explorador de soluciones expandido para mostrar diversas características](media/vs-getting-started-python-03-solution-explorer.png)

    (1) El proyecto está resaltado en negrita. Tiene el nombre que le ha asignado en el cuadro de diálogo Nuevo proyecto. En el disco, este proyecto estará representado mediante un archivo `.pyproj` en la carpeta del proyecto.

    (2) En el nivel superior se encuentra una *solución*, que de forma predeterminada tiene el mismo nombre que el proyecto. Una solución, representada por un archivo `.sln` en el disco, es un contenedor para uno o más proyectos relacionados. Por ejemplo, si escribe una extensión de C++ para la aplicación de Python, ese proyecto de C++ puede residir dentro de la misma solución. La solución también podría contener un proyecto para un servicio web, junto con proyectos para programas de prueba dedicados. 

    (3) Bajo el proyecto verá los archivos de código fuente, en este caso, un solo archivo `.py`. Al seleccionar un archivo, se muestran sus propiedades en la ventana Propiedades. Si hace doble clic en un archivo, se abrirá de la manera más adecuada.

    (4) Bajo el proyecto también se encuentra el nodo **Entornos de Python**. Si lo expande, verá los intérpretes de Python disponibles. Expanda un nodo de intérprete para ver las bibliotecas que se instalan en ese entorno (5).

    Haga clic con el botón derecho en cualquier nodo o elemento del Explorador de soluciones para tener acceso a un menú con los comandos aplicables. Por ejemplo, el comando **Cambiar nombre** permite cambiar el nombre de un nodo o elemento, incluido el proyecto y la solución.
    
## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Escribir y ejecutar código](vs-tutorial-01-02.md)

## <a name="going-deeper"></a>Mayor profundización

- [Python Projects in Visual Studio](python-projects.md) (Proyectos de Python en Visual Studio)
- [Obtenga información sobre el lenguaje Python en python.org](https://www.python.org)
- [Python para principiantes](https://www.python.org/about/gettingstarted/) (python.org)
- [Cursos gratuitos de Python en Microsoft Virtual Academy](https://mva.microsoft.com/search/SearchResults.aspx#!q=python)
- [Preguntas principales de Python en Microsoft Virtual Academy](https://aka.ms/mva-top-python-questions)