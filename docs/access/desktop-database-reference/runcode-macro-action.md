---
title: RunCode 宏操作
TOCTitle: RunCode macro action
ms:assetid: cb0625be-4b5d-4927-9b0e-59a6e411b5bb
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834373(v=office.15)
ms:contentKeyID: 48547706
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm98700
f1_categories:
- Office.Version=v15
ms.openlocfilehash: acf8ed2bd10efd55436b8933a862833b8e49c5f0
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25926687"
---
# <a name="runcode-macro-action"></a><span data-ttu-id="200fc-102">RunCode 宏操作</span><span class="sxs-lookup"><span data-stu-id="200fc-102">RunCode macro action</span></span>


<span data-ttu-id="200fc-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="200fc-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="200fc-104">可以使用 **RunCode** 操作调用 Visual Basic for Applications (VBA) Function 过程。</span><span class="sxs-lookup"><span data-stu-id="200fc-104">You can use the **RunCode** action to call a Visual Basic for Applications (VBA) Function procedure.</span></span>

## <a name="setting"></a><span data-ttu-id="200fc-105">设置</span><span class="sxs-lookup"><span data-stu-id="200fc-105">Setting</span></span>

<span data-ttu-id="200fc-106">**RunCode** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="200fc-106">The **RunCode** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="200fc-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="200fc-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="200fc-108">说明</span><span class="sxs-lookup"><span data-stu-id="200fc-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="200fc-109"><strong>函数名称</strong></span><span class="sxs-lookup"><span data-stu-id="200fc-109"><strong>Function Name</strong></span></span></p></td>
<td><p><span data-ttu-id="200fc-p101">要调用的 VBA Function 过程的名称。请将所有函数参数放在括号中。在“宏生成器”窗格<strong>“操作参数”</strong>部分的<strong>“函数名称”</strong>框中输入函数名称。这是一个必选参数。</span><span class="sxs-lookup"><span data-stu-id="200fc-p101">The name of the VBA Function procedure to call. Enclose any function arguments in parentheses. Enter the function name in the <strong>Function Name</strong> box in the <strong>Action Arguments</strong> section of the Macro Builder pane. This is a required argument.</span></span></p>

> [!NOTE]
> <P><span data-ttu-id="200fc-p102">在 Microsoft Access 数据库（.mdb 或 .accdb）中，单击<STRONG>“生成”</STRONG>按钮，以便使用表达式生成器为此参数选择一个函数。在表达式生成器中的列表中单击所需的函数。</span><span class="sxs-lookup"><span data-stu-id="200fc-p102">In an Access database (.mdb or .accdb), click the <STRONG>Build</STRONG> button to use the Expression Builder to select a function for this argument. Click the desired function in the list in the Expression Builder.</span></span></P>


<p></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="200fc-116">说明</span><span class="sxs-lookup"><span data-stu-id="200fc-116">Remarks</span></span>

<span data-ttu-id="200fc-117">用户定义的 Function 过程都存储在 Microsoft Access 模块中。</span><span class="sxs-lookup"><span data-stu-id="200fc-117">The user-defined Function procedures are stored in Microsoft Access modules.</span></span>

<span data-ttu-id="200fc-118">即使 Function 过程不具有任何参数，括号也是必需的，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="200fc-118">You must include parentheses, even if the Function procedure doesn't have any arguments, as in the following example:</span></span>

`TestFunction()`

<span data-ttu-id="200fc-119">**函数名称**参数中的函数名称不与用于事件属性设置的用户定义的函数名称，不同开头等号 (**=**)。</span><span class="sxs-lookup"><span data-stu-id="200fc-119">Unlike user-defined function names used for event property settings, the function name in the **Function Name** argument doesn't begin with an equal sign (**=**).</span></span>

<span data-ttu-id="200fc-120">Access 会忽略函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="200fc-120">Access ignores the return value of the function.</span></span>


> [!NOTE]
> <P><span data-ttu-id="200fc-121">[!注释] 如果函数名称与模块名称相同，则不能通过宏调用 Function 过程。</span><span class="sxs-lookup"><span data-stu-id="200fc-121">You can't call a Function procedure from a macro if the function name is the same as the module name.</span></span></P>




> [!TIP]
> <P><span data-ttu-id="200fc-p103">[!提示] 要运行用 Visual Basic 编写的 Sub 过程或事件过程，请创建一个调用 Sub 过程或事件过程的 Function 过程。然后使用 <STRONG>RunCode</STRONG> 操作运行该 Function 过程。</span><span class="sxs-lookup"><span data-stu-id="200fc-p103">To run a Sub procedure or event procedure written in Visual Basic, create a Function procedure that calls the Sub procedure or event procedure. Then use the <STRONG>RunCode</STRONG> action to run the Function procedure.</span></span></P>



<span data-ttu-id="200fc-124">如果您使用**RunCode**操作调用的函数，访问查找函数使用数据库标准模块中的**函数名称**参数指定的名称。</span><span class="sxs-lookup"><span data-stu-id="200fc-124">If you use the **RunCode** action to call a function, Access looks for the function with the name specified by the **Function Name** argument in the standard modules for the database.</span></span> <span data-ttu-id="200fc-125">但是，当运行此操作的窗体或报表上的菜单命令或在窗体或报表上的事件的响应，访问首先查找函数在窗体或报表的类模块，然后在标准模块。</span><span class="sxs-lookup"><span data-stu-id="200fc-125">However, when this action runs in response to clicking a menu command on a form or report or in response to an event on a form or report, Access first looks for the function in the form's or report's class module and then in the standard modules.</span></span> <span data-ttu-id="200fc-126">Access 不搜索显示在导航窗格中的**函数名称**参数指定的函数**模块**区域中的类模块。</span><span class="sxs-lookup"><span data-stu-id="200fc-126">Access doesn't search the class modules that appear in the **Modules** area of the Navigation Pane for the function specified by the **Function Name** argument.</span></span>

<span data-ttu-id="200fc-p105">此操作不能在 VBA 模块中使用。然而，可以直接在 VBA 中运行所需的 Function 过程。</span><span class="sxs-lookup"><span data-stu-id="200fc-p105">This action isn't available in a VBA module. Instead, run the desired Function procedure directly in VBA.</span></span>

