---
description: UnknownMember (MDX)
title: UnknownMember (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 0489556836b943ba91d4e17b3a164aeca0c648d2
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "88341151"
---
# <a name="unknownmember-mdx"></a>UnknownMember (MDX)


  Devuelve el miembro desconocido asociado con un nivel o miembro.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
Member expression syntax  
Member_Expression.UnknownMember  
  
Hierarchy_expression syntax  
Hierarchy_Expression.UnknownMember  
```  
  
## <a name="arguments"></a>Argumentos  
 *Member_Expression*  
 Expresión MDX válida que devuelve un miembro.  
  
 *Hierarchy_Expression*  
 Expresión MDX válida que devuelve una jerarquía.  
  
## <a name="remarks"></a>Observaciones  
 Analysis Services crea un miembro desconocido para asociar los datos de la tabla de hechos con una jerarquía cuando no se conoce la jerarquía. El miembro desconocido puede hallarse en cualquiera de los niveles siguientes:  
  
-   En el nivel superior de las jerarquías de atributo que no se agregan.  
  
-   En el primer nivel por debajo del nivel **todos** para las jerarquías naturales.  
  
-   En cualquier nivel en el caso de las jerarquías no naturales.  
  
 Si se especifica una expresión de miembro, la función **UnknownMember** devuelve el miembro secundario desconocido del miembro especificado. Si el miembro especificado no existe, la función devuelve un valor NULL.  
  
 Si se especifica una expresión de jerarquía, la función **UnknownMember** devuelve el miembro desconocido en el nivel superior si existe uno.  
  
 Si el miembro desconocido no existe en el nivel o el miembro, la función **UnknownMember** crea un miembro null.  
  
> [!NOTE]  
>  Si el miembro desconocido no existe en la jerarquía o el miembro, se genera un error.  
  
## <a name="examples"></a>Ejemplos  
 El ejemplo siguiente devuelve el miembro desconocido del miembro All Products de la jerarquía de atributo Product de todos los miembros de la dimensión Measures.  
  
```  
SELECT [Product].[Product].[All Products].UnknownMember  
    ON Columns,  
[Measures].Members  
    ON Rows  
FROM [Adventure Works]  
  
```  
  
 El ejemplo siguiente devuelve el miembro desconocido de la jerarquía Product Categories de todos los miembros de la dimensión Measures.  
  
```  
SELECT [Product].[Product Categories].UnknownMember  
    ON Columns,  
[Measures].Members  
    ON Rows  
FROM [Adventure Works]  
  
```  
  
## <a name="see-also"></a>Consulte también  
 [Referencia de funciones MDX &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
