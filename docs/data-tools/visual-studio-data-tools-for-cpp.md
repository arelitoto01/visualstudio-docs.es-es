---
title: Herramientas de datos de Visual Studio para C++ | Documentos de Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 3a3849d9-1bc7-47d1-805e-1755223ccba2
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
robots: noindex,nofollow
ms.technology: vs-data-tools
ms.openlocfilehash: c5952c4ab8e8adac0338d406800a15a8a0b12989
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2017
---
# <a name="visual-studio-data-tools-for-c"></a>Herramientas de datos de Visual Studio para C++
C++ nativo a menudo pueden proporcionar el rendimiento más rápido cuando se obtiene acceso a orígenes de datos. Sin embargo, datos de conjunto de herramientas para aplicaciones de C++ en Visual Studio no están tan complejo como para aplicaciones. NET. Por ejemplo, las ventanas de orígenes de datos no puede utilizarse para arrastrar y colocar los orígenes de datos en una superficie de diseño de C++. Si necesita una capa de objeto-relacional, tendrá que escribir el suyo propio, o utilizar un producto de terceros.  Lo mismo puede decirse de funcionalidad de enlace de datos, aunque las aplicaciones que utilizan la biblioteca Microsoft Foundation Class pueden utilizar algunas clases de base de datos, junto con los documentos y vistas, para almacenar los datos en memoria y mostrar al usuario. Para obtener más información, consulte [acceso a datos en Visual C++](https://msdn.microsoft.com/en-us/library/7wtdsdkh.aspx) .  
  
 Para conectarse a bases de datos SQL, aplicaciones nativas de C++ pueden utilizar los controladores ODBC y OLE DB y el proveedor de ADO que se incluyen con Windows. Estos pueden conectarse a cualquier base de datos que es compatible con las interfaces. El controlador ODBC es el estándar. OLE DB se proporciona por compatibilidad con versiones anteriores. Para obtener más información sobre estas tecnologías de datos, vea [Windows Data Access Components](https://msdn.microsoft.com/en-us/library/windows/desktop/aa968814\(v=vs.85\).aspx)  
  
 Para aprovechar la funcionalidad personalizada de SQL Server 2005 y versiones posteriores, use la [SQL Server Native Client](https://msdn.microsoft.com/en-us/sqlserver/aa937733). El cliente nativo también contiene el controlador ODBC de SQL Server y el proveedor OLE DB de SQL Server en una biblioteca de vínculos dinámicos (DLL). Compatibilidad con aplicaciones que utilizan API de código nativo (ODBC, OLE DB y ADO) para Microsoft SQL Server.  SQL Server Native Client se instala con SQL Server Data Tools. La Guía de programación está aquí: [programación cliente nativo de SQL Server](https://msdn.microsoft.com/en-us/library/ms130892.aspx).  
  
## <a name="to-connect-to-localdb-through-odbc-and-sql-native-client-from-a-c-application"></a>Para conectarse a localDB a través de ODBC y SQL Native Client desde una aplicación de C++  
  
1.  Instalar SQL Server Data Tools.  
  
2.  Si necesita una base de datos SQL de ejemplo para conectarse a, descargue la base de datos Northwind y descomprímalo a una nueva ubicación.  
  
3.  Usar SQL Server Management Studio para adjuntar el archivo Northwind.mdf descomprimido a localDB. Cuando se inicia SQL Server Management Studio, conéctese a (localdb) \MSSQLLocalDB.  
  
     ![Diálogo de conexión de SSMS](../data-tools/media/raddata-ssms-connect-dialog.png "raddata SSMS conectar el cuadro de diálogo")  
  
     A continuación, haga doble clic en el nodo de localdb en el panel izquierdo y elija **adjuntar**.  
  
     ![SSMS adjuntar base de datos](../data-tools/media/raddata-ssms-attach-database.png "SSMS adjuntar base de datos raddata")  
  
4.  Descargue el ejemplo de SDK de Windows de ODBC y descomprímalo en una nueva ubicación. Este ejemplo muestra los comandos básicos de ODBC que se utilizan para conectarse a una base de datos y emitir consultas y los comandos. Puede aprender más acerca de las funciones en el [Microsoft Open Database Connectivity (ODBC)](https://msdn.microsoft.com/en-us/library/windows/desktop/ms710252\(v=vs.85\).aspx). Cuando se carga primero la solución (se encuentra en la carpeta de C++), Visual Studio le ofrece actualizar la solución a la versión actual de Visual Studio. Haga clic en **Sí**.  
  
5.  Para usar al cliente nativo, necesita su archivo de encabezado y archivos de lib. Estos archivos contienen las funciones y las definiciones específicas de SQL Server, más allá de las funciones ODBC definidas en sql.h. En **proyecto** > **propiedades** > **directorios de VC ++**, agregue el siguiente directorio de inclusión:  
  
 **\<unidad del sistema >: \Program Server\110\SDK\Include SQL** y este directorio de la biblioteca:  
  
 **c:\Program Files\Microsoft SQL Server\110\SDK\Lib**  
  
6.  Agregue estas líneas en odbcsql.cpp. El #define evita irrelevantes definiciones de OLE DB desde que se está compilando.  
  
    ```C++  
    #define _SQLNCLI_ODBC_  
    #include <sqlncli.h>  
    ```  
  
     Tenga en cuenta que el ejemplo no utiliza realmente ninguna de las funciones de cliente nativo, por lo que no son necesarios para poder compilar y ejecutar los pasos anteriores. Pero el proyecto ahora está configurado para que usar esta funcionalidad. Para obtener más información, consulte [programación cliente nativo de SQL Server](https://msdn.microsoft.com/en-us/library/ms130892\(v=sql.130\).aspx).  
  
7.  Especificar qué controlador que se utilizará en el subsistema ODBC. El ejemplo pasa el atributo de cadena de conexión de controlador en como un argumento de línea de comandos. En **proyecto** > **propiedades** > **depuración**, agregue este argumento de comando:  
  
    ```C++  
    DRIVER="SQL Server Native Client 11.0"  
    ```  
  
8.  Presione F5 para compilar y ejecutar la aplicación. Debería ver un cuadro de diálogo desde el controlador que le pide que escriba una base de datos. Escriba `(localdb)\MSSQLLocalDB`y compruebe **Usar conexión de confianza**. Press **OK**. Debería ver una consola con mensajes que indican una conexión correcta. También verá un símbolo del sistema donde se pueden escribir en una instrucción SQL. La siguiente pantalla muestra una consulta de ejemplo y los resultados:  
  
     ![Resultado de la consulta de ejemplo de ODBC](../data-tools/media/raddata-odbc-sample-query-output.png "raddata resultado de la consulta de ejemplo de ODBC")  
  
## <a name="see-also"></a>Vea también  
 [Obtener acceso a los datos en Visual Studio](../data-tools/accessing-data-in-visual-studio.md)