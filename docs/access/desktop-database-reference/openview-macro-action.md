---
title: OpenView 宏操作
TOCTitle: OpenView Macro Action
ms:assetid: 4d3b7e6d-4b81-4fbe-7222-24d745350321
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193569(v=office.15)
ms:contentKeyID: 48544726
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm50135
f1_categories:
- Office.Version=v15
ms.openlocfilehash: ad607f852f5af21bc2979bd635286b86d18489a5
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466784"
---
# <a name="openview-macro-action"></a><span data-ttu-id="96e17-102">OpenView 宏操作</span><span class="sxs-lookup"><span data-stu-id="96e17-102">OpenView Macro Action</span></span>


<span data-ttu-id="96e17-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="96e17-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="96e17-p101">在 Microsoft Access 项目中，可以使用 **OpenView** 操作在数据表视图、设计视图或打印预览中打开视图。如果在数据表视图中打开命名视图，此操作将运行该视图。您可以为视图选择数据输入模式，以及限制视图显示的记录。</span><span class="sxs-lookup"><span data-stu-id="96e17-p101">In an Access project, you can use the **OpenView** action to open a view in Datasheet view, Design view, or Print Preview. This action runs the named view when opened in Datasheet view. You can select data entry for the view and restrict the records that the view displays.</span></span>


> [!NOTE]
> <P><span data-ttu-id="96e17-p102">[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</span><span class="sxs-lookup"><span data-stu-id="96e17-p102">This action will not be allowed if the database is not trusted. For more information about enabling macros, see the links in the See Also section of this article.</span></span></P>



## <a name="setting"></a><span data-ttu-id="96e17-109">设置</span><span class="sxs-lookup"><span data-stu-id="96e17-109">Setting</span></span>

<span data-ttu-id="96e17-110">**OpenView** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="96e17-110">The **OpenView** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="96e17-111">操作参数</span><span class="sxs-lookup"><span data-stu-id="96e17-111">Action argument</span></span></p></th>
<th><p><span data-ttu-id="96e17-112">说明</span><span class="sxs-lookup"><span data-stu-id="96e17-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96e17-113"><strong>视图名称</strong></span><span class="sxs-lookup"><span data-stu-id="96e17-113"><strong>View Name</strong></span></span></p></td>
<td><p><span data-ttu-id="96e17-114">要打开的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="96e17-114">The name of the view to open.</span></span> <span data-ttu-id="96e17-115">宏生成器窗格的<strong>操作参数</strong>部分的<strong>视图名称</strong>框显示当前数据库中的所有视图。</span><span class="sxs-lookup"><span data-stu-id="96e17-115">The <strong>View Name</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane shows all views in the current database.</span></span> <span data-ttu-id="96e17-116">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="96e17-116">This is a required argument.</span></span> <span data-ttu-id="96e17-117">如果在类库数据库中运行包含 <strong>OpenView</strong> 操作的宏，Microsoft Access 将先在该类库数据库中查找具有此名称的视图，然后再在当前数据库中查找。</span><span class="sxs-lookup"><span data-stu-id="96e17-117">If you run a macro containing the <strong>OpenView</strong> action in a library database, Microsoft Access first looks for the view with this name in the library database, and then in the current database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e17-118"><strong>View</strong></span><span class="sxs-lookup"><span data-stu-id="96e17-118"><strong>View</strong></span></span></p></td>
<td><p><span data-ttu-id="96e17-p104">打开视图时将使用的视图。请在<strong>“视图”</strong>框中单击<strong>“数据表”</strong>、<strong>“设计”</strong>、<strong>“打印预览”</strong>、<strong>“数据透视表”</strong>或<strong>“数据透视图”</strong>。默认值为<strong>“数据表”</strong>。</span><span class="sxs-lookup"><span data-stu-id="96e17-p104">The view in which the view will open. Click <strong>Datasheet</strong>, <strong>Design</strong>, <strong>Print Preview</strong>, <strong>PivotTable</strong>, or <strong>PivotChart</strong> in the <strong>View</strong> box. The default is <strong>Datasheet</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e17-122"><strong>Data Mode</strong></span><span class="sxs-lookup"><span data-stu-id="96e17-122"><strong>Data Mode</strong></span></span></p></td>
<td><p><span data-ttu-id="96e17-p105">视图的数据输入模式。此参数仅适用于在数据表视图中打开的视图。请单击<strong>“添加”</strong>（用户可添加新记录，但不能查看或编辑现有记录）、<strong>“编辑”</strong>（用户可查看或编辑现有记录以及添加新记录）或<strong>“只读”</strong>（用户只能查看记录）。默认值为<strong>“编辑”</strong>。</span><span class="sxs-lookup"><span data-stu-id="96e17-p105">The data entry mode for the view. This applies only to views opened in Datasheet view. Click <strong>Add</strong> (the user can add new records but can't view or edit existing records), <strong>Edit</strong> (the user can view or edit existing records and add new records), or <strong>Read Only</strong> (the user can only view records). The default is <strong>Edit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="96e17-127">说明</span><span class="sxs-lookup"><span data-stu-id="96e17-127">Remarks</span></span>

<span data-ttu-id="96e17-128">此操作类似于在导航窗格中双击视图，或者在导航窗格中右键单击视图，然后单击所需的命令。</span><span class="sxs-lookup"><span data-stu-id="96e17-128">This action is similar to double-clicking a view in the Navigation Pane, or right-clicking the view in the Navigation Pane and then clicking the command you want.</span></span>

<span data-ttu-id="96e17-129">**提示**</span><span class="sxs-lookup"><span data-stu-id="96e17-129">**Tips**</span></span>

  - <span data-ttu-id="96e17-p106">您可以将视图从导航窗格拖至某个宏操作行。这会自动创建在数据表视图中打开该视图的 **OpenView** 操作。</span><span class="sxs-lookup"><span data-stu-id="96e17-p106">You can drag a view from the Navigation Pane to a macro action row. This automatically creates an **OpenView** action that opens the view in Datasheet view.</span></span>

  - <span data-ttu-id="96e17-132">通常，当视图运行时，会显示一些系统消息（指明运行的是视图并显示将受到影响的记录数）。如果不想显示这些系统消息，可以使用 **SetWarning** 操作禁止其显示。</span><span class="sxs-lookup"><span data-stu-id="96e17-132">If you don't want to display the system messages that normally appear when a view is run (indicating it is a view and showing how many records will be affected), you can use the **SetWarning** action to suppress the display of these messages.</span></span>

<span data-ttu-id="96e17-133">要在 Visual Basic for Applications (VBA) 模块中运行 **OpenView** 操作，请使用 **DoCmd** 对象的 **OpenView** 方法。</span><span class="sxs-lookup"><span data-stu-id="96e17-133">To run the **OpenView** action in a Visual Basic for Applications (VBA) module, use the **OpenView** method of the **DoCmd** object.</span></span>
