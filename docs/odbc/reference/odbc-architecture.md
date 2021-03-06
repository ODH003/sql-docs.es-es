---
description: Arquitectura ODBC
title: Arquitectura de ODBC | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- ODBC architecture [ODBC], components
- ODBC architecture [ODBC]
ms.assetid: 2604f492-587b-4a51-9876-59a7870b3ef2
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 3afeb698d7eff9d09161a091e3de0194fea93ec2
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "88429007"
---
# <a name="odbc-architecture"></a>Arquitectura ODBC
La arquitectura ODBC tiene cuatro componentes:  
  
-   **Aplicación** de Realiza el procesamiento y llama a las funciones ODBC para enviar instrucciones SQL y recuperar los resultados.  
  
-   **Administrador de controladores** Carga y descarga controladores en nombre de una aplicación. Procesa llamadas a funciones ODBC o las pasa a un controlador.  
  
-   **Controlador** de Procesa llamadas a funciones ODBC, envía solicitudes SQL a un origen de datos específico y devuelve los resultados a la aplicación. Si es necesario, el controlador modifica la solicitud de una aplicación para que la solicitud se ajuste a la sintaxis admitida por el DBMS asociado.  
  
-   **Origen de datos** Consta de los datos a los que el usuario desea acceder y su sistema operativo asociado, DBMS y plataforma de red (si existen) que se usan para tener acceso al DBMS.  
  
 Tenga en cuenta los puntos siguientes sobre la arquitectura ODBC. En primer lugar, pueden existir varios controladores y orígenes de datos, lo que permite a la aplicación acceder simultáneamente a los datos de más de un origen de datos. En segundo lugar, la API de ODBC se usa en dos lugares: entre la aplicación y el administrador de controladores, y entre el administrador de controladores y cada controlador. A veces, la interfaz entre el administrador de controladores y los controladores se conoce como la *interfaz del proveedor de servicios* o *SPI*. Para ODBC, la interfaz de programación de aplicaciones (API) y la interfaz del proveedor de servicios (SPI) son iguales. es decir, el administrador de controladores y cada controlador tienen la misma interfaz con las mismas funciones.  
  
 Esta sección contiene los temas siguientes.  
  
-   [Aplicaciones](../../odbc/reference/applications.md)  
  
-   [El Administrador de controladores](../../odbc/reference/the-driver-manager.md)  
  
-   [Controladores](../../odbc/reference/drivers.md)  
  
-   [Orígenes de datos](../../odbc/reference/data-sources.md)
