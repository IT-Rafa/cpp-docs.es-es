---
title: /NOENTRY (Sin punto de entrada)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ResourceOnlyDLL
- /noentry
helpviewer_keywords:
- entry points [C++], linker specifying
- -NOENTRY linker option
- resource-only DLLs [C++], creating
- NOENTRY linker option
- /NOENTRY linker option [C++]
- DLLs [C++], creating
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
ms.openlocfilehash: fef4340fa4bb130ac54f4d5e66d4cd4d2f2a3049
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607370"
---
# <a name="noentry-no-entry-point"></a>/NOENTRY (Sin punto de entrada)

```
/NOENTRY
```

## <a name="remarks"></a>Comentarios

La opción /NOENTRY es necesaria para la creación de un archivo DLL solo de recursos que contenga código no ejecutable. Para obtener más información, consulte [crear un archivo DLL de Resource-Only](../../build/creating-a-resource-only-dll.md).

Se utiliza para evitar que LINK vincule una referencia con `_main` en la DLL.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del vinculador en el entorno de desarrollo de Visual Studio

1. Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, consulte [establecer las propiedades de un proyecto de Visual C++](../../ide/working-with-project-properties.md).

1. Seleccione el **vinculador** carpeta.

1. Seleccione el **avanzadas** página de propiedades.

1. Modificar el **ningún punto de entrada** propiedad.

### <a name="to-set-this-linker-option-programmatically"></a>Para establecer esta opción del vinculador mediante programación

1. Vea <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>.

## <a name="see-also"></a>Vea también

[Creación de un archivo DLL de recursos](../../build/creating-a-resource-only-dll.md)<br/>
[Establecer las opciones del vinculador](../../build/reference/setting-linker-options.md)<br/>
[Opciones del vinculador](../../build/reference/linker-options.md)