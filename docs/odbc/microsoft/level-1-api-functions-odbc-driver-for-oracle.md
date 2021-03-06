---
description: Funciones de API de nivel 1 (controlador ODBC para Oracle)
title: Funciones de la API de nivel 1 (controlador ODBC para Oracle) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- functions [ODBC], ODBC driver for Oracle
- ODBC level 1 API functions [ODBC]
- ODBC driver for Oracle [ODBC], functions
- level 1 API functions [ODBC]
- API functions [ODBC]
ms.assetid: 98cced6f-41b8-43c1-a3cd-f4ea1615c0af
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 0c82ab0f481fbc60d0308895640371e84886e77e
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "88483548"
---
# <a name="level-1-api-functions-odbc-driver-for-oracle"></a>Funciones de API de nivel 1 (controlador ODBC para Oracle)
> [!IMPORTANT]  
>  Esta característica se quitará en una versión futura de Windows. Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan. En su lugar, utilice el controlador ODBC proporcionado por Oracle.  
  
 Las funciones en este nivel proporcionan el cumplimiento de la interfaz básica más funcionalidad adicional, como la compatibilidad con transacciones.  
  
|Función de API|Notas|  
|------------------|-----------|  
|**SQLColumns**|Crea un conjunto de resultados para una tabla, que es la lista de columnas de la tabla o tablas especificadas. Al solicitar columnas para un sinónimo público, debe haber establecido el atributo de conexión SYNONYMCOLUMNS y especificado una cadena vacía como el argumento *szTableOwner* . Cuando se devuelven columnas para sinónimos públicos, el controlador establece la columna de nombre de tabla en una cadena vacía. El conjunto de resultados contiene una columna adicional, posición ORDINAL, al final de cada fila. Este valor es la posición ordinal de la columna en la tabla.|  
|**SQLDriverConnect**|Se conecta a un origen de datos existente. Para obtener más información, consulte formato de la [cadena de conexión y atributos](../../odbc/microsoft/connection-string-format-and-attributes.md).|  
|**SQLGetConnectOption**|Devuelve el valor actual de una opción de conexión. Esta función se admite parcialmente. El controlador admite todos los valores para el argumento *fOption* , pero no admite algunos valores *vParam* para el argumento *fOption* [SQL_TXN_ISOLATION](../../odbc/microsoft/connect-options.md). Para obtener más información, consulte [Opciones de conexión](../../odbc/microsoft/connect-options.md).|  
|**SQLGetData**|Recupera el valor de un campo único en el registro actual del conjunto de resultados especificado.|  
|**SQLGetFunctions**|Devuelve TRUE para todas las funciones admitidas. Implementado por el administrador de controladores.|  
|**SQLGetInfo**|Devuelve información, como SQLHDBC, SQLUSMALLINT, SQLPOINTER, SQLSMALLINT y SQLSMALLINT \* , sobre el controlador ODBC para Oracle y el origen de datos asociado a un identificador de conexión, *hdbc*.|  
|**SQLGetStmtOption**|Devuelve el valor actual de una opción de instrucción. Para obtener más información, vea opciones de la [instrucción](../../odbc/microsoft/statement-options.md).|  
|**SQLGetTypeInfo**|Devuelve información sobre los tipos de datos admitidos por un origen de datos. El controlador devuelve la información en un conjunto de resultados de SQL.|  
|**SQLParamData**|Se usa junto con **SQLPutData** para especificar los datos de parámetro en el tiempo de ejecución de la instrucción.|  
|**SQLPutData**|Permite a una aplicación enviar datos de un parámetro o una columna al controlador en el momento de la ejecución de la instrucción.|  
|**SQLSetConnectOption**|Proporciona acceso a las opciones que controlan los aspectos de la conexión. Esta función es parcialmente compatible: el controlador admite todos los valores para el argumento *fOption* , pero no admite algunos valores *vParam* para el argumento *fOption* [SQL_TXN_ISOLATION](../../odbc/microsoft/connect-options.md). Para obtener más información, consulte [Opciones de conexión](../../odbc/microsoft/connect-options.md).|  
|**SQLSetStmtOption**|Establece las opciones relacionadas con un identificador de instrucción, *hstmt*. Para obtener más información, vea opciones de la [instrucción](../../odbc/microsoft/statement-options.md).|  
|**SQLSpecialColumns**|Recupera el conjunto óptimo de columnas que identifica de forma única una fila de la tabla.|  
|**SQLStatistics**|Recupera una lista de estadísticas sobre una sola tabla y los índices o los nombres de etiqueta asociados a la tabla. El controlador devuelve la información como un conjunto de resultados.|  
|**SQLTables**|Devuelve la lista de nombres de tabla especificados por el parámetro en la instrucción **SQLTables** . Si no se especifica ningún parámetro, devuelve los nombres de tabla almacenados en el origen de datos actual. El controlador devuelve la información como un conjunto de resultados.<br /><br /> Las llamadas de tipo de enumeración no recibirán una entrada de conjunto de resultados para vistas remotas o vistas con parámetros locales. Sin embargo, una llamada a **SQLTables** con un especificador de nombre de tabla único encontrará una coincidencia para dicha vista, si está presente, con ese nombre; Esto permite que la API Compruebe los conflictos de nombres antes de la creación de una nueva tabla.<br /><br /> Los sinónimos públicos se devuelven con un valor TABLE_OWNER de "".<br /><br /> Las vistas que pertenecen a SYS o SYSTEM se identifican como vista del sistema.|
