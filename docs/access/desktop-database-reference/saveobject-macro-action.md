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
ms.openlocfilehash: 253067d61a496073692ea4e462b9b0a67f0e26cd
ms.sourcegitcommit: 45feafb3b55de0402dddf5548c0c1c43a0eabafd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026293"
---
# <a name="saveobject-macro-action"></a><span data-ttu-id="ff02f-102">SaveObject 宏操作</span><span class="sxs-lookup"><span data-stu-id="ff02f-102">SaveObject macro action</span></span>

<span data-ttu-id="ff02f-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ff02f-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ff02f-p101">可以使用 **SaveObject** 操作保存指定的 Microsoft Access 对象，如果未指定任何对象，则可以保存活动对象。在某些情况下，还可以用新名称保存活动对象（这与 **"快速访问工具栏"** 上的 **"另存为"** 命令的作用相同）。</span><span class="sxs-lookup"><span data-stu-id="ff02f-p101">You can use the **SaveObject** action to save either a specified Access object or the active object if none is specified. You can also save the active object with a new name in some cases (this functions the same as the **Save As** command on the **Quick Access Toolbar**).</span></span>

> [!NOTE]
> <span data-ttu-id="ff02f-106">[!注释] 如果数据库不受信任，将不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="ff02f-106">This action will not be allowed if the database is not trusted.</span></span> 

## <a name="setting"></a><span data-ttu-id="ff02f-107">设置</span><span class="sxs-lookup"><span data-stu-id="ff02f-107">Setting</span></span>

<span data-ttu-id="ff02f-108">**SaveObject** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="ff02f-108">The **SaveObject** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ff02f-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="ff02f-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="ff02f-110">说明</span><span class="sxs-lookup"><span data-stu-id="ff02f-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff02f-111"><strong>对象类型</strong></span><span class="sxs-lookup"><span data-stu-id="ff02f-111"><strong>Object Type</strong></span></span></p></td>
<td><p><span data-ttu-id="ff02f-112">要保存的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="ff02f-112">The type of object you want to save.</span></span> <span data-ttu-id="ff02f-113">单击<strong>表</strong>、<strong>查询</strong>、<strong>窗体</strong>、<strong>报表</strong>、<strong>宏</strong>、<strong>模块</strong>、<strong>数据访问页</strong>、<strong>服务器视图</strong>、<strong>图表</strong>、<strong>存储过程</strong>中，或<strong>对象类型中的<strong>函数</strong></strong>框在宏生成器窗格的<strong>操作参数</strong>部分。</span><span class="sxs-lookup"><span data-stu-id="ff02f-113">Click <strong>Table</strong>, <strong>Query</strong>, <strong>Form</strong>, <strong>Report</strong>, <strong>Macro</strong>, <strong>Module</strong>, <strong>Data Access Page</strong>, <strong>Server View</strong>, <strong>Diagram</strong>, <strong>Stored Procedure</strong>, or <strong>Function</strong> in the <strong>Object Type</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span> <span data-ttu-id="ff02f-114">若要选择活动对象，请将此参数留空。</span><span class="sxs-lookup"><span data-stu-id="ff02f-114">To select the active object, leave this argument blank.</span></span> <span data-ttu-id="ff02f-115">如果此参数中选择的对象类型，您必须在<strong>对象名称</strong>参数中选择现有对象的名称。</span><span class="sxs-lookup"><span data-stu-id="ff02f-115">If you select an object type in this argument, you must select an existing object's name in the <strong>Object Name</strong> argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff02f-116"><strong>对象名称</strong></span><span class="sxs-lookup"><span data-stu-id="ff02f-116"><strong>Object Name</strong></span></span></p></td>
<td><p><span data-ttu-id="ff02f-117">要保存的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="ff02f-117">The name of the object to be saved.</span></span> <span data-ttu-id="ff02f-118"><strong>对象名称</strong>框中显示<strong>对象类型</strong>参数所选类型的数据库中的所有对象。</span><span class="sxs-lookup"><span data-stu-id="ff02f-118">The <strong>Object Name</strong> box shows all objects in the database of the type selected by the <strong>Object Type</strong> argument.</span></span> <span data-ttu-id="ff02f-119">如果将<strong>对象类型</strong>参数留空，您可以将此参数留空保存活动对象，或者，在某些情况下，输入此参数，以保存具有此名称的活动对象中的新名称。</span><span class="sxs-lookup"><span data-stu-id="ff02f-119">If you leave the <strong>Object Type</strong> argument blank, you can leave this argument blank to save the active object, or, in some cases, enter a new name in this argument to save the active object with this name.</span></span> <span data-ttu-id="ff02f-120">如果输入新名称，该名称必须遵循 Microsoft Access 对象的标准命名约定。</span><span class="sxs-lookup"><span data-stu-id="ff02f-120">If you enter a new name, the name must follow the standard naming conventions for Microsoft Access objects.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="ff02f-121">说明</span><span class="sxs-lookup"><span data-stu-id="ff02f-121">Remarks</span></span>

<span data-ttu-id="ff02f-122">**SaveObject**操作适用于所有的数据库对象的用户可以直接打开和保存。</span><span class="sxs-lookup"><span data-stu-id="ff02f-122">The **SaveObject** action works on all database objects that the user can explicitly open and save.</span></span> <span data-ttu-id="ff02f-123">指定的对象必须打开**SaveObject**操作已在对象上的任何效果。</span><span class="sxs-lookup"><span data-stu-id="ff02f-123">The specified object must be open for the **SaveObject** action to have any effect on the object.</span></span> <span data-ttu-id="ff02f-124">此操作具有相同的效果选择一个对象，然后通过单击**快速访问工具栏**上的**保存**保存它。</span><span class="sxs-lookup"><span data-stu-id="ff02f-124">This action has the same effect as selecting an object and then saving it by clicking **Save** on the **Quick Access Toolbar**.</span></span> 

<span data-ttu-id="ff02f-125">**对象类型**参数留空，并在**对象名称**参数中输入新名称具有相同的效果单击**另存为**上的**快速访问工具栏**中，并输入活动对象的新名称。</span><span class="sxs-lookup"><span data-stu-id="ff02f-125">Leaving the **Object Type** argument blank and entering a new name in the **Object Name** argument has the same effect as clicking **Save As** on the **Quick Access Toolbar**, and entering a new name for the active object.</span></span> <span data-ttu-id="ff02f-126">使用**SaveObject**操作，可以指定对象，以保存并通过宏执行**另存为**命令。</span><span class="sxs-lookup"><span data-stu-id="ff02f-126">Using the **SaveObject** action enables you to specify an object to save and to perform a **Save As** command from a macro.</span></span>

> [!NOTE]
> <span data-ttu-id="ff02f-127">[!注释] 不能使用 **SaveObject** 操作用新名称保存以下任何一项：</span><span class="sxs-lookup"><span data-stu-id="ff02f-127">You can't use the **SaveObject** action to save any of the following with a new name:</span></span>
> - <span data-ttu-id="ff02f-128">窗体视图或数据表视图中的窗体</span><span class="sxs-lookup"><span data-stu-id="ff02f-128">A form in Form view or Datasheet view</span></span>
> - <span data-ttu-id="ff02f-129">打印预览中的报表</span><span class="sxs-lookup"><span data-stu-id="ff02f-129">A report in Print Preview</span></span>
> - <span data-ttu-id="ff02f-130">模块</span><span class="sxs-lookup"><span data-stu-id="ff02f-130">A module</span></span>
> - <span data-ttu-id="ff02f-131">数据表视图或打印预览中的服务器视图</span><span class="sxs-lookup"><span data-stu-id="ff02f-131">A server view in Datasheet view or Print Preview</span></span>
> - <span data-ttu-id="ff02f-132">页面视图中的数据访问页</span><span class="sxs-lookup"><span data-stu-id="ff02f-132">A data access page in Page view</span></span>
> - <span data-ttu-id="ff02f-133">数据表视图或打印预览中的表</span><span class="sxs-lookup"><span data-stu-id="ff02f-133">A table in Datasheet view or Print Preview</span></span>
> - <span data-ttu-id="ff02f-134">数据表视图或打印预览中的查询</span><span class="sxs-lookup"><span data-stu-id="ff02f-134">A query in Datasheet view or Print Preview</span></span>
> - <span data-ttu-id="ff02f-135">数据表视图或打印预览中的存储的过程</span><span class="sxs-lookup"><span data-stu-id="ff02f-135">A stored procedure in Datasheet view or Print Preview</span></span>

<span data-ttu-id="ff02f-136">无论是在当前数据库中运行的宏中执行，还是在类库数据库中运行的宏中执行， **SaveObject** 操作总是将指定对象或活动对象保存在创建该对象的数据库中。</span><span class="sxs-lookup"><span data-stu-id="ff02f-136">The **SaveObject** action, whether it's carried out in a macro run in the current database or in a library database, always saves the specified object or the active object in the database in which the object was created.</span></span>

<span data-ttu-id="ff02f-137">如果活动对象保存使用新名称，但的名称就是此类型的现有对象的名称相同，将会出现一个对话框，询问您是否要覆盖现有对象。</span><span class="sxs-lookup"><span data-stu-id="ff02f-137">If you save the active object with a new name, but the name is the same as the name of an existing object of this type, a dialog box asks if you want to overwrite the existing object.</span></span> <span data-ttu-id="ff02f-138">如果已将**SetWarnings**操作**警告**参数设置为**No**，不显示对话框，并自动覆盖旧对象。</span><span class="sxs-lookup"><span data-stu-id="ff02f-138">If you've set the **Warnings On** argument of the **SetWarnings** action to **No**, the dialog box isn't displayed and the old object is automatically overwritten.</span></span>

<span data-ttu-id="ff02f-139">若要在 Visual Basic for Applications (VBA) 模块中运行 **SaveObject** 操作，请使用 **DoCmd** 对象的 **Save** 方法。</span><span class="sxs-lookup"><span data-stu-id="ff02f-139">To run the **SaveObject** action in a Visual Basic for Applications (VBA) module, use the **Save** method of the **DoCmd** object.</span></span>

