---
title: Error irrecuperable C1022
ms.date: 11/04/2016
f1_keywords:
- C1022
helpviewer_keywords:
- C1022
ms.assetid: edada720-dc73-49bc-bd93-a7945a316312
ms.openlocfilehash: 044ebbbe895677acf74977e56879c292486e18cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432570"
---
# <a name="fatal-error-c1022"></a>Error irrecuperable C1022

se esperaba #endif

Una directiva `#if`, `#ifdef`o `#ifndef` no tiene una directiva `#endif` coincidente. Asegúrese de que cada `#if`, `#ifdef`o `#ifndef` tenga una `#endif`coincidente.

El ejemplo siguiente genera la advertencia C1022:

```
// C1022.cpp
#define true 1

#if (true)
#else
#else    // C1022
```

Posible resolución:

```
// C1022b.cpp
// compile with: /c
#define true 1

#if (true)
#else
#endif
```