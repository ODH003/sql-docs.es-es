---
title: Administrar ensamblados de integración CLR | Microsoft Docs
description: Puede hospedar ensamblados DLL administrados en SQL Server.  Puede registrar, modificar y quitar ensamblados, así como administrar los permisos y los archivos asociados.
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- database objects [CLR integration], assemblies
- common language runtime [SQL Server], assemblies
- assemblies [CLR integration], managing
ms.assetid: bdbbf325-14f6-460e-a35a-d3861d3c961e
author: rothja
ms.author: jroth
ms.openlocfilehash: 84f10e104754019e67255b1a031e228a9ff4c48e
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85899582"
---
# <a name="managing-clr-integration-assemblies"></a>Administrar ensamblados de integración CLR
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]
  El código administrado se compila y, a continuación, se implementa en unidades denominadas ensamblado. Un ensamblado se empaqueta como un archivo DLL o ejecutable (.exe). Aunque un archivo ejecutable se puede ejecutar solo, una DLL se debe hospedar en una aplicación existente. Los ensamblados DLL administrados pueden cargarse y hospedarse en [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] . [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] requiere que el ensamblado se registre en una base de datos de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mediante la instrucción CREATE ASSEMBLY para poder cargarlo en el proceso y usarlo. Los ensamblados también pueden actualizarse a partir de una versión más reciente mediante la instrucción ALTER ASSEMBLY o quitarse de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mediante la instrucción DROP ASSEMBLY.  
  
 La información de ensamblado se almacena en la tabla **Sys. assembly_files** en la base de datos donde se ha instalado el ensamblado. La tabla **Sys. assembly_files** contiene las columnas siguientes.  
  
|Columna|Descripción|  
|------------|-----------------|  
|assembly_id|Identificador definido para el ensamblado. Este número se asigna a todos los objetos relacionados con el mismo ensamblado.|  
|name|Nombre del objeto.|  
|file_id|Número que identifica cada objeto, con el primer objeto asociado a una **assembly_id** determinada a la que se proporciona el valor 1. Si hay varios objetos asociados al mismo **assembly_id**, cada valor de **file_id** subsiguiente se incrementa en 1.|  
|contenido|Representación hexadecimal del ensamblado o archivo.|  
  
## <a name="in-this-section"></a>En esta sección  
 [Crear un ensamblado](../../../relational-databases/clr-integration/assemblies/creating-an-assembly.md)  
 Describe la creación de los ensamblados SAFE, EXTERNAL_ACCESS y UNSAFE CLR en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
 [Modificar un ensamblado](../../../relational-databases/clr-integration/assemblies/altering-an-assembly.md)  
 Describe la actualización de los ensamblados CLR en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
 [Quitar un ensamblado](../../../relational-databases/clr-integration/assemblies/dropping-an-assembly.md)  
 Describe cómo quitar los ensamblados CLR de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
## <a name="see-also"></a>Consulte también  
 [Seguridad de la integración CLR](../../../relational-databases/clr-integration/security/clr-integration-security.md)   
 [Seguridad de acceso del código de integración CLR](../../../relational-databases/clr-integration/security/clr-integration-code-access-security.md)  
  
  
