---
title: OpenTable 宏操作
TOCTitle: OpenTable macro action
ms:assetid: 4220ad3a-d064-0034-2806-ec1a447cebac
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192909(v=office.15)
ms:contentKeyID: 48544469
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm149011
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 451d27f97c0b4f5fc4707d3947e262ba84b9a40e
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25926099"
---
# <a name="opentable-macro-action"></a><span data-ttu-id="cf0df-102">OpenTable 宏操作</span><span class="sxs-lookup"><span data-stu-id="cf0df-102">OpenTable macro action</span></span>


<span data-ttu-id="cf0df-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="cf0df-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="cf0df-p101">可以使用 **OpenTable** 操作在数据表视图、设计视图或打印预览中打开表。您还可以为表选择数据输入模式。</span><span class="sxs-lookup"><span data-stu-id="cf0df-p101">You can use the **OpenTable** action to open a table in Datasheet view, Design view, or Print Preview. You can also select a data entry mode for the table.</span></span>

## <a name="setting"></a><span data-ttu-id="cf0df-106">设置</span><span class="sxs-lookup"><span data-stu-id="cf0df-106">Setting</span></span>

<span data-ttu-id="cf0df-107">**OpenTable** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="cf0df-107">The **OpenTable** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="cf0df-108">操作参数</span><span class="sxs-lookup"><span data-stu-id="cf0df-108">Action argument</span></span></p></th>
<th><p><span data-ttu-id="cf0df-109">说明</span><span class="sxs-lookup"><span data-stu-id="cf0df-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf0df-110"><strong>表名称</strong></span><span class="sxs-lookup"><span data-stu-id="cf0df-110"><strong>Table Name</strong></span></span></p></td>
<td><p><span data-ttu-id="cf0df-111">要打开的表的名称。</span><span class="sxs-lookup"><span data-stu-id="cf0df-111">The name of the table to open.</span></span> <span data-ttu-id="cf0df-112"><strong>表名称</strong>框中的<strong>操作参数</strong>部分的宏生成器窗格中显示当前数据库中的所有表。</span><span class="sxs-lookup"><span data-stu-id="cf0df-112">The <strong>Table Name</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane shows all tables in the current database.</span></span> <span data-ttu-id="cf0df-113">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="cf0df-113">This is a required argument.</span></span> <span data-ttu-id="cf0df-114">如果在类库数据库中运行包含 <strong>OpenTable</strong> 操作的宏，Microsoft Access 将先在该类库数据库中查找具有此名称的表，然后再在当前数据库中查找。</span><span class="sxs-lookup"><span data-stu-id="cf0df-114">If you run a macro containing the <strong>OpenTable</strong> action in a library database, Microsoft Microsoft Access looks for the table with this name first in the library database, then in the current database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf0df-115"><strong>View</strong></span><span class="sxs-lookup"><span data-stu-id="cf0df-115"><strong>View</strong></span></span></p></td>
<td><p><span data-ttu-id="cf0df-p103">打开表时将使用的视图。请在<strong>“视图”</strong>框中单击<strong>“数据表”</strong>、<strong>“设计”</strong>、<strong>“打印预览”</strong>、<strong>“数据透视表”</strong>或<strong>“数据透视图”</strong>。默认值为<strong>“数据表”</strong>。</span><span class="sxs-lookup"><span data-stu-id="cf0df-p103">The view in which the table will open. Click <strong>Datasheet</strong>, <strong>Design</strong>, <strong>Print Preview</strong>, <strong>PivotTable</strong>, or <strong>PivotChart</strong> in the <strong>View</strong> box. The default is <strong>Datasheet</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf0df-119"><strong>Data Mode</strong></span><span class="sxs-lookup"><span data-stu-id="cf0df-119"><strong>Data Mode</strong></span></span></p></td>
<td><p><span data-ttu-id="cf0df-p104">表的数据输入模式。此参数仅适用于在数据表视图中打开的表。请单击<strong>“添加”</strong>（用户可添加新记录，但不能编辑现有记录）、<strong>“编辑”</strong>（用户可编辑现有记录和添加新记录）或<strong>“只读”</strong>（用户只能查看记录）。默认值为<strong>“编辑”</strong>。</span><span class="sxs-lookup"><span data-stu-id="cf0df-p104">The data entry mode for the table. This applies only to tables opened in Datasheet view. Click <strong>Add</strong> (the user can add new records but can't edit existing records), <strong>Edit</strong> (the user can edit existing records and add new records), or <strong>Read Only</strong> (the user can only view records). The default is <strong>Edit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="cf0df-124">说明</span><span class="sxs-lookup"><span data-stu-id="cf0df-124">Remarks</span></span>

<span data-ttu-id="cf0df-125">此操作类似于在导航窗格中双击表，或在导航窗格中右键单击表并选择视图。</span><span class="sxs-lookup"><span data-stu-id="cf0df-125">This action is similar to double-clicking the table in the Navigation Pane, or right-clicking the table in the Navigation Pane and selecting a view.</span></span>


> [!TIP]
> <P><span data-ttu-id="cf0df-p105">[!提示] 您可以将表从导航窗格拖至某个宏操作行。这会自动创建在数据表视图中打开该表的 <STRONG>OpenTable</STRONG> 操作。</span><span class="sxs-lookup"><span data-stu-id="cf0df-p105">You can drag a table from the Navigation Pane to a macro action row. This automatically creates an <STRONG>OpenTable</STRONG> action that opens the table in Datasheet view.</span></span></P>



<span data-ttu-id="cf0df-128">要在 Visual Basic for Applications (VBA) 模块中运行 **OpenTable** 操作，请使用 **DoCmd** 对象的 **OpenTable** 方法。</span><span class="sxs-lookup"><span data-stu-id="cf0df-128">To run the **OpenTable** action in a Visual Basic for Applications (VBA) module, use the **OpenTable** method of the **DoCmd** object.</span></span>

