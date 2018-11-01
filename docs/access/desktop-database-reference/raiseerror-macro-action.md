---
title: RaiseError 宏操作
TOCTitle: RaiseError Macro Action
ms:assetid: c8c57685-b373-67d6-cea6-8f2c334547d3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823192(v=office.15)
ms:contentKeyID: 48547661
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: e7cddb3ace4027c2dba45fd685fbf16bd57b783e
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25887339"
---
# <a name="raiseerror-macro-action"></a>RaiseError 宏操作

**适用于**： Access 2013、 Office 2013 

**RaiseError** 操作会引发 **[OnError](onerror-macro-action.md)** 宏操作可以处理的异常。

> [!NOTE]
> [!注释] **RaiseError** 操作仅适用于数据宏。

## <a name="setting"></a>设置

**RaiseError** 操作具有以下参数。

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>参数</p></th>
<th><p>是否必需</p></th>
<th><p>说明</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Error Number</p></td>
<td><p>是</p></td>
<td><p>解析为 Long 数据类型的数字或表达式。</p></td>
</tr>
<tr class="even">
<td><p>Error Description</p></td>
<td><p>否</p></td>
<td><p>一个描述错误的字符串表达式。</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>注释

如果在 [**更改前**](before-change-macro-event.md) 或 [**删除前**](before-delete-macro-event.md) 宏事件中调用 **RaiseError** 操作，将取消该事件。

如果不处理错误的活动**OnError**语句，则会将通过**RaiseError**操作引发的错误： 添加到**USysApplicationLog**系统表。 当**RaiseError**操作写入**USysApplicationLog**表时，**类别**列是自动设置为**执行**。

若要查看 **USysApplicationLog** 表，请执行以下步骤：

1.  单击**文件**菜单，然后单击**选项**。

2.  在 **"Access 选项"** 对话框中，单击 **"当前数据库"** 选项卡。

3.  在 **"导航"** 部分，单击 **"导航选项"**。

4.  在 **"导航选项"** 对话框中，单击 **"显示系统对象"**，然后单击 **"确定"**。

5.  单击 **"确定"** 关闭 **"Access 选项"** 对话框。

## <a name="example"></a>示例

下面的示例演示如何使用 RaiseError 操作取消 Before Change 数据宏事件。 更新 AssignedTo 字段时，LookupRecord 数据块用于确定是否已分配的技术人员当前分配给打开服务请求。 如果是这样，然后取消 Before Change 事件并不会更新记录。

**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。

```vb
    /* Get the name of the technician  */
    Look Up A Record In tblTechnicians
        Where Condition =[tblTechnicians].[ID]=[tblServiceRequests].[AssignedTo]
    SetLocalVar
        Name TechName
        Expression [tblTechnicians].[FirstName] & " " & [tblTechnicians].[LastName]
    /* End LookUpRecord  */
    
    If Updated("AssignedTo") Then
        Look Up A Record In tblServiceRequests
            Where Condition SR.[AssignedTo]=tblServiceRequests[AssignedTo] And 
                SR.[ID]<>tblServiceRequests.[ID] And IsNull(SR.[ActualCompletionDate])
            Alias SR
            RaiseError
                Error Number 1234
                Error Description ="Cannot assign a request to the specified technician: " & [TechName]
    
    End If
```
