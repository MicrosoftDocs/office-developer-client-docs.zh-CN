---
title: RepaintObject 宏操作
TOCTitle: RepaintObject macro action
ms:assetid: e8fa7d0b-578c-5071-2bd5-b772b48637a5
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836055(v=office.15)
ms:contentKeyID: 48548431
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm195788
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 369c518ab0ab213975bb7da3c96b6e5844bad9ee
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25919414"
---
# <a name="repaintobject-macro-action"></a><span data-ttu-id="6774f-102">RepaintObject 宏操作</span><span class="sxs-lookup"><span data-stu-id="6774f-102">RepaintObject macro action</span></span>


<span data-ttu-id="6774f-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="6774f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="6774f-p101">可以使用 **RepaintObject** 操作完成指定数据库对象或活动数据库对象（如果未指定数据库对象）的所有尚未完成的屏幕更新。这类更新包括对象的控件的所有尚未完成的重新计算。</span><span class="sxs-lookup"><span data-stu-id="6774f-p101">You can use the **RepaintObject** action to complete any pending screen updates for a specified database object or for the active database object, if none is specified. Such updates include any pending recalculations for the object's controls.</span></span>

## <a name="setting"></a><span data-ttu-id="6774f-106">设置</span><span class="sxs-lookup"><span data-stu-id="6774f-106">Setting</span></span>

<span data-ttu-id="6774f-107">**RepaintObject** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="6774f-107">The **RepaintObject** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="6774f-108">操作参数</span><span class="sxs-lookup"><span data-stu-id="6774f-108">Action argument</span></span></p></th>
<th><p><span data-ttu-id="6774f-109">说明</span><span class="sxs-lookup"><span data-stu-id="6774f-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6774f-110"><strong>对象类型</strong></span><span class="sxs-lookup"><span data-stu-id="6774f-110"><strong>Object Type</strong></span></span></p></td>
<td><p><span data-ttu-id="6774f-p102">要重画的对象的类型。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“对象类型”</strong>框中单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“报表”</strong>、<strong>“宏”</strong>、<strong>“模块”</strong>、<strong>“数据访问页”</strong>、<strong>“服务器视图”</strong>、<strong>“图表”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。如果将此参数留空，则会选择活动对象。</span><span class="sxs-lookup"><span data-stu-id="6774f-p102">The type of object to repaint. Click <strong>Table</strong>, <strong>Query</strong>, <strong>Form</strong>, <strong>Report</strong>, <strong>Macro</strong>, <strong>Module</strong>, <strong>Data Access Page</strong>, <strong>Server View</strong>, <strong>Diagram</strong>, <strong>Stored Procedure</strong>, or <strong>Function</strong> in the <strong>Object Type</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. Leave this argument blank to select the active object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6774f-114"><strong>对象名称</strong></span><span class="sxs-lookup"><span data-stu-id="6774f-114"><strong>Object Name</strong></span></span></p></td>
<td><p><span data-ttu-id="6774f-115">要重画的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="6774f-115">The name of the object to repaint.</span></span> <span data-ttu-id="6774f-116"><strong>对象名称</strong>框中显示<strong>对象类型</strong>参数所选类型的数据库中的所有对象。</span><span class="sxs-lookup"><span data-stu-id="6774f-116">The <strong>Object Name</strong> box shows all objects in the database of the type selected by the <strong>Object Type</strong> argument.</span></span> <span data-ttu-id="6774f-117">如果将<strong>对象类型</strong>参数留空，还应将此参数留空。</span><span class="sxs-lookup"><span data-stu-id="6774f-117">If you leave the <strong>Object Type</strong> argument blank, leave this argument blank also.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="6774f-118">说明</span><span class="sxs-lookup"><span data-stu-id="6774f-118">Remarks</span></span>

<span data-ttu-id="6774f-p104">Microsoft Access 需等到完成其他尚未完成的任务后才完成尚未完成的屏幕更新。利用此操作，可以立即强制重画指定对象中的控件。在下列情况下，可以使用此操作：</span><span class="sxs-lookup"><span data-stu-id="6774f-p104">Microsoft Access waits to complete pending screen updates until it finishes other pending tasks. With this action, you can force immediate repainting of the controls in the specified object. You can use this action:</span></span>

  - <span data-ttu-id="6774f-p105">使用 **SetValue** 操作更改很多控件中的值时。Access 可能不会立刻显示所做的更改，尤其是其他控件（如计算控件）依靠更改的控件中的值时更是如此。</span><span class="sxs-lookup"><span data-stu-id="6774f-p105">When you use the **SetValue** action to change values in a number of controls. Access might not show the changes immediately, especially if other controls (such as calculated controls) depend on values in the changed controls.</span></span>

  - <span data-ttu-id="6774f-p106">想要确保您正在查看的窗体显示其所有控件中的数据时。例如，在您打开一个窗体后，包含 OLE 对象的控件不会立即显示它们的数据。</span><span class="sxs-lookup"><span data-stu-id="6774f-p106">When you want to make sure that the form you are viewing displays data in all of its controls. For example, controls containing OLE objects don't display their data immediately after you open a form.</span></span>


> [!NOTE]
> <UL>
> <LI>
> <P><span data-ttu-id="6774f-p107">此操作不会导致对数据库的重新查询，因此它不会显示新的或更改过的记录，也不会从对象的基础表或查询中删除已删除的对象。使用 <STRONG>Requery</STRONG> 操作可以重新查询对象的数据源或对象的控件之一。使用 <STRONG>ShowAllRecords</STRONG> 操作可以显示最新记录并删除所有已经应用的筛选。</span><span class="sxs-lookup"><span data-stu-id="6774f-p107">This action doesn't cause a requery of the database, so it doesn't show new and changed records or remove deleted records from the object's underlying table or query. Use the <STRONG>Requery</STRONG> action to requery the source of the object or one of its controls. Use the <STRONG>ShowAllRecords</STRONG> action to display the most recent records and remove any applied filters.</span></span></P>
> <LI>
> <P><span data-ttu-id="6774f-129"><STRONG>RepaintObject</STRONG> 操作的效果不同于单击 <STRONG>"开始"</STRONG>选项卡上 <STRONG>"记录"</STRONG>组中的 <STRONG>"刷新"</STRONG>，后一种操作会显示您或其他用户已对窗体和数据表中当前显示的记录所做的所有更改。</span><span class="sxs-lookup"><span data-stu-id="6774f-129">The <STRONG>RepaintObject</STRONG> action doesn't have the same effect as clicking <STRONG>Refresh</STRONG> in the <STRONG>Records</STRONG> group on the <STRONG>Home</STRONG> tab, which shows any changes you or other users have made to the currently displayed records in forms and datasheets.</span></span></P></LI></UL>



<span data-ttu-id="6774f-130">要在 Visual Basic for Applications (VBA) 模块中运行 **RepaintObject** 操作，请使用 **DoCmd** 对象的 **RepaintObject** 方法。</span><span class="sxs-lookup"><span data-stu-id="6774f-130">To run the **RepaintObject** action in a Visual Basic for Applications (VBA) module, use the **RepaintObject** method of the **DoCmd** object.</span></span>

