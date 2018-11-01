---
title: DeleteObject 宏操作
TOCTitle: DeleteObject Macro Action
ms:assetid: a8deb2a7-4e73-8696-b8c1-3a3939d813f7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821415(v=office.15)
ms:contentKeyID: 48546912
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm152112
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 91a6943267ebcd5445c338f12cc9f892ead0e316
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25879422"
---
# <a name="deleteobject-macro-action"></a><span data-ttu-id="b141b-102">DeleteObject 宏操作</span><span class="sxs-lookup"><span data-stu-id="b141b-102">DeleteObject Macro Action</span></span>


<span data-ttu-id="b141b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="b141b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="b141b-104">可以使用 **DeleteObject** 操作删除指定的数据库对象。</span><span class="sxs-lookup"><span data-stu-id="b141b-104">You can use the **DeleteObject** action to delete a specified database object.</span></span>


> [!NOTE]
> <span data-ttu-id="b141b-p101">[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</span><span class="sxs-lookup"><span data-stu-id="b141b-p101">This action will not be allowed if the database is not trusted. For more information about enabling macros, see the links in the See Also section of this article.</span></span>

## <a name="setting"></a><span data-ttu-id="b141b-107">设置</span><span class="sxs-lookup"><span data-stu-id="b141b-107">Setting</span></span>

<span data-ttu-id="b141b-108">**DeleteObject** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="b141b-108">The **DeleteObject** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="b141b-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="b141b-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="b141b-110">说明</span><span class="sxs-lookup"><span data-stu-id="b141b-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b141b-111"><strong>对象类型</strong></span><span class="sxs-lookup"><span data-stu-id="b141b-111"><strong>Object Type</strong></span></span></p></td>
<td><p><span data-ttu-id="b141b-p102">要删除的对象的类型。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“对象类型”</strong>框中单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“报表”</strong>、<strong>“宏”</strong>、<strong>“模块”</strong>、<strong>“数据访问页”</strong>、<strong>“服务器视图”</strong>、<strong>“图表”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。要删除在导航窗格中选择的对象，请将此参数留空。</span><span class="sxs-lookup"><span data-stu-id="b141b-p102">The type of object to delete. Click <strong>Table</strong>, <strong>Query</strong>, <strong>Form</strong>, <strong>Report</strong>, <strong>Macro</strong>, <strong>Module</strong>, <strong>Data Access Page</strong>, <strong>Server View</strong>, <strong>Diagram</strong>, <strong>Stored Procedure</strong>, or <strong>Function</strong> in the <strong>Object Type</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. To delete the object selected in the Navigation Pane, leave this argument blank.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b141b-115"><strong>对象名称</strong></span><span class="sxs-lookup"><span data-stu-id="b141b-115"><strong>Object Name</strong></span></span></p></td>
<td><p><span data-ttu-id="b141b-116">要删除的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="b141b-116">The name of the object to delete.</span></span> <span data-ttu-id="b141b-117"><strong>对象名称</strong>框中显示<strong>对象类型</strong>参数所选类型的数据库中的所有对象。</span><span class="sxs-lookup"><span data-stu-id="b141b-117">The <strong>Object Name</strong> box shows all objects in the database of the type selected by the <strong>Object Type</strong> argument.</span></span> <span data-ttu-id="b141b-118">如果<strong>对象类型</strong>框为空，还应将此框留空。</span><span class="sxs-lookup"><span data-stu-id="b141b-118">If you leave the <strong>Object Type</strong> box blank, leave this box blank also.</span></span> <span data-ttu-id="b141b-119">如果在类库数据库中运行包含 <strong>DeleteObject</strong> 操作的宏，Microsoft Office Access 2007 将先在该类库数据库中查找具有此名称的对象，然后再在当前数据库中查找。</span><span class="sxs-lookup"><span data-stu-id="b141b-119">If you run a macro containing the <strong>DeleteObject</strong> action in a library database, Microsoft Office Access 2007 first looks for the object with this name in the library database, and then in the current database.</span></span></p></td>
</tr>
</tbody>
</table>



> [!WARNING]
> <span data-ttu-id="b141b-120">如果**对象类型**和**对象名称**框为空，则 Access 将删除而不在遇到**DeleteObject**操作时显示一条警告消息在导航窗格中选择的对象。</span><span class="sxs-lookup"><span data-stu-id="b141b-120">If you leave the **Object Type** and **Object Name** boxes blank, Access deletes the object selected in the Navigation Pane without displaying a warning message when it encounters the **DeleteObject** action.</span></span>



## <a name="remarks"></a><span data-ttu-id="b141b-121">说明</span><span class="sxs-lookup"><span data-stu-id="b141b-121">Remarks</span></span>

<span data-ttu-id="b141b-p104">可以使用 **DeleteObject** 操作删除在运行宏期间创建的临时对象。例如，可以使用 **OpenQuery** 操作运行创建临时表的生成表查询。在使用完临时表后，可以使用 **DeleteObject** 操作将其删除。</span><span class="sxs-lookup"><span data-stu-id="b141b-p104">You can use the **DeleteObject** action to delete temporary objects you have created while running the macro. For example, you could use the **OpenQuery** action to run a make-table query that creates a temporary table. When you are finished using the temporary table, you can use the **DeleteObject** action to delete it.</span></span>

<span data-ttu-id="b141b-125">此操作等效于先在导航窗格中选择对象再按 Del 键，或先在导航窗格中右键单击对象再单击 **"删除"**。</span><span class="sxs-lookup"><span data-stu-id="b141b-125">This action has the same effect as selecting an object in the Navigation Pane and then pressing the DEL key, or right-clicking the object in the Navigation Pane and clicking **Delete**.</span></span>

<span data-ttu-id="b141b-126">要在 Visual Basic for Applications 模块中运行 **DeleteObject** 操作，可使用 **DoCmd** 对象的 **DeleteObject** 方法。</span><span class="sxs-lookup"><span data-stu-id="b141b-126">To run the **DeleteObject** action in a Visual Basic for Applications module, you can use the **DeleteObject** method of the **DoCmd** object.</span></span>

