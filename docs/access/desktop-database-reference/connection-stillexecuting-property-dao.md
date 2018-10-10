---
title: Connection.StillExecuting Property (DAO)
TOCTitle: StillExecuting Property
ms:assetid: 0121f98a-cc23-5b5e-9a75-28307404a9a3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844743(v=office.15)
ms:contentKeyID: 48542927
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 7dfb5dc1abee81e24de7e6cfcd23bd298e684c10
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466256"
---
# <a name="connectionstillexecuting-property-dao"></a>Connection.StillExecuting Property (DAO)

**适用于**： Access 2013 |Office 2013

## <a name="syntax"></a>语法

*表达式*。StillExecuting

*表达式*代表**Connection**对象的变量。

## <a name="remarks"></a>注解

使用 **StillExecuting** 属性可以确定最近调用的异步 **Execute** 或 **OpenConnection** 方法（即用 **dbRunAsync** 选项执行的方法）是否已完成。在 **StillExecuting** 属性为 **True** 的情况下，不能访问任何返回的对象。

一旦 **StillExecuting** 属性返回 **False**，在返回相关 **Connection** 对象的 **OpenConnection** 调用之后，即可引用该对象。只要 **StillExecuting** 仍为 **True**，就不能引用该对象，而只能读取 **StillExecuting** 属性。

使用 **[Cancel](connection-cancel-method-dao.md)** 方法可以终止执行正在进行的任务。

## <a name="example"></a>示例

以下示例使用 **StillExecuting** 属性和 **Cancel** 方法异步打开 **Connection** 对象。

```vb
    Sub CancelConnectionX() 
     
     Dim wrkMain As Workspace 
     Dim conMain As Connection 
     Dim sngTime As Single 
     
     Set wrkMain = CreateWorkspace("ODBCWorkspace", _ 
     "admin", "", dbUseODBC) 
     ' Open the connection asynchronously. 
     
     ' Note: The DSN referenced below must be configured to 
     ' use Microsoft Windows NT Authentication Mode to 
     ' authorize user access to the Microsoft SQL Server. 
     Set conMain = wrkMain.OpenConnection("Publishers", _ 
     dbDriverNoPrompt + dbRunAsync, False, _ 
     "ODBC;DATABASE=pubs;DSN=Publishers") 
     
     sngTime = Timer 
     
     ' Wait five seconds. 
     Do While Timer - sngTime < 5 
     Loop 
     
     ' If the connection has not been made, ask the user 
     ' if she wants to keep waiting. If she does not, cancel 
     ' the connection and exit the procedure. 
     Do While conMain.StillExecuting 
     
     If MsgBox("No connection yet--keep waiting?", _ 
     vbYesNo) = vbNo Then 
     conMain.Cancel 
     MsgBox "Connection cancelled!" 
     wrkMain.Close 
     Exit Sub 
     End If 
     
     Loop 
     
     With conMain 
     ' Use the Connection object conMain. 
     .Close 
     End With 
     
     wrkMain.Close 
     
    End Sub
```
