---
title: OLE DB Provider for Internet Publishing
TOCTitle: The OLE DB Provider for Internet Publishing
ms:assetid: 864e5ece-0f50-5d88-4c40-f951b2a2eded
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249583(v=office.15)
ms:contentKeyID: 48546082
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 617dca5ced5410e2023657ea1b0b748066f7843f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314054"
---
# <a name="ole-db-provider-for-internet-publishing"></a>用于 Internet 发布的 OLE DB 提供程序

**适用于**：Access 2013、Office 2013

ADO [Record](record-object-ado.md)和[Stream](stream-object-ado.md)对象可用于 Internet 发布 (internet 发布提供程序) 的 Microsoft OLE DB 提供程序, 以访问和处理资源, 如 Microsoft FrontPage 提供的 web 文件夹或文件。 使用 ADO，可以指定要成为 URL 的 **Record**、**Stream** 或 [Recordset](recordset-object-ado.md) 的源。 然后，可以上载、下载、移动、复制和删除资源，或者直接操作资源属性。

有关将 **Records** 和 **Streams** 与 Internet Publishing Provider 一起使用的示例代码，请参阅 [Internet Publishing 方案](internet-publishing-scenario.md)。

Internet Publishing Provider 随 Microsoft Windows 2000 一起安装。早期版本的 Internet Publishing Provider 还可通过 Microsoft Office 2000 和 Microsoft Internet Explorer 5.0 来使用。

可通过三种方法来将 ADO 连接到 Internet Publishing Provider：

- 在连接字符串中指定"URL="。例如：
    
  ```vb 
     
    objConn.Open "URL=https://servername" 
  ```

- 为连接字符串的 *Provider* 关键字指定 Msdaipp.dso。 例如：
    
  ```vb 
     
    objConn.Open "provider=MSDAIPP.DSO;data source=https://servername" 
  ```

- 为 [Connection](provider-property-ado.md) 对象的 [Provider](connection-object-ado.md) 属性指定 Msdaipp.dso。 例如：
    
  ```vb 
     
    objConn.Provider = "MSDAIPP.DSO" 
    objConn.Open "https://servername" 
  ```

> [!NOTE]
> 如果使用*provider*连接字符串关键字或**provider**属性将 msdaipp.dso 显式指定为提供程序的值, 则不能在连接字符串中使用 "URL ="。 否则，将会发生错误。 相反, 只需指定该 URL, 如本主题前面所示。

有关 Internet Publishing Provider 的更具体信息，请参阅 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)，也可以参阅随源应用程序提供的提供程序文档。源应用程序是指随其一起安装 OLE DB Provider for Internet Publishing 的应用程序，如 Windows 2000、Office 2000 或 Internet Explorer 5.0。

