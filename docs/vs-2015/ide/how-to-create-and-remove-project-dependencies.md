---
title: 'Cómo: Crear y quitar dependencias del proyecto | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.ProjectDependenciesDlg
helpviewer_keywords:
- vs.build.projectdependencies
- project dependencies
- builds [Visual Studio], setting up
- project build configurations, dependencies
- dependencies, project
- projects [Visual Studio], dependencies
ms.assetid: e2a0a8ff-dae7-40a8-b774-b88aa5235183
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3626cc4c13600b0a6f20cc40713bd77f4527a3ce
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2018
ms.locfileid: "47578712"
---
# <a name="how-to-create-and-remove-project-dependencies"></a>Cómo: Crear y quitar dependencias del proyecto
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La versión más reciente de este tema puede encontrarse en [Cómo: crear y quitar dependencias del proyecto](https://docs.microsoft.com/visualstudio/ide/how-to-create-and-remove-project-dependencies).  
  
Al compilar una solución que contiene varios proyectos, puede ser necesario compilar determinados proyectos primero para generar código que usan otros proyectos. Cuando un proyecto consume código ejecutable generado por otro proyecto, al proyecto que genera el código se le hace referencia como una dependencia de proyecto del proyecto que consume el código. Dichas relaciones de dependencia pueden definirse en el cuadro de diálogo **Dependencias del proyecto**.  
  
### <a name="to-assign-dependencies-to-projects"></a>Para asignar dependencias a los proyectos  
  
1.  En el Explorador de soluciones, seleccione un proyecto.  
  
2.  En el menú **Proyecto**, pulse **Dependencias del proyecto**.  
  
     Se abre el cuadro de diálogo **Dependencias del proyecto**.  
  
    > [!NOTE]
    >  La opción **Dependencias del proyecto** solo está disponible en una solución con más de un proyecto.  
  
3.  En la pestaña **Dependencias**, seleccione un proyecto del menú desplegable **Proyecto**.  
  
4.  En el campo **Depende de**, seleccione la casilla de cualquier otro proyecto que debe compilarse antes de que lo haga este proyecto.  
  
 Su solución debe constar de más de un proyecto antes de que pueda crear dependencias de proyecto.  
  
### <a name="to-remove-dependencies-from-projects"></a>Para quitar las dependencias de los proyectos  
  
1.  En el Explorador de soluciones, seleccione un proyecto.  
  
2.  En el menú **Proyecto**, pulse **Dependencias del proyecto**.  
  
     Se abre el cuadro de diálogo **Dependencias del proyecto**.  
  
    > [!NOTE]
    >  La opción **Dependencias del proyecto** solo está disponible en una solución con más de un proyecto.  
  
3.  En la pestaña **Dependencias**, seleccione un proyecto del menú desplegable **Proyecto**.  
  
4.  En el campo **Depende de**, desactive las casillas junto a cualquier otro proyecto que ya no son dependencias de este proyecto.  
  
## <a name="see-also"></a>Vea también  
 [Compilar y limpiar proyectos y soluciones en Visual Studio](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)   
 [Compilar y generar](../ide/compiling-and-building-in-visual-studio.md)   
 [Descripción de las configuraciones de compilación](../ide/understanding-build-configurations.md)   
 [NO ESTÁ EN LA COMPILACIÓN Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)


