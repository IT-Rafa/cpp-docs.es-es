---
title: Ilustración de enrutamiento de comandos
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, command routing
- command handling [MFC], routing commands
- command routing [MFC], OnCmdMsg handler
ms.assetid: 4b7b4741-565f-4878-b076-fd85c670f87f
ms.openlocfilehash: 3bc7c33762ab1868b29732d17e1a2e9700d11cf7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584566"
---
# <a name="command-routing-illustration"></a>Ilustración de enrutamiento de comandos

Para ilustrarlo, considere la posibilidad de un mensaje de comando desde un elemento de menú Borrar todo en el menú de edición de una aplicación MDI. Supongamos que la función de controlador para este comando resulta ser una función miembro de clase de documento de la aplicación. Le mostramos cómo llega a su controlador de ese comando una vez que el usuario elige el elemento de menú:

1. La ventana de marco principal recibe el mensaje de comando en primer lugar.

1. La ventana de marco principal MDI ofrece una oportunidad para controlar el comando de la ventana secundaria MDI activa actualmente.

1. El enrutamiento estándar de una ventana de marco secundario MDI ofrece a su vista oportunidad en la línea de comandos antes de comprobar su propio mapa de mensajes.

1. La vista comprueba en primer lugar su propio mapa de mensajes y, no encontrar ningún controlador, enruta el comando a su documento asociado.

1. El documento comprueba su mapa de mensajes y encuentra un controlador. Se llama a esta función miembro de documento y el enrutamiento se detiene.

Si el documento no tiene un controlador, se enrutaría el comando a su plantilla de documento. A continuación, el comando devolvería a la vista y, a continuación, en la ventana de marco. Por último, la ventana de marco comprobaría su mapa de mensajes. Si la comprobación no se pudo Además, el comando se enrutaría a la ventana de marco principal MDI y, a continuación, en el objeto de aplicación, el destino final de los comandos no controlados.

## <a name="see-also"></a>Vea también

[Cómo el marco llama a un controlador](../mfc/how-the-framework-calls-a-handler.md)

