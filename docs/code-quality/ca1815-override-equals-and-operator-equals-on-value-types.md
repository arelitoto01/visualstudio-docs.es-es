---
title: 'CA1815: Invalidar Equals y el operador Equals en los tipos de valores'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1815
- OverrideEqualsAndOperatorEqualsOnValueTypes
helpviewer_keywords:
- OverrideEqualsAndOperatorEqualsOnValueTypes
- CA1815
ms.assetid: 0a8ab3a3-ee8e-46f7-985d-dcf00c89363b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: de537e99b15cfe7dd7c8b80dd6c23c3f89e066a8
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2019
ms.locfileid: "55910095"
---
# <a name="ca1815-override-equals-and-operator-equals-on-value-types"></a>CA1815: Invalidar Equals y el operador Equals en los tipos de valores

|||
|-|-|
|TypeName|OverrideEqualsAndOperatorEqualsOnValueTypes|
|Identificador de comprobación|CA1815|
|Categoría|Microsoft.Performance|
|Cambio problemático|Poco problemático|

## <a name="cause"></a>Motivo
 Un tipo de valor público no invalida <xref:System.Object.Equals%2A?displayProperty=fullName>, o no implementa el operador de igualdad (==). Esta regla no comprueba las enumeraciones.

## <a name="rule-description"></a>Descripción de la regla
 Para los tipos de valor, la implementación heredada de <xref:System.Object.Equals%2A> usa la biblioteca de reflexión y compara el contenido de todos los campos. Mediante el cálculo, la reflexión es cara y no es necesario comparar cada campo para comprobar si hay igualdad. Si se espera que los usuarios comparar u ordenar las instancias o usarlas como claves de tabla hash, el tipo de valor debe implementar <xref:System.Object.Equals%2A>. Si el lenguaje de programación admite la sobrecarga de operadores, también debe proporcionar una implementación de los operadores de igualdad y desigualdad.

## <a name="how-to-fix-violations"></a>Cómo corregir infracciones
 Para corregir una infracción de esta regla, proporcione una implementación de <xref:System.Object.Equals%2A>. Si es posible, implemente el operador de igualdad.

## <a name="when-to-suppress-warnings"></a>Cuándo Suprimir advertencias
 Es seguro suprimir una advertencia de esta regla si no se compararán las instancias del tipo de valor entre sí.

## <a name="example-of-a-violation"></a>Ejemplo de una infracción

### <a name="description"></a>Descripción
 El ejemplo siguiente muestra una estructura (tipo de valor) que infringe esta regla.

### <a name="code"></a>Código
 [!code-csharp[FxCop.Performance.OverrideEqualsViolation#1](../code-quality/codesnippet/CSharp/ca1815-override-equals-and-operator-equals-on-value-types_1.cs)]

## <a name="example-of-how-to-fix"></a>Ejemplo de cómo corregir

### <a name="description"></a>Descripción
 En el ejemplo siguiente se corrige la infracción anterior invalidando <xref:System.ValueType.Equals%2A?displayProperty=fullName> e implementar los operadores de igualdad (==,! =).

### <a name="code"></a>Código
 [!code-csharp[FxCop.Performance.OverrideEqualsFixed#1](../code-quality/codesnippet/CSharp/ca1815-override-equals-and-operator-equals-on-value-types_2.cs)]

## <a name="related-rules"></a>Reglas relacionadas
 [CA2224: Invalidar equals al sobrecargar operadores de igualdad](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)

 [CA2231: sobrecargar el operador equals al invalidar ValueType.Equals](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)

 [CA2226: Los operadores deben tener sobrecargar simétricas](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

## <a name="see-also"></a>Vea también
 <xref:System.Object.Equals%2A?displayProperty=fullName>