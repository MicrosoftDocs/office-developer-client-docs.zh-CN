---
title: SetTempVar 宏操作
TOCTitle: SetTempVar Macro Action
ms:assetid: 9c3b7bee-02c5-efbf-1276-4c4a1f7802d9
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198102(v=office.15)
ms:contentKeyID: 48546593
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm150219
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 103be9b9587c2171d3414665a67ec36629df8ce2
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25874620"
---
# <a name="settempvar-macro-action"></a><span data-ttu-id="08fb3-102">SetTempVar 宏操作</span><span class="sxs-lookup"><span data-stu-id="08fb3-102">SetTempVar Macro Action</span></span>


<span data-ttu-id="08fb3-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="08fb3-103">**Applies to**: Access 2013, Office 2013</span></span>



<span data-ttu-id="08fb3-p101">可以使用 **SetTempVar** 操作创建一个临时变量并将其设置为一个特定值。然后，该变量可以在后续操作中作为条件或参数使用，也可以在其他宏、事件过程中或者窗体或报表上使用该变量。</span><span class="sxs-lookup"><span data-stu-id="08fb3-p101">You can use the **SetTempVar** action to create a temporary variable and set it to a specific value. The variable can then be used as a condition or argument in subsequent actions, or you can use the variable in another macro, in an event procedure, or on a form or report.</span></span>

## <a name="setting"></a><span data-ttu-id="08fb3-106">设置</span><span class="sxs-lookup"><span data-stu-id="08fb3-106">Setting</span></span>

<span data-ttu-id="08fb3-107">**SetTempVar** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="08fb3-107">The **SetTempVar** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="08fb3-108">操作参数</span><span class="sxs-lookup"><span data-stu-id="08fb3-108">Action argument</span></span></p></th>
<th><p><span data-ttu-id="08fb3-109">说明</span><span class="sxs-lookup"><span data-stu-id="08fb3-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08fb3-110"><strong>Name</strong></span><span class="sxs-lookup"><span data-stu-id="08fb3-110"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="08fb3-111">请输入临时变量的名称。</span><span class="sxs-lookup"><span data-stu-id="08fb3-111">Enter the name of the temporary variable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08fb3-112"><strong>Expression</strong></span><span class="sxs-lookup"><span data-stu-id="08fb3-112"><strong>Expression</strong></span></span></p></td>
<td><p><span data-ttu-id="08fb3-113">输入将用于设置为临时变量的值的表达式。</span><span class="sxs-lookup"><span data-stu-id="08fb3-113">Enter an expression that will be used to set the value for this temporary variable.</span></span> <span data-ttu-id="08fb3-114">不要在前对表达式与等 (<strong>=</strong>) 登录。</span><span class="sxs-lookup"><span data-stu-id="08fb3-114">Do not precede the expression with the equal (<strong>=</strong>) sign.</span></span> <span data-ttu-id="08fb3-115">您可以单击<strong>生成</strong>按钮</span><span class="sxs-lookup"><span data-stu-id="08fb3-115">You can click the <strong>Build</strong> button</span></span> <img src="media/access-build-button.gif" title="buildbut_ZA06047218" alt="buildbut_ZA06047218" /> <span data-ttu-id="08fb3-117">，以便使用表达式生成器设置此参数。</span><span class="sxs-lookup"><span data-stu-id="08fb3-117">to use the Expression Builder to set this argument.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="08fb3-118">说明</span><span class="sxs-lookup"><span data-stu-id="08fb3-118">Remarks</span></span>

- <span data-ttu-id="08fb3-p103">一次最多可以定义 255 个临时变量。如果您不删除临时变量，它将一直保留在内存中，直到您关闭数据库。在使用完临时变量后，最好将它们删除。要删除单个临时变量，请使用 **[RemoveTempVar](removetempvar-macro-action.md)** 操作，并将其参数设置为要删除的临时变量的名称。如果您有多个临时变量，并且想同时将它们全部删除，请使用 **RemoveAllTempVars** 操作。</span><span class="sxs-lookup"><span data-stu-id="08fb3-p103">You can have up to 255 temporary variables defined at one time. If you do not remove a temporary variable, it will remain in memory until you close the database. It is a good practice to remove temporary variables when you are finished using them. To remove a single temporary variable, use the **[RemoveTempVar](removetempvar-macro-action.md)** action and set its argument to the name of the temporary variable that you want to remove. If you have more than one temporary variable and you want to remove them all at once, use the **RemoveAllTempVars** action.</span></span>

- <span data-ttu-id="08fb3-124">临时变量是全局性的。</span><span class="sxs-lookup"><span data-stu-id="08fb3-124">Temporary variables are global.</span></span> <span data-ttu-id="08fb3-125">在创建了一个临时变量后，可以在事件过程、Visual Basic for Applications (VBA) 模块、查询或表达式中引用它。</span><span class="sxs-lookup"><span data-stu-id="08fb3-125">Once a temporary variable has been created, you can refer to it in an event procedure, a Visual Basic for Applications (VBA) module, a query, or an expression.</span></span> <span data-ttu-id="08fb3-126">例如，如果您创建一个名为*MyVar*的临时变量，您可以使用变量作为控件源对于文本框使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="08fb3-126">For example, if you created a temporary variable named *MyVar*, you could use the variable as the control source for a text box by using the following syntax:</span></span>
    
  `=[TempVars]![MyVar]`
    
  > [!NOTE]
  > <span data-ttu-id="08fb3-127">[!注释] 在宏、查询和事件过程中，不需要在表达式前面放等号。</span><span class="sxs-lookup"><span data-stu-id="08fb3-127">In macros, queries and event procedures, you do not need to precede the expression with an equal sign.</span></span>
 
  <span data-ttu-id="08fb3-128">还可以在任何加载项或被引用的数据库中引用临时变量。</span><span class="sxs-lookup"><span data-stu-id="08fb3-128">You can also refer to temporary variables in any add-ins or referenced databases.</span></span>

- <span data-ttu-id="08fb3-129">要在 VBA 模块中运行 **SetTempVar** 操作，请使用 **TempVars** 对象的 **Add** 方法。</span><span class="sxs-lookup"><span data-stu-id="08fb3-129">To run the **SetTempVar** action in a VBA module, use the **Add** method of the **TempVars** object.</span></span>

## <a name="example"></a><span data-ttu-id="08fb3-130">示例</span><span class="sxs-lookup"><span data-stu-id="08fb3-130">Example</span></span>

<span data-ttu-id="08fb3-131">下面的宏演示如何使用 **SetTempVar** 操作创建临时变量，在条件和消息框中使用该临时变量，然后删除该临时变量。</span><span class="sxs-lookup"><span data-stu-id="08fb3-131">The following macro demonstrates how to create a temporary variable by using the **SetTempVar** action, then using the temporary variable in a condition and a message box, and then removing the temporary variable.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="08fb3-132">条件</span><span class="sxs-lookup"><span data-stu-id="08fb3-132">Condition</span></span></p></th>
<th><p><span data-ttu-id="08fb3-133">操作</span><span class="sxs-lookup"><span data-stu-id="08fb3-133">Action</span></span></p></th>
<th><p><span data-ttu-id="08fb3-134">参数</span><span class="sxs-lookup"><span data-stu-id="08fb3-134">Arguments</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="08fb3-135"><strong>SetTempVar</strong></span><span class="sxs-lookup"><span data-stu-id="08fb3-135"><strong>SetTempVar</strong></span></span></p></td>
<td><p><span data-ttu-id="08fb3-136"><strong>名称</strong>： MyVar<strong>表达式</strong>： InputBox (&quot;输入非零数。&quot;)</span><span class="sxs-lookup"><span data-stu-id="08fb3-136"><strong>Name</strong>: MyVar<strong>Expression</strong>: InputBox(&quot;Enter a non-zero number.&quot;)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08fb3-137">[TempVars] ！[MyVar]&lt; &gt;0</span><span class="sxs-lookup"><span data-stu-id="08fb3-137">[TempVars]![MyVar]&lt;&gt;0</span></span></p></td>
<td><p><span data-ttu-id="08fb3-138"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="08fb3-138"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="08fb3-139"><strong>消息</strong>: =&quot;您输入&quot; &amp; [TempVars] ！[MyVar]&amp; &quot;.&quot;<strong>发嘟嘟声</strong>： <strong>YesType</strong>：<strong>信息</strong></span><span class="sxs-lookup"><span data-stu-id="08fb3-139"><strong>Message</strong>: =&quot;You entered &quot; &amp; [TempVars]![MyVar] &amp; &quot;.&quot;<strong>Beep</strong>: <strong>YesType</strong>: <strong>Information</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="08fb3-140"><strong>RemoveTempVar</strong></span><span class="sxs-lookup"><span data-stu-id="08fb3-140"><strong>RemoveTempVar</strong></span></span></p></td>
<td><p><span data-ttu-id="08fb3-141"><strong>名称</strong>：MyVar</span><span class="sxs-lookup"><span data-stu-id="08fb3-141"><strong>Name</strong>: MyVar</span></span></p></td>
</tr>
</tbody>
</table>

