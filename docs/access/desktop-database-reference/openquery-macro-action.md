---
title: OpenQuery 宏操作
TOCTitle: OpenQuery macro action
ms:assetid: 64bfce73-aeaf-9a78-895c-492e5da43ded
ms:mtpsurl: https://msdn.microsoft.com/library/Ff195094(v=office.15)
ms:contentKeyID: 48545298
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm89069
f1_categories:
- Office.Version=v15
ms.openlocfilehash: fe08f6c6ab0eba46f7fff2713403f56e82983357
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25999062"
---
# <a name="openquery-macro-action"></a><span data-ttu-id="e5b1d-102">OpenQuery 宏操作</span><span class="sxs-lookup"><span data-stu-id="e5b1d-102">OpenQuery macro action</span></span>

<span data-ttu-id="e5b1d-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="e5b1d-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="e5b1d-p101">可以使用 **OpenQuery** 操作在数据表视图、设计视图或打印预览中打开选择查询或交叉表查询。此操作运行动作查询。您还可以为查询选择数据输入模式。</span><span class="sxs-lookup"><span data-stu-id="e5b1d-p101">You can use the **OpenQuery** action to open a select or crosstab query in Datasheet view, Design view, or Print Preview. This action runs an action query. You can also select a data entry mode for the query.</span></span>

> [!NOTE]
> <span data-ttu-id="e5b1d-p102">[!注释] 此操作仅适用于 Microsoft Access 数据库环境（.mdb 或 .accdb）。如果使用的是 Microsoft Access 项目环境 (.adp)，请参阅 **OpenView**、 **OpenStoredProcedure** 或 **OpenFunction** 操作。</span><span class="sxs-lookup"><span data-stu-id="e5b1d-p102">This action is only available in the Access database environment (.mdb or .accdb). See the **OpenView**, **OpenStoredProcedure**, or **OpenFunction** actions if you are using the Access project environment (.adp).</span></span>

## <a name="setting"></a><span data-ttu-id="e5b1d-109">设置</span><span class="sxs-lookup"><span data-stu-id="e5b1d-109">Setting</span></span>

<span data-ttu-id="e5b1d-110">**OpenQuery** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="e5b1d-110">The **OpenQuery** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="e5b1d-111">操作参数</span><span class="sxs-lookup"><span data-stu-id="e5b1d-111">Action argument</span></span></p></th>
<th><p><span data-ttu-id="e5b1d-112">说明</span><span class="sxs-lookup"><span data-stu-id="e5b1d-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5b1d-113"><strong>查询名称</strong></span><span class="sxs-lookup"><span data-stu-id="e5b1d-113"><strong>Query Name</strong></span></span></p></td>
<td><p><span data-ttu-id="e5b1d-114">要打开的查询的名称。</span><span class="sxs-lookup"><span data-stu-id="e5b1d-114">The name of the query to open.</span></span> <span data-ttu-id="e5b1d-115">宏生成器窗格的<strong>操作参数</strong>部分的<strong>查询名称</strong>框显示当前数据库中的所有查询。</span><span class="sxs-lookup"><span data-stu-id="e5b1d-115">The <strong>Query Name</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane shows all queries in the current database.</span></span> <span data-ttu-id="e5b1d-116">这是必需的参数。如果您运行包含<strong>OpenQuery</strong>操作类库数据库中的宏，Microsoft Access 首先查找具有此名称在类库数据库，然后在当前数据库的查询。</span><span class="sxs-lookup"><span data-stu-id="e5b1d-116">This is a required argument.If you run a macro containing the <strong>OpenQuery</strong> action in a library database, Microsoft Access first looks for the query with this name in the library database, and then in the current database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5b1d-117"><strong>View</strong></span><span class="sxs-lookup"><span data-stu-id="e5b1d-117"><strong>View</strong></span></span></p></td>
<td><p><span data-ttu-id="e5b1d-p104">打开查询时将使用的视图。请在<strong>“视图”</strong>框中单击<strong>“数据表”</strong>、<strong>“设计”</strong>、<strong>“打印预览”</strong>、<strong>“数据透视表”</strong>或<strong>“数据透视图”</strong>。默认值为<strong>“数据表”</strong>。</span><span class="sxs-lookup"><span data-stu-id="e5b1d-p104">The view in which the query will open. Click <strong>Datasheet</strong>, <strong>Design</strong>, <strong>Print Preview</strong>, <strong>PivotTable</strong>, or <strong>PivotChart</strong> in the <strong>View</strong> box. The default is <strong>Datasheet</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5b1d-121"><strong>Data Mode</strong></span><span class="sxs-lookup"><span data-stu-id="e5b1d-121"><strong>Data Mode</strong></span></span></p></td>
<td><p><span data-ttu-id="e5b1d-p105">查询的数据输入模式。此参数仅适用于在数据表视图中打开的查询。请单击<strong>“添加”</strong>（用户可添加新记录，但不能编辑现有记录）、<strong>“编辑”</strong>（用户可编辑现有记录和添加新记录）或<strong>“只读”</strong>（用户只能查看记录）。默认值为<strong>“编辑”</strong>。</span><span class="sxs-lookup"><span data-stu-id="e5b1d-p105">The data entry mode for the query. This applies only to queries opened in Datasheet view. Click <strong>Add</strong> (the user can add new records but can't edit existing records), <strong>Edit</strong> (the user can edit existing records and add new records), or <strong>Read Only</strong> (the user can only view records). The default is <strong>Edit</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="e5b1d-126">说明</span><span class="sxs-lookup"><span data-stu-id="e5b1d-126">Remarks</span></span>

<span data-ttu-id="e5b1d-127">如果您使用**数据表\*\*\*\*视图**参数，Access 将显示在结果集中如果查询选择，交叉表，联合，或传递查询其**ReturnsRecords**属性设置为**是**;和操作、 数据定义或其**ReturnsRecords**属性设置为**不**传递查询是否运行查询。</span><span class="sxs-lookup"><span data-stu-id="e5b1d-127">If you use **Datasheet** for the **View** argument, Access displays the result set if the query is a select, crosstab, union, or pass-through query whose **ReturnsRecords** property is set to **Yes**; and it runs the query if it is an action, data-definition, or pass-through query whose **ReturnsRecords** property is set to **No**.</span></span>

<span data-ttu-id="e5b1d-p106">**OpenQuery** 操作类似于在导航窗格中双击查询，或在导航窗格中右键单击查询并选择视图。通过此操作可以选择其他选项。</span><span class="sxs-lookup"><span data-stu-id="e5b1d-p106">The **OpenQuery** action is similar to double-clicking the query in the Navigation Pane, or right-clicking the query in the Navigation Pane and selecting a view. With this action you can select additional options.</span></span>

> [!TIP]
> - <span data-ttu-id="e5b1d-130">可以将查询从导航窗格拖动到宏操作行中。</span><span class="sxs-lookup"><span data-stu-id="e5b1d-130">You can drag a query from the Navigation Pane to a macro action row.</span></span> <span data-ttu-id="e5b1d-131">这会自动创建的数据表视图中打开查询**OpenQuery**操作。</span><span class="sxs-lookup"><span data-stu-id="e5b1d-131">This automatically creates an **OpenQuery** action that opens the query in Datasheet view.</span></span> <span data-ttu-id="e5b1d-132">打开查询时切换到设计视图中删除查询的**数据模式**参数设置。</span><span class="sxs-lookup"><span data-stu-id="e5b1d-132">Switching to Design view while the query is open removes the **Data Mode** argument setting for the query.</span></span> <span data-ttu-id="e5b1d-133">此设置不会生效，即使用户返回到数据表视图。</span><span class="sxs-lookup"><span data-stu-id="e5b1d-133">This setting isn't in effect even if the user returns to Datasheet view.</span></span>
> - <span data-ttu-id="e5b1d-134">如果不想显示通常在运行动作查询时出现的系统消息（指示查询为动作查询并显示将受到影响的记录数），则可以使用 **SetWarnings** 操作禁止显示这些消息。</span><span class="sxs-lookup"><span data-stu-id="e5b1d-134">If you don't want to display the system messages that normally appear when an action query is run (indicating it is an action query and showing how many records will be affected), you can use the **SetWarnings** action to suppress the display of these messages.</span></span>

<span data-ttu-id="e5b1d-135">要在 Visual Basic for Applications (VBA) 模块中运行 **OpenQuery** 操作，请使用 **DoCmd** 对象的 **OpenQuery** 方法。</span><span class="sxs-lookup"><span data-stu-id="e5b1d-135">To run the **OpenQuery** action in a Visual Basic for Applications (VBA) module, use the **OpenQuery** method of the **DoCmd** object.</span></span>

