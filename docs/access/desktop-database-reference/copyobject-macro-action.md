---
title: CopyObject 宏操作
TOCTitle: CopyObject Macro Action
ms:assetid: 746f61df-d5db-284a-0897-75820c2be11f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195876(v=office.15)
ms:contentKeyID: 48545661
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm12836
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 60c0204bd374feaa950d3158873f68127debaf0f
ms.sourcegitcommit: 801b1b54786f7b0e5b0d35466e7ae8d1e840b26f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25862546"
---
# <a name="copyobject-macro-action"></a><span data-ttu-id="5fe8d-102">CopyObject 宏操作</span><span class="sxs-lookup"><span data-stu-id="5fe8d-102">CopyObject Macro Action</span></span>


<span data-ttu-id="5fe8d-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="5fe8d-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="5fe8d-p101">可以使用 **CopyObject** 操作将指定的数据库对象复制到另一个数据库中，或使用新名称将其复制到同一个数据库或 Microsoft Access 项目中。例如，您可以将现有对象复制或备份到另一个数据库中，也可以快速创建略有更改的类似对象。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-p101">You can use the **CopyObject** action to copy the specified database object to a different Access database or to the same database or Access project under a new name. For example, you can copy or back up an existing object in another database or quickly create a similar object with a few changes.</span></span>


> [!NOTE]
> <span data-ttu-id="5fe8d-p102">[!注释] 如果数据库不受信任，将不允许此操作。有关启用宏的详细信息，请参阅本文 See Also 一节中的链接。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-p102">This action will not be allowed if the database is not trusted. For more information about enabling macros, see the links in the See Also section of this article.</span></span>



## <a name="setting"></a><span data-ttu-id="5fe8d-108">设置</span><span class="sxs-lookup"><span data-stu-id="5fe8d-108">Setting</span></span>

<span data-ttu-id="5fe8d-109">**CopyObject** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-109">The **CopyObject** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5fe8d-110">操作参数</span><span class="sxs-lookup"><span data-stu-id="5fe8d-110">Action argument</span></span></p></th>
<th><p><span data-ttu-id="5fe8d-111">说明</span><span class="sxs-lookup"><span data-stu-id="5fe8d-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fe8d-112"><strong>目标数据库</strong></span><span class="sxs-lookup"><span data-stu-id="5fe8d-112"><strong>Destination Database</strong></span></span></p></td>
<td><p><span data-ttu-id="5fe8d-p103">目标数据库的有效路径和文件名。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“目标数据库”</strong>框中输入路径和文件名。如果要选择当前数据库，请将此参数留空。 

</span><span class="sxs-lookup"><span data-stu-id="5fe8d-p103">A valid path and file name for the destination database. Enter the path and file name in the <strong>Destination Database</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. Leave this argument blank if you want to select the current database.</span></span></p>

> [!NOTE]
> <span data-ttu-id="5fe8d-p104">此参数仅在 Access 数据库环境中可用。在 Access 项目环境 (.adp) 中使用此操作时，“目标数据库”参数必须为空。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-p104">This argument is only available in the Access database environment. When using this action in an Access project environment (.adp), the Destination Database argument must be blank.</span></span>


<p><span data-ttu-id="5fe8d-118">如果在类库数据库中运行包含 <strong>CopyObject</strong> 操作的宏并将此参数留空，Microsoft Office Access 2007 就会将该对象复制到类库数据库中。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-118">If you run a macro containing the <strong>CopyObject</strong> action in a library database and leave this argument blank, Microsoft Office Access 2007 will copy the object into the library database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fe8d-119"><strong>新名称</strong></span><span class="sxs-lookup"><span data-stu-id="5fe8d-119"><strong>New Name</strong></span></span></p></td>
<td><p><span data-ttu-id="5fe8d-p105">对象的新名称。在将对象复制到另一个数据库中时，将此参数留空可使名称保持不变。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-p105">A new name for the object. When copying to a different database, leave this argument blank to keep the same name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fe8d-122"><strong>源对象类型</strong></span><span class="sxs-lookup"><span data-stu-id="5fe8d-122"><strong>Source Object Type</strong></span></span></p></td>
<td><p><span data-ttu-id="5fe8d-p106">要复制的对象类型。请单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“报表”</strong>、<strong>“宏”</strong>、<strong>“模块”</strong>、<strong>“数据访问页”</strong>、<strong>“服务器视图”</strong>、<strong>“图表”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。要复制在导航窗格中选择的对象，请将此参数留空。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-p106">The object type you want to copy. Click <strong>Table</strong>, <strong>Query</strong>, <strong>Form</strong>, <strong>Report</strong>, <strong>Macro</strong>, <strong>Module</strong>, <strong>Data Access Page</strong>, <strong>Server View</strong>, <strong>Diagram</strong>, <strong>Stored Procedure</strong>, or <strong>Function</strong>. To copy the object selected in the Navigation Pane, leave this argument blank.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fe8d-126"><strong>源对象名称</strong></span><span class="sxs-lookup"><span data-stu-id="5fe8d-126"><strong>Source Object Name</strong></span></span></p></td>
<td><p><span data-ttu-id="5fe8d-127">要复制的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-127">The name of the object to be copied.</span></span> <span data-ttu-id="5fe8d-128"><strong>源对象名称</strong>框中显示的<strong>源对象类型</strong>参数所选类型的数据库中的所有对象。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-128">The <strong>Source Object Name</strong> box shows all objects in the database of the type selected by the <strong>Source Object Type</strong> argument.</span></span> <span data-ttu-id="5fe8d-129">在<strong>源对象名称</strong>框中，单击要复制的对象。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-129">In the <strong>Source Object Name</strong> box, click the object to copy.</span></span> <span data-ttu-id="5fe8d-130">如果将<strong>源对象类型</strong>参数留空，还应将此参数留空。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-130">If you leave the <strong>Source Object Type</strong> argument blank, leave this argument blank also.</span></span> <span data-ttu-id="5fe8d-131">如果在类库数据库中运行包含 <strong>CopyObject</strong> 操作的宏，Access 将先在该类库数据库中查找具有此名称的对象，然后再在当前数据库中查找。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-131">If you run a macro containing the <strong>CopyObject</strong> action in a library database, Access first looks for the object with this name in the library database, and then in the current database.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="5fe8d-132">说明</span><span class="sxs-lookup"><span data-stu-id="5fe8d-132">Remarks</span></span>

<span data-ttu-id="5fe8d-133">您必须输入的一个或两个**目标数据库**和**新名称**的参数，此操作的值。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-133">You must enter a value for either one or both of the **Destination Database** and **New Name** arguments for this action.</span></span>

<span data-ttu-id="5fe8d-134">如果将**源对象类型**和**源对象名称**参数留空，Access 将复制的导航窗格中选择的对象。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-134">If you leave the **Source Object Type** and **Source Object Name** arguments blank, Access copies the object selected in the Navigation Pane.</span></span> <span data-ttu-id="5fe8d-135">若要在导航窗格中选择一个对象，可以在导航窗格中参数设置为**是**使用**SelectObject**操作。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-135">To select an object in the Navigation Pane, you can use the **SelectObject** action with the In Navigation Pane argument set to **Yes**.</span></span>

<span data-ttu-id="5fe8d-136">**CopyObject** 操作类似于手动执行下列步骤：</span><span class="sxs-lookup"><span data-stu-id="5fe8d-136">The **CopyObject** action is similar to performing the following steps manually:</span></span>

1.  <span data-ttu-id="5fe8d-137">在导航窗格中选择对象。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-137">Select an object in the Navigation Pane.</span></span>

2.  <span data-ttu-id="5fe8d-138">在 Home 选项卡上，在 Clipboard 组中，单击 Copy。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-138">On the Home tab, in the Clipboard group, click Copy.</span></span>

3.  <span data-ttu-id="5fe8d-p109">在同一个选项卡上，单击 **"粘贴"**。此时将出现 **"粘贴为"** 对话框，以便您为对象指定一个新名称。 **CopyObject** 操作会自动执行所有这些步骤。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-p109">On the same tab, click **Paste**.The **Paste As** dialog box appears so that you can give the object a new name. The **CopyObject** action performs all of these steps automatically.</span></span>


> [!NOTE]
> <span data-ttu-id="5fe8d-141">[!注释] 复制数据访问页时， **CopyObject** 操作将仅复制相关 .htm 文件的链接，而不复制该文件本身。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-141">When copying data access pages, the **CopyObject** action copies only the link to the associated .htm file, not the file itself.</span></span>



<span data-ttu-id="5fe8d-p110">在宏运行 **CopyObject** 操作之前，目标数据库的路径和文件名必须已经存在。如果不存在，Access 将显示错误消息。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-p110">The path and file name of the destination database must exist before the macro runs the **CopyObject** action. If they don't exist, Access displays an error message.</span></span>

<span data-ttu-id="5fe8d-144">要在 Visual Basic for Applications (VBA) 模块中运行 **CopyObject** 操作，请使用 **DoCmd** 对象的 **CopyObject** 方法。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-144">To run the **CopyObject** action in a Visual Basic for Applications (VBA) module, use the **CopyObject** method of the **DoCmd** object.</span></span>

<span data-ttu-id="5fe8d-p111">也可以通过单击 **"文件"** 选项卡，然后单击 **"另存为"**，手动复制在导航窗格中选择的对象或当前打开的对象。此命令将仅在当前数据库中创建对象的副本。在 **"另存为"** 对话框中，输入副本的名称，然后选择要将该对象另存为哪种对象类型。如果原始对象已经保存，而且您使用新名称将其保存在当前数据库中，则原来的版本仍以其旧名称存在。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-p111">You can also manually copy an object selected in the Navigation Pane, or an object that is currently open, by clicking the **File** tab and then clicking **Save As**. This command will make a copy of the object in the current database only. In the **Save As** dialog box, enter the name for the copy, and choose what type of object you want to save it as. If the original object has already been saved and you save it in the current database with a new name, the original version still exists with its old name.</span></span>

<span data-ttu-id="5fe8d-149">要将对象手动复制到另一个 Access 数据库中，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="5fe8d-149">To manually copy an object to a different Access database:</span></span>

1.  <span data-ttu-id="5fe8d-150">在 **"外部数据"** 选项卡上的 **"导出"** 组中，单击 **"其他"**，然后单击 **"Access 数据库"**。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-150">On the **External Data** tab, in the **Export** group, click **More** and then click **Access Database**.</span></span>

2.  <span data-ttu-id="5fe8d-151">在 **"导出 - Access 数据库"** 对话框中，输入目标数据库的文件名。-或者-单击 **"浏览"** 以显示 **"保存文件"** 对话框，找到目标数据库，然后单击 **"保存"**。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-151">In the **Export - Access Database** dialog box, enter the file name of the destination database.-or-Click **Browse** to display the **File Save** dialog box, locate the destination database, and then click **Save**.</span></span>

3.  <span data-ttu-id="5fe8d-p112">在 **"导出 - Access 数据库"** 对话框中，单击 **"确定"**。此时将出现 **"导出"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-p112">In the **Export - Access Database** dialog box, click **OK**. The **Export** dialog box appears.</span></span>

4.  <span data-ttu-id="5fe8d-p113">在 **"导出"** 对话框中，输入目标数据库中的对象的名称。选择任何适用的选项，例如表的 **"导出定义和数据"** 或 **"只导出定义"**。完成后，请单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="5fe8d-p113">In the **Export** dialog box, enter a name for the object in the destination database. Choose any applicable options, such as **Export Definition and Data** or **Definition Only** for tables. When you are finished, click **OK**.</span></span>

