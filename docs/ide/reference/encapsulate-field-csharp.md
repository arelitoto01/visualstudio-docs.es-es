---
title: "Refactorización de un campo a una propiedad en C# | Microsoft Docs"
ms.custom: 
ms.date: 12/14/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.encapsulatefield
dev_langs: csharp
ms.workload: dotnet
ms.openlocfilehash: 383f4e5bac2072b77d8e1d862cd4a1b859a57f7c
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/13/2018
---
# <a name="encapsulate-a-field-in-c"></a>Encapsulamiento de un campo en C# #

**Qué:** Le permite convertir un campo en una propiedad y actualizar todos los usos de ese campo para utilizar la propiedad recién creada.

**Cuándo:** Desea mover un campo a una propiedad y actualizar todas las referencias a ese campo.

**Por qué:** Desea proporcionar acceso de otras clases a un campo, pero no desea que esas clases tengan acceso directo.  Al encapsular el campo en una propiedad, puede escribir código para comprobar el valor que se está asignando, por ejemplo.

**Cómo**:

1. Resalte o coloque el cursor de texto en el nombre del campo que se va a encapsular:

   ![Código resaltado](media/encapsulate-highlight-cs.png)

1. A continuación, realice alguno de los siguientes procedimientos:
   * **Teclado**
     * Presione **CTRL+R** y, a continuación, **CTRL+E**.  (Tenga en cuenta que su método abreviado de teclado puede ser diferente en función del perfil que haya seleccionado).
     * Presione **Ctrl +.** para activar el menú **Acciones rápidas y refactorizaciones** y seleccione la entrada **Encapsular campo** en el menú emergente de la ventana Vista previa.
   * **Mouse**
     * Seleccione **Editar > Refactorizar > encapsular campo**.
     * Haga clic con el botón derecho en el código, seleccione el menú **Acciones rápidas y refactorizaciones** y elija la entrada **Encapsular campo** en el menú emergente de la ventana Vista previa.

   Selección | Description
   --------- | -----------
   **Encapsular campo (y usar propiedad)** | Encapsula el campo con una propiedad y actualiza todos los usos del campo para utilizar la propiedad generada
   **Encapsular campo (pero seguir usando el campo)** | Encapsula el campo con una propiedad, pero deja intactos todos los usos del campo

   La propiedad se creará inmediatamente y se actualizarán las referencias al campo, si se han seleccionado.

   > [!TIP]
   > Use el vínculo [**Vista previa de los cambios**](../../ide/preview-changes.md) de la ventana emergente para ver cuál será el resultado antes de confirmar.

   ![Resultado del encapsulamiento de la propiedad](media/encapsulate-result-cs.png)

## <a name="see-also"></a>Vea también

[Refactorización](../refactoring-in-visual-studio.md)  
[Vista previa de cambios](../../ide/preview-changes.md)