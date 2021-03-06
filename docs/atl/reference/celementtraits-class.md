---
title: CElementTraits (clase)
ms.date: 11/04/2016
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
helpviewer_keywords:
- CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
ms.openlocfilehash: 4951f5b87efbff83f39badba5f3e1041a15d8c6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480763"
---
# <a name="celementtraits-class"></a>CElementTraits (clase)

Esta clase se utiliza por las clases de colección para proporcionar funciones y métodos para mover, copiar, comparaciones y operaciones hash.

## <a name="syntax"></a>Sintaxis

```
template<typename T>
class CElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>Parámetros

*T*<br/>
El tipo de datos que se almacenará en la colección.

## <a name="remarks"></a>Comentarios

Esta clase proporciona métodos y funciones estáticas de forma predeterminada para mover, copiar, comparar y hash elementos almacenados en un objeto de clase de colección. `CElementTraits` se especifica como el proveedor predeterminado de estas operaciones mediante las clases de colección [CAtlArray](../../atl/reference/catlarray-class.md), [CAtlList](../../atl/reference/catllist-class.md), [CRBMap](../../atl/reference/crbmap-class.md), [CRBMultiMap](../../atl/reference/crbmultimap-class.md), y [CRBTree](../../atl/reference/crbtree-class.md).

Las implementaciones predeterminadas será suficiente para tipos de datos simples, pero si se utilizan las clases de colección para almacenar objetos más complejos, las funciones y métodos deben reemplazarse por las implementaciones proporcionadas por el usuario.

Para obtener más información, consulte [clases de colección ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Requisitos

**Encabezado:** atlcoll.h

## <a name="see-also"></a>Vea también

[CDefaultElementTraits (clase)](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Información general de clases](../../atl/atl-class-overview.md)
