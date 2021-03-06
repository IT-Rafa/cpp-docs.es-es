---
title: _ATL_FUNC_INFO (estructura)
ms.date: 11/04/2016
f1_keywords:
- _ATL_FUNC_INFO
- ATL::_ATL_FUNC_INFO
- ATL._ATL_FUNC_INFO
helpviewer_keywords:
- _ATL_FUNC_INFO structure
- ATL_FUNC_INFO structure
ms.assetid: 441ebe2c-f971-47de-9f52-a258e8d6f88e
ms.openlocfilehash: 8398bc999e9a62d03990fd1b205ad438b6428431
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554029"
---
# <a name="atlfuncinfo-structure"></a>_ATL_FUNC_INFO (estructura)

Contiene información de tipo que se utiliza para describir un método o propiedad en una interfaz dispinterface.

## <a name="syntax"></a>Sintaxis

```
struct _ATL_FUNC_INFO {
    CALLCONV cc;
    VARTYPE vtReturn;
    SHORT nParams;
    VARTYPE pVarTypes[_ATL_MAX_VARTYPES];
};
```

## <a name="members"></a>Miembros

`cc`<br/>
Convención de llamada. Cuando se usa esta estructura con la [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) (clase), este miembro debe ser CC_STDCALL. `CC_CDECL` es la única opción admitida en Windows CE para el `CALLCONV` campo de la `_ATL_FUNC_INFO` estructura. No se admite cualquier otro valor, por tanto, su comportamiento sin definir.

`vtReturn`<br/>
El tipo de variante de la función devuelve el valor.

`nParams`<br/>
El número de parámetros de función.

`pVarTypes`<br/>
Una matriz de tipos de variante de los parámetros de función.

## <a name="remarks"></a>Comentarios

Internamente, ATL utiliza esta estructura que contiene la información obtenida de una biblioteca de tipos. Es posible que deba manipular directamente esta estructura si se proporciona información de tipo para un controlador de eventos que se usa con el [IDispEventSimpleImpl](../../atl/reference/idispeventsimpleimpl-class.md) clase y [macro SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info) macro.

## <a name="example"></a>Ejemplo

Dado un método dispinterface definido en un IDL:

[!code-cpp[NVC_ATL_Windowing#139](../../atl/codesnippet/cpp/atl-func-info-structure_1.idl)]

tendría que definir un `_ATL_FUNC_INFO` estructura:

[!code-cpp[NVC_ATL_Windowing#140](../../atl/codesnippet/cpp/atl-func-info-structure_2.h)]

## <a name="requirements"></a>Requisitos

Encabezado: atlcom.h

## <a name="see-also"></a>Vea también

[Clases y structs](../../atl/reference/atl-classes.md)<br/>
[IDispEventSimpleImpl (clase)](../../atl/reference/idispeventsimpleimpl-class.md)<br/>
[MACRO SINK_ENTRY_INFO](composite-control-macros.md#sink_entry_info)

