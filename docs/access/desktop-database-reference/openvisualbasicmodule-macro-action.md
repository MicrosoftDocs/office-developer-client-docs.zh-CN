---
title: OpenVisualBasicModule 宏操作
TOCTitle: OpenVisualBasicModule macro action
ms:assetid: 26eb31c8-3c65-b17d-46cd-c8967434a7a0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191906(v=office.15)
ms:contentKeyID: 48543826
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm50916
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 55af2ce884b26b4c3df219e7d1986e7dc2e4c8ce
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28701695"
---
# <a name="openvisualbasicmodule-macro-action"></a><span data-ttu-id="8485b-102">OpenVisualBasicModule 宏操作</span><span class="sxs-lookup"><span data-stu-id="8485b-102">OpenVisualBasicModule macro action</span></span>

<span data-ttu-id="8485b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="8485b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="8485b-p101">可以使用 **OpenVisualBasicModule** 操作在指定的过程处打开指定的 Visual Basic for Applications (VBA) 模块。此过程可以是 Sub 过程、Function 过程或事件过程。</span><span class="sxs-lookup"><span data-stu-id="8485b-p101">You can use the **OpenVisualBasicModule** action to open a specified Visual Basic for Applications (VBA) module at a specified procedure. This can be a Sub procedure, a Function procedure, or an event procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="8485b-106">[!注释] 如果数据库不受信任，将不允许此操作。</span><span class="sxs-lookup"><span data-stu-id="8485b-106">This action will not be allowed if the database is not trusted.</span></span> 

## <a name="setting"></a><span data-ttu-id="8485b-107">设置</span><span class="sxs-lookup"><span data-stu-id="8485b-107">Setting</span></span>

<span data-ttu-id="8485b-108">**OpenVisualBasicModule** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="8485b-108">The **OpenVisualBasicModule** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8485b-109">操作参数</span><span class="sxs-lookup"><span data-stu-id="8485b-109">Action argument</span></span></p></th>
<th><p><span data-ttu-id="8485b-110">说明</span><span class="sxs-lookup"><span data-stu-id="8485b-110">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8485b-111"><strong>模块名称</strong></span><span class="sxs-lookup"><span data-stu-id="8485b-111"><strong>Module Name</strong></span></span></p></td>
<td><p><span data-ttu-id="8485b-112">要打开的模块名称。</span><span class="sxs-lookup"><span data-stu-id="8485b-112">The name of the module you want to open.</span></span> <span data-ttu-id="8485b-113">如果您想要在数据库中的过程中搜索所有的标准模块和打开适当的模块在该过程，您可以将此参数留空。</span><span class="sxs-lookup"><span data-stu-id="8485b-113">You can leave this argument blank if you want to search all the standard modules in the database for a procedure and open the appropriate module at that procedure.</span></span> <span data-ttu-id="8485b-114">如果在类库数据库中运行包含 <strong>OpenVisualBasicModule</strong> 操作的宏，Microsoft Access 将先在该类库数据库中查找具有此名称的模块，然后再在当前数据库中查找。</span><span class="sxs-lookup"><span data-stu-id="8485b-114">If you run a macro containing the <strong>OpenVisualBasicModule</strong> action in a library database, Microsoft Access first looks for the module with this name in the library database, and then in the current database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8485b-115"><strong>过程名称</strong></span><span class="sxs-lookup"><span data-stu-id="8485b-115"><strong>Procedure Name</strong></span></span></p></td>
<td><p><span data-ttu-id="8485b-p103">要在打开模块后显示的过程的名称。如果将此参数留空，则在打开模块后将显示其声明节。</span><span class="sxs-lookup"><span data-stu-id="8485b-p103">The name of the procedure you want to open the module to. If you leave this argument blank, the module opens to the Declarations section.</span></span></p></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="8485b-118">中的**模块名称**或**过程名称**的参数，必须输入一个有效的名称。</span><span class="sxs-lookup"><span data-stu-id="8485b-118">You must enter a valid name in either the **Module Name** or **Procedure Name** argument.</span></span>


## <a name="remarks"></a><span data-ttu-id="8485b-119">说明</span><span class="sxs-lookup"><span data-stu-id="8485b-119">Remarks</span></span>

<span data-ttu-id="8485b-120">此操作可用于打开事件过程，通过指定**模块名称**参数和**过程名称**参数。</span><span class="sxs-lookup"><span data-stu-id="8485b-120">You can use this action to open an event procedure by specifying the **Module Name** argument and the **Procedure Name** argument.</span></span> <span data-ttu-id="8485b-121">例如，若要打开的窗体订单的 PrintInvoice 按钮的**Click**事件过程，将**模块名称**参数设置为**Form.Orders**和**过程名称**参数设置为**PrintInvoice\_单击**。</span><span class="sxs-lookup"><span data-stu-id="8485b-121">For example, to open the **Click** event procedure of the PrintInvoice button on the form Orders, set the **Module Name** argument to **Form.Orders** and set the **Procedure Name** argument to **PrintInvoice\_Click**.</span></span> <span data-ttu-id="8485b-122">若要查看窗体或报表的事件过程，窗体或报表必须打开。</span><span class="sxs-lookup"><span data-stu-id="8485b-122">To view the event procedure for a form or report, the form or report must be open.</span></span>

<span data-ttu-id="8485b-123">同样，要在类模块中打开某个过程，必须指定模块名称；不过，不需要打开类模块。</span><span class="sxs-lookup"><span data-stu-id="8485b-123">Similarly, to open a procedure in a class module, you must specify the module name, although the class module does not have to open.</span></span>

<span data-ttu-id="8485b-124">要打开私有过程，必须打开包含该过程的模块。</span><span class="sxs-lookup"><span data-stu-id="8485b-124">To open a private procedure, the module containing it must be open.</span></span>

<span data-ttu-id="8485b-p105">此操作等效于在导航窗格中右键单击模块，然后单击 **"设计视图"**。通过此操作还可以指定过程名称以及在数据库中的标准模块中搜索过程。</span><span class="sxs-lookup"><span data-stu-id="8485b-p105">This action has the same effect as right-clicking a module in the Navigation Pane and then clicking **Design View**. This action also enables you to specify a procedure name and to search the standard modules in a database for procedures.</span></span>

> [!TIP]
> <span data-ttu-id="8485b-p106">[!提示] 您可以在导航窗格中选择模块并将其拖至宏操作行。这样会自动创建打开模块并显示其声明节的 **OpenVisualBasicModule** 操作。</span><span class="sxs-lookup"><span data-stu-id="8485b-p106">You can select a module in the Navigation Pane and drag it to a macro action row. This automatically creates an **OpenVisualBasicModule** action that opens the module to the Declarations section.</span></span>

<span data-ttu-id="8485b-129">若要在 VBA 模块中运行 **OpenVisualBasicModule** 操作，请使用 **DoCmd** 对象的 **OpenModule** 方法。</span><span class="sxs-lookup"><span data-stu-id="8485b-129">To run the **OpenVisualBasicModule** action in a VBA module, use the **OpenModule** method of the **DoCmd** object.</span></span>

