---
title: Notificaciones de un Rich Edit Control | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fcfcb2e4fe333db1ed629489b405255d4ab050b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="notifications-from-a-rich-edit-control"></a>Notificaciones de un control Rich Edit
Informe de eventos que afectan a un amplio control de edición de mensajes de notificación ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Pueden ser procesados por la ventana primaria o, mediante la reflexión de mensajes, por la amplia editar propio control. Controles Rich edit admiten todos los mensajes de notificación utilizados con controles de edición, así como varios perfiles adicionales. Puede determinar qué mensajes de notificación de un control rich edit envía su ventana primaria estableciendo su "máscara de eventos".  
  
 Para establecer la máscara de eventos para un control rich edit, utilice la [SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask) función miembro. Puede recuperar la máscara de eventos actual para un control rich edit utilizando la [GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask) función miembro.  
  
 Los párrafos siguientes muestran varias notificaciones específicas y sus usos:  
  
-   **EN_MSGFILTER** control el **EN_MSGFILTER** notificación permite a una clase, ya sea la amplia edita control o su ventana primaria, filtrar todos mediante teclado y entradas para el control del mouse. El controlador puede impedir que se está procesando el mensaje de teclado o mouse (ratón) o puede cambiar el mensaje modificando especificado [filtro de mensajes del](http://msdn.microsoft.com/library/windows/desktop/bb787936) estructura.  
  
-   **EN_PROTECTED** controlar la **EN_PROTECTED** mensaje de notificación para detectar cuando el usuario intenta modificar texto protegido. Para marcar un intervalo de texto como protegido, puede establecer el efecto de carácter protegido. Para obtener más información, consulte [formato de caracteres en los controles Rich Edit](../mfc/character-formatting-in-rich-edit-controls.md).  
  
-   **EN_DROPFILES** puede permitir al usuario que coloque archivos en un control rich edit mediante el procesamiento de la **EN_DROPFILES** mensaje de notificación. Especificado [ENDROPFILES](http://msdn.microsoft.com/library/windows/desktop/bb787895) estructura contiene información acerca de los archivos que se va a quitar.  
  
-   **EN_SELCHANGE aparecen** una aplicación puede detectar cuándo cambia la selección actual mediante el procesamiento de la **EN_SELCHANGE aparecen** mensaje de notificación. El mensaje de notificación especifica un [SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb787952) estructura que contiene información acerca de la nueva selección.  
  
## <a name="see-also"></a>Vea también  
 [Usar CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Controles](../mfc/controls-mfc.md)
