---
title: 步骤 4：服务器返回 Recordset（RDS 教程）
TOCTitle: 'Step 4: Server Returns the Recordset (RDS Tutorial)'
ms:assetid: 4503151d-de8b-98d1-1aa8-11f1b6e6b55c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249209(v=office.15)
ms:contentKeyID: 48544542
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 41fd4a1aabda0887d265e3aa0ec9201b1abbbde7
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468641"
---
# <a name="step-4-server-returns-the-recordset-rds-tutorial"></a><span data-ttu-id="0ce90-102">步骤 4：服务器返回 Recordset（RDS 教程）</span><span class="sxs-lookup"><span data-stu-id="0ce90-102">Step 4: Server Returns the Recordset (RDS Tutorial)</span></span>


<span data-ttu-id="0ce90-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="0ce90-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="0ce90-p101">RDS 将检索到的 **Recordset** 对象转换为可以发回到客户端的形式（即，它\*封送 \***Recordset**）。转换的确切形式及其发送方式取决于服务器是位于 Internet、Intranet 还是局域网上，或者服务器是否为动态链接库。但是，该细节并不是关键；RDS 将 **Recordset** 发回到客户端才是关键。</span><span class="sxs-lookup"><span data-stu-id="0ce90-p101">RDS converts the retrieved **Recordset** object to a form that can be sent back to the client (that is, it *marshals* the **Recordset**). The exact form of the conversion and how it is sent depends on whether the server is on the Internet or an intranet, a local area network, or is a dynamic-link library. However, this detail is not critical; all that matters is that RDS sends the **Recordset** back to the client.</span></span>

<span data-ttu-id="0ce90-107">在客户端上， **Recordset** 对象返回，并被分配给本地变量。</span><span class="sxs-lookup"><span data-stu-id="0ce90-107">On the client side, a **Recordset** object is returned and assigned to a local variable.</span></span>

```vb 
 
Sub RDSTutorial4() 
 Dim DS as New RDS.DataSpace 
 Dim RS as ADODB.Recordset 
 Dim DF as Object 
 Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
 Set RS = DF.Query("DSN=Pubs", "SELECT * FROM Authors") 
... 
```

