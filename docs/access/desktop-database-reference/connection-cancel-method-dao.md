---
title: 连接. Cancel 方法 (DAO)
TOCTitle: Cancel Method
ms:assetid: 43ad7b64-823d-3fac-e4d4-5e9514f60011
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192953(v=office.15)
ms:contentKeyID: 48544509
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a0826a30f22cc46eb6ff9a114dbf02cab1d9f76a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295966"
---
# <a name="connectioncancel-method-dao"></a>连接. Cancel 方法 (DAO)

**适用于**：Access 2013、Office 2013

## <a name="syntax"></a>语法

*表达式*。取消

*表达式*一个代表**Connection**对象的变量。

## <a name="remarks"></a>注解

使用**Cancel**方法可以终止执行异步**Execute**或**OpenConnection**方法调用 (即, 使用即用 dbrunasync 选项调用方法)。 如果在尝试终止的方法中未使用即用 dbrunasync, 则 "**取消**" 将返回运行时错误。

如果在调用 **Cancel** 方法之后，您试图引用由异步 **OpenConnection** 调用创建的对象（即，您从其处调用 **Cancel** 方法的 **Connection** 对象），将会发生错误。

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
