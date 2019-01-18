---
title: OpenFunction 宏操作
TOCTitle: OpenFunction macro action
ms:assetid: 0446dbb9-c342-9225-27ba-b8a6892030e1
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844833(v=office.15)
ms:contentKeyID: 48543005
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm89179
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: b13d21ef1bd8a95587eb78cd448f19f9fd0c24c0
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28720210"
---
# <a name="openfunction-macro-action"></a><span data-ttu-id="c533a-102">OpenFunction 宏操作</span><span class="sxs-lookup"><span data-stu-id="c533a-102">OpenFunction macro action</span></span>

<span data-ttu-id="c533a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c533a-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c533a-p101">在 Access 项目中，可以使用 **OpenFunction** 操作在数据表视图、内嵌函数设计视图、SQL 文本编辑器视图（针对用户定义的标量或表函数）或打印预览中打开用户定义的函数。当在数据表视图中打开用户定义的函数时，此操作会运行该函数。您还可以为用户定义的函数选择数据输入模式，以及限制用户定义的函数所显示的记录。</span><span class="sxs-lookup"><span data-stu-id="c533a-p101">In an Access project, you can use the **OpenFunction** action to open a user-defined function in Datasheet view, inline function Design view, SQL Text Editor view (for a scalar or table user-defined function), or Print Preview. This action runs the user-defined function when opened in Datasheet view. You can also select the data entry mode for the user-defined function and restrict the records that the user-defined function displays.</span></span>

> [!NOTE]
> <span data-ttu-id="c533a-107">[!注释] 如果数据库不受信任，将不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="c533a-107">This action will not be allowed if the database is not trusted.</span></span> 

## <a name="setting"></a><span data-ttu-id="c533a-108">设置</span><span class="sxs-lookup"><span data-stu-id="c533a-108">Setting</span></span>

<span data-ttu-id="c533a-109">**OpenFunction** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="c533a-109">The **OpenFunction** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c533a-110">操作参数</span><span class="sxs-lookup"><span data-stu-id="c533a-110">Action argument</span></span></p></th>
<th><p><span data-ttu-id="c533a-111">说明</span><span class="sxs-lookup"><span data-stu-id="c533a-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c533a-112"><strong>函数名称</strong></span><span class="sxs-lookup"><span data-stu-id="c533a-112"><strong>Function Name</strong></span></span></p></td>
<td><p><span data-ttu-id="c533a-113">要打开的用户定义函数的名称。</span><span class="sxs-lookup"><span data-stu-id="c533a-113">The name of the user-defined function to open.</span></span> <span data-ttu-id="c533a-114">宏生成器窗格的<strong>函数名称</strong>框在<strong>操作参数</strong>部分显示当前数据库中的所有用户定义的函数。</span><span class="sxs-lookup"><span data-stu-id="c533a-114">The <strong>Function Name</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane shows all user-defined functions in the current database.</span></span> <span data-ttu-id="c533a-115">这是必需的参数。如果您运行包含类库数据库中的<strong>功能</strong>操作的宏，Microsoft Access 首先查找具有此名称在类库数据库，然后在当前数据库中的函数。</span><span class="sxs-lookup"><span data-stu-id="c533a-115">This is a required argument.If you run a macro containing the <strong>Function</strong> action in a library database, Microsoft Access first looks for the function with this name in the library database, and then in the current database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c533a-116"><strong>View</strong></span><span class="sxs-lookup"><span data-stu-id="c533a-116"><strong>View</strong></span></span></p></td>
<td><p><span data-ttu-id="c533a-p103">打开用户定义的函数时将使用的视图。请在<strong>“视图”</strong>框中单击<strong>“数据表”</strong>、<strong>“设计”</strong>、<strong>“打印预览”</strong>、<strong>“数据透视表”</strong>或<strong>“数据透视图”</strong>。默认值为<strong>“数据表”</strong>。</span><span class="sxs-lookup"><span data-stu-id="c533a-p103">The view in which the user-defined function will open. Click <strong>Datasheet</strong>, <strong>Design</strong>, <strong>Print Preview</strong>, <strong>PivotTable</strong>, or <strong>PivotChart</strong> in the <strong>View</strong> box. The default is <strong>Datasheet</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c533a-120"><strong>Data Mode</strong></span><span class="sxs-lookup"><span data-stu-id="c533a-120"><strong>Data Mode</strong></span></span></p></td>
<td><p><span data-ttu-id="c533a-p104">用户定义的函数的数据输入模式。此参数仅适用于在数据表视图中打开的用户定义的函数。请单击<strong>“添加”</strong>（用户可添加新记录，但不能查看或编辑现有记录）、<strong>“编辑”</strong>（用户可查看或编辑现有记录以及添加新记录）或<strong>“只读”</strong>（用户只能查看记录）。默认值为<strong>“编辑”</strong>。</span><span class="sxs-lookup"><span data-stu-id="c533a-p104">The data entry mode for the user-defined function. This applies only to user-defined functions opened in Datasheet view. Click <strong>Add</strong> (the user can add new records but can't view or edit existing records), <strong>Edit</strong> (the user can view or edit existing records and add new records), or <strong>Read Only</strong> (the user can only view records). The default is <strong>Edit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="c533a-125">说明</span><span class="sxs-lookup"><span data-stu-id="c533a-125">Remarks</span></span>

<span data-ttu-id="c533a-126">此操作类似于在导航窗格中双击用户定义的函数，或在导航窗格中右键单击该函数并选择视图。</span><span class="sxs-lookup"><span data-stu-id="c533a-126">This action is similar to double-clicking a user-defined function in the Navigation Pane, or right-clicking the function in the Navigation Pane and selecting a view.</span></span>

<span data-ttu-id="c533a-127">打开的用户定义的函数时切换到设计视图中删除用户定义函数的**数据模式**参数设置。</span><span class="sxs-lookup"><span data-stu-id="c533a-127">Switching to Design view while the user-defined function is open removes the **Data Mode** argument setting for the user-defined function.</span></span> <span data-ttu-id="c533a-128">此设置不起作用，即使用户返回到数据表视图。</span><span class="sxs-lookup"><span data-stu-id="c533a-128">This setting is not in effect, even if the user returns to Datasheet view.</span></span>

> [!TIP]
> - <span data-ttu-id="c533a-p106">您可以在导航窗格中选择用户定义的函数并将其拖至宏操作行。这样会自动创建在数据表视图中打开该用户定义的函数的 **OpenFunction** 操作。</span><span class="sxs-lookup"><span data-stu-id="c533a-p106">You can select a user-defined function in the Navigation Pane and drag it to a macro action row. This automatically creates an **OpenFunction** action that opens the user-defined function in Datasheet view.</span></span>
> - <span data-ttu-id="c533a-131">通常，当用户定义的函数运行时，会显示一些系统消息（指明运行的是用户定义的函数并显示将受到影响的记录数）。如果不想显示这些系统消息，可以使用 **SetWarning** 操作来禁止其显示。</span><span class="sxs-lookup"><span data-stu-id="c533a-131">If you don't want to display the system messages that normally appear when a user-defined function is run (indicating it is a user-defined function and showing how many records will be affected), you can use the **SetWarning** action to suppress the display of these messages.</span></span>

<span data-ttu-id="c533a-132">要在 Visual Basic for Applications (VBA) 模块中运行 **OpenFunction** 操作，请使用 **DoCmd** 对象的 **OpenFunction** 方法。</span><span class="sxs-lookup"><span data-stu-id="c533a-132">To run the **OpenFunction** action in a Visual Basic for Applications (VBA) module, use the **OpenFunction** method of the **DoCmd** object.</span></span>

