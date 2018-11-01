---
title: SetLocalVar 宏操作
TOCTitle: SetLocalVar Macro Action
ms:assetid: 8a6af395-0f76-72e2-37f3-2cff22a38b3c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197097(v=office.15)
ms:contentKeyID: 48546190
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm176660
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 299227553481c4f149827c31078111db7b427f7f
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25886639"
---
# <a name="setlocalvar-macro-action"></a><span data-ttu-id="0a6ef-102">SetLocalVar 宏操作</span><span class="sxs-lookup"><span data-stu-id="0a6ef-102">SetLocalVar Macro Action</span></span>


<span data-ttu-id="0a6ef-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="0a6ef-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="0a6ef-104">**SetLocalVar** 操作可创建一个临时变量并将其设置为特定值。</span><span class="sxs-lookup"><span data-stu-id="0a6ef-104">The **SetLocalVar** action creates a temporary variable and set it to a specific value.</span></span>

## <a name="setting"></a><span data-ttu-id="0a6ef-105">设置</span><span class="sxs-lookup"><span data-stu-id="0a6ef-105">Setting</span></span>

<span data-ttu-id="0a6ef-106">**SetLocalVar** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="0a6ef-106">The **SetLocalVar** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="0a6ef-107">参数</span><span class="sxs-lookup"><span data-stu-id="0a6ef-107">Argument</span></span></p></th>
<th><p><span data-ttu-id="0a6ef-108">是否必需</span><span class="sxs-lookup"><span data-stu-id="0a6ef-108">Required</span></span></p></th>
<th><p><span data-ttu-id="0a6ef-109">说明</span><span class="sxs-lookup"><span data-stu-id="0a6ef-109">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0a6ef-110"><strong>Name</strong></span><span class="sxs-lookup"><span data-stu-id="0a6ef-110"><strong>Name</strong></span></span></p></td>
<td><p><span data-ttu-id="0a6ef-111">是</span><span class="sxs-lookup"><span data-stu-id="0a6ef-111">Yes</span></span></p></td>
<td><p><span data-ttu-id="0a6ef-112">一个用于指定变量名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="0a6ef-112">A string that specifies the name of the variable.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0a6ef-113"><strong>Expression</strong></span><span class="sxs-lookup"><span data-stu-id="0a6ef-113"><strong>Expression</strong></span></span></p></td>
<td><p><span data-ttu-id="0a6ef-114">是</span><span class="sxs-lookup"><span data-stu-id="0a6ef-114">Yes</span></span></p></td>
<td><p><span data-ttu-id="0a6ef-115">一个表达式，用于设置为临时变量的值。</span><span class="sxs-lookup"><span data-stu-id="0a6ef-115">An expression that will be used to set the value for this temporary variable.</span></span> <span data-ttu-id="0a6ef-116">不在表达式前面放等号 （=）。</span><span class="sxs-lookup"><span data-stu-id="0a6ef-116">Do not precede the expression with the equal sign (=).</span></span> <span data-ttu-id="0a6ef-117">您可以单击<strong>生成</strong>按钮以使用<strong>表达式生成器</strong>设置此参数。</span><span class="sxs-lookup"><span data-stu-id="0a6ef-117">You can click the <strong>Build</strong> button to use the <strong>Expression Builder</strong> to set this argument.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="0a6ef-118">注释</span><span class="sxs-lookup"><span data-stu-id="0a6ef-118">Remarks</span></span>

<span data-ttu-id="0a6ef-p102">由 **SetLocalVar** 操作创建的变量只能在定义这些变量的宏中使用。使用 **[SetTempVar](settempvar-macro-action.md)** 操作可定义可在其他宏、事件过程、窗体或报表中使用的变量。</span><span class="sxs-lookup"><span data-stu-id="0a6ef-p102">Variables created by the **SetLocalVar** action can be used only in the macro in which they are defined. Use the **[SetTempVar](settempvar-macro-action.md)** action to define a variable that can be used in another macro, in an event procedure, or on a form or report.</span></span>

<span data-ttu-id="0a6ef-p103">创建临时变量后，即可在表达式中引用该变量。例如，如果创建一个名为 TotalAmount 的临时变量，则可以使用下面的语法将该变量用作文本框的控件来源。</span><span class="sxs-lookup"><span data-stu-id="0a6ef-p103">Once a temporary variable has been created, you can refer to it in an expression. For example, if you created a temporary variable named TotalAmount, you could use the variable as the control source for a text box by using the following syntax.</span></span>

`=[LocalVars]![TotalAmount]`


> [!NOTE]
> <P><span data-ttu-id="0a6ef-123">[!注释] 在数据宏中，您不必使用 LocalVars 集合来引用变量。</span><span class="sxs-lookup"><span data-stu-id="0a6ef-123">In a Data Macro, you do not have to use the LocalVars collection to refer to a variable.</span></span> <span data-ttu-id="0a6ef-124">例如，如果您在一个名为 TotalAmount 的数据宏创建一个临时变量，您无法用作变量的控件来源文本框中使用以下语法</span><span class="sxs-lookup"><span data-stu-id="0a6ef-124">For example, if you created a temporary variable in a Data Macro named TotalAmount, you could use the variable as the control source for a text box by using the following syntax</span></span><BR><span data-ttu-id="0a6ef-125">= [TotalAmount]</span><span class="sxs-lookup"><span data-stu-id="0a6ef-125">=[TotalAmount]</span></span></P>


