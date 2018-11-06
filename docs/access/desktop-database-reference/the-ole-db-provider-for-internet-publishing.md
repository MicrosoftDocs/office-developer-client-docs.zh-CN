---
title: OLE DB Provider for Internet Publishing
TOCTitle: The OLE DB Provider for Internet Publishing
ms:assetid: 864e5ece-0f50-5d88-4c40-f951b2a2eded
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249583(v=office.15)
ms:contentKeyID: 48546082
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7315df5a20cf032fc256f03893531f58857d470a
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25998663"
---
# <a name="ole-db-provider-for-internet-publishing"></a>用于 Internet 发布的 OLE DB 提供程序

**适用于**： Access 2013、 Office 2013

ADO [Record](record-object-ado.md)和[Stream](stream-object-ado.md)对象可用于 Microsoft OLE DB Provider for Internet Publishing (Internet Publishing Provider) 来访问和处理资源，如 web 文件夹或由 Microsoft FrontPage 的文件。 使用 ADO，可以指定要成为 URL 的 **Record** 、 **Stream** 或 [Recordset](recordset-object-ado.md) 的源。 然后，可以上载、下载、移动、复制和删除资源，或者直接操作资源属性。

有关将 **Records** 和 **Streams** 与 Internet Publishing Provider 一起使用的示例代码，请参阅 [Internet Publishing 方案](internet-publishing-scenario.md)。

Internet Publishing Provider 随 Microsoft Windows 2000 一起安装。早期版本的 Internet Publishing Provider 还可通过 Microsoft Office 2000 和 Microsoft Internet Explorer 5.0 来使用。

可通过三种方法来将 ADO 连接到 Internet Publishing Provider：

- 在连接字符串中指定"URL="。例如：
    
  ```vb 
     
    objConn.Open "URL=https://servername" 
  ```

- 指定的连接字符串的*提供程序*关键字 Msdaipp.dso。 例如：
    
  ```vb 
     
    objConn.Open "provider=MSDAIPP.DSO;data source=https://servername" 
  ```

- 为 [Connection](provider-property-ado.md) 对象的 [Provider](connection-object-ado.md) 属性指定 Msdaipp.dso。例如：
    
  ```vb 
     
    objConn.Provider = "MSDAIPP.DSO" 
    objConn.Open "https://servername" 
  ```

> [!NOTE]
> 如果 Msdaipp.dso 显式指定的提供程序，使用*提供程序*的连接字符串关键字或**Provider**属性，值为您不能使用"URL ="连接字符串中。 否则，将会发生错误。 本主题中前面所示相反，只需指定的 URL。

有关 Internet Publishing Provider 的更具体信息，请参阅 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)，也可以参阅随源应用程序提供的提供程序文档。源应用程序是指随其一起安装 OLE DB Provider for Internet Publishing 的应用程序，如 Windows 2000、Office 2000 或 Internet Explorer 5.0。

