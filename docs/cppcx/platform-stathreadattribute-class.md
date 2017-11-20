---
title: STAThreadAttribute (clase) | Documentos de Microsoft
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- COLLECTION/Platform::Platform
- COLLECTION/Platform::Platform::STAThreadAttribute constructor 1
- COLLECTION/Platform::Platform::STAThreadAttribute::Equals
- COLLECTION/Platform::Platform::STAThreadAttribute::GetHashCode
- COLLECTION/Platform::Platform::STAThreadAttribute::ToString
dev_langs: C++
helpviewer_keywords: Platform::STAThreadAttribute Class
ms.assetid: f97960fc-e673-4d9e-910a-54c8415411c4
caps.latest.revision: "3"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 54e4b7621879252b14fa0fe71c837439da147df5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2017
---
# <a name="platformstathreadattribute-class"></a>Platform::STAThreadAttribute (Clase)
Indica que el modelo de subprocesamiento de una aplicación es un contenedor uniproceso (STA).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
public ref class STAThreadAttribute sealed : Attribute  
```  
  
### <a name="members"></a>Miembros  
  
### <a name="public-constructors"></a>Constructores públicos  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[STAThreadAttribute (Constructor 1)](#ctor)|Inicializa una nueva instancia de la clase.|  
  
### <a name="public-methods"></a>Métodos públicos  
 El atributo STAThreadAttribute hereda de [clase Platform:: Object](../cppcx/platform-object-class.md). STAThreadAttribute también sobrecarga o tiene los siguientes miembros:  
  
|Nombre|Descripción|  
|----------|-----------------|  
|[STAThreadAttribute::Equals](#equals)|Determina si el objeto especificado es igual al objeto actual.|  
|[STAThreadAttribute::GetHashCode](#gethashcode)|Devuelve el código hash de esta instancia.|  
|[STAThreadAttribute::ToString](#tostring)|Devuelve una cadena que representa el objeto actual.|  
  
## <a name="inheritance-hierarchy"></a>Jerarquía de herencia  
 `Platform`  
  
### <a name="requirements"></a>Requisitos  
 **Encabezado:** collection.h  
  
 **Espacio de nombres:** Plataforma  



## <a name="ctor"></a> STAThreadAttribute constructor
Inicializa una nueva instancia de la clase STAThreadAttribute.  
  
### <a name="syntax"></a>Sintaxis  
  
```cpp  
public:STAThreadAttribute()  
```  
  


## <a name="equals"></a>STAThreadAttribute::Equals
Determina si el objeto especificado es igual al objeto actual.  
  
### <a name="syntax"></a>Sintaxis  
  
```cpp  
public:virtual override bool Equals(  Object^ obj)  
```  
  
### <a name="parameters"></a>Parámetros  
 obj  
 Objeto que se va a comparar.  
  
### <a name="return-value"></a>Valor devuelto  
 `true` si los objetos son iguales; en caso contrario, `false`.  
  


## <a name="gethashcode"></a>STAThreadAttribute::GetHashCode
Devuelve el código hash de esta instancia.  
  
### <a name="syntax"></a>Sintaxis  
  
```cpp  
public:int GetHashCode()  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Código hash de esta instancia.  
  


## <a name="tostring"></a>STAThreadAttribute::ToString
Devuelve una cadena que representa el objeto actual.  
  
### <a name="syntax"></a>Sintaxis  
  
```cpp  
public:String^ ToString()  
```  
  
### <a name="return-value"></a>Valor devuelto  
 Una cadena que representa el objeto actual.  
  

  
## <a name="see-also"></a>Vea también  
 [Namespace de plataforma](platform-namespace-c-cx.md)