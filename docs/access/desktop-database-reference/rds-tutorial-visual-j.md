---
title: RDS 教程 (Visual J++)
TOCTitle: RDS Tutorial (Visual J++)
ms:assetid: b5679bfe-e830-05df-8a1c-0744c96abe90
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249870(v=office.15)
ms:contentKeyID: 48547248
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6b01809cd17c9c1a5c1a73a5765bb8808692e4c2
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25877917"
---
# <a name="rds-tutorial-visual-j"></a><span data-ttu-id="c5c3a-102">RDS 教程 (Visual J++)</span><span class="sxs-lookup"><span data-stu-id="c5c3a-102">RDS Tutorial (Visual J++)</span></span>


<span data-ttu-id="c5c3a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c5c3a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c5c3a-p101">ADO/WFC 不完全遵循 RDS 对象模型，因为它不实现 [RDS.DataControl](datacontrol-object-rds.md) 对象。ADO/WFC 仅实现客户端类 [RDS.DataSpace](dataspace-object-rds.md)。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-p101">ADO/WFC does not completely follow the RDS object model in that it does not implement the [RDS.DataControl](datacontrol-object-rds.md) object. ADO/WFC only implements the client-side class, [RDS.DataSpace](dataspace-object-rds.md).</span></span>

<span data-ttu-id="c5c3a-p102">**DataSpace** 类实现 [CreateObject](createobject-method-rds.md) 方法，该方法返回 [ObjectProxy](https://msdn.microsoft.com/library/jj249624\(v=office.15\)) 对象。 **DataSpace** 类还实现 [InternetTimeout](internettimeout-property-rds.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-p102">The **DataSpace** class implements one method, [CreateObject](createobject-method-rds.md), which returns an [ObjectProxy](https://msdn.microsoft.com/library/jj249624\(v=office.15\)) object. The **DataSpace** class also implements the [InternetTimeout](internettimeout-property-rds.md) property.</span></span>

<span data-ttu-id="c5c3a-108">**ObjectProxy** 类实现 call 方法，该方法可以调用任何服务器端业务对象。</span><span class="sxs-lookup"><span data-stu-id="c5c3a-108">The **ObjectProxy** class implements one method, call, which can invoke any server-side business object.</span></span>

<span data-ttu-id="c5c3a-109">**本教程由此开始。**</span><span class="sxs-lookup"><span data-stu-id="c5c3a-109">**This is the beginning of the tutorial.**</span></span>

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

<span data-ttu-id="c5c3a-110">**本教程到此结束。**</span><span class="sxs-lookup"><span data-stu-id="c5c3a-110">**This is the end of the tutorial.**</span></span>

