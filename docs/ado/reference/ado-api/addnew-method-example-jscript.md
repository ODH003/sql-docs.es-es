---
description: Ejemplo del método AddNew (JScript)
title: Ejemplo del método AddNew (JScript) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: ado
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: reference
dev_langs:
- JScript
helpviewer_keywords:
- AddNew method [ADO], JScript example
ms.assetid: eabdd278-6576-4be7-9315-fb79cb8ef678
author: rothja
ms.author: jroth
ms.openlocfilehash: bbc055034c6a73248a9032b5412652c5fae6574d
ms.sourcegitcommit: 917df4ffd22e4a229af7dc481dcce3ebba0aa4d7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2021
ms.locfileid: "100035845"
---
# <a name="addnew-method-example-jscript"></a>Ejemplo del método AddNew (JScript)
En este ejemplo se usa el método [AddNew](./addnew-method-ado.md) para crear un nuevo registro con el nombre especificado. Corte y pegue el código siguiente en el Bloc de notas o en otro editor de texto y guárdelo como **AddNewJS. asp**.  
  
```  
<!-- BeginAddNewJS -->  
<%@LANGUAGE="JScript" %>  
<!-- Include file for JScript ADO Constants -->  
<%// use this meta tag instead of adojavas.inc%>  
<!--METADATA TYPE="typelib" uuid="00000205-0000-0010-8000-00AA006D2EA4" -->  
  
<html>  
  
<head>  
    <title>Add New Method Example (JScript)</title>  
<style>  
<!--  
body {  
   font-family: 'Verdana','Arial','Helvetica',sans-serif;  
   BACKGROUND-COLOR:white;  
   COLOR:black;  
    }  
-->  
</style>  
</head>  
  
<body>  
<h1>AddNew Method Example (JScript)</h1>  
  
<%  
    if (Request.Form("Addit") == "AddNew")  
    {  
        // connection and recordset variables  
        var Cnxn = Server.CreateObject("ADODB.Connection")  
        var strCnxn = "Provider='sqloledb';Data Source=" + Request.ServerVariables("SERVER_NAME") + ";" +  
            "Initial Catalog='Northwind';Integrated Security='SSPI';";  
        var rsEmployee = Server.CreateObject("ADODB.Recordset");  
        //record variables  
        var FName = String(Request.Form("FirstName"));  
        var LName = String(Request.Form("LastName"));  
  
        try  
        {  
            // open connection  
            Cnxn.Open(strCnxn)  
  
            // open Employee recordset using client-side cursor  
            rsEmployee.CursorLocation = adUseClient;  
            rsEmployee.Open("Employees", strCnxn, adOpenKeyset, adLockOptimistic, adCmdTable);  
  
            rsEmployee.AddNew();  
            rsEmployee("FirstName") = FName;  
            rsEmployee("LastName") = LName;  
            rsEmployee.Update;  
  
            // of course, you would normally do error handling here  
            Response.Write("New record added.")  
        }  
        catch (e)  
        {  
            Response.Write(e.message);  
        }  
        finally  
        {  
            // clean up  
            if (rsEmployee.State == adStateOpen)  
                rsEmployee.Close;  
            if (Cnxn.State == adStateOpen)  
                Cnxn.Close;  
            rsEmployee = null;  
            Cnxn = null;  
        }  
    }  
%>  
  
<form method="post" action="AddNewJS.asp" id=form1 name=form1>  
<table>  
<tr>  
    <td colspan="2">  
    <h4>Please enter the record to add:</h4>  
    </td>  
</tr>  
<tr>  
    <td>  
        First Name:  
    </td>  
    <td>  
        <input name="FirstName" maxLength=20>  
    </td>  
</tr>  
<tr>  
    <td>  
        Last Name:  
    </td>  
    <td>  
        <input name="LastName" size="30" maxLength=30>  
    </td>  
</tr>  
<tr>  
    <td align="right">  
        <input type="submit" value="Submit" name="Submit">  
    </td>  
    <TD align="left">  
        <INPUT type="reset" value="Reset" name="Reset">  
    </TD>  
</tr>  
</table>  
<INPUT type="hidden" value="AddNew" name="Addit">  
</form>  
</body>  
</HTML>  
<!-- EndAddNewJS -->  
```  
  
## <a name="see-also"></a>Consulte también  
 [AddNew (método) (ADO)](./addnew-method-ado.md)   
 [Objeto de conjunto de registros (ADO)](./recordset-object-ado.md)