---
title: 处理失败更新
TOCTitle: Dealing with Failed Updates
ms:assetid: f6f4914d-59b3-f3f2-b986-218e07ce5a1d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250258(v=office.15)
ms:contentKeyID: 48548752
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 6d3af3026052954ec74b10026e0cf288a6aa5249
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465910"
---
# <a name="dealing-with-failed-updates"></a><span data-ttu-id="ee80f-102">处理失败更新</span><span class="sxs-lookup"><span data-stu-id="ee80f-102">Dealing with Failed Updates</span></span>


<span data-ttu-id="ee80f-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="ee80f-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="dealing-with-failed-updates"></a><span data-ttu-id="ee80f-104">处理失败更新</span><span class="sxs-lookup"><span data-stu-id="ee80f-104">Dealing with Failed Updates</span></span>

<span data-ttu-id="ee80f-p101">当更新由于错误而停止时，如何解决错误将依赖于错误的性质和严重性以及应用程序的逻辑。但是，如果数据库与其他用户共享，则典型的错误是有其他人在您之前修改了字段。这种错误类型称为*冲突*。ADO 将检测此情况并报告错误。</span><span class="sxs-lookup"><span data-stu-id="ee80f-p101">When an update concludes with errors, how you resolve the errors depends on the nature and severity of the errors and the logic of your application. However, if the database is shared with other users, a typical error is that someone else modifies the field before you do. This type of error is called a *conflict.* ADO detects this situation and reports an error.</span></span>

<span data-ttu-id="ee80f-109">如果有更新错误，它们将被错误处理例程捕获。</span><span class="sxs-lookup"><span data-stu-id="ee80f-109">If there are update errors, they will be trapped in an error-handling routine.</span></span> <span data-ttu-id="ee80f-110">通过用 **adFilterConflictingRecords** 常量来筛选 **Recordset** ，可以只显示冲突行。</span><span class="sxs-lookup"><span data-stu-id="ee80f-110">Filter the **Recordset** with the **adFilterConflictingRecords** constant so that only the conflicting rows are visible.</span></span> <span data-ttu-id="ee80f-111">在此示例中的错误解析策略是只打印作者姓和名 (**au\_fname**和**au\_lname**)。</span><span class="sxs-lookup"><span data-stu-id="ee80f-111">In this example, the error-resolution strategy is merely to print the author's first and last names (**au\_fname** and **au\_lname**).</span></span>

<span data-ttu-id="ee80f-112">警告用户发生更新冲突的代码类似如下：</span><span class="sxs-lookup"><span data-stu-id="ee80f-112">The code to alert the user to the update conflict looks like this:</span></span>

```vb 
 
objRs.Filter = adFilterConflictingRecords 
objRs.MoveFirst 
Do While Not objRst.EOF 
   Debug.Print "Conflict: Name =  "; objRs!au_fname; " "; objRs!au_lname 
   objRs.MoveNext 
Loop 
```

