---
title: Compilador advertencia (nivel 1) C4020
ms.date: 11/04/2016
f1_keywords:
- C4020
helpviewer_keywords:
- C4020
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
ms.openlocfilehash: 75148c210ddd2a611061d58c036d12c084f442cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482035"
---
# <a name="compiler-warning-level-1-c4020"></a>Compilador advertencia (nivel 1) C4020

'function': hay demasiados parámetros reales

El número de parámetros reales en una llamada de función supera el número de parámetros formales de la definición o prototipo de función. El compilador pasa los parámetros reales adicionales según la convención de llamada de la función.

El ejemplo siguiente genera C4020:

```
// C4020.c
// compile with: /W1 /c
void f(int);
int main() {
   f(1,2);   // C4020
}
```

Posible resolución:

```
// C4020b.c
// compile with: /c
void f(int);
int main() {
   f(1);
}
```