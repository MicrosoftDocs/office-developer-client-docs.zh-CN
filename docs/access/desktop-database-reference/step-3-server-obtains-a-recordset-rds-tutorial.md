---
title: 步骤 3：服务器获取 Recordset（RDS 教程）
TOCTitle: 'Step 3: Server Obtains a Recordset (RDS Tutorial)'
ms:assetid: fadb6a9b-ed44-264f-22fd-26b121f98040
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250282(v=office.15)
ms:contentKeyID: 48548856
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ddd306e95ccf9ed68848b516c6d23d45286edf63
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25943834"
---
# <a name="step-3-server-obtains-a-recordset-rds-tutorial"></a><span data-ttu-id="60c39-102">步骤 3： 服务器获取 Recordset （RDS 教程）</span><span class="sxs-lookup"><span data-stu-id="60c39-102">Step 3: Server obtains a Recordset (RDS Tutorial)</span></span>

<span data-ttu-id="60c39-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="60c39-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="60c39-p101">服务器程序使用连接字符串和命令文本在数据源中查询所需的行。尽管也可以使用其他 Microsoft 数据访问接口（如 OLE DB），但通常使用 ADO 来检索该 **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="60c39-p101">The server program uses the connect string and command text to query the data source for the desired rows. ADO is typically used to retrieve this **Recordset**, although other Microsoft data access interfaces, such as OLE DB, could be used.</span></span>

<span data-ttu-id="60c39-106">自定义服务器程序的形式可以类似如下：</span><span class="sxs-lookup"><span data-stu-id="60c39-106">A custom server program might look like this:</span></span>

```vb 
 
Public Function ServerProgram(cn as String, qry as String) as Object 
Dim rs as New ADODB.Recordset 
 rs.CursorLocation = adUseClient 
 rs.Open qry, cn 
 rs.ActiveConnection = Nothing 
 Set ServerProgram = rs 
End Function 
```

