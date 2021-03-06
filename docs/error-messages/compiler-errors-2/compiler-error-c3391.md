---
title: Error del compilador C3391
ms.date: 11/04/2016
f1_keywords:
- C3391
helpviewer_keywords:
- C3391
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
ms.openlocfilehash: cac397e4588c493fb8c47932feb97a5f12cf2583
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578222"
---
# <a name="compiler-error-c3391"></a>Error del compilador C3391

'type_arg': argumento de tipo no válido para el parámetro genérico 'param' de 'generic_type' genérico debe ser un tipo de valor distinto de null

Se crearon instancias de un tipo genérico incorrectamente. Compruebe la definición de tipo. Para obtener más información, consulte <xref:System.Nullable> y [genéricos](../../windows/generics-cpp-component-extensions.md).

## <a name="example"></a>Ejemplo

El siguiente ejemplo usa C# para crear un componente que contiene un tipo genérico que tiene ciertas restricciones que no se admiten al crear tipos genéricos en C / c++ / CLI. Para obtener más información, vea [Restricciones de tipos de parámetros](/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters).

```cs
// C3391.cs
// Compile by using: csc /target:library C3391.cs
// a C# program
public class GR<N>
where N : struct {}
```

Cuando el componente C3391.dll está disponible, el ejemplo siguiente genera la advertencia C3391.

```cpp
// C3391_b.cpp
// Compile by using: cl /clr C3391_b.cpp
#using <C3391.dll>
using namespace System;
value class VClass {};

int main() {
   GR< Nullable<VClass> >^ a =
      gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable
   GR<VClass>^ aa = gcnew GR<VClass>(); // OK
}
```