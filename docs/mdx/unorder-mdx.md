---
description: Unorder (MDX)
title: Desordenar (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 192f320ebc5257f2e6829e15fc40b8144208a521
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "88341182"
---
# <a name="unorder-mdx"></a>Unorder (MDX)


  Quita cualquier orden impuesto sobre un conjunto especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
Unorder(Set_Expression)   
```  
  
## <a name="arguments"></a>Argumentos  
 *Set_Expression*  
 Expresión MDX (Expresiones multidimensionales) válida que devuelve un conjunto.  
  
## <a name="remarks"></a>Observaciones  
 La función **unorder** quita cualquier orden impuesta en las tuplas contenidas en el conjunto por cualquier otra función o instrucción, como la función [Order](../mdx/order-mdx.md) . El orden de las tuplas en el conjunto devuelto por la función **unorder** es indeterminado.  
  
 La función **unorder** se utiliza como una sugerencia para la optimización de consultas para el procesamiento de conjuntos. Si el orden de las tuplas dentro de un conjunto no es importante para un cálculo o una consulta, el uso de la función **unorder** puede proporcionar una ventaja de rendimiento en dichos casos. Por ejemplo, la función [NonEmpty (MDX)](../mdx/nonempty-mdx.md) puede funcionar mejor cuando el conjunto proporcionado a esta función no está ordenado que si [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] necesita conservar el orden, aunque con [!INCLUDE[ssASCurrent](../includes/ssascurrent-md.md)] , el procesador de consultas intenta realizar esta función automáticamente para muchas funciones, como **SUM** y **Aggregate**. La ventaja de rendimiento que supone el uso de **unorder** solo es probable que se aprecie en conjuntos muy grandes que se componen de millones de tuplas.  
  
## <a name="example"></a>Ejemplo  
 El siguiente pseudocódigo muestra la sintaxis de esta función.  
  
```  
NonEmpty (UnOrder (<set_expression>))  
```  
  
## <a name="see-also"></a>Consulte también  
 [Referencia de funciones MDX &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
