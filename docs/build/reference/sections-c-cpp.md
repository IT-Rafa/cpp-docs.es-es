---
title: SECTIONS (C/C++)
ms.date: 11/04/2016
f1_keywords:
- SECTIONS
helpviewer_keywords:
- SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
ms.openlocfilehash: 7b6708e760a85a137a01718d07a5f167de849220
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485871"
---
# <a name="sections-cc"></a>SECTIONS (C/C++)

Presenta una sección de uno o varios `definitions` que son especificadores de acceso en las secciones en el archivo de salida del proyecto.

```
SECTIONS
definitions
```

## <a name="remarks"></a>Comentarios

Cada definición debe estar en una línea independiente. El `SECTIONS` palabra clave puede estar en la misma línea que la primera definición o en una línea anterior. El archivo .def puede contener uno o varios `SECTIONS` instrucciones.

Esto `SECTIONS` instrucción establece los atributos de una o más secciones en el archivo de imagen y puede usarse para reemplazar los atributos predeterminados para cada tipo de sección.

El formato de `definitions` es:

`.section_name specifier`

donde `.section_name` es el nombre de una sección de la imagen del programa y `specifier` es uno o varios de los modificadores de acceso siguiente:

|Modificador|Descripción|
|--------------|-----------------|
|`EXECUTE`|La sección es ejecutable|
|`READ`|Permite operaciones de lectura de datos|
|`SHARED`|Comparte la sección entre todos los procesos que cargan la imagen|
|`WRITE`|Permite que las operaciones de escritura en datos|

Separe los nombres de especificador con un espacio. Por ejemplo:

```
SECTIONS
.rdata READ WRITE
```

`SECTIONS` marca el principio de una lista de sección `definitions`. Cada `definition` debe estar en una línea independiente. El `SECTIONS` palabra clave puede estar en la misma línea que la primera `definition` o en una línea anterior. El archivo .def puede contener uno o varios `SECTIONS` instrucciones. El `SEGMENTS` se admite la palabra clave como sinónimo de `SECTIONS`.

Se admiten las versiones anteriores de Visual C++:

```
section [CLASS 'classname'] specifier
```

El `CLASS` palabra clave se admite por compatibilidad, pero se omite.

Es una manera equivalente para especificar atributos de sección con el [/SECTION](../../build/reference/section-specify-section-attributes.md) opción.

## <a name="see-also"></a>Vea también

[Reglas para instrucciones de definición de módulos](../../build/reference/rules-for-module-definition-statements.md)