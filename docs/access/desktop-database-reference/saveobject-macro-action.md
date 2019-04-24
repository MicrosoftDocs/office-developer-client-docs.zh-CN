---
title: SaveObject 宏操作
TOCTitle: SaveObject macro action
ms:assetid: 85716dfc-f76f-ca47-cc40-f8f88162f85a
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196789(v=office.15)
ms:contentKeyID: 48546060
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm116962
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: cf6fe02616134f864a0e07092951ab9cf49aadbc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308930"
---
# <a name="saveobject-macro-action"></a><span data-ttu-id="72c84-102">SaveObject 宏操作</span><span class="sxs-lookup"><span data-stu-id="72c84-102">SaveObject macro action</span></span>

<span data-ttu-id="72c84-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="72c84-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="72c84-p101">可以使用 **SaveObject** 操作保存指定的 Microsoft Access 对象，如果未指定任何对象，则可以保存活动对象。在某些情况下，还可以用新名称保存活动对象（这与 **“快速访问工具栏”** 上的 **“另存为”** 命令的作用相同）。</span><span class="sxs-lookup"><span data-stu-id="72c84-p101">You can use the **SaveObject** action to save either a specified Access object or the active object if none is specified. You can also save the active object with a new name in some cases (this functions the same as the **Save As** command on the **Quick Access Toolbar**).</span></span>

> [!NOTE]
> <span data-ttu-id="72c84-106">如果数据库不受信任，则不允许执行此操作。</span><span class="sxs-lookup"><span data-stu-id="72c84-106">This action will not be allowed if the database is not trusted.</span></span> 

## <a name="setting"></a><span data-ttu-id="72c84-107">设置</span><span class="sxs-lookup"><span data-stu-id="72c84-107">Setting</span></span>

<span data-ttu-id="72c84-108">**SaveObject** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="72c84-108">The **SaveObject** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="72c84-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="72c84-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="72c84-110">说明</span><span class="sxs-lookup"><span data-stu-id="72c84-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="72c84-111"><strong>对象类型</strong></span><span class="sxs-lookup"><span data-stu-id="72c84-111"><strong>Object Type</strong></span></span></p></td>
<td><p><span data-ttu-id="72c84-p102">要保存的对象的类型。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“对象类型”</strong>框中单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“报表”</strong>、<strong>“宏”</strong>、<strong>“模块”</strong>、<strong>“数据访问页”</strong>、<strong>“服务器视图”</strong>、<strong>“图表”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。要选择活动对象，请将此参数留空。如果在此参数中选择了一种对象类型，则必须在“对象名称”<strong></strong>参数中选择现有对象的名称。</span><span class="sxs-lookup"><span data-stu-id="72c84-p102">The type of object you want to save. Click <strong>Table</strong>, <strong>Query</strong>, <strong>Form</strong>, <strong>Report</strong>, <strong>Macro</strong>, <strong>Module</strong>, <strong>Data Access Page</strong>, <strong>Server View</strong>, <strong>Diagram</strong>, <strong>Stored Procedure</strong>, or <strong>Function</strong> in the <strong>Object Type</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. To select the active object, leave this argument blank. If you select an object type in this argument, you must select an existing object's name in the <strong>Object Name</strong> argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="72c84-116"><strong>对象名称</strong></span><span class="sxs-lookup"><span data-stu-id="72c84-116"><strong>Object Name</strong></span></span></p></td>
<td><p><span data-ttu-id="72c84-117">要保存的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="72c84-117">The name of the object to be saved.</span></span> <span data-ttu-id="72c84-118"><strong>“对象名称”</strong>框会显示数据库中属于“对象类型”<strong></strong>参数所选的类型的所有对象。</span><span class="sxs-lookup"><span data-stu-id="72c84-118">The <strong>Object Name</strong> box shows all objects in the database of the type selected by the <strong>Object Type</strong> argument.</span></span> <span data-ttu-id="72c84-119">如果将“对象类型”<strong></strong>参数留空，则可将此参数留空以保存活动对象，在某些情况下，也可以在此参数中输入一个新名称，用此新名称来保存活动对象。</span><span class="sxs-lookup"><span data-stu-id="72c84-119">If you leave the <strong>Object Type</strong> argument blank, you can leave this argument blank to save the active object, or, in some cases, enter a new name in this argument to save the active object with this name.</span></span> <span data-ttu-id="72c84-120">如果输入新名称，该名称必须遵循 Microsoft Access 对象的标准命名约定。</span><span class="sxs-lookup"><span data-stu-id="72c84-120">If you enter a new name, the name must follow the standard naming conventions for Microsoft Access objects.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="72c84-121">注解</span><span class="sxs-lookup"><span data-stu-id="72c84-121">Remarks</span></span>

<span data-ttu-id="72c84-122">**SaveObject** 操作可用于用户能够显式地打开和保存的所有数据库对象。</span><span class="sxs-lookup"><span data-stu-id="72c84-122">The **SaveObject** action works on all database objects that the user can explicitly open and save.</span></span> <span data-ttu-id="72c84-123">指定的对象必须处于打开状态，**SaveObject** 操作才会对其有作用。</span><span class="sxs-lookup"><span data-stu-id="72c84-123">The specified object must be open for the **SaveObject** action to have any effect on the object.</span></span> <span data-ttu-id="72c84-124">此操作等效于选择一个对象，然后通过单击 **“快速访问工具栏”** 上的 **“保存”** 来保存该对象。</span><span class="sxs-lookup"><span data-stu-id="72c84-124">This action has the same effect as selecting an object and then saving it by clicking **Save** on the **Quick Access Toolbar**.</span></span> 

<span data-ttu-id="72c84-125">将“对象类型”\*\*\*\* 参数留空并在“对象名称”\*\*\*\* 参数中输入一个新名称等效于以下操作：单击 **“快速访问工具栏”** 上的 **“另存为”**，然后为活动对象输入一个新名称。</span><span class="sxs-lookup"><span data-stu-id="72c84-125">Leaving the **Object Type** argument blank and entering a new name in the **Object Name** argument has the same effect as clicking **Save As** on the **Quick Access Toolbar**, and entering a new name for the active object.</span></span> <span data-ttu-id="72c84-126">通过使用 **SaveObject** 操作，您可以指定要保存的对象以及执行宏中的 **“另存为”** 命令。</span><span class="sxs-lookup"><span data-stu-id="72c84-126">Using the **SaveObject** action enables you to specify an object to save and to perform a **Save As** command from a macro.</span></span>

> [!NOTE]
> <span data-ttu-id="72c84-127">不能使用 **SaveObject** 操作用新名称保存以下任何一项：</span><span class="sxs-lookup"><span data-stu-id="72c84-127">You can't use the **SaveObject** action to save any of the following with a new name:</span></span>
> - <span data-ttu-id="72c84-128">"窗体" 视图或 "数据表" 视图中的窗体</span><span class="sxs-lookup"><span data-stu-id="72c84-128">A form in Form view or Datasheet view</span></span>
> - <span data-ttu-id="72c84-129">打印预览中的报表</span><span class="sxs-lookup"><span data-stu-id="72c84-129">A report in Print Preview</span></span>
> - <span data-ttu-id="72c84-130">一个模块</span><span class="sxs-lookup"><span data-stu-id="72c84-130">A module</span></span>
> - <span data-ttu-id="72c84-131">"数据表" 视图或 "打印预览" 中的服务器视图</span><span class="sxs-lookup"><span data-stu-id="72c84-131">A server view in Datasheet view or Print Preview</span></span>
> - <span data-ttu-id="72c84-132">页面视图中的数据访问页</span><span class="sxs-lookup"><span data-stu-id="72c84-132">A data access page in Page view</span></span>
> - <span data-ttu-id="72c84-133">数据表视图或打印预览中的表</span><span class="sxs-lookup"><span data-stu-id="72c84-133">A table in Datasheet view or Print Preview</span></span>
> - <span data-ttu-id="72c84-134">数据表视图或打印预览中的查询</span><span class="sxs-lookup"><span data-stu-id="72c84-134">A query in Datasheet view or Print Preview</span></span>
> - <span data-ttu-id="72c84-135">数据表视图或打印预览中的存储过程</span><span class="sxs-lookup"><span data-stu-id="72c84-135">A stored procedure in Datasheet view or Print Preview</span></span>

<span data-ttu-id="72c84-136">无论是在当前数据库中运行的宏中执行，还是在类库数据库中运行的宏中执行，**SaveObject** 操作总是将指定对象或活动对象保存在创建该对象的数据库中。</span><span class="sxs-lookup"><span data-stu-id="72c84-136">The **SaveObject** action, whether it's carried out in a macro run in the current database or in a library database, always saves the specified object or the active object in the database in which the object was created.</span></span>

<span data-ttu-id="72c84-p106">If you save the active object with a new name, but the name is the same as the name of an existing object of this type, a dialog box asks if you want to overwrite the existing object. If you've set the **Warnings On** argument of the **SetWarnings** action to **No**, the dialog box isn't displayed and the old object is automatically overwritten.</span><span class="sxs-lookup"><span data-stu-id="72c84-p106">If you save the active object with a new name, but the name is the same as the name of an existing object of this type, a dialog box asks if you want to overwrite the existing object. If you've set the **Warnings On** argument of the **SetWarnings** action to **No**, the dialog box isn't displayed and the old object is automatically overwritten.</span></span>

<span data-ttu-id="72c84-139">若要在 Visual Basic for Applications (VBA) 模块中运行 **SaveObject** 操作，请使用 **DoCmd** 对象的 **Save** 方法。</span><span class="sxs-lookup"><span data-stu-id="72c84-139">To run the **SaveObject** action in a Visual Basic for Applications (VBA) module, use the **Save** method of the **DoCmd** object.</span></span>

