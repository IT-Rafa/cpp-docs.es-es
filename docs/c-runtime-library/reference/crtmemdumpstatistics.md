---
title: _CrtMemDumpStatistics
ms.date: 11/04/2016
apiname:
- _CrtMemDumpStatistics
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- CrtMemDumpStatistics
- _CrtMemDumpStatistics
helpviewer_keywords:
- _CrtMemDumpStatistics function
- CrtMemDumpStatistics function
ms.assetid: 27b9d731-3184-4a2d-b9a7-6566ab28a9fe
ms.openlocfilehash: 66eb58b65f3fa20e01ad16d68f3fe1baafd8cd04
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605132"
---
# <a name="crtmemdumpstatistics"></a>_CrtMemDumpStatistics

Vuelca la información del encabezado de depuración de un estado del montón especificado en un formato legible para el usuario (solo versión de depuración).

## <a name="syntax"></a>Sintaxis

```C
void _CrtMemDumpStatistics(
   const _CrtMemState *state
);
```

### <a name="parameters"></a>Parámetros

*state*<br/>
Puntero al estado del montón que se va a volcar.

## <a name="remarks"></a>Comentarios

El **_CrtMemDumpStatistics** función vuelca la información de encabezado de depuración de un estado del montón en un formato legible por el usuario especificado. La aplicación puede usar las estadísticas del volcado para realizar el seguimiento de las asignaciones y detectar problemas de memoria. El estado de la memoria puede contener un estado de montón concreto o la diferencia entre dos estados. Cuando [_DEBUG](../../c-runtime-library/debug.md) no está definido, las llamadas a **_CrtMemDumpStatistics** se quitan durante el preprocesamiento.

El *estado* parámetro debe ser un puntero a un **_CrtMemState** estructura que ha sido rellenada por [_CrtMemCheckpoint](crtmemcheckpoint.md) o devuelto por [_ CrtMemDifference](crtmemdifference.md) antes **_CrtMemDumpStatistics** se llama. Si *estado* es **NULL**, se invoca el controlador de parámetros no válidos, como se describe en [validación de parámetros](../../c-runtime-library/parameter-validation.md). Si la ejecución puede continuar, **errno** está establecido en **EINVAL** y se realiza ninguna acción. Para obtener más información, consulte [errno, _doserrno, _sys_errlist y _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Para obtener más información sobre las funciones de estado del montón y la **_CrtMemState** estructura, vea [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details). Para más información sobre cómo se asignan, inicializan y administran los bloques de memoria en la versión de depuración del montón base, vea [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Requisitos

|Rutina|Encabezado necesario|Encabezados opcionales|
|-------------|---------------------|----------------------|
|**_CrtMemDumpStatistics**|\<crtdbg.h>|\<errno.h>|

Para obtener más información sobre compatibilidad, vea [Compatibilidad](../../c-runtime-library/compatibility.md).

**Bibliotecas:** solo versiones de depuración de [Características de la biblioteca CRT](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Vea también

[Rutinas de depuración](../../c-runtime-library/debug-routines.md)<br/>
