---
title: Usar informaciones sobre herramientas en un objeto CStatusBarCtrl
ms.date: 11/04/2016
f1_keywords:
- CStatusBarCtrl
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
ms.openlocfilehash: a5ebefe3d5daab9917cdb1db7eface09c78b456a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438797"
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>Usar informaciones sobre herramientas en un objeto CStatusBarCtrl

Para habilitar informaciones sobre herramientas para un control de barra de estado, cree el `CStatusBarCtrl` objeto con el estilo SBT_TOOLTIPS.

> [!NOTE]
>  Si usas un `CStatusBar` objeto para implementar la barra de estado, use el `CStatusBar::CreateEx` función. Permite especificar estilos adicionales para el objeto incrustado `CStatusBarCtrl` objeto.

Una vez el `CStatusBarCtrl` se ha creado correctamente el objeto, use [CStatusBarCtrl:: SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) y [CStatusBarCtrl:: GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) para establecer y recuperar el texto de sugerencia para un panel específico.

Una vez que se ha establecido la información sobre herramientas, se muestra solo si el elemento tiene un icono y ningún texto, o si no puede mostrarse en la parte de todo el texto. Información sobre herramientas no se admite en el modo simple.

## <a name="see-also"></a>Vea también

[Uso de CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Controles](../mfc/controls-mfc.md)

