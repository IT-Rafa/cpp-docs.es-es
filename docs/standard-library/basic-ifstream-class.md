---
title: basic_ifstream (Clase) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- fstream/std::basic_ifstream
- fstream/std::basic_ifstream::close
- fstream/std::basic_ifstream::is_open
- fstream/std::basic_ifstream::open
- fstream/std::basic_ifstream::rdbuf
- fstream/std::basic_ifstream::swap
dev_langs: C++
helpviewer_keywords:
- std::basic_ifstream [C++]
- std::basic_ifstream [C++], close
- std::basic_ifstream [C++], is_open
- std::basic_ifstream [C++], open
- std::basic_ifstream [C++], rdbuf
- std::basic_ifstream [C++], swap
ms.assetid: 366cd9a7-efc4-4b7f-ba10-c8271e47ffcf
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d300abc29a88c8beaa5e5992b4bca073732b0233
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="basicifstream-class"></a>basic_ifstream (Clase)
Describe un objeto que controla la extracción de elementos y objetos codificados de un búfer de flujo de clase [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>, con elementos de tipo `Elem`, cuyos rasgos de caracteres están determinados por la clase `Tr`.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_ifstream : public basic_istream<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `Elem`  
 Elemento básico del búfer del archivo.  
  
 `Tr`  
 Rasgos del elemento básico del búfer del archivo (normalmente `char_traits`< `Elem`>).  
  
## <a name="remarks"></a>Comentarios  
 El objeto almacena un objeto de clase `basic_filebuf`< `Elem`, `Tr`>.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra cómo leer texto de un archivo.  
  
```  
// basic_ifstream_class.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ifstream ifs("basic_ifstream_class.txt");  
    if (!ifs.bad())  
    {  
        // Dump the contents of the file to cout.  
        cout << ifs.rdbuf();  
        ifs.close();  
    }  
}  
```  
  
## <a name="input-basicifstreamclasstxt"></a>Entrada: basic_ifstream_class.txt  
  
```  
This is the contents of basic_ifstream_class.txt.  
```  
  
## <a name="output"></a>Resultados  
  
```  
This is the contents of basic_ifstream_class.txt.  
```  
  
### <a name="constructors"></a>Constructores  
  
|||  
|-|-|  
|[basic_ifstream](#basic_ifstream)|Inicializa una nueva instancia de un objeto `basic_ifstream`.|  
  
### <a name="member-functions"></a>Funciones miembro  
  
|||  
|-|-|  
|[close](#close)|Cierra un archivo.|  
|[is_open](#is_open)|Determina si un archivo está abierto.|  
|[open](#open)|Abre un archivo.|  
|[rdbuf](#rdbuf)|Devuelve la dirección del búfer de secuencia almacenado.|  
|[swap](#swap)|Intercambia el contenido de `basic_ifstream` por el contenido del `basic_ifstream` proporcionado.|  
  
### <a name="operators"></a>Operadores  
  
|||  
|-|-|  
|[operator=](#op_eq)|Asigna el contenido de este objeto de secuencia. Se trata de una asignación de movimiento que implica un `rvalue` que no deja ninguna copia atrás.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** \<fstream>  
  
 **Espacio de nombres:** std  
  
##  <a name="basic_ifstream"></a>  basic_ifstream::basic_ifstream  
 Construye un objeto de tipo `basic_ifstream`.  
  
```  
basic_ifstream();

explicit basic_ifstream(
    const char* _Filename,  
    ios_base::openmode _Mode = ios_base::in,  
    int _Prot = (int)ios_base::_Openprot);

explicit basic_ifstream(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode = ios_base::in,  
    int _Prot = (int)ios_base::_Openprot);

basic_ifstream(basic_ifstream&& right);
```  
  
### <a name="parameters"></a>Parámetros  
 `_Filename`  
 Nombre del archivo que se va a abrir.  
  
 `_Mode`  
 Una de las enumeraciones de [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `_Prot`  
 Protección predeterminada de apertura del archivo, equivalente al parámetro `shflag` de [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).  
  
### <a name="remarks"></a>Comentarios  
 El primer constructor inicializa la clase base al llamar a [basic_istream](../standard-library/basic-istream-class.md)(`sb`), donde `sb` es el objeto almacenado de clase [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>. También inicializa `sb` al llamar a `basic_filebuf`< `Elem`, `Tr`>.  
  
 El segundo y el tercer constructor inicializan la clase base al llamar a `basic_istream`(`sb`). También inicializa `sb` al llamar a [basic_filebuf](../standard-library/basic-filebuf-class.md#basic_filebuf)< `Elem`, `Tr`> y luego a `sb`. [open](../standard-library/basic-filebuf-class.md#open)(`_Filename`, `_Mode` &#124; `ios_base::in`). Si esta última función devuelve un puntero nulo, el constructor llama a **setstate**(`failbit`).  
  
 El cuarto constructor inicializa el objeto con el contenido de `right`, tratado como una referencia a un valor R.  
  
### <a name="example"></a>Ejemplo  
  En el siguiente ejemplo se muestra cómo leer texto de un archivo. Para crear el archivo, vea el ejemplo de [basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream).  
  
```  
// basic_ifstream_ctor.cpp  
// compile with: /EHsc  
  
#include <fstream>  
#include <iostream>  
  
using namespace std;  
  
int main(int argc, char **argv)  
{  
    ifstream ifs("basic_ifstream_ctor.txt");  
    if (!ifs.bad())  
    {  
        // Dump the contents of the file to cout.  
        cout << ifs.rdbuf();  
        ifs.close();  
    }  
}  
```  
  
##  <a name="close"></a>  basic_ifstream::close  
 Cierra un archivo.  
  
```  
void close();
```  
  
### <a name="remarks"></a>Comentarios  
 Las llamadas a funciones miembro [rdbuf](#rdbuf)  **->**  [cerrar](../standard-library/basic-filebuf-class.md#close).  
  
### <a name="example"></a>Ejemplo  
  Vea [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) para obtener un ejemplo que usa **close**.  
  
##  <a name="is_open"></a>  basic_ifstream::is_open  
 Determina si un archivo está abierto.  
  
```  
bool is_open() const;
```  
  
### <a name="return-value"></a>Valor devuelto  
 **True** si el archivo está abierto, **False** en caso contrario.  
  
### <a name="remarks"></a>Comentarios  
 La función miembro devuelve [rdbuf](#rdbuf)  **->**  [is_open](../standard-library/basic-filebuf-class.md#is_open).  
  
### <a name="example"></a>Ejemplo  
  Vea [basic_filebuf::is_open](../standard-library/basic-filebuf-class.md#is_open) para obtener un ejemplo que usa `is_open`.  
  
##  <a name="open"></a>  basic_ifstream::open  
 Abre un archivo.  
  
```  
void open(
    const char* _Filename,  
    ios_base::openmode _Mode = ios_base::in,  
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,  
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode = ios_base::in,  
    int _Prot = (int)ios_base::_Openprot);

void open(
    const wchar_t* _Filename,  
    ios_base::openmode _Mode);
```  
  
### <a name="parameters"></a>Parámetros  
 `_Filename`  
 Nombre del archivo que se va a abrir.  
  
 `_Mode`  
 Una de las enumeraciones de [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `_Prot`  
 Protección predeterminada de apertura del archivo, equivalente al parámetro `shflag` de [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).  
  
### <a name="remarks"></a>Comentarios  
 La función miembro llama a [rdbuf](#rdbuf) **->** [open](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode` &#124; **ios_base::in**). Si se produce un error en open, la función llama a [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**), que puede iniciar una excepción ios_base::failure.  
  
### <a name="example"></a>Ejemplo  
  Vea [basic_filebuf::open](../standard-library/basic-filebuf-class.md#open) para obtener un ejemplo que usa **open**.  
  
##  <a name="op_eq"></a>  basic_ifstream::operator=  
 Asigna el contenido de este objeto de secuencia. Se trata de una asignación de movimiento que implica un valor R que no deja ninguna copia atrás.  
  
```  
basic_ifstream& operator=(basic_ifstream&& right);
```  
  
### <a name="parameters"></a>Parámetros  
 `right`  
 Referencia a un valor R a un objeto `basic_ifstream`.  
  
### <a name="return-value"></a>Valor devuelto  
 Devuelve `*this`.  
  
### <a name="remarks"></a>Comentarios  
 El operador de miembro reemplaza el contenido del objeto por el contenido de `right`, que se trata como referencia rvalue. Para más información, vea [Lvalues y rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md).  
  
##  <a name="rdbuf"></a>  basic_ifstream::rdbuf  
 Devuelve la dirección del búfer de secuencia almacenado.  
  
```  
basic_filebuf<Elem, Tr> *rdbuf() const 
```  
  
### <a name="return-value"></a>Valor devuelto  
 Puntero a un objeto [basic_filebuf](../standard-library/basic-filebuf-class.md) que representa el búfer de flujo almacenado.  
  
### <a name="example"></a>Ejemplo  
  Vea [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close) para obtener un ejemplo de uso de `rdbuf`.  
  
##  <a name="swap"></a>  basic_ifstream::swap  
 Intercambia el contenido de dos objetos `basic_ifstream`.  
  
```  
void swap(basic_ifstream& right);
```  
  
### <a name="parameters"></a>Parámetros  
 `right`  
 Referencia a otro búfer de secuencia.  
  
### <a name="remarks"></a>Comentarios  
 La función miembro intercambia el contenido de este objeto por el contenido de `right`.  
  
## <a name="see-also"></a>Vea también  
 [Seguridad para subprocesos en la biblioteca estándar de C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Programación con iostream](../standard-library/iostream-programming.md)   
 [Convenciones de iostreams](../standard-library/iostreams-conventions.md)

