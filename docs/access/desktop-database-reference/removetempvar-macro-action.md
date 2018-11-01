---
title: RemoveTempVar 宏操作
TOCTitle: RemoveTempVar Macro Action
ms:assetid: 7bcc5010-3e30-ecef-2c5d-a35e73c8e325
ms:mtpsurl: https://msdn.microsoft.com/library/Ff196352(v=office.15)
ms:contentKeyID: 48545822
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm147125
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 54831b0f0da673c7c7a6a901fd40fc6daee12603
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25887549"
---
# <a name="removetempvar-macro-action"></a><span data-ttu-id="4153a-102">RemoveTempVar 宏操作</span><span class="sxs-lookup"><span data-stu-id="4153a-102">RemoveTempVar Macro Action</span></span>


<span data-ttu-id="4153a-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="4153a-103">**Applies to**: Access 2013, Office 2013</span></span>



<span data-ttu-id="4153a-104">可以使用 **RemoveTempVar** 操作删除用 **SetTempVar** 操作创建的单个临时变量。</span><span class="sxs-lookup"><span data-stu-id="4153a-104">You can use the **RemoveTempVar** action to remove a single temporary variable that you created by using the **SetTempVar** action.</span></span>

## <a name="setting"></a><span data-ttu-id="4153a-105">设置</span><span class="sxs-lookup"><span data-stu-id="4153a-105">Setting</span></span>

<span data-ttu-id="4153a-106">**RemoveTempVar** 操作具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="4153a-106">The **RemoveTempVar** action has the following argument.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4153a-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="4153a-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="4153a-108">说明</span><span class="sxs-lookup"><span data-stu-id="4153a-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4153a-109"><strong>Name</strong></span><span class="sxs-lookup"><span data-stu-id="4153a-109"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="4153a-110">请输入要删除的临时变量的名称。</span><span class="sxs-lookup"><span data-stu-id="4153a-110">Enter the name of the temporary variable you want to remove.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="4153a-111">说明</span><span class="sxs-lookup"><span data-stu-id="4153a-111">Remarks</span></span>

  - <span data-ttu-id="4153a-p101">一次最多可以定义 255 个临时变量。如果您不删除临时变量，它将一直保留在内存中，直到您关闭数据库。在使用完临时变量后，最好将它们删除。</span><span class="sxs-lookup"><span data-stu-id="4153a-p101">You can have up to 255 temporary variables defined at one time. If you do not remove a temporary variable, it will remain in memory until you close the database. It is a good practice to remove temporary variables when you are finished using them.</span></span>

  - <span data-ttu-id="4153a-115">在关闭数据库或项目时，Access 会自动删除所有临时变量。</span><span class="sxs-lookup"><span data-stu-id="4153a-115">Access automatically removes all temporary variables when you close the database or project.</span></span>

  - <span data-ttu-id="4153a-p102">如果要删除的变量的名称拼写不正确，Access 不会显示出错。要删除的变量将一直保留在内存中，直到您关闭数据库。</span><span class="sxs-lookup"><span data-stu-id="4153a-p102">If you misspell the name of the variable to be removed, Access does not display an error. The variable you wanted to remove will remain in memory until you close the database.</span></span>

  - <span data-ttu-id="4153a-118">如果创建了多个临时变量并且想同时将它们全部删除，请使用 **RemoveAllTempVars** 操作。</span><span class="sxs-lookup"><span data-stu-id="4153a-118">If you have created more than one temporary variable and you want to remove them all at once, use the **RemoveAllTempVars** action.</span></span>

  - <span data-ttu-id="4153a-119">要在 VBA 模块中运行 **RemoveTempVar** 操作，请使用 **TempVars** 对象的 **Remove** 方法。</span><span class="sxs-lookup"><span data-stu-id="4153a-119">To run the **RemoveTempVar** action in a VBA module, use the **Remove** method of the **TempVars** object.</span></span>

## <a name="example"></a><span data-ttu-id="4153a-120">示例</span><span class="sxs-lookup"><span data-stu-id="4153a-120">Example</span></span>

<span data-ttu-id="4153a-121">下面的宏演示如何创建一个临时变量，在条件和消息框中使用它，然后使用 **RemoveTempVar** 操作删除该临时变量。</span><span class="sxs-lookup"><span data-stu-id="4153a-121">The following macro demonstrates how to create a temporary variable, use it in a condition and a message box, and then remove the temporary variable by using the **RemoveTempVar** action.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="4153a-122">条件</span><span class="sxs-lookup"><span data-stu-id="4153a-122">Condition</span></span></p></th>
<th><p><span data-ttu-id="4153a-123">操作</span><span class="sxs-lookup"><span data-stu-id="4153a-123">Action</span></span></p></th>
<th><p><span data-ttu-id="4153a-124">参数</span><span class="sxs-lookup"><span data-stu-id="4153a-124">Arguments</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="4153a-125"><strong>SetTempVar</strong></span><span class="sxs-lookup"><span data-stu-id="4153a-125"><strong>SetTempVar</strong></span></span></p></td>
<td><p><span data-ttu-id="4153a-126"><strong>名称</strong>： MyVar<strong>表达式</strong>： InputBox (&quot;输入非零数。&quot;)</span><span class="sxs-lookup"><span data-stu-id="4153a-126"><strong>Name</strong>: MyVar<strong>Expression</strong>: InputBox(&quot;Enter a non-zero number.&quot;)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4153a-127">[TempVars] ！[MyVar]&lt; &gt;0</span><span class="sxs-lookup"><span data-stu-id="4153a-127">[TempVars]![MyVar]&lt;&gt;0</span></span></p></td>
<td><p><span data-ttu-id="4153a-128"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="4153a-128"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="4153a-129"><strong>消息</strong>: =&quot;您输入&quot; &amp; [TempVars] ！[MyVar]&amp; &quot;.&quot;<strong>发嘟嘟声</strong>： <strong>YesType</strong>：<strong>信息</strong></span><span class="sxs-lookup"><span data-stu-id="4153a-129"><strong>Message</strong>: =&quot;You entered &quot; &amp; [TempVars]![MyVar] &amp; &quot;.&quot;<strong>Beep</strong>: <strong>YesType</strong>: <strong>Information</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="4153a-130"><strong>RemoveTempVar</strong></span><span class="sxs-lookup"><span data-stu-id="4153a-130"><strong>RemoveTempVar</strong></span></span></p></td>
<td><p><span data-ttu-id="4153a-131"><strong>名称</strong>：MyVar</span><span class="sxs-lookup"><span data-stu-id="4153a-131"><strong>Name</strong>: MyVar</span></span></p></td>
</tr>
</tbody>
</table>

