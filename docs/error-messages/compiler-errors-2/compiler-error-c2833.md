---
title: Error del compilador C2833
ms.date: 11/04/2016
f1_keywords:
- C2833
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
ms.openlocfilehash: dad6a64f145c3d49d3b43044ea76a11d35827943
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460546"
---
# <a name="compiler-error-c2833"></a>Error del compilador C2833

'operator operator' no es un operador o tipo reconocido

La palabra `operator` debe ir seguido por un operador que desea invalidar o un tipo que va a convertir.

Para obtener una lista de los operadores que se pueden definir en un tipo administrado, consulte [operadores definidos por el usuario](../../dotnet/user-defined-operators-cpp-cli.md).

El ejemplo siguiente genera C2833:

```
// C2833.cpp
// compile with: /c
class A {};

void operator ::* ();   // C2833
void operator :: ();   // OK
```