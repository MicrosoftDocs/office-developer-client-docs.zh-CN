---
title: 步骤 1：指定服务器程序（RDS 教程）
TOCTitle: 'Step 1: Specify a Server Program (RDS Tutorial)'
ms:assetid: e6c2c624-d9bc-c899-60bc-e80a67ce8596
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250172(v=office.15)
ms:contentKeyID: 48548389
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 89aa87aa63a3d8bfdeb291f78d6525f51c4262b5
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465496"
---
# <a name="step-1-specify-a-server-program-rds-tutorial"></a>步骤 1：指定服务器程序（RDS 教程）


**适用于**： Access 2013 |Office 2013

在大多数情况下，使用 [RDS.DataSpace](dataspace-object-rds.md) 对象的 [CreateObject](createobject-method-rds.md) 方法指定默认服务器程序 [RDSServer.DataFactory](datafactory-object-rdsserver.md) 或自定义服务器程序（业务对象）。服务器程序在服务器上实例化，返回的是对服务器程序的引用（即*代理*）。

本教程使用默认服务器程序：

```vb 
 
Sub RDSTutorial1() 
 Dim DS as New RDS.DataSpace 
 Dim DF as Object 
 Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
... 
```

