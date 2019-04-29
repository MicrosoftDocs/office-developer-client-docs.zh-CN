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
ms.openlocfilehash: 5256efbff734d4555ac263dd330e3349c789cd74
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406974"
---
# <a name="dtblcombobox"></a><span data-ttu-id="93e8b-103">DTBLCOMBOBOX</span><span class="sxs-lookup"><span data-stu-id="93e8b-103">DTBLCOMBOBOX</span></span>

  
  
<span data-ttu-id="93e8b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="93e8b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="93e8b-105">介绍将在从显示表生成的对话框中使用的组合框控件。</span><span class="sxs-lookup"><span data-stu-id="93e8b-105">Describes a combo box control that will be used in a dialog box built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="93e8b-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="93e8b-106">Header file:</span></span>  <br/> |<span data-ttu-id="93e8b-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="93e8b-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="93e8b-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="93e8b-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="93e8b-109">SizedDtblComboBox</span><span class="sxs-lookup"><span data-stu-id="93e8b-109">SizedDtblComboBox</span></span>](sizeddtblcombobox.md) <br/> |
   
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

## <a name="members"></a><span data-ttu-id="93e8b-110">Members</span><span class="sxs-lookup"><span data-stu-id="93e8b-110">Members</span></span>

 <span data-ttu-id="93e8b-111">**ulbLpszCharsAllowed**</span><span class="sxs-lookup"><span data-stu-id="93e8b-111">**ulbLpszCharsAllowed**</span></span>
  
> <span data-ttu-id="93e8b-112">从**DTBLCOMBOBOX**结构的开头到一个字符字符串筛选器的偏移量, 该字符串筛选器描述可在组合框的编辑控件中输入的字符的限制 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="93e8b-112">An offset from the start of the **DTBLCOMBOBOX** structure to a character string filter that describes restrictions, if any, to the characters that can be entered into the combo box's edit control.</span></span> <span data-ttu-id="93e8b-113">筛选器不会解释为正则表达式, 并且将相同的筛选器应用于每个输入的字符。</span><span class="sxs-lookup"><span data-stu-id="93e8b-113">The filter is not interpreted as a regular expression and the same filter is applied to every character entered.</span></span> <span data-ttu-id="93e8b-114">筛选器的格式如下所示:</span><span class="sxs-lookup"><span data-stu-id="93e8b-114">The format of the filter is as follows:</span></span> 
    
|<span data-ttu-id="93e8b-115">**字符**</span><span class="sxs-lookup"><span data-stu-id="93e8b-115">**Character**</span></span>|<span data-ttu-id="93e8b-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="93e8b-116">**Description**</span></span>|
|:-----|:-----|
| `*` <br/> |<span data-ttu-id="93e8b-117">允许使用任何字符 (例如, `"*"`)。</span><span class="sxs-lookup"><span data-stu-id="93e8b-117">Any character is allowed (for example,  `"*"`).</span></span>  <br/> |
| `[ ]` <br/> |<span data-ttu-id="93e8b-118">定义一组字符 (例如`"[0123456789]"`)。</span><span class="sxs-lookup"><span data-stu-id="93e8b-118">Defines a set of characters (for example,  `"[0123456789]"`).</span></span>  <br/> |
| `-` <br/> |<span data-ttu-id="93e8b-119">指示字符的范围 (例如, `"[a-z]"`)。</span><span class="sxs-lookup"><span data-stu-id="93e8b-119">Indicates a range of characters (for example,  `"[a-z]"`).</span></span>  <br/> |
| `~` <br/> |<span data-ttu-id="93e8b-120">指示不允许使用这些字符。</span><span class="sxs-lookup"><span data-stu-id="93e8b-120">Indicates that these characters are not allowed.</span></span> <span data-ttu-id="93e8b-121">(例如, `"[~0-9]"`)。</span><span class="sxs-lookup"><span data-stu-id="93e8b-121">(for example,  `"[~0-9]"`).</span></span>  <br/> |
| `\` <br/> |<span data-ttu-id="93e8b-122">用于引用前面的任何符号 (例如, `"[\-\\\[\]]"`允许-、 \, [和] 字符)。</span><span class="sxs-lookup"><span data-stu-id="93e8b-122">Used to quote any of the previous symbols (for example,  `"[\-\\\[\]]"` means -, \, [, and ] characters are allowed).</span></span>  <br/> |
   
 <span data-ttu-id="93e8b-123">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="93e8b-123">**ulFlags**</span></span>
  
> <span data-ttu-id="93e8b-124">用于指定字符字符串筛选器格式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="93e8b-124">Bitmask of flags used to designate the format of the character string filter.</span></span> <span data-ttu-id="93e8b-125">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="93e8b-125">The following flag can be set:</span></span>
    
<span data-ttu-id="93e8b-126">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="93e8b-126">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="93e8b-127">筛选器采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="93e8b-127">The filter is in Unicode format.</span></span> <span data-ttu-id="93e8b-128">如果未设置 MAPI_UNICODE 标志, 则筛选器将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="93e8b-128">If the MAPI_UNICODE flag is not set, the filter is in ANSI format.</span></span>
    
 <span data-ttu-id="93e8b-129">**ulNumCharsAllowed**</span><span class="sxs-lookup"><span data-stu-id="93e8b-129">**ulNumCharsAllowed**</span></span>
  
> <span data-ttu-id="93e8b-130">可在组合框的文本框中输入的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="93e8b-130">Maximum number of characters that can be entered in the combo box's text box.</span></span>
    
 <span data-ttu-id="93e8b-131">**ulPRPropertyName**</span><span class="sxs-lookup"><span data-stu-id="93e8b-131">**ulPRPropertyName**</span></span>
  
> <span data-ttu-id="93e8b-132">类型为 PT_TSTRING 的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="93e8b-132">Property tag for a property of type PT_TSTRING.</span></span> 
    
 <span data-ttu-id="93e8b-133">**ulPRTableName**</span><span class="sxs-lookup"><span data-stu-id="93e8b-133">**ulPRTableName**</span></span>
  
> <span data-ttu-id="93e8b-134">PT_OBJECT 类型的属性的属性标记, 可以通过**OpenProperty**调用使用**IMAPITable**接口打开该属性。</span><span class="sxs-lookup"><span data-stu-id="93e8b-134">Property tag for a property of type PT_OBJECT on which an **IMAPITable** interface can be opened by using an **OpenProperty** call.</span></span> <span data-ttu-id="93e8b-135">该表必须有一列的属性与**ulPRPropertyName**成员标识的属性的类型相同。</span><span class="sxs-lookup"><span data-stu-id="93e8b-135">The table must have one column with a property that is the same type as the property identified by the **ulPRPropertyName** member.</span></span> <span data-ttu-id="93e8b-136">该表的行用于填充列表。</span><span class="sxs-lookup"><span data-stu-id="93e8b-136">The rows of the table are used to populate the list.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="93e8b-137">说明</span><span class="sxs-lookup"><span data-stu-id="93e8b-137">Remarks</span></span>

<span data-ttu-id="93e8b-138">**DTBLCOMBOBOX**结构描述一个组合框, 该控件由一个列表和一个选择字段组成。</span><span class="sxs-lookup"><span data-stu-id="93e8b-138">A **DTBLCOMBOBOX** structure describes a combo box a control that consists of a list and a selection field.</span></span> <span data-ttu-id="93e8b-139">该列表显示用户可以从中选择的信息, 并且选择字段显示当前所选内容。</span><span class="sxs-lookup"><span data-stu-id="93e8b-139">The list presents the information from which a user can select, and the selection field displays the current selection.</span></span> <span data-ttu-id="93e8b-140">选择字段是一个编辑控件, 还可用于输入列表中尚未存在的文本。</span><span class="sxs-lookup"><span data-stu-id="93e8b-140">The selection field is an edit control that can also be used to enter text not already in the list.</span></span> 
  
<span data-ttu-id="93e8b-141">这两个属性标记成员协同工作, 以使用编辑控件来协调列表显示。</span><span class="sxs-lookup"><span data-stu-id="93e8b-141">The two property tag members work together to coordinate the list display with the edit control.</span></span> <span data-ttu-id="93e8b-142">当 MAPI 首次显示组合框时, 它会调用与显示表相关联的**IMAPIProp**实现的**OpenProperty**方法, 以检索**ulPRTableName**成员所表示的表。</span><span class="sxs-lookup"><span data-stu-id="93e8b-142">When MAPI first displays the combo box, it calls the **OpenProperty** method of the **IMAPIProp** implementation that is associated with the display table to retrieve the table represented by the **ulPRTableName** member.</span></span> <span data-ttu-id="93e8b-143">此表包含一个列, 该列包含**ulPRPropertyName**成员所表示的属性的值。</span><span class="sxs-lookup"><span data-stu-id="93e8b-143">This table has one column a column that contains values for the property represented by the **ulPRPropertyName** member.</span></span> <span data-ttu-id="93e8b-144">因此, 此列的类型必须与**ulPRPropertyName**属性的类型相同, 并且这两个列都必须是字符串。</span><span class="sxs-lookup"><span data-stu-id="93e8b-144">Therefore, this column must be of the same type as the **ulPRPropertyName** property and both columns must be character strings.</span></span> 
  
<span data-ttu-id="93e8b-145">该列的值将显示在组合框的列表部分。</span><span class="sxs-lookup"><span data-stu-id="93e8b-145">The values for the column are displayed in the list section of the combo box.</span></span> <span data-ttu-id="93e8b-146">因此, **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) 不是**ulPRPropertyName**的有效属性标记。</span><span class="sxs-lookup"><span data-stu-id="93e8b-146">Therefore, **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) is not a valid property tag for **ulPRPropertyName**.</span></span> <span data-ttu-id="93e8b-147">当用户选择其中一个行或在文本框中输入新数据时, **ulPRPropertyName**属性设置为所选或输入的值。</span><span class="sxs-lookup"><span data-stu-id="93e8b-147">When a user either selects one of the rows or enters new data into the text box, the **ulPRPropertyName** property is set to the selected or entered value.</span></span> 
  
<span data-ttu-id="93e8b-148">若要显示编辑控件的初始值, MAPI 调用[IMAPIProp:: GetProps](imapiprop-getprops.md)检索显示表的属性值。</span><span class="sxs-lookup"><span data-stu-id="93e8b-148">To display an initial value for the edit control, MAPI calls [IMAPIProp::GetProps](imapiprop-getprops.md) to retrieve the property values for the display table.</span></span> <span data-ttu-id="93e8b-149">如果其中一个检索的属性与**ulPRPropertyName**成员所表示的属性相匹配, 则其值将成为初始值。</span><span class="sxs-lookup"><span data-stu-id="93e8b-149">If one of the retrieved properties matches the property represented by the **ulPRPropertyName** member, its value becomes the initial value.</span></span> 
  
<span data-ttu-id="93e8b-150">有关显示表的概述, 请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="93e8b-150">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="93e8b-151">有关如何实现显示表的信息, 请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="93e8b-151">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="93e8b-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="93e8b-152">See also</span></span>



[<span data-ttu-id="93e8b-153">DTCTL</span><span class="sxs-lookup"><span data-stu-id="93e8b-153">DTCTL</span></span>](dtctl.md)
  
[<span data-ttu-id="93e8b-154">PidTagControlType 规范属性</span><span class="sxs-lookup"><span data-stu-id="93e8b-154">PidTagControlType Canonical Property</span></span>](pidtagcontroltype-canonical-property.md)


[<span data-ttu-id="93e8b-155">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="93e8b-155">MAPI Structures</span></span>](mapi-structures.md)

