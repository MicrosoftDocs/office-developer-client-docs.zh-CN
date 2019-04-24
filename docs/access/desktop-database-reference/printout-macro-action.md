---
title: PrintOut 宏操作
TOCTitle: PrintOut macro action
ms:assetid: 13688158-1cf1-4b2e-d90a-271c8890e413
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845432(v=office.15)
ms:contentKeyID: 48543368
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm1697
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 04212a8bf63d5039c6548463612f006f0d116229
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301405"
---
# <a name="printout-macro-action"></a><span data-ttu-id="c7a4c-102">PrintOut 宏操作</span><span class="sxs-lookup"><span data-stu-id="c7a4c-102">PrintOut macro action</span></span>

<span data-ttu-id="c7a4c-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="c7a4c-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="c7a4c-p101">可以使用 **PrintOut** 操作来打印打开的数据库中的活动对象。可以打印数据表、报表、窗体、数据访问页和模块。</span><span class="sxs-lookup"><span data-stu-id="c7a4c-p101">You can use the **PrintOut** action to print the active object in the open database. You can print datasheets, reports, forms, data access pages, and modules.</span></span>

> [!NOTE]
> <span data-ttu-id="c7a4c-106">如果数据库不受信任，则不允许执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c7a4c-106">This action will not be allowed if the database is not trusted.</span></span> 

## <a name="setting"></a><span data-ttu-id="c7a4c-107">设置</span><span class="sxs-lookup"><span data-stu-id="c7a4c-107">Setting</span></span>

<span data-ttu-id="c7a4c-108">**PrintOut** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="c7a4c-108">The **PrintOut** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="c7a4c-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="c7a4c-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="c7a4c-110">说明</span><span class="sxs-lookup"><span data-stu-id="c7a4c-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7a4c-111"><strong>打印范围</strong></span><span class="sxs-lookup"><span data-stu-id="c7a4c-111"><strong>Print Range</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a4c-p102">要打印的范围。请在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“打印范围”</strong>框中单击<strong>“全部”</strong>（用户可以打印所有对象）、<strong>“选中内容”</strong>（用户可以打印该对象的选定部分）或<strong>“页”</strong>（用户可以在“开始页码”<strong></strong>和“结束页码”<strong></strong>参数中指定页范围）。默认值为<strong>“全部”</strong>。</span><span class="sxs-lookup"><span data-stu-id="c7a4c-p102">The range to print. Click <strong>All</strong> (the user can print all of the object), <strong>Selection</strong> (the user can print the part of the object that's selected), or <strong>Pages</strong> (the user can specify a range of pages in the <strong>Page From</strong> and <strong>Page To</strong> arguments) in the <strong>Print Range</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. The default is <strong>All</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a4c-115"><strong>开始页码</strong></span><span class="sxs-lookup"><span data-stu-id="c7a4c-115"><strong>Page From</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a4c-p103">要打印的第一页。打印从此页顶部开始。如果在<strong>“打印范围”</strong>框中选择<strong>“页”</strong>，则此参数是必选参数。</span><span class="sxs-lookup"><span data-stu-id="c7a4c-p103">The first page to print. Printing starts at the top of this page. This argument is required if you select <strong>Pages</strong> in the <strong>Print Range</strong> box.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a4c-119"><strong>结束页码</strong></span><span class="sxs-lookup"><span data-stu-id="c7a4c-119"><strong>Page To</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a4c-p104">要打印的最后一页。打印在此页底部结束。如果在<strong>“打印范围”</strong>框中选择<strong>“页”</strong>，则此参数是必选参数。</span><span class="sxs-lookup"><span data-stu-id="c7a4c-p104">The last page to print. Printing stops at the bottom of this page. This argument is required if you select <strong>Pages</strong> in the <strong>Print Range</strong> box.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a4c-123"><strong>Print Quality</strong></span><span class="sxs-lookup"><span data-stu-id="c7a4c-123"><strong>Print Quality</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a4c-124">打印质量。</span><span class="sxs-lookup"><span data-stu-id="c7a4c-124">The print quality.</span></span> <span data-ttu-id="c7a4c-125">请单击<strong>“高品质”</strong>、<strong>“中品质”</strong>、<strong>“低品质”</strong>或<strong>“草稿”</strong>。</span><span class="sxs-lookup"><span data-stu-id="c7a4c-125">Click <strong>High</strong>, <strong>Medium</strong>, <strong>Low</strong>, or <strong>Draft</strong>.</span></span> <span data-ttu-id="c7a4c-126">质量越低，对象的打印速度就越快。</span><span class="sxs-lookup"><span data-stu-id="c7a4c-126">The lower the quality, the faster the object prints.</span></span> <span data-ttu-id="c7a4c-127">默认值为<strong>“高品质”</strong>。</span><span class="sxs-lookup"><span data-stu-id="c7a4c-127">The default is <strong>High</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a4c-128"><strong>Copies</strong></span><span class="sxs-lookup"><span data-stu-id="c7a4c-128"><strong>Copies</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a4c-129">要打印的份数。</span><span class="sxs-lookup"><span data-stu-id="c7a4c-129">The number of copies to print.</span></span> <span data-ttu-id="c7a4c-130">默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="c7a4c-130">The default is 1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a4c-131"><strong>逐份打印</strong></span><span class="sxs-lookup"><span data-stu-id="c7a4c-131"><strong>Collate Copies</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a4c-p107">单击<strong>“是”</strong>（进行分页）或<strong>“否”</strong>（不进行分页）。如果此参数设置为<strong>“否”</strong>，对象的打印速度可能会更快。默认值为<strong>“是”</strong>。</span><span class="sxs-lookup"><span data-stu-id="c7a4c-p107">Click <strong>Yes</strong> (collate the printed copies) or <strong>No</strong> (do not collate copies). The object may print faster if this argument is set to <strong>No</strong>. The default is <strong>Yes</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="c7a4c-135">注解</span><span class="sxs-lookup"><span data-stu-id="c7a4c-135">Remarks</span></span>

<span data-ttu-id="c7a4c-p108">此操作类似于选择某个对象，单击 **"文件"** 选项卡，然后单击 **"打印"**。但是，在执行此操作时，不会出现 **"打印"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="c7a4c-p108">This action is similar to selecting an object, clicking the **File** tab and then clicking **Print**. With this action, however, no **Print** dialog box appears.</span></span>

> [!TIP]
> <span data-ttu-id="c7a4c-138">[!提示] 如果您有经常使用的特定打印设置，请创建一个包含 **PrintOut** 操作的宏，并让该操作的参数使用这些设置。</span><span class="sxs-lookup"><span data-stu-id="c7a4c-138">If you have particular print settings you use frequently, create a macro containing a **PrintOut** action with these settings in its arguments.</span></span>

<span data-ttu-id="c7a4c-p109">此操作的参数与 **"打印"** 对话框中的选项相对应。但是，与 **FindRecord** 操作和 **"查找和替换"** 对话框不同，这些参数设置并不与 **"打印"** 对话框选项共享。</span><span class="sxs-lookup"><span data-stu-id="c7a4c-p109">The arguments for this action correspond to options in the **Print** dialog box. However, unlike the **FindRecord** action and **Find and Replace** dialog box, the argument settings aren't shared with the **Print** dialog box options.</span></span>

<span data-ttu-id="c7a4c-141">要在 Visual Basic for Applications (VBA) 模块中运行 **PrintOut** 操作，请使用 **DoCmd** 对象的 **PrintOut** 方法。</span><span class="sxs-lookup"><span data-stu-id="c7a4c-141">To run the **PrintOut** action in a Visual Basic for Applications (VBA) module, use the **PrintOut** method of the **DoCmd** object.</span></span>

