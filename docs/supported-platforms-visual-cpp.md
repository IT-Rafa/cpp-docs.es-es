---
title: Plataformas compatibles (Visual C++)
ms.date: 11/04/2016
ms.technology:
- cpp-tools
helpviewer_keywords:
- Visual C++, platforms supported
- platforms [C++]
ms.assetid: 0d893056-4008-411a-b3d1-5f57fd7da95c
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 5a077ae90078e4157c154cae2821e67642eff64a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459441"
---
# <a name="supported-platforms-visual-c"></a>Plataformas compatibles (Visual C++)

Las aplicaciones compiladas con Visual Studio pueden tener como destino distintas plataformas, tal y como se indica a continuación.

|Sistema operativo|x86|x64|ARM|
|----------------------|---------|---------|---------|
|Windows XP|X\*|X\*||
|Windows Server 2003|X\*|X\*||
|Windows Vista|X|X||
|Windows Server 2008|X|X||
|Windows 7|X|X||
|Windows Server 2012 R2|X|X||
|Windows 8|X|X|X|
|Windows 8.1|X|X|X|
|Windows 10|X|X|X|
|Android \*\*|X|X|X|
|iOS \*\*|X|X|X|
|Linux \*\*\*|X|X|X|

\* Para la compilación de proyectos de Windows XP y Windows Server 2003, puede usar el conjunto de herramientas de la plataforma Windows XP incluido en Visual Studio 2017, Visual Studio 2015, Visual Studio 2013 y Visual Studio 2012 Update 1 o posterior. Para más información sobre cómo usar este conjunto de herramientas de la plataforma, vea [Configurar 11 programas de C++ para Windows XP](build/configuring-programs-for-windows-xp.md). Para más información sobre cómo cambiar el conjunto de herramientas de la plataforma, vea [Cómo: Modificar versión de .NET Framework de destino y el conjunto de herramientas de la plataforma](build/how-to-modify-the-target-framework-and-platform-toolset.md).

\*\* Si quiere establecer como destino las plataformas iOS o Android, instale la carga de trabajo **Desarrollo móvil con C++** en el instalador de Visual Studio 2017 (o el componente opcional **Visual C++ para desarrollo móvil multiplataforma** en el programa de instalación de Visual Studio 2015). Para obtener instrucciones, vea [Instalar Visual C++ para el desarrollo móvil multiplataforma](/visualstudio/cross-platform/install-visual-cpp-for-cross-platform-mobile-development). Para compilar código de iOS, debe tener un equipo Mac y además cumplir otros requisitos. Para obtener una lista de los requisitos previos e instrucciones de instalación, vea [Instalar y configurar herramientas para compilar con iOS](/visualstudio/cross-platform/install-and-configure-tools-to-build-using-ios). Puede compilar código ARM o x86 para que coincida con el hardware de destino. Use configuraciones x86 en compilaciones para el simulador de iOS, el emulador de Microsoft Visual Studio para Android y algunos dispositivos Android. Use configuraciones de ARM en compilaciones para dispositivos iOS y la mayoría de los dispositivos Android.

\*\*\* Si quiere establecer como destino las plataformas Linux, instale la carga de trabajo **Desarrollo para Linux con C++** en el instalador de Visual Studio 2017. Para obtener instrucciones, consulte [Descargar, instalar y configurar la carga de trabajo de Linux](linux/download-install-and-setup-the-linux-development-workload.md). Este conjunto de herramientas compila el archivo ejecutable en la máquina de destino, permitiendo así compilar para cualquier arquitectura compatible.

Para más información sobre cómo configurar la plataforma de destino, vea [Procedimiento para configurar proyectos de Visual C++ en plataformas de destino de 64 bits, x64](build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).

## <a name="see-also"></a>Vea también

- [Herramientas y características de Visual C++ en las ediciones de Visual Studio](ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)
- [Introducción](/visualstudio/ide/getting-started-with-visual-cpp-in-visual-studio)