---
title: Error del compilador C3707
ms.date: 11/04/2016
f1_keywords:
- C3707
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
ms.openlocfilehash: 8a1525539c84ea427815a03057bb6d2f9213fec7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431119"
---
# <a name="compiler-error-c3707"></a>Error del compilador C3707

'function': el método dispinterface debe tener un dispid

Si usa un `dispinterface` método, se le debe asignar un `dispid`. Para corregir este error, asigne un `dispid` a la `dispinterface` método, por ejemplo, al quitar el comentario del `id` atributo en el método en el ejemplo siguiente. Para obtener más información, vea los atributos [dispinterface](../../windows/dispinterface.md) y [id](../../windows/id.md).

El ejemplo siguiente genera C3707:

```
// C3707.cpp
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[module(name="xx")];
[dispinterface]
__interface IEvents : IDispatch
{
   HRESULT event1([in] int i);   // C3707
   // try the following line instead
   // [id(1)] HRESULT event1([in] int i);
};

int main() {
}
```