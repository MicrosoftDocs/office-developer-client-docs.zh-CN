---
title: RenameObject 宏操作
TOCTitle: RenameObject macro action
ms:assetid: fee04eb0-23c0-5d57-b903-e1ae54f2d25e
ms:mtpsurl: https://msdn.microsoft.com/library/Ff837293(v=office.15)
ms:contentKeyID: 48548948
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm165893
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: ce16b86ea06e041d490d0c68917daf18bd80dbb6
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28698384"
---
# <a name="renameobject-macro-action"></a><span data-ttu-id="e73fe-102">RenameObject 宏操作</span><span class="sxs-lookup"><span data-stu-id="e73fe-102">RenameObject macro action</span></span>

<span data-ttu-id="e73fe-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e73fe-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e73fe-104">可以使用 **RenameObject** 操作重命名指定的数据库对象。</span><span class="sxs-lookup"><span data-stu-id="e73fe-104">You can use the **RenameObject** action to rename a specified database object.</span></span>

> [!NOTE]
> <span data-ttu-id="e73fe-105">[!注释] 如果数据库不受信任，将不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="e73fe-105">This action will not be allowed if the database is not trusted.</span></span>

## <a name="setting"></a><span data-ttu-id="e73fe-106">设置</span><span class="sxs-lookup"><span data-stu-id="e73fe-106">Setting</span></span>

<span data-ttu-id="e73fe-107">**RenameObject** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="e73fe-107">The **RenameObject** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e73fe-108">操作参数</span><span class="sxs-lookup"><span data-stu-id="e73fe-108">Action argument</span></span></p></th>
<th><p><span data-ttu-id="e73fe-109">说明</span><span class="sxs-lookup"><span data-stu-id="e73fe-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e73fe-110"><strong>新名称</strong></span><span class="sxs-lookup"><span data-stu-id="e73fe-110"><strong>New Name</strong></span></span></p></td>
<td><p><span data-ttu-id="e73fe-p101">数据库对象的新名称。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“新名称”</strong>框中输入对象名称。这是一个必选参数。</span><span class="sxs-lookup"><span data-stu-id="e73fe-p101">A new name for the database object. Enter the object name in the <strong>New Name</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. This is a required argument.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e73fe-114"><strong>对象类型</strong></span><span class="sxs-lookup"><span data-stu-id="e73fe-114"><strong>Object Type</strong></span></span></p></td>
<td><p><span data-ttu-id="e73fe-p102">要重命名的对象的类型。请单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“报表”</strong>、<strong>“宏”</strong>、<strong>“模块”</strong>、<strong>“数据访问页”</strong>、<strong>“服务器视图”</strong>、<strong>“图表”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。要重命名导航窗格中选定的对象，请将此参数留空。</span><span class="sxs-lookup"><span data-stu-id="e73fe-p102">The type of object you want to rename. Click <strong>Table</strong>, <strong>Query</strong>, <strong>Form</strong>, <strong>Report</strong>, <strong>Macro</strong>, <strong>Module</strong>, <strong>Data Access Page</strong>, <strong>Server View</strong>, <strong>Diagram</strong>, <strong>Stored Procedure</strong>, or <strong>Function</strong>. To rename the object selected in the Navigation Pane, leave this argument blank.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e73fe-118"><strong>旧名称</strong></span><span class="sxs-lookup"><span data-stu-id="e73fe-118"><strong>Old Name</strong></span></span></p></td>
<td><p><span data-ttu-id="e73fe-119">要重命名的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="e73fe-119">The name of the object to be renamed.</span></span> <span data-ttu-id="e73fe-120"><strong>旧名称</strong>框中显示<strong>对象类型</strong>参数所选类型的数据库中的所有对象。</span><span class="sxs-lookup"><span data-stu-id="e73fe-120">The <strong>Old Name</strong> box shows all objects in the database of the type selected by the <strong>Object Type</strong> argument.</span></span> <span data-ttu-id="e73fe-121">如果将<strong>对象类型</strong>参数留空，还应将此参数留空。</span><span class="sxs-lookup"><span data-stu-id="e73fe-121">If you leave the <strong>Object Type</strong> argument blank, leave this argument blank also.</span></span></p><p><span data-ttu-id="e73fe-122"><strong>注意</strong>： 如果您运行包含类库数据库中的<STRONG>重命名</STRONG>操作的宏，Microsoft Access 首先会查找具有此名称在类库数据库，然后在当前数据库中的对象。</span><span class="sxs-lookup"><span data-stu-id="e73fe-122"><strong>NOTE</strong>: If you run a macro containing the <STRONG>Rename</STRONG> action in a library database, Microsoft Access first looks for the object with this name in the library database, and then in the current database.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="e73fe-123">说明</span><span class="sxs-lookup"><span data-stu-id="e73fe-123">Remarks</span></span>

<span data-ttu-id="e73fe-124">数据库对象的新名称必须遵循 Access 对象的标准命名约定。</span><span class="sxs-lookup"><span data-stu-id="e73fe-124">The new name of the database object must follow the standard naming conventions for Access objects.</span></span>

<span data-ttu-id="e73fe-125">无法重命名打开的对象。</span><span class="sxs-lookup"><span data-stu-id="e73fe-125">You can't rename an open object.</span></span>

<span data-ttu-id="e73fe-126">如果将**对象类型**和**旧名称**参数留空，访问重命名选定的导航窗格中的对象。</span><span class="sxs-lookup"><span data-stu-id="e73fe-126">If you leave the **Object Type** and **Old Name** arguments blank, Access renames the object selected in the Navigation Pane.</span></span> <span data-ttu-id="e73fe-127">若要在导航窗格中选择一个对象，可以**在导航窗格中**参数设置为**是**使用**SelectObject**操作。</span><span class="sxs-lookup"><span data-stu-id="e73fe-127">To select an object in the Navigation Pane, you can use the **SelectObject** action with the **In Navigation Pane** argument set to **Yes**.</span></span>

<span data-ttu-id="e73fe-p105">还可以通过以下方法重命名对象：在导航窗格中右键单击对象，单击 **"重命名"**，然后输入一个新名称。使用 **RenameObject** 操作时，您不必先在导航窗格中选择对象，也不必停止宏的运行来输入新名称。</span><span class="sxs-lookup"><span data-stu-id="e73fe-p105">You can also rename an object by right-clicking it in the Navigation Pane, clicking **Rename**, and entering a new name. With the **RenameObject** action, you don't have to select the object first in the Navigation Pane, and you don't have to stop the macro to enter the new name.</span></span>

<span data-ttu-id="e73fe-130">此操作与 **CopyObject** 操作不同，CopyObject 操作是用新名称创建对象的一个副本。</span><span class="sxs-lookup"><span data-stu-id="e73fe-130">This action differs from the **CopyObject** action, which creates a copy of the object under a new name.</span></span>

<span data-ttu-id="e73fe-131">若要在 Visual Basic for Applications (VBA) 模块中运行 **RenameObject** 操作，请使用 **DoCmd** 对象的 **Rename** 方法。</span><span class="sxs-lookup"><span data-stu-id="e73fe-131">To run the **RenameObject** action in a Visual Basic for Applications (VBA) module, use the **Rename** method of the **DoCmd** object.</span></span>

