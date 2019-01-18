---
title: 处理失败的更新
TOCTitle: Dealing with failed updates
ms:assetid: f6f4914d-59b3-f3f2-b986-218e07ce5a1d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250258(v=office.15)
ms:contentKeyID: 48548752
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 9a44548fd8747428b12c03c24207f36d3871e349
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28725936"
---
# <a name="dealing-with-failed-updates"></a>处理失败的更新

**适用于**： Access 2013、 Office 2013

## <a name="dealing-with-failed-updates"></a>处理失败的更新

当更新由于错误而停止时，如何解决错误将依赖于错误的性质和严重性以及应用程序的逻辑。但是，如果数据库与其他用户共享，则典型的错误是有其他人在您之前修改了字段。这种错误类型称为*冲突*。ADO 将检测此情况并报告错误。

如果有更新错误，它们将被错误处理例程捕获。 通过用 **adFilterConflictingRecords** 常量来筛选 **Recordset** ，可以只显示冲突行。 在此示例中的错误解析策略是只打印作者姓和名 (**au\_fname**和**au\_lname**)。

警告用户发生更新冲突的代码类似如下：

```vb 
 
objRs.Filter = adFilterConflictingRecords 
objRs.MoveFirst 
Do While Not objRst.EOF 
   Debug.Print "Conflict: Name =  "; objRs!au_fname; " "; objRs!au_lname 
   objRs.MoveNext 
Loop 
```

