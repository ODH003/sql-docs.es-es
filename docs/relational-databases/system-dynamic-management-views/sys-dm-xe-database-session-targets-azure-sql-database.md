---
description: sys.dm_xe_database_session_targets (Azure SQL Database)
title: sys.dm_xe_database_session_targets
titleSuffix: Azure SQL Database
ms.date: 06/10/2016
ms.service: sql-database
ms.prod_service: sql-database
ms.reviewer: ''
ms.topic: reference
ms.assetid: 7f353e2a-f8fc-4366-97e4-aa1c49eadaf4
author: WilliamDAssafMSFT
ms.author: wiassaf
monikerRange: = azuresqldb-current
ms.custom: seo-dt-2019
ms.openlocfilehash: e3a11ca92581e879c1fc0fbc51fc02b630251fad
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "100344297"
---
# <a name="sysdm_xe_database_session_targets-azure-sql-database"></a>sys.dm_xe_database_session_targets (Azure SQL Database)
[!INCLUDE[Azure SQL Database Azure SQL Managed Instance](../../includes/applies-to-version/asdb-asdbmi.md)]

  Devuelve información acerca de los destinos de la sesión.  
  
||  
|-|  
|**Se aplica a**: [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] V12 y a las versiones futuras.|  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|event_session_address|**varbinary(8**|La dirección de memoria de la sesión de eventos. Tiene una relación de varios a uno con sys.dm_xe_database_sessions. Address. No admite valores NULL.|  
|target_name|**nvarchar(60)**|El nombre del destino dentro de una sesión. No admite valores NULL.|  
|target_package_guid|**uniqueidentifier**|GUID del paquete que contiene el destino. No admite valores NULL.|  
|execution_count|**bigint**|El número de veces que se ha ejecutado el destino para la sesión. No admite valores NULL.|  
|execution_duration_ms|**bigint**|El tiempo total, en milisegundos, que se ha estado ejecutando el destino. No admite valores NULL.|  
|target_data|**nvarchar(max)**|Datos que mantiene el destino como, por ejemplo, información de agregación de eventos. Acepta valores NULL.|  
  
## <a name="permissions"></a>Permisos  
 Necesita el permiso VIEW DATABASE STATE.  
  
### <a name="relationship-cardinalities"></a>Cardinalidades de relación  
  
|De|En|Relación|  
|----------|--------|------------------|  
|Sys.dm_xe_database_session_targets sys.dm_xe_database_session_targets.event_session_address|sys.dm_xe_database_sessions. Address|Varios a uno|  
  
  
