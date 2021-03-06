---
title: Desplazamientos a la derecha
ms.date: 11/04/2016
ms.assetid: c878e97d-ea3c-4c6b-90a8-b1b24b2d5b19
ms.openlocfilehash: f39c1f2f49f5a8a1f3bb5eb3f21736eedf32077e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518214"
---
# <a name="right-shifts"></a>Desplazamientos a la derecha

El resultado de un desplazamiento a la derecha de un tipo entero con signo de valor negativo

Cuando se desplaza a la derecha un valor negativo se produce la mitad del valor absoluto, redondeado a la baja. Por ejemplo, un valor `short` con signo de -253 (hexadecimal 0xFF03, binario 11111111 00000011) desplazado a la derecha un bit produce -127 (hexadecimal 0xFF81, binario 11111111 10000001). Un 253 positivo desplazado a la derecha produce + 126.

Los desplazamientos a la derecha preservan el bit de signo de los tipos enteros con signo. Cuando un entero con signo se desplaza a la derecha, el bit más significativo permanece establecido. Por ejemplo, si 0xF0000000 es un `int` con signo, un desplazamiento a la derecha produce 0xF8000000. Desplazar un `int` negativo a la derecha 32 veces produce 0xFFFFFFFF.

Cuando un entero sin signo se desplaza a la derecha, el bit más significativo se borra. Por ejemplo, si 0xF000 es sin signo, el resultado es 0x7800. Desplazar un `unsigned` o `int` positivo a la derecha 32 veces produce 0 x 00000000.

## <a name="see-also"></a>Vea también

[Enteros](../c-language/integers.md)