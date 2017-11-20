---
title: "Visibilidad de espacios de nombres y tipos (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cbc01a3a-3b69-4ded-9c42-ecbf0fd0a00e
caps.latest.revision: 13
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 13
---
# Visibilidad de espacios de nombres y tipos (C++/CX)
Un espacio de nombres es una construcción de C\+\+ estándar para agrupar tipos que tienen funcionalidad relacionada y para evitar conflictos de nombre en bibliotecas. El sistema de tipos de [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] requiere que todos los tipos públicos de [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], incluidos los de tu propio código, se declaren en un espacio de nombres en el ámbito de espacio de nombres. Los tipos públicos que se declaran en el ámbito global o que se anidan dentro de otra clase producen un error en tiempo de compilación.  
  
 Un archivo .winmd debe tener el mismo nombre que el espacio de nombres de la raíz. Por ejemplo, se pueden crear instancias de una clase denominada A.B.C.MyClass solo si está definida en un archivo de metadatos denominado A.winmd, A.B.winmd o A.B.C.winmd. El nombre del ejecutable no tiene que coincidir con el nombre del archivo .winmd.  
  
## Visibilidad de tipos  
 En un espacio de nombres, los tipos de [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], a diferencia de los tipos de C\+\+ estándar, poseen accesibilidad privada o pública. De forma predeterminada, la accesibilidad es privada. Solo un tipo público está visible para los metadatos y, por consiguiente, lo pueden utilizar aplicaciones y componentes que puedan estar escritos en lenguajes diferentes de C\+\+. En general, las reglas para tipos visibles son más restrictivas que las reglas para tipos no visibles porque los tipos visibles no pueden exponer conceptos específicos de C\+\+ que no se admiten en lenguajes de .NET o JavaScript.  
  
> [!NOTE]
>  Los metadatos solo se usan en tiempo de ejecución por lenguajes .NET y JavaScript. Cuando una aplicación o un componente de C\+\+ está hablando con otra aplicación u otro componente de C\+\+ \(esto incluye a los componentes de Windows, que se escriben todos en C\+\+\), no se requiere el uso de metadatos en tiempo de ejecución.  
  
## Accesibilidad y visibilidad de miembros  
 En una clase ref, interfaz o delegado privados no se emiten miembros para metadatos, incluso si tienen accesibilidad pública. En las clases ref públicas, puedes controlar la visibilidad de los miembros en los metadatos independientemente de su accesibilidad en tu código fuente. Al igual que en C\+\+ estándar, debes aplicar el principio de menor privilegio; no conviene que tus miembros estén visibles en los metadatos a menos que tengan que estarlo necesariamente.  
  
 Utiliza los modificadores de acceso siguientes para controlar tanto la visibilidad de los metadatos como la accesibilidad del código fuente.  
  
||||  
|-|-|-|  
|Modificador|Significado|¿Emitido para metadatos?|  
|private|La accesibilidad predeterminada. El mismo significado que en C\+\+ estándar.|No|  
|protected|El mismo significado que en C\+\+ estándar, tanto dentro de la aplicación o componente como en los metadatos.|Sí|  
|public|El mismo significado que en C\+\+ estándar.|Sí|  
|`public protected` o `protected public`|Accesibilidad protegida en metadatos, pública dentro de la aplicación o componente.|Sí|  
|`protected private` o `private protected`|No visible en los metadatos; accesibilidad protegida dentro de la aplicación o componente.||  
|`internal` o `private public`|El miembro es público dentro de la aplicación o componente, pero no está visible en los metadatos.|No|  
  
## Espacios de nombres de [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]  
 La API de Windows consta de tipos que se declaran en los espacios de nombres Windows::\*. Estos espacios de nombres se reservan para Windows y no se les puede agregar tipos. En el **Explorador de objetos**, puedes ver estos espacios de nombres en el archivo windows.winmd. Para documentación sobre estos espacios de nombres, vea [API de Windows](http://msdn.microsoft.com/library/windows/apps/br211377).  
  
## Espacios de nombres de [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]  
 [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) define determinados tipos en estos espacios de nombres como parte de la proyección del sistema de tipos de [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)].  
  
|||  
|-|-|  
|**Espacio de nombres**|**Descripción**|  
|default|Contiene los tipos numéricos y char16 integrados. Estos tipos están en el ámbito de cada espacio de nombres y nunca se requiere una instrucción `using`.|  
|Plataforma|Contiene principalmente tipos públicos que corresponden a tipos de [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] tales como `Array<T>`, `String`, `Guid` y `Boolean`. También incluye tipos auxiliares especializados como `Platform::Agile<T>` y `Platform::Box<T>`.|  
|Platform::Collections|Contiene las clases de colección concretas que implementan las interfaces de colección de [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]`IVector`, `IMap`, etc. Estos tipos se definen en un archivo de encabezado collection.h y no en platform.winmd.|  
|Platform::Details|Contiene tipos que el compilador utiliza y que no están previstos para consumo público.|  
  
## Vea también  
 [Sistema de tipos \(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)