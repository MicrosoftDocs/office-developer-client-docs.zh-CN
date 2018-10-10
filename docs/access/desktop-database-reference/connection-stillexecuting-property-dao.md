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
# <a name="connectionstillexecuting-property-dao"></a><span data-ttu-id="f50a8-102">Connection.StillExecuting Property (DAO)</span><span class="sxs-lookup"><span data-stu-id="f50a8-102">Connection.StillExecuting Property (DAO)</span></span>

<span data-ttu-id="f50a8-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="f50a8-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="syntax"></a><span data-ttu-id="f50a8-104">语法</span><span class="sxs-lookup"><span data-stu-id="f50a8-104">Syntax</span></span>

<span data-ttu-id="f50a8-105">*表达式*。StillExecuting</span><span class="sxs-lookup"><span data-stu-id="f50a8-105">*expression* .StillExecuting</span></span>

<span data-ttu-id="f50a8-106">*表达式*代表**Connection**对象的变量。</span><span class="sxs-lookup"><span data-stu-id="f50a8-106">*expression* A variable that represents a **Connection** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="f50a8-107">注解</span><span class="sxs-lookup"><span data-stu-id="f50a8-107">Remarks</span></span>

<span data-ttu-id="f50a8-p101">使用 **StillExecuting** 属性可以确定最近调用的异步 **Execute** 或 **OpenConnection** 方法（即用 **dbRunAsync** 选项执行的方法）是否已完成。在 **StillExecuting** 属性为 **True** 的情况下，不能访问任何返回的对象。</span><span class="sxs-lookup"><span data-stu-id="f50a8-p101">Use the **StillExecuting** property to determine if the most recently called asynchronous **Execute** or **OpenConnection** method (that is, a method executed with the **dbRunAsync** option) is complete. While the **StillExecuting** property is **True**, any returned object cannot be accessed.</span></span>

<span data-ttu-id="f50a8-p102">一旦 **StillExecuting** 属性返回 **False**，在返回相关 **Connection** 对象的 **OpenConnection** 调用之后，即可引用该对象。只要 **StillExecuting** 仍为 **True**，就不能引用该对象，而只能读取 **StillExecuting** 属性。</span><span class="sxs-lookup"><span data-stu-id="f50a8-p102">Once the **StillExecuting** property returns **False**, following the **OpenConnection** call that returns the associated **Connection** object, the object can be referenced. So long as **StillExecuting** remains **True**, the object may not be referenced, other than to read the **StillExecuting** property.</span></span>

<span data-ttu-id="f50a8-112">使用 **[Cancel](connection-cancel-method-dao.md)** 方法可以终止执行正在进行的任务。</span><span class="sxs-lookup"><span data-stu-id="f50a8-112">Use the **[Cancel](connection-cancel-method-dao.md)** method to terminate execution of a task in progress.</span></span>

## <a name="example"></a><span data-ttu-id="f50a8-113">示例</span><span class="sxs-lookup"><span data-stu-id="f50a8-113">Example</span></span>

<span data-ttu-id="f50a8-114">以下示例使用 **StillExecuting** 属性和 **Cancel** 方法异步打开 **Connection** 对象。</span><span class="sxs-lookup"><span data-stu-id="f50a8-114">This example uses the **StillExecuting** property and the **Cancel** method to asynchronously open a **Connection** object.</span></span>

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
