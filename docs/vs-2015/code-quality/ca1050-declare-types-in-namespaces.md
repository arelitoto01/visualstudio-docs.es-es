---
title: 'CA1050: Declare tipos en espacios de nombres | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1050
- DeclareTypesInNamespaces
helpviewer_keywords:
- DeclareTypesInNamespaces
- CA1050
ms.assetid: 1002748d-ac8d-404f-85dd-7a12d1ad3e05
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: ef0559cc727e7ffd667ee72ebe241a958fa57450
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2018
ms.locfileid: "47591241"
---
# <a name="ca1050-declare-types-in-namespaces"></a>CA1050: Declare tipos en espacios de nombres
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

La versión más reciente de este tema puede encontrarse en [CA1050: Declare tipos en espacios de nombres](https://docs.microsoft.com/visualstudio/code-quality/ca1050-declare-types-in-namespaces).

|||
|-|-|
|TypeName|DeclareTypesInNamespaces|
|Identificador de comprobación|CA1050|
|Categoría|Microsoft.Design|
|Cambio problemático|Problemático|

## <a name="cause"></a>Motivo
 Se define un tipo público o protegido fuera del ámbito de un espacio de nombres.

## <a name="rule-description"></a>Descripción de la regla
 Los tipos se declaran en los espacios de nombres para evitar conflictos de nombres y como una manera de organizar los tipos relacionados en una jerarquía de objetos. Tipos que están fuera de cualquier espacio de nombres están en un espacio de nombres global que no se puede hacer referencia en el código.

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones
 Para corregir una infracción de esta regla, coloque el tipo en un espacio de nombres.

## <a name="when-to-suppress-warnings"></a>Cuándo suprimir advertencias
 Aunque nunca debe suprimir una advertencia de esta regla, es seguro hacerlo cuando el ensamblado nunca se usará junto con otros ensamblados.

## <a name="example"></a>Ejemplo
 El ejemplo siguiente muestra una biblioteca que tiene un tipo declarado incorrectamente fuera de un espacio de nombres y un tipo que tiene el mismo nombre declarado en un espacio de nombres.

 [!code-csharp[FxCop.Design.TypesLiveInNamespaces#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TypesLiveInNamespaces/cs/FxCop.Design.TypesLiveInNamespaces.cs#1)]
 [!code-vb[FxCop.Design.TypesLiveInNamespaces#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.TypesLiveInNamespaces/vb/FxCop.Design.TypesLiveInNamespaces.vb#1)]

## <a name="example"></a>Ejemplo
 La aplicación siguiente utiliza la biblioteca que se definió anteriormente. Tenga en cuenta que el tipo que se declara fuera de un espacio de nombres se crea cuando el nombre `Test` no está calificada con un espacio de nombres. Tenga en cuenta también que para tener acceso a la `Test` escriba `Goodspace`, se requiere el nombre del espacio de nombres.

 [!code-csharp[FxCop.Design.TestTypesLive#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TestTypesLive/cs/FxCop.Design.TestTypesLive.cs#1)]
 [!code-vb[FxCop.Design.TestTypesLive#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.TestTypesLive/vb/FxCop.Design.TestTypesLive.vb#1)]


