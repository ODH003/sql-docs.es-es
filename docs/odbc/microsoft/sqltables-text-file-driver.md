---
description: SQLTables (controlador de archivo de texto)
title: SQLTables (controlador de archivo de texto) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- text file driver [ODBC], SQLTables
- SQLTables function [ODBC], Text File Driver
ms.assetid: f47fd1a4-5bd8-4b2e-8ae3-e595e49f4f95
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: a6c6f65603cee70811d7c9894ba9d840d28ad4f4
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "88339711"
---
# <a name="sqltables-text-file-driver"></a>SQLTables (controlador de archivo de texto)
> [!NOTE]  
>  En este tema se proporciona información específica del controlador de archivo de texto. Para obtener información general sobre esta función, vea el tema correspondiente en referencia de la [API de ODBC](../../odbc/reference/syntax/odbc-api-reference.md).  
  
|Argumento|Comentarios|  
|--------------|--------------|  
|*szTableOwner*|El único argumento válido para *szTableOwner* es null porque ninguno de los controladores admite nombres de propietario. Con *szTableOwner* establecido en null, se devuelven todas las tablas. Se devuelve NULL en el TABLE_OWNER columna.|  
|*szTableQualifier*|En la columna TABLE_QUALIFIER, **SQLTables** devolverá la ruta de acceso a un directorio.|  
|*SzTableType*|"Tabla" es el único tipo de tabla admitido.<br /><br /> Cuando se usa el controlador de texto, la lista de archivos devueltos por **SQLTables** viene determinada por las extensiones de archivo del cuadro de **lista Extensiones** del cuadro de diálogo **configuración de texto ODBC** .|
