---
title: context_unblock_unbalanced (Clase)
ms.date: 11/04/2016
f1_keywords:
- context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced::context_unblock_unbalanced
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
ms.openlocfilehash: cc2ef970fa354da4abb7351cb4f1188451887552
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525936"
---
# <a name="contextunblockunbalanced-class"></a>context_unblock_unbalanced (Clase)

Esta clase describe una excepción que se produce cuando se llama a los métodos `Block` y `Unblock` de un objeto `Context` que no están emparejados correctamente.

## <a name="syntax"></a>Sintaxis

```
class context_unblock_unbalanced : public std::exception;
```

## <a name="members"></a>Miembros

### <a name="public-constructors"></a>Constructores públicos

|Name|Descripción|
|----------|-----------------|
|[context_unblock_unbalanced](#ctor)|Sobrecargado. Construye un objeto `context_unblock_unbalanced`.|

## <a name="remarks"></a>Comentarios

Las llamadas a la `Block` y `Unblock` métodos de un `Context` objeto siempre se debe emparejar correctamente. El Runtime de simultaneidad permite las operaciones que ocurra en cualquier orden. Por ejemplo, una llamada a `Block` puede ir seguida de una llamada a `Unblock`, o viceversa. Esta excepción se produce si, por ejemplo, dos llamadas a la `Unblock` método se realizaron en una fila, en un `Context` objeto que no se ha bloqueado.

## <a name="inheritance-hierarchy"></a>Jerarquía de herencia

`exception`

`context_unblock_unbalanced`

## <a name="requirements"></a>Requisitos

**Encabezado:** concrt.h

**Espacio de nombres:** simultaneidad

##  <a name="ctor"></a> context_unblock_unbalanced)

Construye un objeto `context_unblock_unbalanced`.

```
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

context_unblock_unbalanced() throw();
```

### <a name="parameters"></a>Parámetros

*_Cuerpo*<br/>
Mensaje descriptivo del error.

## <a name="see-also"></a>Vea también

[concurrency (espacio de nombres)](concurrency-namespace.md)
