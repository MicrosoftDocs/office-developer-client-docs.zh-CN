---
title: RDS 教程 (Visual J++)
TOCTitle: RDS Tutorial (Visual J++)
ms:assetid: b5679bfe-e830-05df-8a1c-0744c96abe90
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249870(v=office.15)
ms:contentKeyID: 48547248
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 15eadc36079faa529585e539b67eb0da246cf4bc
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467113"
---
# <a name="rds-tutorial-visual-j"></a><span data-ttu-id="75d36-102">RDS 教程 (Visual J++)</span><span class="sxs-lookup"><span data-stu-id="75d36-102">RDS Tutorial (Visual J++)</span></span>


<span data-ttu-id="75d36-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="75d36-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="75d36-p101">ADO/WFC 不完全遵循 RDS 对象模型，因为它不实现 [RDS.DataControl](datacontrol-object-rds.md) 对象。ADO/WFC 仅实现客户端类 [RDS.DataSpace](dataspace-object-rds.md)。</span><span class="sxs-lookup"><span data-stu-id="75d36-p101">ADO/WFC does not completely follow the RDS object model in that it does not implement the [RDS.DataControl](datacontrol-object-rds.md) object. ADO/WFC only implements the client-side class, [RDS.DataSpace](dataspace-object-rds.md).</span></span>

<span data-ttu-id="75d36-p102">**DataSpace** 类实现 [CreateObject](createobject-method-rds.md) 方法，该方法返回 [ObjectProxy](https://msdn.microsoft.com/library/jj249624\(v=office.15\)) 对象。 **DataSpace** 类还实现 [InternetTimeout](internettimeout-property-rds.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="75d36-p102">The **DataSpace** class implements one method, [CreateObject](createobject-method-rds.md), which returns an [ObjectProxy](https://msdn.microsoft.com/library/jj249624\(v=office.15\)) object. The **DataSpace** class also implements the [InternetTimeout](internettimeout-property-rds.md) property.</span></span>

<span data-ttu-id="75d36-108">**ObjectProxy** 类实现 call 方法，该方法可以调用任何服务器端业务对象。</span><span class="sxs-lookup"><span data-stu-id="75d36-108">The **ObjectProxy** class implements one method, call, which can invoke any server-side business object.</span></span>

<span data-ttu-id="75d36-109">**本教程由此开始。**</span><span class="sxs-lookup"><span data-stu-id="75d36-109">**This is the beginning of the tutorial.**</span></span>

```java 
 
import com.ms.wfc.data.*; 
public class RDSTutorial 
{ 
 public void tutorial() 
 { 
// Step 1: Specify a server program. 
 ObjectProxy obj = 
 DataSpace.createObject( 
 "RDSServer.DataFactory", 
 "https://YourServer"); 
 
// Step 2: Server returns a Recordset. 
 Recordset rs = (Recordset) obj.call( 
 "Query", 
 new Object[] {"DSN=Pubs;", "SELECT * FROM Authors"}); 
 
// Step 3: Changes are sent to the server. 
 ... // Edit Recordset. 
 obj.call( 
 "SubmitChanges", 
 new Object[] {"DSN=Pubs;", rs}); 
 return; 
 } 
} 
```

<span data-ttu-id="75d36-110">**本教程到此结束。**</span><span class="sxs-lookup"><span data-stu-id="75d36-110">**This is the end of the tutorial.**</span></span>

