---
title: Clases relacionadas con OLE
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE classes [MFC]
- OLE [MFC], classes
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
ms.openlocfilehash: 2c3aa5ea4e720b14c5fdc4cb3285cd812eb550e2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584657"
---
# <a name="ole-related-classes"></a>Clases relacionadas con OLE

Estas clases proporcionan varios servicios diferentes, que abarcan desde las excepciones en el archivo de entrada y salida.

[COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)<br/>
Se usa para crear elementos cuando se solicita desde otros contenedores. Esta clase actúa como clase base para tipos más específicos de fábricas, incluyendo `COleTemplateServer`.

[COleMessageFilter](../mfc/reference/colemessagefilter-class.md)<br/>
Se usa para administrar la simultaneidad con OLE ligero remoto procedimiento llamadas (LRPC).

[COleStreamFile](../mfc/reference/colestreamfile-class.md)<br/>
Usa COM `IStream` interfaz para proporcionar `CFile` acceso a archivos compuestos. Esta clase (derivado de `CFile`) habilita la serialización de MFC usar almacenamiento estructurado OLE.

[CRectTracker](../mfc/reference/crecttracker-class.md)<br/>
Se utiliza para permitir mover, cambiar el tamaño y reorientación de elementos en contexto.

## <a name="see-also"></a>Vea también

[Información general de clases](../mfc/class-library-overview.md)

