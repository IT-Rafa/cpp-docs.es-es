---
title: 'Cómo: agregar compatibilidad con MFC a archivos de Script de recursos (C++)'
ms.date: 11/04/2016
f1_keywords:
- vc.resvw.add.MFC
helpviewer_keywords:
- rc files [C++], adding MFC support
- .rc files [C++], adding MFC support
- MFC, adding support to resource scripts files
- resource script files [C++], adding MFC support
ms.assetid: 599dfe9d-ad26-4e34-899c-49b56599e37f
ms.openlocfilehash: c2d0f9ee30085bd2bcc02cf48fd18f6de63eb69a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594394"
---
# <a name="how-to-add-mfc-support-to-resource-script-files-c"></a>Cómo: agregar compatibilidad con MFC a archivos de Script de recursos (C++)

Normalmente, cuando crea una aplicación MFC para Windows usando el [MFC Application Wizard](../mfc/reference/mfc-application-wizard.md), el asistente genera un conjunto básico de archivos (como un archivo de recursos (.rc) de la secuencia de comandos) que contiene las características principales de Microsoft Foundation clases (MFC). Sin embargo, cuando se edita un archivo .rc para una aplicación Windows que no esté basada en MFC, no estarán disponibles las siguientes características, específicas del marco de trabajo de MFC:

- Asistentes para código MFC

- Cadenas de mensajes de menú

- Contenidos de listas de controles de cuadro combinado

- Hospedaje de controles ActiveX

No obstante, es posible agregar compatibilidad con MFC a archivos .rc que no la tengan.

### <a name="to-add-mfc-support-to-rc-files"></a>Para agregar compatibilidad con MFC a archivos .rc

1. Abra el archivo de script de recursos.

   > [!NOTE]
   > Si el proyecto no contuviera un archivo .rc, vea [Crear un nuevo archivo de script de recursos](../windows/how-to-create-a-resource-script-file.md).

2. En [vista de recursos](../windows/resource-view-window.md), resalte la carpeta de recursos (por ejemplo, MFC.rc).

3. En el [ventana propiedades](/visualstudio/ide/reference/properties-window), establezca el **MFC Mode** propiedad **True**.

   > [!NOTE]
   > Además de tener que establecer este marcador, el archivo .rc deberá formar parte de un proyecto MFC. Por ejemplo, simplemente establecer **MFC Mode** a **True** en un archivo .rc en Win32 proyecto no obtendrá ninguna de las características MFC.

## <a name="requirements"></a>Requisitos

MFC

## <a name="see-also"></a>Vea también

[Archivos de recursos](../windows/resource-files-visual-studio.md)<br/>
[Editores de recursos](../windows/resource-editors.md)