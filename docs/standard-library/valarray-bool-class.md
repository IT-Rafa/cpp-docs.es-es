---
title: valarray&lt;bool&gt; (Clase) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- valarray<bool>
- valarray/std::valarray<bool>
dev_langs: C++
helpviewer_keywords: valarray<bool> class
ms.assetid: fc0e7121-4758-4ea5-86c3-f04448f04acf
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 63547ef45ca91bc0c2a93391c0e965b836f9ad96
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2017
---
# <a name="valarrayltboolgt-class"></a>valarray&lt;bool&gt; (Clase)
Una versión especializada de la clase de plantilla **valarray\<Type>** para elementos de tipo `bool`.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class valarray<bool>  
```  
  
## <a name="example"></a>Ejemplo  
  
```cpp  
// valarray_bool.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   valarray<bool> vaBool ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )   
      vaL [ i ] =  -i;  
   for ( i = 1 ; i < 10 ; i += 2 )   
      vaL [ i ] =  i;  
   for ( i = 0 ; i < 10 ; i++ )   
      vaR [ i ] =  i;  
  
   cout << "The initial Left valarray is: ( ";  
   for ( i = 0 ; i < 10 ; i++ )  
      cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
   for ( i = 0 ; i < 10 ; i++ )  
      cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaBool = ( vaL < vaR );  
   cout << "The result of the less-than comparison "  
   << "test is the\n valarray<bool>: ( ";  
   for ( i = 0 ; i < 10 ; i++ )  
      cout << vaBool [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The result of the less-than comparison test is the  
 valarray<bool>: ( 0 0 1 0 1 0 1 0 1 0 ).  
*\  
```  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<valarray>  
  
 **Espacio de nombres:** std  
  
## <a name="see-also"></a>Vea también  
 [valarray (Clase)](../standard-library/valarray-class.md)   
 [Seguridad para subprocesos en la biblioteca estándar de C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)
