---
title: aligned_storage (Clase) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::aligned_storage
dev_langs: C++
helpviewer_keywords:
- aligned_storage class
- aligned_storage
ms.assetid: f255e345-1f05-4d07-81e4-017f420839fb
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a10f0ee119eab96e183f77c3e51fe877d31ca5ba
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2017
---
# <a name="alignedstorage-class"></a>aligned_storage (Clase)
Crea un tipo alineado como corresponda.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
template <std::size_t Len, std::size_t Align>  
struct aligned_storage;  
 
template <std::size_t Len, std::size_t Align = alignment_of<max_align_t>::value>  
using aligned_storage_t = typename aligned_storage<Len, Align>::type;  
```  
  
#### <a name="parameters"></a>Parámetros  
 `Len`  
 Tamaño del objeto.  
  
 `Align`  
 Alineación del objeto.  
  
## <a name="remarks"></a>Comentarios  
 El typedef de miembro `type` de plantilla es un sinónimo de un tipo POD con alineación `Align` y tamaño `Len`. `Align` debe ser igual a `alignment_of<T>::value` para algún tipo `T` o para la alineación predeterminada.  
  
## <a name="example"></a>Ejemplo  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
typedef std::aligned_storage<sizeof (int),   
    std::alignment_of<double>::value>::type New_type;   
int main()   
    {   
    std::cout << "alignment_of<int> == "   
        << std::alignment_of<int>::value << std::endl;   
    std::cout << "aligned to double == "   
        << std::alignment_of<New_type>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
alignment_of<int> == 4  
aligned to double == 8  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<type_traits>  
  
 **Espacio de nombres:** std  
  
## <a name="see-also"></a>Vea también  
 [<type_traits>](../standard-library/type-traits.md)   
 [alignment_of (Clase)](../standard-library/alignment-of-class.md)