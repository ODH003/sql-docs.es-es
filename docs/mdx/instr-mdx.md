---
description: Instr (MDX)
title: Instr (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 877fc4658081108e810e404dfc8d4a368c6964ba
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "88387361"
---
# <a name="instr-mdx"></a>Instr (MDX)


  Devuelve la posición de la primera aparición de una cadena dentro de otra.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
InStr([start, ]searched_string, search_string[, compare])  
```  
  
## <a name="arguments"></a>Argumentos  
 *start*  
 (Opcional) Expresión numérica que establece la posición inicial de cada búsqueda. Si se omite este valor, la búsqueda comienza en la posición del primer carácter. Si start es NULL, el valor devuelto de la función es indefinido.  
  
 *searched_string*  
 Expresión de cadena en la que se va a buscar.  
  
 *search_string*  
 Expresión de cadena que se va a buscar.  
  
 *Comparar*  
 (opcional) Valor entero. Este argumento siempre se pasa por alto. Se define para la compatibilidad con otras funciones de **instr** en otros lenguajes.  
  
## <a name="return-value"></a>Valor devuelto  
 Valor entero con la posición inicial de *cadena2* en *cadena1*.  
  
 Además, la función **instr** devuelve los valores que se muestran en la tabla siguiente, en función de la condición:  
  
|Condición|Valor devuelto|  
|---------------|------------------|  
|String1 es de longitud cero|cero (0)|  
|String1 es NULL|no definido|  
|String2 es de longitud cero|start|  
|String2 es NULL|no definido|  
|String2 no se encuentra|cero (0)|  
|start es mayor que Len(String2)|cero (0)|  
  
## <a name="remarks"></a>Observaciones  
  
> [!WARNING]  
>  **Instr** siempre realiza una comparación sin distinción entre mayúsculas y minúsculas.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el uso de la función **instr** y se muestran diferentes escenarios de resultados.  
  
```  
with   
    member [Date].[Date].[Results] as "Results"  
    member measures.[lowercase found in lowercase string] as InStr( "abcdefghijklmnñopqrstuvwxyz", "o")  
    member measures.[uppercase found in lowercase string] as InStr( "abcdefghijklmnñopqrstuvwxyz", "O")  
    member measures.[searched string is empty]            as InStr( "", "o")  
    member measures.[searched string is null]             as iif(IsError(InStr( null, "o")), "Is Error", iif(IsNull(InStr( null, "o")), "Is Null","Is undefined"))  
    member measures.[search string is empty]              as InStr( "abcdefghijklmnñopqrstuvwxyz", "")  
    member measures.[search string is empty start 10]     as InStr(10, "abcdefghijklmnñopqrstuvwxyz", "")  
    member measures.[search string is null]               as iif(IsError(InStr( null, "o")), "Is Error", iif(IsNull(InStr( null, "o")), "Is Null","Is undefined"))  
    member measures.[found from start 10]                 as InStr( 10, "abcdefghijklmnñopqrstuvwxyz", "o")  
    member measures.[NOT found from start 17]             as InStr( 17, "abcdefghijklmnñopqrstuvwxyz", "o")  
    member measures.[NULL start]                          as iif(IsError(InStr( null, "abcdefghijklmnñopqrstuvwxyz", "o")), "Is Error", iif(IsNull(InStr( null, "abcdefghijklmnñopqrstuvwxyz", "o")), "Is Null","Is undefined"))  
    member measures.[start greater than searched length]  as InStr( 170, "abcdefghijklmnñopqrstuvwxyz", "o")  
  
select  [Results] on columns,  
       { measures.[lowercase found in lowercase string]  
       , measures.[uppercase found in lowercase string]  
       , measures.[searched string is empty]  
       , measures.[searched string is null]  
       , measures.[search string is empty]  
       , measures.[search string is empty start 10]  
       , measures.[search string is null]  
       , measures.[found from start 10]  
       , measures.[NOT found from start 17]  
       , measures.[NULL start]   
       , measures.[start greater than searched length]  
       } on rows  
  
from [Adventure Works]  
```  
  
 La tabla siguiente muestra los resultados obtenidos.  
  
|Campo en medidas|Resultados|  
|-|-|  
|lowercase found in lowercase string|16|  
|uppercase found in lowercase string|16|  
|searched string is empty|0|  
|searched string is null|Sin definir|  
|search string is empty|1|  
|search string is empty start 10|10|  
|search string is null|Sin definir|  
|found from start 10|16|  
|NOT found from start 17|0|  
|NULL start|Sin definir|  
|start greater than searched length|0|  
  
  
