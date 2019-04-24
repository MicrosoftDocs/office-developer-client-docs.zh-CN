---
title: SetProperty 宏操作
TOCTitle: SetProperty macro action
ms:assetid: 58d2eac3-35b2-e9f8-47e0-62c9b52f2c24
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194340(v=office.15)
ms:contentKeyID: 48545004
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm139044
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: c5972ad630efe3afe27565924c7c6a8a2230a9f2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32314572"
---
# <a name="setproperty-macro-action"></a><span data-ttu-id="f2664-102">SetProperty 宏操作</span><span class="sxs-lookup"><span data-stu-id="f2664-102">SetProperty macro action</span></span>

<span data-ttu-id="f2664-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="f2664-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="f2664-104">可以使用 **SetProperty** 操作设置窗体或报表上控件的属性。</span><span class="sxs-lookup"><span data-stu-id="f2664-104">You can use the **SetProperty** action to set a property for a control on a form or a report.</span></span>

## <a name="setting"></a><span data-ttu-id="f2664-105">Setting</span><span class="sxs-lookup"><span data-stu-id="f2664-105">Setting</span></span>

<span data-ttu-id="f2664-106">**SetProperty** 操作具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="f2664-106">The **SetProperty** action has the following arguments.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="f2664-107">操作参数</span><span class="sxs-lookup"><span data-stu-id="f2664-107">Action argument</span></span></p></th>
<th><p><span data-ttu-id="f2664-108">说明</span><span class="sxs-lookup"><span data-stu-id="f2664-108">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2664-109">控件名称</span><span class="sxs-lookup"><span data-stu-id="f2664-109">Control Name</span></span></p></td>
<td><p><span data-ttu-id="f2664-110">请键入要为其设置属性值的字段或控件的名称。</span><span class="sxs-lookup"><span data-stu-id="f2664-110">Type the name of the field or control for which you want to set the property value.</span></span> <span data-ttu-id="f2664-111">仅使用控件名称，不要使用完整语法。</span><span class="sxs-lookup"><span data-stu-id="f2664-111">Use only the control name, not the full syntax.</span></span> <span data-ttu-id="f2664-112">将此参数留空，以便为当前窗体或报表设置属性。</span><span class="sxs-lookup"><span data-stu-id="f2664-112">Leave this argument blank to set the property for the current form or report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2664-113">属性</span><span class="sxs-lookup"><span data-stu-id="f2664-113">Property</span></span></p></td>
<td><p><span data-ttu-id="f2664-p102">请选择要设置的属性。有关可以使用此操作设置的属性的列表，请参阅本文的<strong>说明</strong>部分。</span><span class="sxs-lookup"><span data-stu-id="f2664-p102">Select the property that you want to set. See the <strong>Remarks</strong> section in this article for a list of the properties that can be set by using this action.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2664-116">值</span><span class="sxs-lookup"><span data-stu-id="f2664-116">Value</span></span></p></td>
<td><p><span data-ttu-id="f2664-p103">请键入要设置的属性值。对于值为“是”或“否”的属性，使用 <strong>-1</strong> 代表“是”，<strong>0</strong> 代表“否”。</span><span class="sxs-lookup"><span data-stu-id="f2664-p103">Type the value that the property is to be set to. For properties whose values are either Yes or No, use <strong>-1</strong> for Yes and <strong>0</strong> for No.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a><span data-ttu-id="f2664-119">注解</span><span class="sxs-lookup"><span data-stu-id="f2664-119">Remarks</span></span>

- <span data-ttu-id="f2664-120">可以使用 **SetProperty** 操作设置控件的下列属性：“已启用”\*\*\*\*、“可见”\*\*\*\*、“锁定”\*\*\*\*、“靠左”\*\*\*\*、“靠上”\*\*\*\*、“宽度”\*\*\*\*、“高度”\*\*\*\*、“前景色”\*\*\*\*、“背景色”\*\*\*\* 或“标题”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f2664-120">You can use the **SetProperty** action to set the following properties of a control: **Enabled**, **Visible**, **Locked**, **Left**, **Top**, **Width**, **Height**, **Fore Color**, **Back Color**, or **Caption**.</span></span>

- <span data-ttu-id="f2664-121">如果为***值*** 参数输入的值无效，则不会发生错误，但 Access 可能会根据解释该参数的方式将属性更改为其他值。</span><span class="sxs-lookup"><span data-stu-id="f2664-121">If you enter an invalid value for the ***Value*** argument, no error occurs, but Access might change the property to a different value, depending on how it interprets the argument.</span></span>

- <span data-ttu-id="f2664-p104">只有在以下情况下才能在独立的宏中使用 **SetProperty** 操作：该操作前面的一个操作选择包含您要为其设置属性的控件的窗体或报表。如果窗体或报表未打开，可以使用 **OpenForm** 或 **OpenReport** 操作打开并选择它。如果窗体或报表已经打开，可以使用 **SelectObject** 操作选择它。接下来，可以使用 **SetProperty** 操作设置属性。如果在一个宏中使用 **SetProperty** 操作，而该宏嵌入其中的控件与您要为其设置属性的控件在相同的窗体或报表上，则选择对象不是必需的。</span><span class="sxs-lookup"><span data-stu-id="f2664-p104">You can use the **SetProperty** action in a stand-alone macro only if you precede it with an action that selects the form or report containing the control for which you are setting the property. If the form or report is not open, you can use the **OpenForm** or **OpenReport** action to open and select it. If the form or report is already open, you can use the **SelectObject** action to select it. You can then use the **SetProperty** action to set the property. Selecting the object is not necessary if you use the **SetProperty** action in a macro which is embedded in a control on the same form or report as the control for which you are setting the property.</span></span>

- <span data-ttu-id="f2664-127">要在 VBA 模块中运行 **SetProperty** 操作，请使用 **DoCmd** 对象的 **SetProperty** 方法。</span><span class="sxs-lookup"><span data-stu-id="f2664-127">To run the **SetProperty** action in a VBA module, use the **SetProperty** method of the **DoCmd** object.</span></span>

## <a name="example"></a><span data-ttu-id="f2664-128">示例</span><span class="sxs-lookup"><span data-stu-id="f2664-128">Example</span></span>

<span data-ttu-id="f2664-129">下面的示例演示如何使用 SetProperty 操作切换**MyTextBox**文本框的可见性。</span><span class="sxs-lookup"><span data-stu-id="f2664-129">The following example shows how to use the SetProperty action to toggle the visibility of the **MyTextBox** text box.</span></span>

<span data-ttu-id="f2664-130">**示例代码提供方：**[Microsoft Access 2010 程序员参考](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125)。</span><span class="sxs-lookup"><span data-stu-id="f2664-130">**Sample code provided by** the [Microsoft Access 2010 Programmer’s Reference](https://www.amazon.com/Microsoft-Access-2010-Programmers-Reference/dp/8126528125).</span></span>

```vb
    Submacro: TestVisible
        SetProperty
            Control Name Text40
            Property Visible
            Value =Not[Text40].[Visible]
    End Submacro
```
