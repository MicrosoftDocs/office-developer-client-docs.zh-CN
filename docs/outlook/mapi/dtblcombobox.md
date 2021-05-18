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
# <a name="dtblcombobox"></a><span data-ttu-id="20188-103">DTBLCOMBOBOX</span><span class="sxs-lookup"><span data-stu-id="20188-103">DTBLCOMBOBOX</span></span>

  
  
<span data-ttu-id="20188-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="20188-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="20188-105">描述将在基于显示表构建的对话框中使用的组合框控件。</span><span class="sxs-lookup"><span data-stu-id="20188-105">Describes a combo box control that will be used in a dialog box built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="20188-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="20188-106">Header file:</span></span>  <br/> |<span data-ttu-id="20188-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="20188-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="20188-108">相关宏：</span><span class="sxs-lookup"><span data-stu-id="20188-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="20188-109">SizedDtblComboBox</span><span class="sxs-lookup"><span data-stu-id="20188-109">SizedDtblComboBox</span></span>](sizeddtblcombobox.md) <br/> |
   
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

## <a name="members"></a><span data-ttu-id="20188-110">Members</span><span class="sxs-lookup"><span data-stu-id="20188-110">Members</span></span>

 <span data-ttu-id="20188-111">**ulbLpszCharsAllowed**</span><span class="sxs-lookup"><span data-stu-id="20188-111">**ulbLpszCharsAllowed**</span></span>
  
> <span data-ttu-id="20188-112">从 **DTBLCOMBOBOX** 结构开始到描述可在组合框的编辑控件中输入的字符的限制（如果有）的字符串筛选器的偏移量。</span><span class="sxs-lookup"><span data-stu-id="20188-112">An offset from the start of the **DTBLCOMBOBOX** structure to a character string filter that describes restrictions, if any, to the characters that can be entered into the combo box's edit control.</span></span> <span data-ttu-id="20188-113">筛选器不会解释为正则表达式，并且相同的筛选器将应用于输入的每一个字符。</span><span class="sxs-lookup"><span data-stu-id="20188-113">The filter is not interpreted as a regular expression and the same filter is applied to every character entered.</span></span> <span data-ttu-id="20188-114">筛选器的格式如下：</span><span class="sxs-lookup"><span data-stu-id="20188-114">The format of the filter is as follows:</span></span> 
    
|<span data-ttu-id="20188-115">**字符**</span><span class="sxs-lookup"><span data-stu-id="20188-115">**Character**</span></span>|<span data-ttu-id="20188-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="20188-116">**Description**</span></span>|
|:-----|:-----|
| `*` <br/> |<span data-ttu-id="20188-117">允许任何字符 (例如  `"*"` ，) 。</span><span class="sxs-lookup"><span data-stu-id="20188-117">Any character is allowed (for example,  `"*"`).</span></span>  <br/> |
| `[ ]` <br/> |<span data-ttu-id="20188-118">定义一组字符 (例如  `"[0123456789]"` ，) 。</span><span class="sxs-lookup"><span data-stu-id="20188-118">Defines a set of characters (for example,  `"[0123456789]"`).</span></span>  <br/> |
| `-` <br/> |<span data-ttu-id="20188-119">指示一系列字符 (例如  `"[a-z]"` ，) 。</span><span class="sxs-lookup"><span data-stu-id="20188-119">Indicates a range of characters (for example,  `"[a-z]"`).</span></span>  <br/> |
| `~` <br/> |<span data-ttu-id="20188-120">指示不允许这些字符。</span><span class="sxs-lookup"><span data-stu-id="20188-120">Indicates that these characters are not allowed.</span></span> <span data-ttu-id="20188-121"> (，例如  `"[~0-9]"` ，) 。</span><span class="sxs-lookup"><span data-stu-id="20188-121">(for example,  `"[~0-9]"`).</span></span>  <br/> |
| `\` <br/> |<span data-ttu-id="20188-122">用于引用前面的任何符号 (例如，允许使用  `"[\-\\\[\]]"` -、[和 \, ] 字符) 。</span><span class="sxs-lookup"><span data-stu-id="20188-122">Used to quote any of the previous symbols (for example,  `"[\-\\\[\]]"` means -, \, [, and ] characters are allowed).</span></span>  <br/> |
   
 <span data-ttu-id="20188-123">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="20188-123">**ulFlags**</span></span>
  
> <span data-ttu-id="20188-124">用于指定字符串筛选器格式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="20188-124">Bitmask of flags used to designate the format of the character string filter.</span></span> <span data-ttu-id="20188-125">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="20188-125">The following flag can be set:</span></span>
    
<span data-ttu-id="20188-126">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="20188-126">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="20188-127">筛选器采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="20188-127">The filter is in Unicode format.</span></span> <span data-ttu-id="20188-128">如果未MAPI_UNICODE，筛选器采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="20188-128">If the MAPI_UNICODE flag is not set, the filter is in ANSI format.</span></span>
    
 <span data-ttu-id="20188-129">**ulNumCharsAllowed**</span><span class="sxs-lookup"><span data-stu-id="20188-129">**ulNumCharsAllowed**</span></span>
  
> <span data-ttu-id="20188-130">可以在组合框的文本框中输入的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="20188-130">Maximum number of characters that can be entered in the combo box's text box.</span></span>
    
 <span data-ttu-id="20188-131">**ulPRPropertyName**</span><span class="sxs-lookup"><span data-stu-id="20188-131">**ulPRPropertyName**</span></span>
  
> <span data-ttu-id="20188-132">类型为 PT_TSTRING 的属性PT_TSTRING。</span><span class="sxs-lookup"><span data-stu-id="20188-132">Property tag for a property of type PT_TSTRING.</span></span> 
    
 <span data-ttu-id="20188-133">**ulPRTableName**</span><span class="sxs-lookup"><span data-stu-id="20188-133">**ulPRTableName**</span></span>
  
> <span data-ttu-id="20188-134">属性类型的属性标记PT_OBJECT **OpenProperty** 调用打开 **IMAPITable** 接口。</span><span class="sxs-lookup"><span data-stu-id="20188-134">Property tag for a property of type PT_OBJECT on which an **IMAPITable** interface can be opened by using an **OpenProperty** call.</span></span> <span data-ttu-id="20188-135">该表必须具有一个列，其属性与 **ulPRPropertyName** 成员标识的属性的类型相同。</span><span class="sxs-lookup"><span data-stu-id="20188-135">The table must have one column with a property that is the same type as the property identified by the **ulPRPropertyName** member.</span></span> <span data-ttu-id="20188-136">表的行用于填充列表。</span><span class="sxs-lookup"><span data-stu-id="20188-136">The rows of the table are used to populate the list.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="20188-137">备注</span><span class="sxs-lookup"><span data-stu-id="20188-137">Remarks</span></span>

<span data-ttu-id="20188-138">**DTBLCOMBOBOX** 结构描述一个组合框一个包含列表和选择字段的控件。</span><span class="sxs-lookup"><span data-stu-id="20188-138">A **DTBLCOMBOBOX** structure describes a combo box a control that consists of a list and a selection field.</span></span> <span data-ttu-id="20188-139">该列表显示用户可以从中选择的信息，并且选择字段显示当前所选内容。</span><span class="sxs-lookup"><span data-stu-id="20188-139">The list presents the information from which a user can select, and the selection field displays the current selection.</span></span> <span data-ttu-id="20188-140">选择字段是一个编辑控件，可用于输入列表中尚未包含的文本。</span><span class="sxs-lookup"><span data-stu-id="20188-140">The selection field is an edit control that can also be used to enter text not already in the list.</span></span> 
  
<span data-ttu-id="20188-141">这两个属性标记成员协同工作，以协调列表显示与编辑控件。</span><span class="sxs-lookup"><span data-stu-id="20188-141">The two property tag members work together to coordinate the list display with the edit control.</span></span> <span data-ttu-id="20188-142">当 MAPI 首次显示组合框时，它将调用与显示表关联的 **IMAPIProp** 实现 **OpenProperty** 方法，以检索 **ulPRTableName** 成员表示的表。</span><span class="sxs-lookup"><span data-stu-id="20188-142">When MAPI first displays the combo box, it calls the **OpenProperty** method of the **IMAPIProp** implementation that is associated with the display table to retrieve the table represented by the **ulPRTableName** member.</span></span> <span data-ttu-id="20188-143">此表有一列，列包含 **ulPRPropertyName** 成员所代表的属性的值。</span><span class="sxs-lookup"><span data-stu-id="20188-143">This table has one column a column that contains values for the property represented by the **ulPRPropertyName** member.</span></span> <span data-ttu-id="20188-144">因此，此列的类型必须与 **ulPRPropertyName** 属性的类型相同，并且两列都必须是字符串。</span><span class="sxs-lookup"><span data-stu-id="20188-144">Therefore, this column must be of the same type as the **ulPRPropertyName** property and both columns must be character strings.</span></span> 
  
<span data-ttu-id="20188-145">列的值显示在组合框的列表部分。</span><span class="sxs-lookup"><span data-stu-id="20188-145">The values for the column are displayed in the list section of the combo box.</span></span> <span data-ttu-id="20188-146">因此 **，PR_NULL (** [PidTagNull](pidtagnull-canonical-property.md)) 不是 **ulPRPropertyName 的有效属性标记**。</span><span class="sxs-lookup"><span data-stu-id="20188-146">Therefore, **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)) is not a valid property tag for **ulPRPropertyName**.</span></span> <span data-ttu-id="20188-147">当用户选择其中一行或在文本框中输入新数据时 **，ulPRPropertyName** 属性将设置为选定或输入的值。</span><span class="sxs-lookup"><span data-stu-id="20188-147">When a user either selects one of the rows or enters new data into the text box, the **ulPRPropertyName** property is set to the selected or entered value.</span></span> 
  
<span data-ttu-id="20188-148">若要显示编辑控件的初始值，MAPI 将调用 [IMAPIProp：：GetProps](imapiprop-getprops.md) 来检索显示表的属性值。</span><span class="sxs-lookup"><span data-stu-id="20188-148">To display an initial value for the edit control, MAPI calls [IMAPIProp::GetProps](imapiprop-getprops.md) to retrieve the property values for the display table.</span></span> <span data-ttu-id="20188-149">如果检索的属性之一与 **ulPRPropertyName** 成员所代表的属性匹配，则其值将成为初始值。</span><span class="sxs-lookup"><span data-stu-id="20188-149">If one of the retrieved properties matches the property represented by the **ulPRPropertyName** member, its value becomes the initial value.</span></span> 
  
<span data-ttu-id="20188-150">有关显示表的概述，请参阅显示 [表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="20188-150">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="20188-151">若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="20188-151">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="20188-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20188-152">See also</span></span>



[<span data-ttu-id="20188-153">DTCTL</span><span class="sxs-lookup"><span data-stu-id="20188-153">DTCTL</span></span>](dtctl.md)
  
[<span data-ttu-id="20188-154">PidTagControlType 规范属性</span><span class="sxs-lookup"><span data-stu-id="20188-154">PidTagControlType Canonical Property</span></span>](pidtagcontroltype-canonical-property.md)


[<span data-ttu-id="20188-155">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="20188-155">MAPI Structures</span></span>](mapi-structures.md)

