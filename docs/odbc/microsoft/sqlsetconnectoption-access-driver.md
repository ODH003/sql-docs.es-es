---
description: SQLSetConnectOption (controlador de Access)
title: SQLSetConnectOption (controlador de Access) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- Access driver [ODBC], SQLSetConnectOption
- SQLSetConnectOption function [ODBC], Access Driver
ms.assetid: 58399bc4-d0b1-4eaa-a474-c92b2d5855ea
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: a007693a59c190a29bf9895446e916d5c232bb9f
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "88483318"
---
# <a name="sqlsetconnectoption-access-driver"></a>SQLSetConnectOption (controlador de Access)
> [!NOTE]  
>  En este tema se proporciona información específica del controlador de acceso. Para obtener información general sobre esta función, vea el tema correspondiente en referencia de la [API de ODBC](../../odbc/reference/syntax/odbc-api-reference.md).  
  
|fOption|Comentario|  
|-------------|-------------|  
|SQL_ACCESS_MODE|El SQL_ACCESS_MODE fOption se puede establecer en SQL_MODE_READ_ONLY o SQL_MODE_READ_WRITE. Sin embargo, el controlador no impide las actualizaciones si SQL_ACCESS_MODE está establecido en SQL_MODE_READ_ONLY.|  
|SQL_AUTOCOMMIT|Cuando se usa el controlador de Microsoft Access, la opción SQL_AUTOCOMMIT se puede establecer en SQL_AUTOCOMMIT_ON o SQL_AUTOCOMMIT_OFF, porque el controlador de Microsoft Access admite transacciones [1].|  
|SQL_CURRENT_QUALIFIER|Compatible.|  
|SQL_LOGIN_TIMEOUT|No compatible.|  
|SQL_OPT_TRACE|Compatible.|  
|SQL_OPT_TRACEFILE|Compatible.|  
|SQL_PACKET_SIZE|No compatible.|  
|SQL_QUIET_MODE|No compatible.|  
|SQL_TRANSLATE_DLL|No compatible.|  
|SQL_TRANSLATION_OPTION|No compatible.|  
|SQL_TXN_ISOLATION|SQL_TXN_ISOLATION siempre se SQL_TXN_READ_COMMITTED.|  
  
 [1] las transacciones atómicas no son compatibles con el controlador de Microsoft Access. Al confirmar una transacción mediante el controlador de Microsoft Access, existe un retraso finito entre el momento en que se confirma la transacción y el momento en que se escriben los valores en el disco. Este retraso viene determinado por un retraso inherente al motor de Microsoft Jet. El tiempo de espera de la página no será menor que un valor mínimo, incluso si la opción PageTimeout se establece por debajo de ese valor. Como resultado, no hay ninguna garantía de que los datos confirmados sean estables, ya que los cambios pueden realizarse durante el retraso.
