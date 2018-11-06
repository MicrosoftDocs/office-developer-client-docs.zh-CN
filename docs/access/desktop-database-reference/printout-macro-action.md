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
ms.openlocfilehash: c2e5b3e2cdfb743df8a098d3978ccd3d6eb66d90
ms.sourcegitcommit: 1dd744993ecb4bed241ace874ad26edaef1778b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2018
ms.locfileid: "25999027"
---
# <a name="printout-macro-action"></a><span data-ttu-id="9ebce-102">PrintOut 宏操作</span><span class="sxs-lookup"><span data-stu-id="9ebce-102">PrintOut macro action</span></span>

<span data-ttu-id="9ebce-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="9ebce-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="9ebce-p101">可以使用 **PrintOut** 操作来打印打开的数据库中的活动对象。可以打印数据表、报表、窗体、数据访问页和模块。</span><span class="sxs-lookup"><span data-stu-id="9ebce-p101">You can use the **PrintOut** action to print the active object in the open database. You can print datasheets, reports, forms, data access pages, and modules.</span></span>

> [!NOTE]
> <span data-ttu-id="9ebce-106">[!注释] 如果数据库不受信任，将不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="9ebce-106">This action will not be allowed if the database is not trusted.</span></span> 

## <a name="setting"></a><span data-ttu-id="9ebce-107">设置</span><span class="sxs-lookup"><span data-stu-id="9ebce-107">Setting</span></span>

<span data-ttu-id="9ebce-108">**PrintOut** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="9ebce-108">The **PrintOut** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="9ebce-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="9ebce-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="9ebce-110">说明</span><span class="sxs-lookup"><span data-stu-id="9ebce-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ebce-111"><strong>打印范围</strong></span><span class="sxs-lookup"><span data-stu-id="9ebce-111"><strong>Print Range</strong></span></span></p></td>
<td><p><span data-ttu-id="9ebce-112">要打印的范围。</span><span class="sxs-lookup"><span data-stu-id="9ebce-112">The range to print.</span></span> <span data-ttu-id="9ebce-113">单击<strong>中的<strong>所有</strong>（用户可以打印对象的所有）、<strong>选定内容</strong>（用户可以打印所选的对象的一部分） 或<strong>网页</strong>（用户可以在<strong>页面</strong>和结束<strong>页码</strong>参数中指定的页面范围）打印范围</strong>框在宏生成器窗格的<strong>操作参数</strong>部分。</span><span class="sxs-lookup"><span data-stu-id="9ebce-113">Click <strong>All</strong> (the user can print all of the object), <strong>Selection</strong> (the user can print the part of the object that's selected), or <strong>Pages</strong> (the user can specify a range of pages in the <strong>Page From</strong> and <strong>Page To</strong> arguments) in the <strong>Print Range</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane.</span></span> <span data-ttu-id="9ebce-114">默认值为 <strong>"全部"</strong>。</span><span class="sxs-lookup"><span data-stu-id="9ebce-114">The default is <strong>All</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ebce-115"><strong>开始页码</strong></span><span class="sxs-lookup"><span data-stu-id="9ebce-115"><strong>Page From</strong></span></span></p></td>
<td><p><span data-ttu-id="9ebce-p103">要打印的第一页。打印从此页顶部开始。如果在<strong>“打印范围”</strong>框中选择<strong>“页”</strong>，则此参数是必选参数。</span><span class="sxs-lookup"><span data-stu-id="9ebce-p103">The first page to print. Printing starts at the top of this page. This argument is required if you select <strong>Pages</strong> in the <strong>Print Range</strong> box.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ebce-119"><strong>结束页码</strong></span><span class="sxs-lookup"><span data-stu-id="9ebce-119"><strong>Page To</strong></span></span></p></td>
<td><p><span data-ttu-id="9ebce-p104">要打印的最后一页。打印在此页底部结束。如果在<strong>“打印范围”</strong>框中选择<strong>“页”</strong>，则此参数是必选参数。</span><span class="sxs-lookup"><span data-stu-id="9ebce-p104">The last page to print. Printing stops at the bottom of this page. This argument is required if you select <strong>Pages</strong> in the <strong>Print Range</strong> box.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ebce-123">“打印质量”<strong></strong></span><span class="sxs-lookup"><span data-stu-id="9ebce-123"><strong>Print Quality</strong></span></span></p></td>
<td><p><span data-ttu-id="9ebce-p105">打印质量。请单击<strong>“高品质”</strong>、<strong>“中品质”</strong>、<strong>“低品质”</strong>或<strong>“草稿”</strong>。质量越低，对象的打印速度就越快。默认值为<strong>“高品质”</strong>。</span><span class="sxs-lookup"><span data-stu-id="9ebce-p105">The print quality. Click <strong>High</strong>, <strong>Medium</strong>, <strong>Low</strong>, or <strong>Draft</strong>. The lower the quality, the faster the object prints. The default is <strong>High</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ebce-128"><strong>Copies</strong></span><span class="sxs-lookup"><span data-stu-id="9ebce-128"><strong>Copies</strong></span></span></p></td>
<td><p><span data-ttu-id="9ebce-p106">要打印的份数。默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="9ebce-p106">The number of copies to print. The default is 1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ebce-131"><strong>逐份打印</strong></span><span class="sxs-lookup"><span data-stu-id="9ebce-131"><strong>Collate Copies</strong></span></span></p></td>
<td><p><span data-ttu-id="9ebce-p107">单击<strong>“是”</strong>（进行分页）或<strong>“否”</strong>（不进行分页）。如果此参数设置为<strong>“否”</strong>，对象的打印速度可能会更快。默认值为<strong>“是”</strong>。</span><span class="sxs-lookup"><span data-stu-id="9ebce-p107">Click <strong>Yes</strong> (collate the printed copies) or <strong>No</strong> (do not collate copies). The object may print faster if this argument is set to <strong>No</strong>. The default is <strong>Yes</strong>.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="9ebce-135">说明</span><span class="sxs-lookup"><span data-stu-id="9ebce-135">Remarks</span></span>

<span data-ttu-id="9ebce-p108">此操作类似于选择某个对象，单击 **"文件"** 选项卡，然后单击 **"打印"**。但是，在执行此操作时，不会出现 **"打印"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="9ebce-p108">This action is similar to selecting an object, clicking the **File** tab and then clicking **Print**. With this action, however, no **Print** dialog box appears.</span></span>

> [!TIP]
> <span data-ttu-id="9ebce-138">[!提示] 如果您有经常使用的特定打印设置，请创建一个包含 **PrintOut** 操作的宏，并让该操作的参数使用这些设置。</span><span class="sxs-lookup"><span data-stu-id="9ebce-138">If you have particular print settings you use frequently, create a macro containing a **PrintOut** action with these settings in its arguments.</span></span>

<span data-ttu-id="9ebce-p109">此操作的参数与 **"打印"** 对话框中的选项相对应。但是，与 **FindRecord** 操作和 **"查找和替换"** 对话框不同，这些参数设置并不与 **"打印"** 对话框选项共享。</span><span class="sxs-lookup"><span data-stu-id="9ebce-p109">The arguments for this action correspond to options in the **Print** dialog box. However, unlike the **FindRecord** action and **Find and Replace** dialog box, the argument settings aren't shared with the **Print** dialog box options.</span></span>

<span data-ttu-id="9ebce-141">要在 Visual Basic for Applications (VBA) 模块中运行 **PrintOut** 操作，请使用 **DoCmd** 对象的 **PrintOut** 方法。</span><span class="sxs-lookup"><span data-stu-id="9ebce-141">To run the **PrintOut** action in a Visual Basic for Applications (VBA) module, use the **PrintOut** method of the **DoCmd** object.</span></span>

