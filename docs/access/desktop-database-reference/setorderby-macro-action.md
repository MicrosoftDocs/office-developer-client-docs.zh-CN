---
title: SetOrderBy 宏操作
TOCTitle: SetOrderBy Macro Action
ms:assetid: 78f65ce9-b56f-f476-3bd6-f3307bc22a08
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196152(v=office.15)
ms:contentKeyID: 48545765
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm98639
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 3f14ea2fb2c41058fe15764c3f06931ffd0dc9ae
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467784"
---
# <a name="setorderby-macro-action"></a><span data-ttu-id="4c7ce-102">SetOrderBy 宏操作</span><span class="sxs-lookup"><span data-stu-id="4c7ce-102">SetOrderBy Macro Action</span></span>


<span data-ttu-id="4c7ce-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="4c7ce-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="4c7ce-104">您可以使用 **SetOrderBy** 操作指定希望如何筛选窗体、报表、表或查询结果中的记录。</span><span class="sxs-lookup"><span data-stu-id="4c7ce-104">You can use the **SetOrderBy** action to specify how you want to sort records in a form, report, table, or query result.</span></span>

## <a name="setting"></a><span data-ttu-id="4c7ce-105">设置</span><span class="sxs-lookup"><span data-stu-id="4c7ce-105">Setting</span></span>

<span data-ttu-id="4c7ce-106">**SetOrderBy** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="4c7ce-106">The **SetOrderBy** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4c7ce-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="4c7ce-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="4c7ce-108">说明</span><span class="sxs-lookup"><span data-stu-id="4c7ce-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c7ce-109"><strong>Order By</strong></span><span class="sxs-lookup"><span data-stu-id="4c7ce-109"><strong>Order By</strong></span></span></p></td>
<td><p><span data-ttu-id="4c7ce-110">一个字符串表达式，包含作为记录排序依据的一个或多个字段的名称或可选的 ASC 或 DESC 关键字。</span><span class="sxs-lookup"><span data-stu-id="4c7ce-110">A string expression that includes the name of the field or fields on which to sort records and the optional ASC or DESC keywords.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c7ce-111"><strong>控件名称</strong></span><span class="sxs-lookup"><span data-stu-id="4c7ce-111"><strong>Control Name</strong></span></span></p></td>
<td><p><span data-ttu-id="4c7ce-p101">如果提供该参数并且活动对象是窗体或报表，则为与将要排序的子窗体或子报表对应的控件的名称。如果为空并且活动对象是窗体或报表，则对父窗体或报表进行排序。</span><span class="sxs-lookup"><span data-stu-id="4c7ce-p101">If provided and the active object is a form or report, the name of the control that corresponds to the subform or subreport that will be sorted. If empty and the active object is a form or report, the parent form or report is sorted..</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="4c7ce-114">注释</span><span class="sxs-lookup"><span data-stu-id="4c7ce-114">Remarks</span></span>

<span data-ttu-id="4c7ce-115">在运行该宏操作时，将对处于活动状态且具有焦点的表、窗体、报表或数据表（如查询结果）进行排序。</span><span class="sxs-lookup"><span data-stu-id="4c7ce-115">When you run this macro action, the sort is applied to the table, form, report or datasheet (query result) that is active and has the focus.</span></span>

<span data-ttu-id="4c7ce-p102">Order By 参数是作为记录排序依据的一个或多个字段的名称。如果使用多个字段名称，需用逗号 (,) 分隔每个名称。活动对象的 **OrderBy** 属性用于保存排序值并在以后应用该值。OrderBy 值与在其中创建这些值的对象一起保存。在打开对象时将自动加载这些值，但不会自动应用它们。</span><span class="sxs-lookup"><span data-stu-id="4c7ce-p102">The Order By argument is the name of the field or fields on which you want to sort records. When you use more than one field name, separate the names with a comma (,). The **OrderBy** property of the active object is used to save the ordering value and apply it at a later time. OrderBy values are saved with the objects in which they are created. They are automatically loaded when the object is opened, but they aren't automatically applied.</span></span>

<span data-ttu-id="4c7ce-121">在输入一个或多个字段名称以设置 Order By 参数然后运行该宏时，默认情况下将按升序排列记录。</span><span class="sxs-lookup"><span data-stu-id="4c7ce-121">When you set the Order By argument by entering one or more field names and then run the macro, the records are sorted by default in ascending order.</span></span>

<span data-ttu-id="4c7ce-p103">若要按降序排列记录，请在 Order By 参数表达式的末尾键入 DESC。例如，若要按联系人姓名的降序对客户记录进行排序，请将 Order By 参数设置为"ContactName DESC"。若要按"LastName"的降序和"FirstName"的升序对姓名进行排序，请将 Order By 参数设置为"LastName DESC, FirstName ASC"。</span><span class="sxs-lookup"><span data-stu-id="4c7ce-p103">To sort records in descending order, type DESC at the end of the Order By argument expression. For example, to sort customer records in descending order by contact name, set the Order By argument to "ContactName DESC". To sort names by LastName descending, and FirstName ascending, set the Order By argument to "LastName DESC, FirstName ASC".</span></span>

