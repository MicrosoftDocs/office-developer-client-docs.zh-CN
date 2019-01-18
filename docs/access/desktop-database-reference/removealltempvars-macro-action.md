---
title: RemoveAllTempVars 宏操作
TOCTitle: RemoveAllTempVars macro action
ms:assetid: 409fd836-4a53-cefd-4264-8cee0fa8ac52
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192877(v=office.15)
ms:contentKeyID: 48544430
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm117413
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: eade809a6e3982dc0dc4cf94ae382af72e8f454e
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28705074"
---
# <a name="removealltempvars-macro-action"></a><span data-ttu-id="5df61-102">RemoveAllTempVars 宏操作</span><span class="sxs-lookup"><span data-stu-id="5df61-102">RemoveAllTempVars macro action</span></span>


<span data-ttu-id="5df61-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="5df61-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="5df61-104">可以使用 **RemoveAllTempVars** 操作删除用 **SetTempVar** 操作创建的所有临时变量。</span><span class="sxs-lookup"><span data-stu-id="5df61-104">You can use the **RemoveAllTempVars** action to remove any temporary variables that you created by using the **SetTempVar** action.</span></span>

## <a name="setting"></a><span data-ttu-id="5df61-105">设置</span><span class="sxs-lookup"><span data-stu-id="5df61-105">Setting</span></span>

<span data-ttu-id="5df61-106">**RemoveAllTempVars** 操作不具有任何参数。</span><span class="sxs-lookup"><span data-stu-id="5df61-106">The **RemoveAllTempVars** action does not have any arguments.</span></span>

## <a name="remarks"></a><span data-ttu-id="5df61-107">说明</span><span class="sxs-lookup"><span data-stu-id="5df61-107">Remarks</span></span>

  - <span data-ttu-id="5df61-p101">一次最多可以定义 255 个临时变量。如果您不删除临时变量，它将一直保留在内存中，直到您关闭数据库或项目。在使用完临时变量后，最好将它们删除。</span><span class="sxs-lookup"><span data-stu-id="5df61-p101">You can have up to 255 temporary variables defined at one time. If you do not remove a temporary variable, it will remain in memory until you close the database or project. It is a good practice to remove temporary variables when you are finished using them.</span></span>

  - <span data-ttu-id="5df61-111">在关闭数据库或项目时，Access 会自动删除所有临时变量。</span><span class="sxs-lookup"><span data-stu-id="5df61-111">Access automatically removes all temporary variables when you close the database or project.</span></span>

  - <span data-ttu-id="5df61-112">要删除单个临时变量，请使用 **RemoveTempVar** 操作，并将其参数设置为要删除的临时变量的名称。</span><span class="sxs-lookup"><span data-stu-id="5df61-112">To remove a single temporary variable, use the **RemoveTempVar** action and set its argument to the name of the temporary variable you want to remove.</span></span>

  - <span data-ttu-id="5df61-113">要在 VBA 模块中运行 **RemoveAllTempVars** 操作，请使用 **TempVars** 对象的 **RemoveAll** 方法。</span><span class="sxs-lookup"><span data-stu-id="5df61-113">To run the **RemoveAllTempVars** action in a VBA module, use the **RemoveAll** method of the **TempVars** object.</span></span>

## <a name="example"></a><span data-ttu-id="5df61-114">示例</span><span class="sxs-lookup"><span data-stu-id="5df61-114">Example</span></span>

<span data-ttu-id="5df61-115">下面的宏演示如何创建一个临时变量，在条件和消息框中使用它，然后使用 **RemoveAllTempVars** 操作删除该临时变量。</span><span class="sxs-lookup"><span data-stu-id="5df61-115">The following macro demonstrates how to create a temporary variable, use it in a condition and a message box, and then remove the temporary variable by using the **RemoveAllTempVars** action.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="5df61-116">条件</span><span class="sxs-lookup"><span data-stu-id="5df61-116">Condition</span></span></p></th>
<th><p><span data-ttu-id="5df61-117">操作</span><span class="sxs-lookup"><span data-stu-id="5df61-117">Action</span></span></p></th>
<th><p><span data-ttu-id="5df61-118">参数</span><span class="sxs-lookup"><span data-stu-id="5df61-118">Arguments</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="5df61-119"><strong>SetTempVar</strong></span><span class="sxs-lookup"><span data-stu-id="5df61-119"><strong>SetTempVar</strong></span></span></p></td>
<td><p><span data-ttu-id="5df61-120"><strong>名称</strong>： MyVar<strong>表达式</strong>： InputBox (&quot;输入非零数。&quot;)</span><span class="sxs-lookup"><span data-stu-id="5df61-120"><strong>Name</strong>: MyVar<strong>Expression</strong>: InputBox(&quot;Enter a non-zero number.&quot;)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5df61-121">[TempVars] ！[MyVar]&lt; &gt;0</span><span class="sxs-lookup"><span data-stu-id="5df61-121">[TempVars]![MyVar]&lt;&gt;0</span></span></p></td>
<td><p><span data-ttu-id="5df61-122"><strong>MessageBox</strong></span><span class="sxs-lookup"><span data-stu-id="5df61-122"><strong>MessageBox</strong></span></span></p></td>
<td><p><span data-ttu-id="5df61-123"><strong>消息</strong>: =&quot;您输入&quot; &amp; [TempVars] ！[MyVar]&amp; &quot;.&quot;<strong>发嘟嘟声</strong>： <strong>YesType</strong>：<strong>信息</strong></span><span class="sxs-lookup"><span data-stu-id="5df61-123"><strong>Message</strong>: =&quot;You entered &quot; &amp; [TempVars]![MyVar] &amp; &quot;.&quot;<strong>Beep</strong>: <strong>YesType</strong>: <strong>Information</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="5df61-124"><strong>RemoveAllTempVars</strong></span><span class="sxs-lookup"><span data-stu-id="5df61-124"><strong>RemoveAllTempVars</strong></span></span></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

