---
title: Controles Rich Edit sin límite
ms.date: 11/04/2016
helpviewer_keywords:
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
ms.openlocfilehash: 1c5578181b580ddb07b69f5fd2e91aea4b85a72b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624877"
---
# <a name="bottomless-rich-edit-controls"></a>Controles Rich Edit sin límite

La aplicación puede cambiar el tamaño de un control rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) según sea necesario para que sea siempre el mismo tamaño que su contenido. Un control rich edit es compatible con esta funcionalidad llamada "ilimitada" mediante el envío de su ventana primaria un [EN_REQUESTRESIZE](/windows/desktop/Controls/en-requestresize) recibe un mensaje de notificación cada vez que cambia el tamaño de su contenido.

Al procesar la **EN_REQUESTRESIZE** mensaje de notificación, una aplicación debe cambiar el tamaño del control a las dimensiones de la manera especificada [REQRESIZE](/windows/desktop/api/richedit/ns-richedit-_reqresize) estructura. Una aplicación también puede mover cualquier información que se encuentra el control para dar cabida a cambio del control en el alto. Para cambiar el tamaño del control, puede usar el `CWnd` función [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos).

Puede forzar un control Rich edit enriquecido para enviar un **EN_REQUESTRESIZE** mensaje de notificación mediante el uso de la [función miembro RequestResize](../mfc/reference/cricheditctrl-class.md#requestresize) función miembro. Este mensaje puede ser útil en el [OnSize](../mfc/reference/cwnd-class.md#onsize) controlador.

Para recibir **EN_REQUESTRESIZE** mensajes de notificación, debe habilitar la notificación mediante el `SetEventMask` función miembro.

## <a name="see-also"></a>Vea también

[Uso de CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Controles](../mfc/controls-mfc.md)

