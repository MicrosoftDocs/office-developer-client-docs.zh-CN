---
title: SetFilter 宏操作
TOCTitle: SetFilter macro action
ms:assetid: dee699e2-0840-1612-23ce-199ef8d30566
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835438(v=office.15)
ms:contentKeyID: 48548203
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm122943
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: ac1a2c8a603fb74b56d71f73605455ecdbc87035
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28698678"
---
# <a name="setfilter-macro-action"></a><span data-ttu-id="4d4df-102">SetFilter 宏操作</span><span class="sxs-lookup"><span data-stu-id="4d4df-102">SetFilter macro action</span></span>

<span data-ttu-id="4d4df-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4d4df-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="4d4df-104">可以使用 **SetFilter** 操作向活动数据表、窗体、报表或表中的记录应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="4d4df-104">You can use the **SetFilter** action to apply a filter to the records in the active datasheet, form, report, or table.</span></span>

## <a name="setting"></a><span data-ttu-id="4d4df-105">设置</span><span class="sxs-lookup"><span data-stu-id="4d4df-105">Setting</span></span>

<span data-ttu-id="4d4df-106">**SetFilter** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="4d4df-106">The **SetFilter** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4d4df-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="4d4df-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="4d4df-108">说明</span><span class="sxs-lookup"><span data-stu-id="4d4df-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d4df-109">Filter Name</span><span class="sxs-lookup"><span data-stu-id="4d4df-109">Filter Name</span></span></p></td>
<td><p><span data-ttu-id="4d4df-110">如果提供该参数，则会将查询或筛选器的名称另存为查询。</span><span class="sxs-lookup"><span data-stu-id="4d4df-110">If provided, the name of a query or of a filter saved as a query.</span></span> <span data-ttu-id="4d4df-111">客户端数据库中需要此参数或 WhereCondition 参数。</span><span class="sxs-lookup"><span data-stu-id="4d4df-111">This argument or the WhereCondition argument is required in a client database.</span></span> <span data-ttu-id="4d4df-112">在 web 数据库中，此参数不可用。</span><span class="sxs-lookup"><span data-stu-id="4d4df-112">In a web database, this argument is not available.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d4df-113">Where Condition</span><span class="sxs-lookup"><span data-stu-id="4d4df-113">Where Condition</span></span></p></td>
<td><p><span data-ttu-id="4d4df-114">如果提供该参数，则为可限制数据表、窗体、报表或表中记录的 SQL WHERE 子句。</span><span class="sxs-lookup"><span data-stu-id="4d4df-114">If provided, a SQL WHERE clause that restricts the records in the datasheet, form, report, or table.</span></span> <span data-ttu-id="4d4df-115">在 web 数据库中，此参数是必需的。</span><span class="sxs-lookup"><span data-stu-id="4d4df-115">In a web database, this argument is required.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d4df-116">控件名称</span><span class="sxs-lookup"><span data-stu-id="4d4df-116">Control Name</span></span></p></td>
<td><p><span data-ttu-id="4d4df-p103">如果提供该参数，则为与要筛选的子窗体或子报表相对应的控件的名称。如果为空，则筛选当前对象。</span><span class="sxs-lookup"><span data-stu-id="4d4df-p103">If provided, the name of the control that corresponds to the subform or subreport to be filtered. If empty, the current object is filtered.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="4d4df-119">注释</span><span class="sxs-lookup"><span data-stu-id="4d4df-119">Remarks</span></span>

<span data-ttu-id="4d4df-120">在 Web 数据库中，"Where Condition"参数不能以等号 (=) 开头。</span><span class="sxs-lookup"><span data-stu-id="4d4df-120">In a web database, the Where Condition argument cannot begin with an equal sign (=).</span></span>

<span data-ttu-id="4d4df-121">在运行该操作时，将对处于活动状态且具有焦点的表、窗体、报表或数据表（如查询结果）应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="4d4df-121">When you run this action, the filter is applied to the table, form, report or datasheet (for example, query result) that is active and has the focus.</span></span>

<span data-ttu-id="4d4df-p104">活动对象的 **Filter** 属性用于保存 WhereCondition 参数并在以后应用该参数。筛选器与在其中创建筛选器的对象一起保存。在打开对象时会自动加载筛选器，但不会自动应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="4d4df-p104">The **Filter** property of the active object is used to save the WhereCondition argument and apply it at a later time. Filters are saved with the objects in which they are created. They are automatically loaded when the object is opened, but they are not automatically applied.</span></span>

<span data-ttu-id="4d4df-125">在客户端数据库中，若要在打开对象时自动应用筛选器，请将 **FilterOnLoad** 属性设置为 True。</span><span class="sxs-lookup"><span data-stu-id="4d4df-125">In a client database, to automatically apply a filter when the object is opened, set the **FilterOnLoad** property to True.</span></span>

<span data-ttu-id="4d4df-126">在 Web 数据库中，若要在打开对象时自动应用筛选器，请将 **SetFilter** 操作设置为宏，并将该宏添加到对象的 **OnLoad** 事件中。</span><span class="sxs-lookup"><span data-stu-id="4d4df-126">In a web database, to automatically apply a filter when the object is opened, add the **SetFilter** action to a macro, and add the macro to the object's **OnLoad** event.</span></span>

## <a name="example"></a><span data-ttu-id="4d4df-127">示例</span><span class="sxs-lookup"><span data-stu-id="4d4df-127">Example</span></span>

<span data-ttu-id="4d4df-128">下面的示例演示如何使用 SetFilter 操作筛选在其中定义为宏的窗体。</span><span class="sxs-lookup"><span data-stu-id="4d4df-128">The following example shows how to use the SetFilter action to filter the form in which the macro is defined.</span></span>

<span data-ttu-id="4d4df-129">**示例代码提供者** [Microsoft Access 2010 Programmer's Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="4d4df-129">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    OpenForm
        Form Name sfrmFoods
        View Form
        Filter Name
        Where Condition
        Data Mode
        Window Mode Normal
    
    SetFilter
        Filter Name
        Where Condtion =[display_name] Like "*cheese*"
        Control Name
```
