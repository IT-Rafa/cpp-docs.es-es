---
title: Elegir un fondo transparente u opaco (Editor de imágenes para iconos)
ms.date: 11/19/2018
helpviewer_keywords:
- opaque backgrounds [C++]
- colors [C++], image
- Image editor [C++], transparent or opague backgrounds
- images [C++], transparency
- images [C++], opaque background
ms.assetid: 61b743d9-c86b-405d-9a81-0806431b4363
ms.openlocfilehash: ceea31b998d5c4dca52657db570ace664f7e373f
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175436"
---
# <a name="choosing-a-transparent-or-opaque-background-image-editor-for-icons"></a>Elegir un fondo transparente u opaco (Editor de imágenes para iconos)

Al mover o copiar una selección de una imagen, son los píxeles de la selección que coinciden con el color de fondo actual, de forma predeterminada, transparente; no ocultan los píxeles en la ubicación de destino.

Puede cambiar de un fondo transparente (valor predeterminado) a un fondo opaco y viceversa. Cuando se usa una herramienta de selección, el **fondo transparente** y **fondo opaco** opciones aparecen en la **opción** selector en la **delEditordeimágenes** barra de herramientas (como se muestra a continuación).

![Opciones de fondo &#45; opaca o transparente](../windows/media/vcimageeditoropaqtranspback.gif "en segundo plano opciones &#45; opaca o transparente")<br/>
**Opciones transparentes y opacas** en el **barra de herramientas del Editor de imágenes**

### <a name="to-switch-between-a-transparent-and-opaque-background"></a>Para cambiar entre un fondo transparente y opaco

1. En el **Editor de imágenes** barra de herramientas, haga clic en el **opción** selector y, a continuación, haga clic en el fondo correspondiente:

   - `Opaque Background (O)`: Imagen existente está oculto por todas las partes de la selección.

   - `Transparent Background (T)`: Imagen existente se muestra en las partes de la selección que coinciden con el color de fondo actual.

   \- o -

1. En el **imagen** menú, active o desactive **dibujar figuras opacas**.

Puede cambiar el color de fondo mientras una selección ya está en vigor para cambiar qué partes de la imagen son transparentes.

Para obtener información sobre cómo agregar recursos a proyectos administrados, vea [Resources in Desktop Apps](/dotnet/framework/resources/index) en el *Guía del desarrollador de .NET Framework*. Para obtener información sobre cómo agregar manualmente archivos de recursos a proyectos administrados, acceder a los recursos, mostrar recursos estáticos y asignar cadenas de recursos a propiedades, vea [crear archivos de recursos para las aplicaciones de escritorio](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Para obtener información sobre la globalización y localización de recursos en aplicaciones administradas, vea [Globalizar y localizar aplicaciones de .NET Framework](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Requisitos

Ninguna

## <a name="see-also"></a>Vea también

[Teclas de aceleración](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Trabajar con colores](../windows/working-with-color-image-editor-for-icons.md)