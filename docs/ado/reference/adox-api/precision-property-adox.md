---
description: Precision (propiedad, ADOX)
title: Propiedad Precision (ADOX) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _Column::put_Precision
- _Column::PutPrecision
- _Column::GetPrecision
- _Column::get_Precision
- _Column::Precision
helpviewer_keywords:
- Precision property [ADOX]
ms.assetid: 0e0ecbbf-d7de-49d4-a128-5a519ecd54ba
author: rothja
ms.author: jroth
ms.openlocfilehash: f98cc2ee59e7b3e0c873a6bc48c3234148543484
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "100053909"
---
# <a name="precision-property-adox"></a>Precision (propiedad, ADOX)
Indica la precisión máxima de los valores de datos de la [columna](./column-object-adox.md).  
  
## <a name="settings-and-return-values"></a>Configuración y valores devueltos  
 Establece y devuelve un valor **Long** que es la precisión máxima de los valores de datos de la columna cuando la propiedad [Type](./type-property-column-adox.md) es un tipo numérico. La **precisión** se omite para todos los demás tipos de datos.  
  
## <a name="remarks"></a>Observaciones  
 El valor predeterminado es cero (**0**).  
  
 Esta propiedad es de solo lectura para los objetos de [columna](./column-object-adox.md) ya anexados a una colección.  
  
## <a name="applies-to"></a>Se aplica a  
 [Objeto Column (ADOX)](./column-object-adox.md)  
  
## <a name="see-also"></a>Consulte también  
 [Ejemplo de código ADOX: ejemplo de propiedades NumericScale y Precision (VB)](./adox-code-example-numericscale-and-precision-properties-example-vb.md)   
 [Type (propiedad, Column) (ADOX)](./type-property-column-adox.md)   
 [Objeto Column (ADOX)](./column-object-adox.md)