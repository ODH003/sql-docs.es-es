---
description: DateCreated (propiedad, ADOX)
title: DateCreated (propiedad, ADOX) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
apitype: COM
f1_keywords:
- _Table::get_DateCreated
- _Table::DateCreated
- _Table::GetDateCreated
helpviewer_keywords:
- DateCreated property [ADOX]
ms.assetid: 2bf4b00d-045c-444e-8af7-8af6297ed418
author: rothja
ms.author: jroth
ms.openlocfilehash: 5fff28639b996e05e2e0eed14eed357fe62e5e0b
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "100050165"
---
# <a name="datecreated-property-adox"></a>DateCreated (propiedad, ADOX)
Indica la fecha de creación del objeto.  
  
## <a name="return-values"></a>Valores devueltos  
 Devuelve un valor **Variant** que especifica la fecha de creación. El valor es NULL si el proveedor no admite **DateCreated** .  
  
## <a name="remarks"></a>Observaciones  
 La propiedad **DateCreated** es null para los objetos recién anexados. Después de anexar una nueva [vista](./view-object-adox.md) o [procedimiento](./procedure-object-adox.md), debe llamar al método [Refresh](../ado-api/refresh-method-ado.md) de la colección [views](./views-collection-adox.md) o [Procedures](./procedures-collection-adox.md) para obtener los valores de la propiedad **DateCreated** .  
  
## <a name="applies-to"></a>Se aplica a  

:::row:::
    :::column:::
        [Objeto Procedure (ADOX)](./procedure-object-adox.md)  
    :::column-end:::
    :::column:::
        [Objeto Table (ADOX)](./table-object-adox.md)  
    :::column-end:::
    :::column:::
        [Objeto View (ADOX)](./view-object-adox.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>Consulte también  
 [Ejemplo de propiedades DateCreated y DateModified (VB)](./datecreated-and-datemodified-properties-example-vb.md)   
 [DateModified (propiedad, ADOX)](./datemodified-property-adox.md)