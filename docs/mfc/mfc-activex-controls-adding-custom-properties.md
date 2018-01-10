---
title: 'Controles ActiveX MFC: Agregar propiedades personalizadas | Documentos de Microsoft'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], properties
- properties [MFC], custom
ms.assetid: 85af5167-74c7-427b-b8f3-e0d7b73942e5
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f64154142c4c5f0fb3f24dc63120799132983880
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-adding-custom-properties"></a>Controles ActiveX MFC: Agregar propiedades personalizadas
Propiedades personalizadas se diferencian de las propiedades estándar en que propiedades personalizadas no están ya implementadas por la `COleControl` clase. Una propiedad personalizada se utiliza para exponer un cierto estado o aspecto de un control ActiveX al programador que utiliza el control.  
  
 En este artículo se describe cómo agregar una propiedad personalizada al control ActiveX mediante el Asistente para agregar propiedades y explica las modificaciones de código resultante. Entre los temas se incluyen los siguientes:  
  
-   [Usar al Asistente para agregar propiedades para agregar una propiedad personalizada](#_core_using_classwizard_to_add_a_custom_property)  
  
-   [Agregue los cambios de propiedad Asistente para propiedades personalizadas](#_core_classwizard_changes_for_custom_properties)  
  
 Propiedades personalizadas se presentan en cuatro variedades de implementación: Variable miembro, Variable miembro con notificación, métodos Get/Set y parametrizada.  
  
-   Implementación de Variable miembro  
  
     Esta implementación representa el estado de la propiedad como una variable de miembro en la clase de control. Utilice la implementación de Variable miembro cuando no es importante saber cuándo cambia el valor de propiedad. De los tres tipos, esta implementación crea la menor cantidad de código auxiliar para la propiedad. La macro de entrada de mapa de envíos para la implementación de variable miembro es [DISP_PROPERTY](../mfc/reference/dispatch-maps.md#disp_property).  
  
-   Variable de miembro con la implementación de notificación  
  
     Esta implementación consta de una variable de miembro y una función de notificación creada por el Asistente para agregar propiedades. El marco de trabajo llama automáticamente a la función de notificación después de los cambios de valor de propiedad. Utilice la Variable de miembro con la implementación de notificación cuando necesite recibirá una notificación cuando un valor de propiedad ha cambiado. Esta implementación requiere más tiempo porque requiere una llamada de función. La macro de entrada de mapa de envíos para esta implementación es [DISP_PROPERTY_NOTIFY](../mfc/reference/dispatch-maps.md#disp_property_notify).  
  
-   Implementación de métodos Get/Set.  
  
     Esta implementación está formada por un par de funciones miembro en la clase de control. La implementación de métodos Get/Set llama automáticamente a la obtención de miembros función cuando el usuario del control solicita el valor actual de la propiedad y la función miembro Set cuando el usuario del control solicita que se puede cambiar la propiedad. Utilice esta implementación cuando necesite para calcular el valor de una propiedad en tiempo de ejecución, validar un valor pasado por el usuario del control antes de cambiar la propiedad real, o implementar un tipo de propiedad de lectura o escritura-solo. La macro de entrada de mapa de envíos para esta implementación es [DISP_PROPERTY_EX](../mfc/reference/dispatch-maps.md#disp_property_ex). La siguiente sección, [mediante el Asistente para agregar propiedades para agregar una propiedad personalizada](#_core_using_classwizard_to_add_a_custom_property), usa la propiedad personalizada CircleOffset para ilustrar esta implementación.  
  
-   Implementación con parámetros  
  
     Implementación parametrizada es compatible con el Asistente para agregar propiedades. Una propiedad con parámetros (a veces denominada una matriz de propiedad) se puede utilizar para tener acceso a un conjunto de valores a través de una sola propiedad del control. La macro de entrada de mapa de envíos para esta implementación es `DISP_PROPERTY_PARAM`. Para obtener más información sobre cómo implementar este tipo, consulte [implementar una propiedad con parámetros](../mfc/mfc-activex-controls-advanced-topics.md) en el artículo controles ActiveX: temas avanzados.  
  
##  <a name="_core_using_classwizard_to_add_a_custom_property"></a>Mediante el Asistente para agregar propiedades para agregar una propiedad personalizada  
 El siguiente procedimiento muestra cómo agregar una propiedad personalizada, CircleOffset, que utiliza la implementación de métodos Get/Set. La propiedad personalizada CircleOffset permite que el usuario del control desplazar el círculo desde el centro del rectángulo delimitador del control. El procedimiento para agregar propiedades personalizadas con una implementación que no sea de métodos Get/Set es muy similar.  
  
 También se puede utilizar este mismo procedimiento para agregar otras propiedades personalizadas que desee. Sustituya el nombre de propiedad personalizada para el nombre de la propiedad CircleOffset y los parámetros.  
  
#### <a name="to-add-the-circleoffset-custom-property-using-the-add-property-wizard"></a>Para agregar la propiedad personalizada CircleOffset mediante el Asistente para agregar propiedades  
  
1.  Cargue el proyecto del control.  
  
2.  En la vista de clases, expanda el nodo de biblioteca del control.  
  
3.  Haga clic con el botón derecho en el nodo de interfaz del control (el segundo nodo del nodo de biblioteca) para abrir el menú contextual.  
  
4.  En el menú contextual, haga clic en **agregar** y, a continuación, haga clic en **Agregar propiedad**.  
  
     Se abrirá la [Asistente para agregar propiedades](../ide/names-add-property-wizard.md).  
  
5.  En el **nombre de la propiedad** , escriba `CircleOffset`.  
  
6.  Para **Tipo de implementación**, haga clic en **Métodos Get/Set**.  
  
7.  En el **tipo de propiedad** cuadro, seleccione **corto**.  
  
8.  Escriba nombres únicos para sus funciones Get y Set o acepte los nombres predeterminados.  
  
9. Haga clic en **Finalizar**.  
  
##  <a name="_core_classwizard_changes_for_custom_properties"></a>Agregar propiedad cambios del Asistente para propiedades personalizadas  
 Cuando se agrega la propiedad personalizada CircleOffset, el Asistente para agregar propiedades realiza cambios en el encabezado (. (H) y la implementación (. Archivos CPP) de la clase de control.  
  
 Las líneas siguientes se agregan a la. Archivo H para declarar dos funciones denominadas `GetCircleOffset` y `SetCircleOffset`:  
  
 [!code-cpp[NVC_MFC_AxUI#25](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_1.h)]  
  
 La siguiente línea se agrega a su control. Este archivo IDL:  
  
 [!code-cpp[NVC_MFC_AxUI#26](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_2.idl)]  
  
 Esta línea asigna a la propiedad CircleOffset un número de identificador específico, obtenido de la posición del método en la lista de métodos y propiedades del Asistente para agregar propiedades.  
  
 Además, se agrega la siguiente línea al mapa de envíos (en el. Archivo CPP de la clase de control) para asignar la propiedad CircleOffset a dos funciones de controlador del control:  
  
 [!code-cpp[NVC_MFC_AxUI#27](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_3.cpp)]  
  
 Por último, las implementaciones de la `GetCircleOffset` y `SetCircleOffset` funciones se agregan al final del control. Archivo CPP. En la mayoría de los casos, se modificará la función Get para devolver el valor de la propiedad. La función Set normalmente contiene código que se debe ejecutar antes o después de cambiar la propiedad.  
  
 [!code-cpp[NVC_MFC_AxUI#28](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-properties_4.cpp)]  
  
 Tenga en cuenta que el Asistente para agregar propiedades agrega automáticamente una llamada a [SetModifiedFlag](../mfc/reference/colecontrol-class.md#setmodifiedflag), en el cuerpo de la función de conjunto. Llamar a esta función marca el control como modificado. Si se ha modificado un control, su nuevo estado se guardará cuando se guarda el contenedor. Esta función se debe llamar cuando cambia una propiedad, que se guardan como parte del estado persistente del control, el valor.  
  
## <a name="see-also"></a>Vea también  
 [Controles ActiveX de MFC](../mfc/mfc-activex-controls.md)   
 [Controles ActiveX de MFC: propiedades](../mfc/mfc-activex-controls-properties.md)   
 [Controles ActiveX de MFC: métodos](../mfc/mfc-activex-controls-methods.md)   
 [COleControl (clase)](../mfc/reference/colecontrol-class.md)