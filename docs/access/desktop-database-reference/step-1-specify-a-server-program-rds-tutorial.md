---
title: 步骤 1：指定服务器程序（RDS 教程）
TOCTitle: 'Step 1: Specify a Server Program (RDS Tutorial)'
ms:assetid: e6c2c624-d9bc-c899-60bc-e80a67ce8596
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250172(v=office.15)
ms:contentKeyID: 48548389
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: fe85853b013caf8610e7706f3d836551ce8801c7
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25871876"
---
# <a name="step-1-specify-a-server-program-rds-tutorial"></a><span data-ttu-id="3055f-102">步骤 1：指定服务器程序（RDS 教程）</span><span class="sxs-lookup"><span data-stu-id="3055f-102">Step 1: Specify a Server Program (RDS Tutorial)</span></span>


<span data-ttu-id="3055f-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="3055f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="3055f-p101">在大多数情况下，使用 [RDS.DataSpace](dataspace-object-rds.md) 对象的 [CreateObject](createobject-method-rds.md) 方法指定默认服务器程序 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 或自定义服务器程序（业务对象）。服务器程序在服务器上实例化，返回的是对服务器程序的引用（即*代理*）。</span><span class="sxs-lookup"><span data-stu-id="3055f-p101">In the most general case, use the [RDS.DataSpace](dataspace-object-rds.md) object [CreateObject](createobject-method-rds.md) method to specify the default server program, [RDSServer.DataFactory](datafactory-object-rdsserver.md), or your own custom server program (business object). A server program is instantiated on the server, and a reference to the server program, or *proxy*, is returned.</span></span>

<span data-ttu-id="3055f-106">本教程使用默认服务器程序：</span><span class="sxs-lookup"><span data-stu-id="3055f-106">This tutorial uses the default server program:</span></span>

```vb 
 
Sub RDSTutorial1() 
 Dim DS as New RDS.DataSpace 
 Dim DF as Object 
 Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
... 
```

