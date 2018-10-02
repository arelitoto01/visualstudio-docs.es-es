---
title: 'Cómo: aplicar automáticamente las claves de producto durante la implementación de Visual Studio | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d79260be-6234-4fd3-89b5-a9756b4a93c1
caps.latest.revision: 11
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 45ed6a059c0a9cf9ae5063e538ec9b9c87698ef1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2018
ms.locfileid: "47580822"
---
# <a name="how-to-automatically-apply-product-keys-when-deploying-visual-studio"></a>Cómo: aplicar automáticamente las claves de producto durante la implementación de Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Para obtener la documentación más reciente de Visual Studio 2017, consulte [aplicar automáticamente las claves de producto durante la implementación de Visual Studio](https://docs.microsoft.com/en-us/visualstudio/install/automatically-apply-product-keys-when-deploying-visual-studio).

Puede aplicar la clave de producto mediante programación como parte de un script que se usa para automatizar la implementación de Visual Studio 2015. Las claves de producto se pueden establecer en un dispositivo mediante programación durante la instalación de Visual Studio o después de completar una instalación.  
  
## <a name="apply-the-license-during-installation"></a>Aplicar la licencia durante la instalación  
 Utilice el parámetro /ProductKey para aplicar una clave de producto durante el proceso de instalación de Visual Studio. Este parámetro de configuración se puede utilizar con el parámetro/Silent parámetro para instalar Visual Studio en un estado ya con licencia para el usuario final. Para usar el parámetro /ProductKey, abra un símbolo del sistema. Ejecute el programa de configuración (por ejemplo vs_enterprise.exe o vs_professional.exe) y establezca el parámetro /ProductKey con una clave de producto (25 caracteres) que no incluya guiones:  
  
 Este es un comando de ejemplo para la instalación de Visual Studio 2015 Enterprise con la clave de producto AAAAABBBBBCCCCCDDDDDEEEEEEE:  
  
 `vs_enterprise.exe [any other setup parameters] /ProductKey AAAAABBBBBCCCCCDDDDDDEEEEEE`  
  
## <a name="apply-the-license-after-installation"></a>Aplicar la licencia después de la instalación  
 Puede activar una versión instalada de Visual Studio con una clave de producto mediante la utilidad storePID.exe en los equipos de destino en modo silencioso. StorePID.exe es una utilidad que se instala con Visual Studio en  **\<unidad >:\\\Program archivos (x86) \Microsoft Visual Studio 14.0\Common7\IDE\StorePID.exe**.  
  
 Ejecute storePID.exe con privilegios elevados, ya sea mediante un agente de System Center o un símbolo con privilegios elevados, seguido de la clave de producto (incluidos los guiones) y el código de producto de Microsoft (MPC). Asegúrese de incluir los guiones en la clave del producto.  
  
 `StorePID.exe [product key including the dashes] [MPC]`  
  
 Este es un ejemplo de línea de comandos para la instalación de Visual Studio 2015 Enterprise, que tiene un MPC de 07060, con una clave de producto "AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE":  
  
 `C:\Program Files (x86)\Microsoft Visual Studio 14.0\Common7\IDE\StorePID.exe AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE 07060`  
  
 En la siguiente tabla se muestran los códigos MPC de cada edición de Visual Studio:  
  
|Edición de Visual Studio|MPC|  
|---------------------------|---------|  
|Visual Studio Enterprise 2015|07060|  
|Visual Studio Professional 2015|07062|  
|Visual Studio Test Professional 2015|07066|  
|Visual Studio Ultimate 2013|06181|  
|Visual Studio Premium 2013|06191|  
|Visual Studio Professional 2013|06177|  
|Visual Studio Test Professional 2013|06194|  
  
 Para obtener más información sobre cómo obtener una clave de producto, consulte [Cómo: buscar la clave de producto de Visual Studio](../install/how-to-locate-the-visual-studio-product-key.md).  
  
 Si StorePID.exe aplicó correctamente la clave del producto, devolverá 0. Si encuentra errores, devolverá un número comprendido entre 1 y 6.  
  
## <a name="see-also"></a>Vea también  
 [Instalar Visual Studio](../install/install-visual-studio-2015.md)