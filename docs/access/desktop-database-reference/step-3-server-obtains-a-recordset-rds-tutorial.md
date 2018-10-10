---
title: 步骤 3：服务器获取 Recordset（RDS 教程）
TOCTitle: 'Step 3: Server Obtains a Recordset (RDS Tutorial)'
ms:assetid: fadb6a9b-ed44-264f-22fd-26b121f98040
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250282(v=office.15)
ms:contentKeyID: 48548856
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a8509c7869613a92acf0d61e4fb1ebc5be411c0a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467667"
---
# <a name="step-3-server-obtains-a-recordset-rds-tutorial"></a><span data-ttu-id="16ca8-102">步骤 3：服务器获取 Recordset（RDS 教程）</span><span class="sxs-lookup"><span data-stu-id="16ca8-102">Step 3: Server Obtains a Recordset (RDS Tutorial)</span></span>


<span data-ttu-id="16ca8-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="16ca8-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="16ca8-p101">服务器程序使用连接字符串和命令文本在数据源中查询所需的行。尽管也可以使用其他 Microsoft 数据访问接口（如 OLE DB），但通常使用 ADO 来检索该 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="16ca8-p101">The server program uses the connect string and command text to query the data source for the desired rows. ADO is typically used to retrieve this **Recordset**, although other Microsoft data access interfaces, such as OLE DB, could be used.</span></span>

<span data-ttu-id="16ca8-106">自定义服务器程序的形式可以类似如下：</span><span class="sxs-lookup"><span data-stu-id="16ca8-106">A custom server program might look like this:</span></span>

```vb 
 
Public Function ServerProgram(cn as String, qry as String) as Object 
Dim rs as New ADODB.Recordset 
 rs.CursorLocation = adUseClient 
 rs.Open qry, cn 
 rs.ActiveConnection = Nothing 
 Set ServerProgram = rs 
End Function 
```

