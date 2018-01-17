---
title: reference_wrapper (Clase) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- functional/std::reference_wrapper
- type_traits/std::reference_wrapper
- xrefwrap/std::reference_wrapper
- type_traits/std::reference_wrapper::get
- type_traits/std::reference_wrapper::operator()
- functional/std::reference_wrapper::result_type
- functional/std::reference_wrapper::type
- functional/std::reference_wrapper::get
- functional/std::reference_wrapper::operator()
dev_langs: C++
helpviewer_keywords:
- std::reference_wrapper [C++]
- std::reference_wrapper [C++]
- std::reference_wrapper [C++], result_type
- std::reference_wrapper [C++], type
- std::reference_wrapper [C++], get
ms.assetid: 90b8ed62-e6f1-44ed-acc7-9619bd58865a
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 87608912712f201d4731deac53d7a59fdddf41d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="referencewrapper-class"></a>reference_wrapper (Clase)
Contiene una referencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
template <class Ty>  
class reference_wrapper  
{  
public:  
    typedef Ty type;  
 
    reference_wrapper(Ty&) noexcept;
    operator Ty&() const noexcept;
    Ty& get() const noexcept;

    template <class... Types> 
    auto operator()(Types&&... args) const ->
        decltype(std::invoke(get(), std::forward<Types>(args)...));
 
private:  
    Ty *ptr; // exposition only  
};  
```  
  
## <a name="remarks"></a>Comentarios  
Un `reference_wrapper<Ty>` es un contenedor que se puede asignar de copia o que se puede construir de copia alrededor de una referencia para un objeto o una función de tipo `Ty`, y contiene un puntero que señala a un objeto de ese tipo. Un `reference_wrapper` puede usarse para almacenar referencias en contenedores estándar, y para pasar objetos mediante referencia a `std::bind`.  
  
El tipo `Ty` debe ser un tipo de objeto o un tipo de función, o una aserción estática produce un error en tiempo de compilación.  
  
Las funciones auxiliares [std::ref](functional-functions.md#ref) y [std::cref](functional-functions.md#cref) pueden usarse para crear objetos `reference_wrapper`.  
  
### <a name="constructors"></a>Constructores  
  
|||  
|-|-|  
|[reference_wrapper](#reference_wrapper)|Construye un objeto `reference_wrapper`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[result_type](#result_type)|Tipo de resultado débil de la referencia ajustada.|  
|[type](#type)|Tipo de la referencia ajustada.|  
  
### <a name="member-functions"></a>Funciones miembro  
  
|||  
|-|-|  
|[get](#get)|Obtiene la referencia ajustada.|  
  
### <a name="operators"></a>Operadores  
  
|||  
|-|-|  
|[reference_wrapper::operator Ty&amp;](#op_ty_amp)|Obtiene un puntero a la referencia ajustada.|  
|[reference_wrapper::operator()](#op_call)|Llama a la referencia ajustada.|  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<functional>  
  
 **Espacio de nombres:** std  
  
##  <a name="get"></a> reference_wrapper::get  
 Obtiene la referencia ajustada.  
  
```  
Ty& get() const noexcept;
```  
  
### <a name="remarks"></a>Comentarios  
La función miembro devuelve la referencia ajustada.  
  
### <a name="example"></a>Ejemplo  
  
```cpp  
// std__functional__reference_wrapper_get.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int main() {   
    int i = 1;   
    std::reference_wrapper<int> rwi(i);   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "rwi = " << rwi << std::endl;   
    rwi.get() = -1;   
    std::cout << "i = " << i << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
rwi = 1  
i = -1  
```  
  
##  <a name="op_ty_amp"></a> reference_wrapper::operator Ty&amp;  
 Obtiene la referencia ajustada.  
  
```  
operator Ty&() const noexcept;
```  
  
### <a name="remarks"></a>Comentarios  
 El operador miembro devuelve `*ptr`.  
  
### <a name="example"></a>Ejemplo  
  
```cpp  
// std__functional__reference_wrapper_operator_cast.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int main() {   
    int i = 1;   
    std::reference_wrapper<int> rwi(i);   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "(int)rwi = " << (int)rwi << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
(int)rwi = 1  
```  
  
##  <a name="op_call"></a> reference_wrapper::operator()  
 Llama a la referencia ajustada.  
  
```  
template <class... Types>  
auto operator()(Types&&... args);
```  
  
### <a name="parameters"></a>Parámetros  
 `Types`  
 Los tipos de la lista de argumentos.  
  
 `args`  
 La lista de argumentos.  
  
### <a name="remarks"></a>Comentarios  
 El miembro de plantilla `operator()` devuelve `std::invoke(get(), std::forward<Types>(args)...)`.  
  
### <a name="example"></a>Ejemplo  
  
```cpp  
// std__functional__reference_wrapper_operator_call.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    std::reference_wrapper<int (int)> rwi(neg);   
  
    std::cout << "rwi(3) = " << rwi(3) << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
rwi(3) = -3  
```  
  
##  <a name="reference_wrapper"></a> reference_wrapper::reference_wrapper  
 Construye un objeto `reference_wrapper`.  
  
```  
reference_wrapper(Ty& val) noexcept;
```  
  
### <a name="parameters"></a>Parámetros  
 `Ty`  
 El tipo que se va a ajustar.  
  
 `val`  
 El valor que se va a ajustar.  
  
### <a name="remarks"></a>Comentarios  
 El constructor almacena el valor almacenado `ptr` en `&val`.  
  
### <a name="example"></a>Ejemplo  
  
```cpp  
// std__functional__reference_wrapper_reference_wrapper.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    int i = 1;   
    std::reference_wrapper<int> rwi(i);   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "rwi = " << rwi << std::endl;   
    rwi.get() = -1;   
    std::cout << "i = " << i << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
rwi = 1  
i = -1  
```  
  
##  <a name="result_type"></a> reference_wrapper::result_type  
 Tipo de resultado débil de la referencia ajustada.  
  
```  
typedef R result_type;  
```  
  
### <a name="remarks"></a>Comentarios  
 La definición de tipo `result_type` es un sinónimo para el tipo de resultado débil de una función ajustada. Esta definición de tipo solo es significativa para los tipos de función.  
  
### <a name="example"></a>Ejemplo  
  
```cpp  
// std__functional__reference_wrapper_result_type.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    typedef std::reference_wrapper<int (int)> Mywrapper;   
    Mywrapper rwi(neg);   
    Mywrapper::result_type val = rwi(3);   
  
    std::cout << "val = " << val << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
val = -3  
```  
  
##  <a name="type"></a> reference_wrapper::type  
 Tipo de la referencia ajustada.  
  
```  
typedef Ty type;  
```  
  
### <a name="remarks"></a>Comentarios  
 La definición de tipo es un sinónimo del argumento de plantilla `Ty`.  
  
### <a name="example"></a>Ejemplo  
  
```cpp  
// std__functional__reference_wrapper_type.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val) {   
    return (-val);   
}   
  
int main() {   
    int i = 1;   
    typedef std::reference_wrapper<int> Mywrapper;   
    Mywrapper rwi(i);   
    Mywrapper::type val = rwi.get();   
  
    std::cout << "i = " << i << std::endl;   
    std::cout << "rwi = " << val << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
i = 1  
rwi = 1  
```  
  
## <a name="see-also"></a>Vea también  
 [cref](../standard-library/functional-functions.md#cref)   
 [ref](../standard-library/functional-functions.md#ref)
