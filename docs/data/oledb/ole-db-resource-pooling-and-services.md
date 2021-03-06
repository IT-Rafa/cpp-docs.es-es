---
title: Servicios y agrupación de recursos OLE DB
ms.date: 10/29/2018
helpviewer_keywords:
- resource pooling [OLE DB], provider requirements
- OLE DB, resource pooling
- service providers [OLE DB]
- OLE DB services [OLE DB], provider requirements
- OLE DB services [OLE DB]
- OLE DB providers, resource pooling
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
ms.openlocfilehash: 1fb5164b9e744175f60c920a1d92278e9d5213f2
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "51264663"
---
# <a name="ole-db-resource-pooling-and-services"></a>Servicios y agrupación de recursos OLE DB

Para que funcione bien con la agrupación de OLE DB, o con cualquier servicio de OLE DB, el proveedor debe admitir la agregación de todos los objetos. Se trata de un requisito de cualquier 1.5 de OLE DB o el proveedor de una versión posterior. Es fundamental para aprovechar los servicios. No se puede agrupar los proveedores que no son compatibles con la agregación y no se proporciona sin ningún servicio.

Agrupar, los proveedores deben admitir el modelo de subprocesamiento libre. El grupo de recursos determina el modelo de subprocesos del proveedor según la propiedad DBPROP_THREADMODEL.

Si el proveedor tiene un estado de conexión global que puede cambiar mientras el origen de datos está en un estado inicializado, debe admitir la nueva propiedad DBPROP_RESETDATASOURCE. Esta propiedad se llama antes de una conexión se vuelve a usar y ofrece al proveedor de la oportunidad de limpiar el estado antes de su uso siguiente. Si el proveedor no puede limpiar algún estado asociado a la conexión, puede devolver DBPROPSTATUS_NOTSETTABLE para la propiedad y no se volverá a utilizar la conexión.

Los proveedores que se conectan a una base de datos remota y pueden detectar si se puede perder en esa conexión deben admitir la propiedad DBPROP_CONNECTIONSTATUS. Esta propiedad proporciona la capacidad de detectar conexiones inactivas y asegúrese de que no se devuelven al grupo de los servicios de OLE DB.

Por último, la inscripción automática en transacciones generalmente no funciona a menos que se implementa en el mismo nivel que se produce la agrupación. Los proveedores que admiten la inscripción automática en transacciones deben admitir la deshabilitación mediante la exposición de la propiedad DBPROP_INIT_OLEDBSERVICES y deshabilitar la inscripción si la selección de DBPROPVAL_OS_TXNENLISTMENT.

## <a name="see-also"></a>Vea también

[Técnicas avanzadas para proveedores](../../data/oledb/advanced-provider-techniques.md)