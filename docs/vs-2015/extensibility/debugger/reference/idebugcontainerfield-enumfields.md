---
title: IDebugContainerField::EnumFields | Documentos de Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugContainerField::EnumFields
helpviewer_keywords:
- IDebugContainerField::EnumFields method
ms.assetid: 9e5e681b-ad49-4c62-bd95-4afa11d61a57
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2a1fb33a65fb0bb86d3c043dd250b60b1533fed4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2018
ms.locfileid: "47576871"
---
# <a name="idebugcontainerfieldenumfields"></a>IDebugContainerField::EnumFields
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

La versión más reciente de este tema puede encontrarse en [IDebugContainerField::EnumFields](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcontainerfield-enumfields).  
  
Crea un enumerador para los campos del contenedor.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp#  
HRESULT EnumFields(   
   FIELD_KIND         dwKindFilter,  
   FIELD_MODIFIERS    dwModifiersFilter,  
   LPCOLESTR          pszNameFilter,  
   NAME_MATCH         nameMatch,  
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumFields(  
   enum_ FIELD_KIND      dwKindFilter,   
   enum_ FIELD_MODIFIERS dwModifiersFilter,   
   string                pszNameFilter,   
   NAME_MATCH            nameMatch,   
   out IEnumDebugFields  ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `dwKindFilter`  
 [in] Una combinación de [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md) constantes que seleccione los campos que se van a enumerar. Tipos de campo pueden describir los tipos de almacenamiento, como una clase o primitiva, o específica de información, como local, parámetro o puntero "this".  
  
 `dwModifiersFilter`  
 [in] Una combinación de [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md) constantes que seleccione los campos que se van a enumerar. Modificadores de campo pueden ser permisos de acceso, como público o privado o información de almacenamiento, como virtual, estática o final.  
  
 `pszNameFilter`  
 [in] El nombre del campo que hay que enumerar. Esto puede ser un valor nulo si todos los campos que se van a devolverse.  
  
 `nameMatch`  
 [in] Un valor de la [NAME_MATCH](../../../extensibility/debugger/reference/name-match.md) enumeración que controla si la búsqueda distingue mayúsculas de minúsculas o no.  
  
 `ppEnum`  
 [out] Devuelve un [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objeto que representa la lista de campos. Devuelve un valor null si no hay ningún campo.  
  
## <a name="return-value"></a>Valor devuelto  
 Si se realiza correctamente, devuelve S_OK o S_FALSE si no hay ningún campo. De lo contrario, devuelve un código de error.  
  
## <a name="remarks"></a>Comentarios  
 El `dwKindFilter`, `dwModifiersFilter`, y `pszNameFilter` parámetros se pueden combinar, por ejemplo, para seleccionar todos los métodos virtuales públicos denominados "MyMethod".  
  
## <a name="see-also"></a>Vea también  
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md)   
 [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md)   
 [NAME_MATCH](../../../extensibility/debugger/reference/name-match.md)
