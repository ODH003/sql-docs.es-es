---
description: SQLAsyncNotificationCallback (función)
title: Función SQLAsyncNotificationCallback | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: c56aedc9-f7f7-4641-b605-f0f98ed4400c
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: b9d03e8a3fa7e62c19dd09a210dca3a56348c692
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "88476234"
---
# <a name="sqlasyncnotificationcallback-function"></a>SQLAsyncNotificationCallback (función)
**Conformidad**  
 Versión introducida: ODBC 3,8  
  
 Compatibilidad con estándares: ninguno  
  
 **Resumen**  
 **SQLAsyncNotificationCallback** permite que un controlador vuelva a llamar al administrador de controladores cuando haya algún progreso de la operación asincrónica actual después de que el controlador devuelva SQL_STILL_EXECUTING. El controlador solo puede llamar a **SQLAsyncNotificationCallback** .  
  
 Los controladores no llaman a **SQLAsyncNotificationCallback** con el nombre de función **SQLAsyncNotificationCallback**. En su lugar, el administrador de controladores pasa un puntero de función a un controlador como el valor del atributo SQL_ATTR_ASYNC_DBC_NOTIFICATION_CALLBACK o SQL_ATTR_ASYNC_STMT_NOTIFICATION_CALLBACK del identificador de la conexión o el identificador de instrucción correspondiente, respectivamente. A los distintos identificadores se les pueden asignar distintos valores de puntero de función. El tipo del puntero de función se define como SQL_ASYNC_NOTIFICATION_CALLBACK.  
  
 **SQLAsyncNotificationCallback** es seguro para subprocesos. Un controlador puede optar por usar varios subprocesos que llaman a **SQLAsyncNotificationCallback** en diferentes identificadores simultáneamente.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef SQLRETURN (SQL_API *SQL_ASYNC_NOTIFICATION_CALLBACK)(  
   SQLPOINTER pContex,   
   BOOL fLast);  
```  
  
## <a name="arguments"></a>Argumentos  
 *pContex*  
 Puntero a una estructura de datos definida por el administrador de controladores. El valor se pasa al controlador mediante SQLSetConnectAttr (SQL_ATTR_ASYNC_DBC_NOTIFICATION_CONTEXT) o SQLSetStmtAttr (SQL_ATTR_ASYNC_STMT_NOTIFICATION_CONTEXT).  El controlador no tiene acceso al valor.  
  
 *fLast*  
 Lo utiliza un controlador para indicar que esta invocación de función de devolución de llamada es la última de la operación asincrónica actual. El controlador devolverá un código de retorno distinto de SQL_STILL_EXECUTING cuando el administrador de controladores vuelva a llamar a la función. El administrador de controladores puede usar esta información, por ejemplo, para informar a la aplicación de antemano de que se completará la operación asincrónica.  
  
 Si el *identificador* no es un identificador válido del tipo especificado por *HandleType*, **SQLCancelHandle** devuelve SQL_INVALID_HANDLE.  
  
## <a name="returns"></a>Devoluciones  
 SQL_SUCCESS o SQL_ERROR.  
  
## <a name="diagnostics"></a>Diagnóstico  
 **SQLAsyncNotificationCallback** puede devolver SQL_ERROR para las dos situaciones siguientes (esto indica un problema de implementación en el administrador de controladores o controladores).  
  
|Error|Descripción|  
|-----------|-----------------|  
|La conexión o la instrucción no solicitaron la notificación.||  
|*Identificador* no válido|El controlador pasó en un identificador no válido, que no superó las pruebas de validación internas del administrador de controladores.|  
  
## <a name="see-also"></a>Vea también  
 [Ejecución asincrónica (método de sondeo)](../../../odbc/reference/develop-app/asynchronous-execution-polling-method.md)
