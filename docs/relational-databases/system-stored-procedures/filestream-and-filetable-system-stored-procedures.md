---
description: Procedimientos almacenados del sistema de Filestream y FileTable (Transact-SQL)
title: Procedimientos almacenados del sistema FileStream y FileTable (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: reference
dev_langs:
- TSQL
helpviewer_keywords:
- FileTables [SQL Server], catalog views
ms.assetid: 2c83a4a7-720b-4435-a3b5-788c29f56949
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7ee0eced0370c3ea16091827555e90f4951d6cf7
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "100346700"
---
# <a name="filestream-and-filetable-system-stored-procedures-transact-sql"></a>Procedimientos almacenados del sistema FileStream y FileTable (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  En esta sección se describen los procedimientos almacenados del sistema para la característica FileTable y FileStream.  

## <a name="filestream-and-filetable-system-stored-procedures"></a>Procedimientos almacenados del sistema FileStream y Filetable
  [sp_filestream_force_garbage_collection (Transact-SQL)](filestream-and-filetable-sp-filestream-force-garbage-collection.md)

   Fuerza la ejecución del recolector de elementos no utilizados de FILESTREAM eliminando los archivos FILESTREAM innecesarios.

  [sp_kill_filestream_non_transacted_handles (Transact-SQL)](filestream-and-filetable-sp-kill-filestream-non-transacted-handles.md)

  Cierra los identificadores de archivos no transaccionales para datos de FileTable.


## <a name="see-also"></a>Consulte también
[Secuencia de archivos](../../relational-databases/blob/filestream-sql-server.md)
<br>[Filetables](../../relational-databases/blob/filetables-sql-server.md)
<br>[Vistas de administración dinámica de secuencia de archivo y FileTable (Transact-SQL)](../system-dynamic-management-views/filestream-and-filetable-dynamic-management-views-transact-sql.md)
<br>[Vistas de catálogo de secuencia de archivo y FileTable (Transact-SQL)](../system-catalog-views/filestream-and-filetable-catalog-views-transact-sql.md)
  
  
