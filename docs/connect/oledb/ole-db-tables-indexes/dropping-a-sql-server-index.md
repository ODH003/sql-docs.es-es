---
title: Eliminación de un índice de SQL Server (controlador OLE DB) | Microsoft Docs
description: Obtenga información sobre la función IIndexDefinition::DropIndex en OLE DB Driver for SQL Server que permite que los consumidores quiten un índice de una tabla de SQL Server.
ms.custom: ''
ms.date: 06/14/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- removing indexes
- deleting indexes
- DropIndex function
- dropping indexes
- OLE DB Driver for SQL Server, indexes
- indexes [OLE DB]
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 91b9dd9e5ae5978eb8e0290e8d023a0ebca5e9c3
ms.sourcegitcommit: c95f3ef5734dec753de09e07752a5d15884125e2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88858864"
---
# <a name="dropping-a-sql-server-index"></a>Quitar un índice de SQL Server
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  OLE DB Driver for SQL Server expone la función **IIndexDefinition::DropIndex**. Esto permite que los consumidores quiten índices de las tablas de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
 OLE DB Driver for SQL Server expone algunas restricciones PRIMARY KEY y UNIQUE de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] como índices. El propietario de la tabla, el propietario de la base de datos y algunos miembros con roles administrativos pueden modificar las tablas de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], quitando una restricción. De forma predeterminada, solo el propietario de la tabla puede quitar un índice existente. Por tanto, que **DropIndex** se realice correctamente o no depende no solo de los derechos de acceso del usuario de la aplicación sino también del tipo de índice indicado.  
  
 Los consumidores especifican el nombre de tabla como una cadena de caracteres Unicode en el miembro *pwszName* de la unión *uName* en el parámetro *pTableID*. El miembro *eKind* de *pTableID* debe ser DBKIND_NAME.  
  
 Los consumidores especifican el nombre de índice como una cadena de caracteres Unicode en el miembro *pwszName* de la unión *uName* en el parámetro *pIndexID*. El miembro *eKind* de *pIndexID* debe ser DBKIND_NAME. El controlador OLE DB para SQL Server no admite la característica OLE DB de quitar todos los índices de una tabla cuando *pIndexID* es NULL. Si *pIndexID* es NULL, se devuelve E_INVALIDARG.  
  
## <a name="see-also"></a>Consulte también  
 [Tablas e índices](../../oledb/ole-db-tables-indexes/tables-and-indexes.md)   
 [ALTER TABLE &#40;Transact-SQL&#41;](../../../t-sql/statements/alter-table-transact-sql.md)   
 [DROP INDEX &#40;Transact-SQL&#41;](../../../t-sql/statements/drop-index-transact-sql.md)  
  
  
