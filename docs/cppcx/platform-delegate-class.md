---
title: Platform::Delegate (Clase)
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Delegate
helpviewer_keywords:
- Platform::Delegate Class
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
ms.openlocfilehash: 1b4a4955bbff53e6e0c5606f2900e22cc69146cc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50446233"
---
# <a name="platformdelegate-class"></a>Platform::Delegate (Clase)

Representa un objeto de función.

## <a name="syntax"></a>Sintaxis

```cpp
public delegate void delegate_name();
```

### <a name="members"></a>Miembros

La clase Delegate tiene los métodos Equals(), GetHashCode() y ToString() que se derivan de [Platform::Object Class](../cppcx/platform-object-class.md).

### <a name="remarks"></a>Comentarios

Use la palabra clave [delegate](../windows/delegate-cpp-component-extensions.md) para crear delegados; no use Platform::Delegate de manera explícita. Para obtener más información, vea [Delegados (Guía de programación de C#)](../cppcx/delegates-c-cx.md). Para un ejemplo de cómo crear y usar un delegado, vea [Creating Windows Runtime Components in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

### <a name="requirements"></a>Requisitos

**Cliente mínimo admitido:** Windows 8

**Servidor mínimo admitido:** Windows Server 2012

**Espacio de nombres:** Plataforma

**Metadatos:** platform.winmd

## <a name="see-also"></a>Vea también

[Espacio de nombres de plataforma](../cppcx/platform-namespace-c-cx.md)