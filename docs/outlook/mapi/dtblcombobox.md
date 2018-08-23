---
title: DTBLCOMBOBOX
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLCOMBOBOX
api_type:
- COM
ms.assetid: 73b68614-6aca-4669-b879-5631c5d6483c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a8d2f2c82c61280bae88c715f8ffae19e10f00f9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577840"
---
# <a name="dtblcombobox"></a><span data-ttu-id="b0013-103">DTBLCOMBOBOX</span><span class="sxs-lookup"><span data-stu-id="b0013-103">DTBLCOMBOBOX</span></span>

  
  
<span data-ttu-id="b0013-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b0013-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b0013-105">描述将显示表中生成的对话框中使用的组合框控件。</span><span class="sxs-lookup"><span data-stu-id="b0013-105">Describes a combo box control that will be used in a dialog box built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b0013-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="b0013-106">Header file:</span></span>  <br/> |<span data-ttu-id="b0013-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b0013-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="b0013-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="b0013-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="b0013-109">SizedDtblComboBox</span><span class="sxs-lookup"><span data-stu-id="b0013-109">SizedDtblComboBox</span></span>](sizeddtblcombobox.md) <br/> |
   
```cpp
typedef struct _DTBLCOMBOBOX
{
  ULONG ulbLpszCharsAllowed;
  ULONG ulFlags;
  ULONG ulNumCharsAllowed;
  ULONG ulPRPropertyName;
  ULONG ulPRTableName;
} DTBLCOMBOBOX, FAR *LPDTBLCOMBOBOX;

```

## <a name="members"></a><span data-ttu-id="b0013-110">Members</span><span class="sxs-lookup"><span data-stu-id="b0013-110">Members</span></span>

 <span data-ttu-id="b0013-111">**ulbLpszCharsAllowed**</span><span class="sxs-lookup"><span data-stu-id="b0013-111">**ulbLpszCharsAllowed**</span></span>
  
> <span data-ttu-id="b0013-112">从**DTBLCOMBOBOX**结构开始到字符的字符串筛选器，描述限制，如果任何，可以在组合框中输入的字符编辑控件的偏移量。</span><span class="sxs-lookup"><span data-stu-id="b0013-112">An offset from the start of the **DTBLCOMBOBOX** structure to a character string filter that describes restrictions, if any, to the characters that can be entered into the combo box's edit control.</span></span> <span data-ttu-id="b0013-113">筛选器将不被解释为一个正则表达式和相同的筛选器应用于输入每个字符。</span><span class="sxs-lookup"><span data-stu-id="b0013-113">The filter is not interpreted as a regular expression and the same filter is applied to every character entered.</span></span> <span data-ttu-id="b0013-114">筛选器的格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="b0013-114">The format of the filter is as follows:</span></span> 
    
|<span data-ttu-id="b0013-115">**字符**</span><span class="sxs-lookup"><span data-stu-id="b0013-115">**Character**</span></span>|<span data-ttu-id="b0013-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="b0013-116">**Description**</span></span>|
|:-----|:-----|
| `*` <br/> |<span data-ttu-id="b0013-117">允许任何字符 (例如， `"*"`)。</span><span class="sxs-lookup"><span data-stu-id="b0013-117">Any character is allowed (for example,  `"*"`).</span></span>  <br/> |
| `[ ]` <br/> |<span data-ttu-id="b0013-118">定义一组字符 (例如， `"[0123456789]"`)。</span><span class="sxs-lookup"><span data-stu-id="b0013-118">Defines a set of characters (for example,  `"[0123456789]"`).</span></span>  <br/> |
| `-` <br/> |<span data-ttu-id="b0013-119">指示某个范围的字符 (例如， `"[a-z]"`)。</span><span class="sxs-lookup"><span data-stu-id="b0013-119">Indicates a range of characters (for example,  `"[a-z]"`).</span></span>  <br/> |
| `~` <br/> |<span data-ttu-id="b0013-120">指示不允许这些字符。</span><span class="sxs-lookup"><span data-stu-id="b0013-120">Indicates that these characters are not allowed.</span></span> <span data-ttu-id="b0013-121">(例如， `"[~0-9]"`)。</span><span class="sxs-lookup"><span data-stu-id="b0013-121">(for example,  `"[~0-9]"`).</span></span>  <br/> |
| `\` <br/> |<span data-ttu-id="b0013-122">用于 quote 任何以前符号 (例如，`"[\-\\\[\]]"`是指-， \, [，和] 允许字符)。</span><span class="sxs-lookup"><span data-stu-id="b0013-122">Used to quote any of the previous symbols (for example,  `"[\-\\\[\]]"` means -, \, [, and ] characters are allowed).</span></span>  <br/> |
   
 <span data-ttu-id="b0013-123">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="b0013-123">**ulFlags**</span></span>
  
> <span data-ttu-id="b0013-124">用于指定格式的字符的字符串筛选器的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="b0013-124">Bitmask of flags used to designate the format of the character string filter.</span></span> <span data-ttu-id="b0013-125">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="b0013-125">The following flag can be set:</span></span>
    
<span data-ttu-id="b0013-126">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b0013-126">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="b0013-127">筛选器在 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="b0013-127">The filter is in Unicode format.</span></span> <span data-ttu-id="b0013-128">如果未设置 MAPI_UNICODE 标志，筛选器为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="b0013-128">If the MAPI_UNICODE flag is not set, the filter is in ANSI format.</span></span>
    
 <span data-ttu-id="b0013-129">**ulNumCharsAllowed**</span><span class="sxs-lookup"><span data-stu-id="b0013-129">**ulNumCharsAllowed**</span></span>
  
> <span data-ttu-id="b0013-130">可以在组合框的文本框中输入的字符的最大数量。</span><span class="sxs-lookup"><span data-stu-id="b0013-130">Maximum number of characters that can be entered in the combo box's text box.</span></span>
    
 <span data-ttu-id="b0013-131">**ulPRPropertyName**</span><span class="sxs-lookup"><span data-stu-id="b0013-131">**ulPRPropertyName**</span></span>
  
> <span data-ttu-id="b0013-132">属性标记类型 PT_TSTRING 的属性。</span><span class="sxs-lookup"><span data-stu-id="b0013-132">Property tag for a property of type PT_TSTRING.</span></span> 
    
 <span data-ttu-id="b0013-133">**ulPRTableName**</span><span class="sxs-lookup"><span data-stu-id="b0013-133">**ulPRTableName**</span></span>
  
> <span data-ttu-id="b0013-134">属性标记类型 PT_OBJECT 在其可以使用**OpenProperty**呼叫打开**IMAPITable**接口的属性。</span><span class="sxs-lookup"><span data-stu-id="b0013-134">Property tag for a property of type PT_OBJECT on which an **IMAPITable** interface can be opened by using an **OpenProperty** call.</span></span> <span data-ttu-id="b0013-135">表中必须包含一个列是由**ulPRPropertyName**成员标识的属性类型相同的属性。</span><span class="sxs-lookup"><span data-stu-id="b0013-135">The table must have one column with a property that is the same type as the property identified by the **ulPRPropertyName** member.</span></span> <span data-ttu-id="b0013-136">Table 的行用于填充列表。</span><span class="sxs-lookup"><span data-stu-id="b0013-136">The rows of the table are used to populate the list.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="b0013-137">注解</span><span class="sxs-lookup"><span data-stu-id="b0013-137">Remarks</span></span>

<span data-ttu-id="b0013-138">**DTBLCOMBOBOX**结构介绍组合框列表和选择字段组成的控件。</span><span class="sxs-lookup"><span data-stu-id="b0013-138">A **DTBLCOMBOBOX** structure describes a combo box a control that consists of a list and a selection field.</span></span> <span data-ttu-id="b0013-139">列表呈现从中可以选择用户，并选择字段显示当前选定内容的信息。</span><span class="sxs-lookup"><span data-stu-id="b0013-139">The list presents the information from which a user can select, and the selection field displays the current selection.</span></span> <span data-ttu-id="b0013-140">选择字段是还可用于在列表中尚未输入文本编辑控件。</span><span class="sxs-lookup"><span data-stu-id="b0013-140">The selection field is an edit control that can also be used to enter text not already in the list.</span></span> 
  
<span data-ttu-id="b0013-141">两个属性标记成员协同工作来协调列表显示与编辑控件。</span><span class="sxs-lookup"><span data-stu-id="b0013-141">The two property tag members work together to coordinate the list display with the edit control.</span></span> <span data-ttu-id="b0013-142">当 MAPI 首次显示组合框中时，它会调用与要检索表示由**ulPRTableName**成员的表的显示表相关联的**IMAPIProp**实现**OpenProperty**方法。</span><span class="sxs-lookup"><span data-stu-id="b0013-142">When MAPI first displays the combo box, it calls the **OpenProperty** method of the **IMAPIProp** implementation that is associated with the display table to retrieve the table represented by the **ulPRTableName** member.</span></span> <span data-ttu-id="b0013-143">此表有一个列包含由**ulPRPropertyName**成员属性的值的列。</span><span class="sxs-lookup"><span data-stu-id="b0013-143">This table has one column a column that contains values for the property represented by the **ulPRPropertyName** member.</span></span> <span data-ttu-id="b0013-144">因此，此列必须**ulPRPropertyName**属性类型相同的并且这两个列必须字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="b0013-144">Therefore, this column must be of the same type as the **ulPRPropertyName** property and both columns must be character strings.</span></span> 
  
<span data-ttu-id="b0013-145">组合框列表部分中显示的列的值。</span><span class="sxs-lookup"><span data-stu-id="b0013-145">The values for the column are displayed in the list section of the combo box.</span></span> <span data-ttu-id="b0013-146">因此， **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) 不是有效属性标记为**ulPRPropertyName**。</span><span class="sxs-lookup"><span data-stu-id="b0013-146">Therefore, **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) is not a valid property tag for **ulPRPropertyName**.</span></span> <span data-ttu-id="b0013-147">当用户选择行之一，或在文本框中输入新的数据时， **ulPRPropertyName**属性设置为所选或输入值。</span><span class="sxs-lookup"><span data-stu-id="b0013-147">When a user either selects one of the rows or enters new data into the text box, the **ulPRPropertyName** property is set to the selected or entered value.</span></span> 
  
<span data-ttu-id="b0013-148">若要显示的编辑控件的初始值，MAPI 调用[IMAPIProp::GetProps](imapiprop-getprops.md)检索显示表的属性值。</span><span class="sxs-lookup"><span data-stu-id="b0013-148">To display an initial value for the edit control, MAPI calls [IMAPIProp::GetProps](imapiprop-getprops.md) to retrieve the property values for the display table.</span></span> <span data-ttu-id="b0013-149">如果检索到的属性之一与匹配由**ulPRPropertyName**成员的属性，则其值成为的初始值。</span><span class="sxs-lookup"><span data-stu-id="b0013-149">If one of the retrieved properties matches the property represented by the **ulPRPropertyName** member, its value becomes the initial value.</span></span> 
  
<span data-ttu-id="b0013-150">显示表的概述，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="b0013-150">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="b0013-151">有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="b0013-151">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b0013-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0013-152">See also</span></span>



[<span data-ttu-id="b0013-153">DTCTL</span><span class="sxs-lookup"><span data-stu-id="b0013-153">DTCTL</span></span>](dtctl.md)
  
[<span data-ttu-id="b0013-154">PidTagControlType 规范属性</span><span class="sxs-lookup"><span data-stu-id="b0013-154">PidTagControlType Canonical Property</span></span>](pidtagcontroltype-canonical-property.md)


[<span data-ttu-id="b0013-155">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="b0013-155">MAPI Structures</span></span>](mapi-structures.md)

