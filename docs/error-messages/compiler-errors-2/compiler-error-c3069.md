---
title: Error del compilador C3069
ms.date: 11/04/2016
f1_keywords:
- C3069
helpviewer_keywords:
- C3069
ms.assetid: ca94291b-2bb4-4e3f-9acf-534234b83513
ms.openlocfilehash: 6c6451d31da2bb708d3f233225be713981b062e6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474443"
---
# <a name="compiler-error-c3069"></a>Error del compilador C3069

'operator': no se permite para el tipo de enumeración

Un operador no se admite en las enumeraciones de CLR.  Para obtener más información, consulte [Cómo: definir y usar enumeraciones en C++ / c++ / CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md).

## <a name="example"></a>Ejemplo

El ejemplo siguiente genera la advertencia C3069:

```
// C3069.cpp
// compile with: /clr
enum struct E { e1 };
enum F { f1 };

int main() {
   E e = E::e1;
   bool tf;
   tf = !e;   // C3069

   // supported for native enums
   F f = f1;
   tf = !f;
}
```