---
title: Error del compilador C2218
ms.date: 11/04/2016
f1_keywords:
- C2218
helpviewer_keywords:
- C2218
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
ms.openlocfilehash: 5a9d897686fc915c9892fa2bcd51fa3ca3c8b05e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468629"
---
# <a name="compiler-error-c2218"></a>Error del compilador C2218

'__vectorcall' no se puede usar con '/arch:IA32'

La convención de llamada `__vectorcall` solo se admite en código nativo en procesadores x86 y x64 que incluyen Extensiones SIMD de streaming 2 (SSE2) y versiones posteriores. Para obtener más información, consulte [__vectorcall](../../cpp/vectorcall.md).

Para corregir este error, cambie las opciones del compilador para que se dirijan a los conjuntos de instrucciones SSE2, AVX o AVX2. Para obtener más información, consulte [/arch (x86)](../../build/reference/arch-x86.md).