---
description: Utilizar CacheSize
title: Usar CacheSize | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- locks [ADO], CacheSize property
- CacheSize property [ADO]
ms.assetid: ca1c3422-b6a4-4ba6-af55-54f975b698b1
author: rothja
ms.author: jroth
ms.openlocfilehash: 31c9b1dd1ccc3ef61b120bf3d075b81fc34c0eb6
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "100032287"
---
# <a name="using-cachesize"></a>Utilizar CacheSize
Utilice la propiedad **CacheSize** para controlar el número de registros que se van a recuperar de una vez en la memoria local desde el proveedor. Por ejemplo, si el **CacheSize** es 10, después de abrir primero el objeto de **conjunto de registros** , el proveedor recupera los primeros 10 registros en la memoria local. A medida que se desplaza por el objeto de **conjunto de registros** , el proveedor devuelve los datos del búfer de memoria local. En cuanto se desplaza por encima del último registro de la memoria caché, el proveedor recupera los 10 registros siguientes del origen de datos en la memoria caché.  
  
> [!NOTE]
>  **CacheSize** se basa en la propiedad específica del proveedor de **filas abiertas máximas** (en la colección **Properties** del objeto **Recordset** ). No se puede establecer **CacheSize** en un valor mayor que el **máximo de filas abiertas.** Para modificar el número de filas que puede abrir el proveedor, establezca máximo de **filas abiertas**.  
  
 El valor de **CacheSize** se puede ajustar durante la vida del objeto de **conjunto de registros** , pero el cambio de este valor solo afecta al número de registros de la memoria caché después de las recuperaciones posteriores del origen de datos. Si se cambia el valor de propiedad por sí solo, no se cambiará el contenido actual de la memoria caché.  
  
 Si hay menos registros para recuperar que el **CacheSize** especifica, el proveedor devuelve los registros restantes y no se produce ningún error.  
  
 No se permite un valor **CacheSize** de cero y devuelve un error.  
  
 Los registros recuperados de la memoria caché no reflejan los cambios simultáneos que otros usuarios han realizado en los datos de origen. Para forzar una actualización de todos los datos en caché, use el método [Resync](../../../ado/reference/ado-api/resync-method.md) .  
  
 Si **CacheSize** se establece en un valor mayor que 1, los métodos de navegación ([Move](../../../ado/reference/ado-api/move-method-ado.md), [MoveFirst, MoveLast, MoveNext y MovePrevious](../../../ado/reference/ado-api/movefirst-movelast-movenext-and-moveprevious-methods-ado.md)) pueden dar lugar a la navegación a un registro eliminado, en caso de que se produzca la eliminación una vez recuperados los registros. Después de la captura inicial, las eliminaciones posteriores no se reflejarán en la memoria caché de datos hasta que intente obtener acceso a un valor de datos de una fila eliminada. Sin embargo, si se establece **CacheSize** en 1, se elimina este problema porque no se pueden capturar filas eliminadas.
