---
title: Error del compilador C2410
ms.date: 11/04/2016
f1_keywords:
- C2410
helpviewer_keywords:
- C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
ms.openlocfilehash: 8b01a2f7b9c55fb57c880df5033538f4e45f76b4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643695"
---
# <a name="compiler-error-c2410"></a>Error del compilador C2410

'identifier': nombre de miembro ambiguo en 'contexto'

El identificador es un miembro de más de una estructura o unión en este contexto.

Usar un especificador de estructura o unión en el operando que produjo el error. Un especificador de estructura o unión es un identificador de tipo `struct` o `union` (un `typedef` nombre o una variable del mismo tipo que la estructura o unión que se hace referencia). El especificador debe ser el operando izquierdo de la primer operador de selección de miembro (.) para usar el operando.