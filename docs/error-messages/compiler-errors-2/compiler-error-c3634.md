---
title: Error del compilador C3634
ms.date: 11/04/2016
f1_keywords:
- C3634
helpviewer_keywords:
- C3634
ms.assetid: fd09f10c-f863-483b-9756-71c16b760b02
ms.openlocfilehash: 2acd76fee5e7ca309991e639044a45ea83ed112b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527548"
---
# <a name="compiler-error-c3634"></a>Error del compilador C3634

'function': no se puede definir un método abstracto de tipo administrado o WinRTclass

Un método abstracto se puede declarar en una clase WinRT o administrada, pero no definirse.

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera el error C3634.

```
// C3634.cpp
// compile with: /clr
ref class C {
   virtual void f() = 0;
};

void C::f() {   // C3634 - don't define managed class' pure virtual method
}
```
