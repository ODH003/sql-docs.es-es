---
description: Trabajar con el script de la consola de ejemplo FilesExecuting la consola SSMA (AccessToSQL)
title: Trabajar con scripts de la consola de ejemplo FilesExecuting la consola de SSMA | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: ad75b648-d119-4119-98f0-d18f058be68d
author: nahk-ivanov
ms.author: alexiva
ms.openlocfilehash: 519706bd731c9590676cfef3c0363f49ea903e8a
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "100066051"
---
# <a name="working-with-the-sample-console-script-filesexecuting-the-ssma-console-accesstosql"></a>Trabajar con el script de la consola de ejemplo FilesExecuting la consola SSMA (AccessToSQL)
Se han proporcionado algunos archivos de ejemplo junto con el producto para la referencia de usuario y el uso. En esta sección se describe la manera de personalizar fácilmente estos scripts para ajustarse a las necesidades del usuario final.  
  
## <a name="sample-console-script-files"></a>Archivos de script de la consola de ejemplo  
Se han proporcionado los siguientes archivos de script de la consola de ejemplo que abarcan distintos escenarios para la referencia del usuario:  
  
-   ServersConnectionFileSample.xml  
  
-   VariableValueFileSample.xml  
  
-   AssessmentReportGenerationSample.xml  
  
-   ConversionAndDataMigrationSample.xml  
  
-   **ServersConnectionFileSample.xml:**  
  
    -   Este ejemplo proporciona los diferentes modos de conexión disponibles para la base de datos de origen y de destino, y el usuario puede seleccionar cualquier modo según el requisito. Este ejemplo contiene las definiciones de servidor.  
  
    -   El usuario puede conectarse a la base de datos requerida simplemente cambiando los valores a las definiciones de servidor de origen y de destino necesarias. En el ejemplo se proporcionan todos los valores que se han proporcionado como valores de variable que están disponibles en el **VariableValueFileSample.xml**. El resto de parámetros de conexión se pueden quitar del archivo de conexión del servidor de trabajo del usuario.  
  
    -   Para obtener más información sobre cómo conectarse a los servidores de origen y de destino, vea [crear archivos de conexión de servidor &#40;AccessToSQL&#41;](../../ssma/access/creating-the-server-connection-files-accesstosql.md) .  
  
-   **VariableValueFileSample.xml:** Todas las variables que se han usado en los archivos de script de la consola de ejemplo y `ServersConnectionFileSample.xml` se han intercalado en este archivo. Para ejecutar los scripts de la consola de ejemplo, el usuario tiene que reemplazar simplemente los valores de la variable de ejemplo por los definidos por el usuario y pasar este archivo como un argumento de línea de comandos adicional junto con el archivo de script.  
  
    Para obtener más información sobre el archivo de valores de variable, vea [crear archivos de valor variable &#40;AccessToSQL&#41;](../../ssma/access/creating-variable-value-files-accesstosql.md).  
  
-   **AssessmentReportGenerationSample.xml:** Este ejemplo permite al usuario generar un informe de evaluación de XML que el usuario puede usar para el análisis antes de empezar a convertir y migrar los datos.  
  
    En el `generate-assessment-report` comando, el usuario tiene que cambiar el valor de la variable (consulte **VariableValueFileSample.xml**) en el `object-name` atributo al nombre de la base de datos que está usando el usuario. Dependiendo del tipo de objeto especificado, el `object-type` valor también tendrá que cambiarse.  
  
    Si el usuario tiene que evaluar varios objetos o bases de datos, puede especificar varios `metabase-object` nodos, tal como se muestra en el `generate-assessment-report` ejemplo 4 del comando del archivo de script de la consola de ejemplo.  
  
    Para obtener más información sobre la generación de informes, consulte [generación de informes &#40;AccessToSQL&#41;](../../ssma/access/generating-reports-accesstosql.md).  
  
    > [!NOTE]  
    > -   Asegúrese de que el argumento de la línea de comandos del archivo de valores de variable se pasa a la aplicación de consola y VariableValueFileSample.xml se actualiza con los valores especificados por el usuario.  
    > -   Asegúrese de que el argumento de la línea de comandos del archivo de conexión de servidor se pasa a la aplicación de consola y el ServersConnectionFileSample.xml se actualiza con los valores de parámetro de servidor correctos.  
  
-   **ConversionAndDataMigrationSample.xml:** Este ejemplo permite al usuario realizar una migración de un extremo a otro de la conversión a la migración de datos. A continuación se muestra la lista de valores de atributo obligatorios que tendrán que cambiar:  
  
    |Nombre de comando|Descripción|Atributo|  
    |----------------|---------------|-------------|  
    |`map-schema`|Asignación de esquema de la base de datos de origen al esquema de destino.|`source-schema:` Especifica la base de datos de origen que requiere que se convierta.<br /><br />`sql-server-schema`: Especifica la base de datos de destino que se va a migrar a|  
    |`convert-schema`|Realiza la conversión del esquema del origen al esquema de destino.<br /><br />Si el usuario tiene que evaluar varios objetos o bases de datos, puede especificar varios `metabase-object` nodos, tal como se muestra en el `convert-schema` ejemplo 4 del comando del archivo de script de la consola de ejemplo.|`object-name`: Especifique el nombre de objeto o base de datos de origen que requiere la conversión. Asegúrese de que `object-type` se cambia el correspondiente según el tipo de objeto que se especifica en el `object-name`|  
    |`synchronize-target`|Sincroniza los objetos de destino con la base de datos de destino.<br /><br />Si el usuario tiene que evaluar varios objetos o bases de datos, puede especificar varios `metabase-object` nodos, tal como se muestra en el `synchronize-target` ejemplo 3 del comando del archivo de script de la consola de ejemplo.|`object-name:` Especifique el nombre de objeto o base de datos de SQL Server que requiere que se cree. Asegúrese de que `object-type` se cambia el correspondiente según el tipo de objeto que se especifica en el `object-name`|  
    |`migrate-data`|Migra los datos de origen al destino.<br /><br />Si el usuario tiene que evaluar varios objetos o bases de datos, puede especificar varios `metabase-object` nodos, tal como se muestra en el `migrate-data` ejemplo 2 del comando del archivo de script de la consola de ejemplo.|`object-name:` Especifica el nombre de la base de datos o de las tablas de origen que requiere la migración. Asegúrese de que `object-type` se cambia el correspondiente según el tipo de objeto que se especifica en el `object-name`|  
  
## <a name="see-also"></a>Consulte también  
[Crear archivos de valores de variable &#40;AccessToSQL&#41;](../../ssma/access/creating-variable-value-files-accesstosql.md)  
[Crear los archivos de conexión del servidor &#40;AccessToSQL&#41;](../../ssma/access/creating-the-server-connection-files-accesstosql.md)  
[Generar informes &#40;AccessToSQL&#41;](../../ssma/access/generating-reports-accesstosql.md)  
  
