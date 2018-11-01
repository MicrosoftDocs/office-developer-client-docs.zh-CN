---
title: 步骤 4：服务器返回 Recordset（RDS 教程）
TOCTitle: 'Step 4: Server Returns the Recordset (RDS Tutorial)'
ms:assetid: 4503151d-de8b-98d1-1aa8-11f1b6e6b55c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249209(v=office.15)
ms:contentKeyID: 48544542
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1c7aaaa556d11fc3c457c89a35edb1240628aa9e
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25868621"
---
# <a name="step-4-server-returns-the-recordset-rds-tutorial"></a>步骤 4：服务器返回记录集（RDS 教程）


**适用于**： Access 2013、 Office 2013

RDS 将检索到的 **Recordset** 对象转换为可以发回到客户端的形式（即，它*封送 ***Recordset**）。转换的确切形式及其发送方式取决于服务器是位于 Internet、Intranet 还是局域网上，或者服务器是否为动态链接库。但是，该细节并不是关键；RDS 将 **Recordset** 发回到客户端才是关键。

在客户端上， **Recordset** 对象返回，并被分配给本地变量。

```vb 
 
Sub RDSTutorial4() 
 Dim DS as New RDS.DataSpace 
 Dim RS as ADODB.Recordset 
 Dim DF as Object 
 Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
 Set RS = DF.Query("DSN=Pubs", "SELECT * FROM Authors") 
... 
```

