---
title: Estilos de control ToolBar
ms.date: 11/04/2016
helpviewer_keywords:
- ToolBar control styles [MFC]
ms.assetid: 0f717eb9-fa32-4263-b852-809238863feb
ms.openlocfilehash: f26edc6c0ce4a19528a9a8754428411318e9b9d2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648999"
---
# <a name="toolbar-control-styles"></a>Estilos de control ToolBar

[Clase CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) tiene un conjunto de marcas de estilo que determinan el aspecto y comportamiento del botón. Puede establecer una combinación de estas marcas mediante una llamada a [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle). En este tema se enumera los valores de estilo de indicador y sus significados.

## <a name="property-values"></a>Valores de propiedad

Los valores siguientes determinan el tipo de botón que representa el control:

|||
|-|-|
|TBBS_BUTTON|Botón de comando estándar (valor predeterminado).  |
|TBBS_CHECKBOX|Casilla de verificación.  |
|TBBS_CHECKGROUP|Inicio de un grupo de casillas.  |
|TBBS_GROUP|Inicio de un grupo de botones.  |
|TBBS_SEPARATOR|Separador.  |

Los valores siguientes representan el estado actual del control:

|||
|-|-|
|TBBS_CHECKED|Casilla de verificación está activada.  |
|TBBS_DISABLED|Control está deshabilitado.  |
|TBBS_INDETERMINATE|Casilla de verificación está en un estado indeterminado.  |
|TBBS_PRESSED|Botón está presionado.  |

El valor siguiente cambia el diseño del botón en la barra de herramientas:

|||
|-|-|
|TBBS_BREAK|Coloca el elemento en una nueva línea o en una nueva columna sin separación de columnas.  |

## <a name="remarks"></a>Comentarios

El estilo actual se almacena en [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle). No establezca un nuevo valor en `m_nStyle` directamente, ya que algunas clases derivadas realizan un procesamiento adicional cuando se llama a `SetStyles`.

El administrador visual determina el aspecto de botones en cada estado. Consulte [Administrador de visualización](../../mfc/visualization-manager.md) para obtener más información.

## <a name="requirements"></a>Requisitos

**Encabezado:** afxtoolbarbutton.h

## <a name="see-also"></a>Vea también

[Macros y funciones globales](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CMFCToolBarButton (clase)](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[Administrador de visualización](../../mfc/visualization-manager.md)

