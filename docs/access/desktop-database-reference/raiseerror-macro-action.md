---
title: RaiseError 宏操作
TOCTitle: RaiseError macro action
ms:assetid: c8c57685-b373-67d6-cea6-8f2c334547d3
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823192(v=office.15)
ms:contentKeyID: 48547661
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: b706ffed14fdb440f3c3192c7c36015343f2e134
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32300922"
---
# <a name="raiseerror-macro-action"></a><span data-ttu-id="2ab7a-102">RaiseError 宏操作</span><span class="sxs-lookup"><span data-stu-id="2ab7a-102">RaiseError macro action</span></span>

<span data-ttu-id="2ab7a-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="2ab7a-103">**Applies to**: Access 2013, Office 2013</span></span> 

<span data-ttu-id="2ab7a-104">**RaiseError** 操作会引发 **[OnError](onerror-macro-action.md)** 宏操作可以处理的异常。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-104">The **RaiseError** action throws an exception that can be handled by the **[OnError](onerror-macro-action.md)** macro action.</span></span>

> [!NOTE]
> <span data-ttu-id="2ab7a-105">**RaiseError** 操作仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-105">The **RaiseError** action is available only in Data Macros.</span></span>

## <a name="setting"></a><span data-ttu-id="2ab7a-106">Setting</span><span class="sxs-lookup"><span data-stu-id="2ab7a-106">Setting</span></span>

<span data-ttu-id="2ab7a-107">**RaiseError** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-107">The **RaiseError** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2ab7a-108">参数</span><span class="sxs-lookup"><span data-stu-id="2ab7a-108">Argument</span></span></p></th>
<th><p><span data-ttu-id="2ab7a-109">必需</span><span class="sxs-lookup"><span data-stu-id="2ab7a-109">Required</span></span></p></th>
<th><p><span data-ttu-id="2ab7a-110">说明</span><span class="sxs-lookup"><span data-stu-id="2ab7a-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ab7a-111">Error Number</span><span class="sxs-lookup"><span data-stu-id="2ab7a-111">Error Number</span></span></p></td>
<td><p><span data-ttu-id="2ab7a-112">是</span><span class="sxs-lookup"><span data-stu-id="2ab7a-112">Yes</span></span></p></td>
<td><p><span data-ttu-id="2ab7a-113">解析为 Long 数据类型的数字或表达式。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-113">A number or an expression that resolves to the Long data type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ab7a-114">Error Description</span><span class="sxs-lookup"><span data-stu-id="2ab7a-114">Error Description</span></span></p></td>
<td><p><span data-ttu-id="2ab7a-115">否</span><span class="sxs-lookup"><span data-stu-id="2ab7a-115">No</span></span></p></td>
<td><p><span data-ttu-id="2ab7a-116">一个描述错误的字符串表达式。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-116">A string expression that describes the error.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="2ab7a-117">注解</span><span class="sxs-lookup"><span data-stu-id="2ab7a-117">Remarks</span></span>

<span data-ttu-id="2ab7a-118">如果在 [**更改前**](before-change-macro-event.md) 或 [**删除前**](before-delete-macro-event.md) 宏事件中调用 **RaiseError** 操作，将取消该事件。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-118">If the **RaiseError** action is called in a **[Before Change](before-change-macro-event.md)** or **[Before Delete](before-delete-macro-event.md)** macro event, the event is cancelled.</span></span>

<span data-ttu-id="2ab7a-p101">If there is not an active **OnError** statment that is handling errors, then the error thrown by the **RaiseError** action is added to the **USysApplicationLog** system table. When the **RaiseError** action to writes to the **USysApplicationLog** table, the **Category** column is automatically set to **Execution**.</span><span class="sxs-lookup"><span data-stu-id="2ab7a-p101">If there is not an active **OnError** statment that is handling errors, then the error thrown by the **RaiseError** action is added to the **USysApplicationLog** system table. When the **RaiseError** action to writes to the **USysApplicationLog** table, the **Category** column is automatically set to **Execution**.</span></span>

<span data-ttu-id="2ab7a-121">若要查看 **USysApplicationLog** 表，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="2ab7a-121">To see the **USysApplicationLog** table, use the following steps:</span></span>

1.  <span data-ttu-id="2ab7a-122">单击 "**文件**" 菜单, 然后单击 "**选项**"。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-122">Click the **File** menu, and then click **Options**.</span></span>

2.  <span data-ttu-id="2ab7a-123">在 **"Access 选项"** 对话框中，单击 **"当前数据库"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-123">In the **Access Options** dialog box, click the **Current Database** tab.</span></span>

3.  <span data-ttu-id="2ab7a-124">在 **"导航"** 部分，单击 **"导航选项"**。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-124">In the **Navigation** section, click **Navigation Options**.</span></span>

4.  <span data-ttu-id="2ab7a-125">在 **"导航选项"** 对话框中，单击 **"显示系统对象"**，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-125">In the **Navigation Options** dialog box, click **Show System Objects**, and then click **OK**.</span></span>

5.  <span data-ttu-id="2ab7a-126">单击 **"确定"** 关闭 **"Access 选项"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-126">Click **OK** to dismiss the **Access Options** dialog box.</span></span>

## <a name="example"></a><span data-ttu-id="2ab7a-127">示例</span><span class="sxs-lookup"><span data-stu-id="2ab7a-127">Example</span></span>

<span data-ttu-id="2ab7a-128">下面的示例演示如何使用 RaiseError 操作取消 Before Change data 宏事件。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-128">The following example shows how to use the RaiseError action to cancel the Before Change data macro event.</span></span> <span data-ttu-id="2ab7a-129">更新 "分配" 字段后, 将使用 LookupRecord 数据块确定分配的技术人员当前是否已分配给打开的服务请求。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-129">When the AssignedTo field is updated, a LookupRecord data block is used to determine whether the assigned technician is currently assigned to an open service request.</span></span> <span data-ttu-id="2ab7a-130">如果为 true, 则取消前更改事件, 且不更新记录。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-130">If this is true, then the Before Change event is cancelled and the record is not updated.</span></span>

<span data-ttu-id="2ab7a-131">**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="2ab7a-131">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

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
