---
title: CRTThreadTraits (clase)
ms.date: 11/04/2016
f1_keywords:
- CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits
- ATLBASE/ATL::CRTThreadTraits::CreateThread
helpviewer_keywords:
- CRTThreadTraits class
- threading [ATL], creation functions
- threading [ATL], CRT threads
ms.assetid: eb6e20b0-c2aa-4170-8e34-aaeeacc86343
ms.openlocfilehash: 1e54b4db2605c3006697d0a26d34066de666f0fc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641953"
---
# <a name="crtthreadtraits-class"></a>CRTThreadTraits (clase)

Esta clase proporciona la función de creación de un subproceso de CRT. Utilice esta clase si el subproceso va a usar las funciones de CRT.

> [!IMPORTANT]
>  Esta clase y sus miembros no se puede usar en aplicaciones que se ejecutan en el tiempo de ejecución de Windows.

## <a name="syntax"></a>Sintaxis

```
class CRTThreadTraits
```

## <a name="members"></a>Miembros

### <a name="public-methods"></a>Métodos públicos

|Name|Descripción|
|----------|-----------------|
|[CRTThreadTraits::CreateThread](#createthread)|(Estático) Llame a esta función para crear un subproceso que puede usar funciones de CRT.|

## <a name="remarks"></a>Comentarios

Rasgos de subproceso son clases que proporcionan una función de creación de un tipo determinado de subproceso. La función de creación tiene la misma firma y la misma semántica que el Windows [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) función.

Rasgos del subproceso se utilizan las clases siguientes:

- [CThreadPool](../../atl/reference/cthreadpool-class.md)

- [CWorkerThread](../../atl/reference/cworkerthread-class.md)

Si el subproceso no va a utilizar las funciones de CRT, use [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md) en su lugar.

## <a name="requirements"></a>Requisitos

**Encabezado:** atlbase.h

##  <a name="createthread"></a>  CRTThreadTraits::CreateThread

Llame a esta función para crear un subproceso que puede usar funciones de CRT.

```
static HANDLE CreateThread(
    LPSECURITY_ATTRIBUTES lpsa,
    DWORD dwStackSize,
    LPTHREAD_START_ROUTINE pfnThreadProc,
    void* pvParam,
    DWORD dwCreationFlags,
    DWORD* pdwThreadId) throw();
```

### <a name="parameters"></a>Parámetros

*LPSA*<br/>
Los atributos de seguridad para el nuevo subproceso.

*dwStackSize*<br/>
El tamaño de pila para el nuevo subproceso.

*pfnThreadProc*<br/>
El procedimiento de subproceso del subproceso nuevo.

*pvParam*<br/>
El parámetro que se pasa al procedimiento de subproceso.

*dwCreationFlags*<br/>
La creación de indicadores (0 o CREATE_SUSPENDED).

*pdwThreadId*<br/>
[out] Dirección de la variable DWORD que, si se ejecuta correctamente, recibe el identificador de subproceso del subproceso recién creado.

### <a name="return-value"></a>Valor devuelto

Devuelve el identificador al subproceso recién creado o NULL en caso de error. Llame a [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360) para obtener más información.

### <a name="remarks"></a>Comentarios

Consulte [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) para obtener más información sobre los parámetros para esta función.

Esta función llama a [_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) para crear el subproceso.

## <a name="see-also"></a>Vea también

[Información general de clases](../../atl/atl-class-overview.md)
