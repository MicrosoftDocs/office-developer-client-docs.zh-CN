---
title: OpenStoredProcedure 宏操作
TOCTitle: OpenStoredProcedure Macro Action
ms:assetid: b14dbb82-7c8a-0ace-e251-46599551a490
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822003(v=office.15)
ms:contentKeyID: 48547142
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm187628
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 8b30049348171fcd65bbc2edd25c18256a12c955
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466880"
---
# <a name="openstoredprocedure-macro-action"></a><span data-ttu-id="90b40-102">OpenStoredProcedure 宏操作</span><span class="sxs-lookup"><span data-stu-id="90b40-102">OpenStoredProcedure Macro Action</span></span>


<span data-ttu-id="90b40-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="90b40-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="90b40-p101">在 Microsoft Access 项目中，可以使用 **OpenStoredProcedure** 操作在数据表视图、存储过程设计视图或打印预览中打开存储过程。如果在数据表视图中打开命名的存储过程，此操作将运行该存储过程。您可以为存储过程选择数据输入模式，以及限制存储过程显示的记录。</span><span class="sxs-lookup"><span data-stu-id="90b40-p101">In an Access project, you can use the **OpenStoredProcedure** action to open a stored procedure in Datasheet view, stored procedure Design view, or Print Preview. This action runs the named stored procedure when opened in Datasheet view. You can select the data entry mode for the stored procedure and restrict the records that the stored procedure displays.</span></span>


> [!NOTE]
> <P><span data-ttu-id="90b40-p102">[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</span><span class="sxs-lookup"><span data-stu-id="90b40-p102">This action will not be allowed if the database is not trusted. For more information about enabling macros, see the links in the See Also section of this article.</span></span></P>



## <a name="setting"></a><span data-ttu-id="90b40-109">设置</span><span class="sxs-lookup"><span data-stu-id="90b40-109">Setting</span></span>

<span data-ttu-id="90b40-110">**OpenStoredProcedure** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="90b40-110">The **OpenStoredProcedure** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="90b40-111">操作参数</span><span class="sxs-lookup"><span data-stu-id="90b40-111">Action argument</span></span></p></th>
<th><p><span data-ttu-id="90b40-112">说明</span><span class="sxs-lookup"><span data-stu-id="90b40-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="90b40-113"><strong>过程名称</strong></span><span class="sxs-lookup"><span data-stu-id="90b40-113"><strong>Procedure Name</strong></span></span></p></td>
<td><p><span data-ttu-id="90b40-114">要打开的存储过程的名称。</span><span class="sxs-lookup"><span data-stu-id="90b40-114">The name of the stored procedure to open.</span></span> <span data-ttu-id="90b40-115">在<strong>操作参数</strong>部分的宏生成器窗格<strong>过程名称框</strong>中显示当前数据库中的所有存储的过程。</span><span class="sxs-lookup"><span data-stu-id="90b40-115">The <strong>Procedure Name box</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane shows all stored procedures in the current database.</span></span> <span data-ttu-id="90b40-116">这是必需参数。</span><span class="sxs-lookup"><span data-stu-id="90b40-116">This is a required argument.</span></span> <span data-ttu-id="90b40-117">如果在类库数据库中运行包含 <strong>OpenStoredProcedure</strong> 操作的宏，Microsoft Access 将先在该类库数据库中查找具有此名称的存储过程，然后再在当前数据库中查找。</span><span class="sxs-lookup"><span data-stu-id="90b40-117">If you run a macro containing the <strong>OpenStoredProcedure</strong> action in a library database, Microsoft Access first looks for the stored procedure with this name first in the library database, and then in the current database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="90b40-118"><strong>View</strong></span><span class="sxs-lookup"><span data-stu-id="90b40-118"><strong>View</strong></span></span></p></td>
<td><p><span data-ttu-id="90b40-p104">打开存储过程时将使用的视图。请在<strong>“视图”</strong>框中单击<strong>“数据表”</strong>、<strong>“设计”</strong>、<strong>“打印预览”</strong>、<strong>“数据透视表”</strong>或<strong>“数据透视图”</strong>。默认值为<strong>“数据表”</strong>。</span><span class="sxs-lookup"><span data-stu-id="90b40-p104">The view in which the stored procedure will open. Click <strong>Datasheet</strong>, <strong>Design</strong>, <strong>Print Preview</strong>, <strong>PivotTable</strong>, or <strong>PivotChart</strong> in the <strong>View</strong> box. The default is <strong>Datasheet</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="90b40-122"><strong>Data Mode</strong></span><span class="sxs-lookup"><span data-stu-id="90b40-122"><strong>Data Mode</strong></span></span></p></td>
<td><p><span data-ttu-id="90b40-p105">存储过程的数据输入模式。此参数仅适用于在数据表视图中打开的存储过程。请单击<strong>“添加”</strong>（用户可添加新记录，但不能查看或编辑现有记录）、<strong>“编辑”</strong>（用户可查看或编辑现有记录以及添加新记录）或<strong>“只读”</strong>（用户只能查看记录）。默认值为<strong>“编辑”</strong>。</span><span class="sxs-lookup"><span data-stu-id="90b40-p105">The data entry mode for the stored procedure. This applies only to stored procedures opened in Datasheet view. Click <strong>Add</strong> (the user can add new records but can't view or edit existing records), <strong>Edit</strong> (the user can view or edit existing records and add new records), or <strong>Read Only</strong> (the user can only view records). The default is <strong>Edit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="90b40-127">说明</span><span class="sxs-lookup"><span data-stu-id="90b40-127">Remarks</span></span>

<span data-ttu-id="90b40-128">此操作类似于在导航窗格中双击存储过程，或者在导航窗格中右键单击存储过程，然后选择所需的命令。</span><span class="sxs-lookup"><span data-stu-id="90b40-128">This action is similar to double-clicking the stored procedure in the Navigation Pane, or right-clicking the stored procedure in the Navigation Pane and selecting the command you want.</span></span>

<span data-ttu-id="90b40-129">存储的过程处于打开状态时切换到设计视图中删除存储过程的**数据模式**参数设置。</span><span class="sxs-lookup"><span data-stu-id="90b40-129">Switching to Design view while the stored procedure is open removes the **Data Mode** argument setting for the stored procedure.</span></span> <span data-ttu-id="90b40-130">此设置不起作用，即使用户返回到数据表视图。</span><span class="sxs-lookup"><span data-stu-id="90b40-130">This setting is not in effect, even if the user returns to Datasheet view.</span></span>


> [!TIP]
> <P></P>
> <UL>
> <LI>
> <P><span data-ttu-id="90b40-131">可以将存储的过程从导航窗格拖动到宏操作行中。</span><span class="sxs-lookup"><span data-stu-id="90b40-131">You can drag a stored procedure from the Navigation Pane to a macro action row.</span></span> <span data-ttu-id="90b40-132">这会自动创建的数据表视图中打开的存储的过程<STRONG>OpenStoredProcedure</STRONG>操作。</span><span class="sxs-lookup"><span data-stu-id="90b40-132">This automatically creates an <STRONG>OpenStoredProcedure</STRONG> action that opens the stored procedure in Datasheet view.</span></span></P>
> <LI>
> <P><span data-ttu-id="90b40-133">
> 						通常，当运行存储过程时，会显示一些系统消息（指明运行的是存储过程并显示将受影响的记录数），如果不想显示这些消息，可以使用 <STRONG>SetWarning</STRONG> 操作来禁止其显示。
</span><span class="sxs-lookup"><span data-stu-id="90b40-133">If you do not want to display the system messages that normally appear when a stored procedure is run (indicating it is a stored procedure and showing how many records will be affected), you can use the <STRONG>SetWarning</STRONG> action to suppress the display of these messages.</span></span></P></LI></UL>
<P></P>



<span data-ttu-id="90b40-134">要在 Visual Basic for Applications (VBA) 模块中运行 **OpenStoredProcedure** 操作，请使用 **DoCmd** 对象的 **OpenStoredProcedure** 方法。</span><span class="sxs-lookup"><span data-stu-id="90b40-134">To run the **OpenStoredProcedure** action in a Visual Basic for Applications (VBA) module, use the **OpenStoredProcedure** method of the **DoCmd** object.</span></span>

