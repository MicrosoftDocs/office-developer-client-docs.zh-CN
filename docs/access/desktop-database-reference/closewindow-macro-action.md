---
title: CloseWindow 宏操作
TOCTitle: CloseWindow Macro Action
ms:assetid: ba96bc26-7f3f-fd3d-8d3a-e18bfe90cdf0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822510(v=office.15)
ms:contentKeyID: 48547377
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm64319
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 1d80ac5b545f07d3bd39f69f16c4578e49439cdf
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465579"
---
# <a name="closewindow-macro-action"></a><span data-ttu-id="9ffa3-102">CloseWindow 宏操作</span><span class="sxs-lookup"><span data-stu-id="9ffa3-102">CloseWindow Macro Action</span></span>


<span data-ttu-id="9ffa3-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="9ffa3-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="9ffa3-104">您可以使用**CloseWindow**操作关闭指定的访问文档选项卡或活动文档选项卡，如果未指定。</span><span class="sxs-lookup"><span data-stu-id="9ffa3-104">You can use the **CloseWindow** action to close either a specified Access document tab or the active document tab if none is specified.</span></span>

## <a name="setting"></a><span data-ttu-id="9ffa3-105">设置</span><span class="sxs-lookup"><span data-stu-id="9ffa3-105">Setting</span></span>

<span data-ttu-id="9ffa3-106">**CloseWindow** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="9ffa3-106">The **CloseWindow** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9ffa3-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="9ffa3-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="9ffa3-108">说明</span><span class="sxs-lookup"><span data-stu-id="9ffa3-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ffa3-109"><strong>对象类型</strong></span><span class="sxs-lookup"><span data-stu-id="9ffa3-109"><strong>Object Type</strong></span></span></p></td>
<td><p><span data-ttu-id="9ffa3-p101">要关闭其文档选项卡的数据库对象的类型。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“对象类型”</strong>框中单击<strong>“表”</strong>、<strong>“查询”</strong>、<strong>“窗体”</strong>、<strong>“报表”</strong>、<strong>“宏”</strong>、<strong>“模块”</strong>、<strong>“数据访问页”</strong>、<strong>“服务器视图”</strong>、<strong>“图表”</strong>、<strong>“存储过程”</strong>或<strong>“函数”</strong>。要选择活动的文档选项卡，请将此参数留空。 

</span><span class="sxs-lookup"><span data-stu-id="9ffa3-p101">The type of object whose document tab you want to close. Click <strong>Table</strong>, <strong>Query</strong>, <strong>Form</strong>, <strong>Report</strong>, <strong>Macro</strong>, <strong>Module</strong>, <strong>Data Access Page</strong>, <strong>Server View</strong>, <strong>Diagram</strong>, <strong>Stored Procedure</strong>, or <strong>Function</strong> in the <strong>Object Type</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. To select the active document tab, leave this argument blank.</span></span></p>

> [!NOTE]
> <P><span data-ttu-id="9ffa3-113">如果您正在关闭模块在 Visual Basic 编辑器中，您必须在<STRONG>对象类型</STRONG>参数中使用<STRONG>模块</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="9ffa3-113">If you are closing a module in the Visual Basic Editor, you must use <STRONG>Module</STRONG> in the <STRONG>Object Type</STRONG> argument.</span></span></P>


<p></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ffa3-114"><strong>对象名称</strong></span><span class="sxs-lookup"><span data-stu-id="9ffa3-114"><strong>Object Name</strong></span></span></p></td>
<td><p><span data-ttu-id="9ffa3-115">要关闭的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="9ffa3-115">The name of the object to be closed.</span></span> <span data-ttu-id="9ffa3-116"><strong>对象名称</strong>框中显示<strong>对象类型</strong>参数所选类型的数据库中的所有对象。</span><span class="sxs-lookup"><span data-stu-id="9ffa3-116">The <strong>Object Name</strong> box shows all objects in the database of the type selected by the <strong>Object Type</strong> argument.</span></span> <span data-ttu-id="9ffa3-117">单击要关闭的对象。</span><span class="sxs-lookup"><span data-stu-id="9ffa3-117">Click the object to close.</span></span> <span data-ttu-id="9ffa3-118">如果将<strong>对象类型</strong>参数留空，还应将此参数留空。</span><span class="sxs-lookup"><span data-stu-id="9ffa3-118">If you leave the <strong>Object Type</strong> argument blank, leave this argument blank also.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ffa3-119"><strong>Save</strong></span><span class="sxs-lookup"><span data-stu-id="9ffa3-119"><strong>Save</strong></span></span></p></td>
<td><p><span data-ttu-id="9ffa3-p103">关闭对象时是否保存对其所做的更改。单击<strong>“是”</strong>（保存对象）、<strong>“否”</strong>（关闭对象但不保存）或<strong>“提示”</strong>（提示用户是否保存对象）。默认值为<strong>“提示”</strong>。</span><span class="sxs-lookup"><span data-stu-id="9ffa3-p103">Whether to save changes to the object when it is closed. Click <strong>Yes</strong> (save the object), <strong>No</strong> (close the object without saving it), or <strong>Prompt</strong> (prompt the user whether or not to save the object). The default is <strong>Prompt</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="9ffa3-123">说明</span><span class="sxs-lookup"><span data-stu-id="9ffa3-123">Remarks</span></span>

<span data-ttu-id="9ffa3-p104">**CloseWindow** 操作适用于用户可显式打开或关闭的所有数据库对象。此操作等效于选择某个对象，然后通过右键单击该对象的文档选项卡并单击快捷菜单上的 **"关闭"** 来关闭该对象，也等效于单击对象的 **"关闭"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="9ffa3-p104">The **CloseWindow** action works on all database objects that the user can explicitly open or close. This action has the same effect as selecting an object and then closing it by right-clicking the object's document tab and then clicking **Close** on the shortcut menu, or clicking the **Close** button for the object.</span></span>

<span data-ttu-id="9ffa3-126">如果**保存**参数设置为**提示**并执行**CloseWindow**操作之前不起作用已经保存了对象，一个对话框，提示用户宏关闭之前保存的对象。</span><span class="sxs-lookup"><span data-stu-id="9ffa3-126">If the **Save** argument is set to **Prompt** and the object hasn't already been saved before the **CloseWindow** action is carried out, a dialog box prompts the user to save the object before the macro closes it.</span></span> <span data-ttu-id="9ffa3-127">如果已将**SetWarnings**操作**警告**参数设置为**No**，不显示对话框，并自动保存的对象。</span><span class="sxs-lookup"><span data-stu-id="9ffa3-127">If you have set the **Warnings On** argument of the **SetWarnings** action to **No**, the dialog box is not displayed and the object is automatically saved.</span></span>

<span data-ttu-id="9ffa3-128">若要在 Visual Basic for Applications (VBA) 模块中运行 **CloseWindow** 操作，请使用 **DoCmd** 对象的 **CloseWindow** 方法。</span><span class="sxs-lookup"><span data-stu-id="9ffa3-128">To run the **CloseWindow** action in a Visual Basic for Applications (VBA) module, use the **CloseWindow** method of the **DoCmd** object.</span></span>

