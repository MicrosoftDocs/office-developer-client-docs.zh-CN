---
title: DTBLEDIT
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLEDIT
api_type:
- COM
ms.assetid: ec3566a0-75ad-466d-a61e-f7d61ccb946d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d0418ac2ec5d01d58c63e4ad48a1066cc386e946
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774849"
---
# <a name="dtbledit"></a><span data-ttu-id="94b2a-103">DTBLEDIT</span><span class="sxs-lookup"><span data-stu-id="94b2a-103">DTBLEDIT</span></span>

  
  
<span data-ttu-id="94b2a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="94b2a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="94b2a-105">描述将显示表中生成的对话框中使用编辑控件。</span><span class="sxs-lookup"><span data-stu-id="94b2a-105">Describes an edit control that will be used in a dialog box built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="94b2a-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="94b2a-106">Header file:</span></span>  <br/> |<span data-ttu-id="94b2a-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="94b2a-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="94b2a-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="94b2a-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="94b2a-109">SizedDtblEdit</span><span class="sxs-lookup"><span data-stu-id="94b2a-109">SizedDtblEdit</span></span>](sizeddtbledit.md) <br/> |
   
```cpp
typedef struct _DTBLEDIT
{
  ULONG ulbLpszCharsAllowed;
  ULONG ulFlags;
  ULONG ulNumCharsAllowed;
  ULONG ulPropTag;
} DTBLEDIT, FAR *LPDTBLEDIT;

```

## <a name="members"></a><span data-ttu-id="94b2a-110">Members</span><span class="sxs-lookup"><span data-stu-id="94b2a-110">Members</span></span>

 <span data-ttu-id="94b2a-111">**ulbLpszCharsAllowed**</span><span class="sxs-lookup"><span data-stu-id="94b2a-111">**ulbLpszCharsAllowed**</span></span>
  
> <span data-ttu-id="94b2a-112">从**DTBLEDIT**结构开始到描述的限制，如果有，可以编辑控件中输入的字符的字符的字符串筛选器偏移量。</span><span class="sxs-lookup"><span data-stu-id="94b2a-112">An offset from the start of the **DTBLEDIT** structure to a character string filter that describes restrictions, if any, to the characters that can be entered into the edit control.</span></span> <span data-ttu-id="94b2a-113">筛选器将不被解释为一个正则表达式和相同的筛选器应用于输入每个字符。</span><span class="sxs-lookup"><span data-stu-id="94b2a-113">The filter is not interpreted as a regular expression and the same filter is applied to every character entered.</span></span> <span data-ttu-id="94b2a-114">筛选器的格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="94b2a-114">The format of the filter is as follows:</span></span> 
    
|<span data-ttu-id="94b2a-115">**字符**</span><span class="sxs-lookup"><span data-stu-id="94b2a-115">**Character**</span></span>|<span data-ttu-id="94b2a-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="94b2a-116">**Description**</span></span>|
|:-----|:-----|
| `*` <br/> |<span data-ttu-id="94b2a-117">允许任何字符 (例如， `"*"`)。</span><span class="sxs-lookup"><span data-stu-id="94b2a-117">Any character is allowed (for example,  `"*"`).</span></span>  <br/> |
| `[ ]` <br/> |<span data-ttu-id="94b2a-118">定义一组字符 (例如， `"[0123456789]".`)</span><span class="sxs-lookup"><span data-stu-id="94b2a-118">Defines a set of characters (for example,  `"[0123456789]".`)</span></span>  <br/> |
| `-` <br/> |<span data-ttu-id="94b2a-119">指示某个范围的字符 (例如， `"[a-z]"`)。</span><span class="sxs-lookup"><span data-stu-id="94b2a-119">Indicates a range of characters (for example,  `"[a-z]"`).</span></span>  <br/> |
| `~` <br/> |<span data-ttu-id="94b2a-120">指示不允许这些字符 (例如， `"[~0-9]"`)。</span><span class="sxs-lookup"><span data-stu-id="94b2a-120">Indicates that these characters are not allowed (for example,  `"[~0-9]"`).</span></span>  <br/> |
| `\` <br/> |<span data-ttu-id="94b2a-121">用于 quote 任何以前符号 (例如，`"[\-\\\[\]]"`是指-， \, [，和] 允许字符)。</span><span class="sxs-lookup"><span data-stu-id="94b2a-121">Used to quote any of the previous symbols (for example,  `"[\-\\\[\]]"` means -, \, [, and ] characters are allowed).</span></span>  <br/> |
   
 <span data-ttu-id="94b2a-122">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="94b2a-122">**ulFlags**</span></span>
  
> <span data-ttu-id="94b2a-123">用于指定格式的字符筛选器的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="94b2a-123">Bitmask of flags used to designate the format of the character filter.</span></span> <span data-ttu-id="94b2a-124">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="94b2a-124">The following flag can be set:</span></span>
    
<span data-ttu-id="94b2a-125">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="94b2a-125">MAPI_UNICODE</span></span>
  
> <span data-ttu-id="94b2a-126">筛选器在 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="94b2a-126">The filter is in Unicode format.</span></span> <span data-ttu-id="94b2a-127">如果未设置 MAPI_UNICODE 标志，筛选器为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="94b2a-127">If the MAPI_UNICODE flag is not set, the filter is in ANSI format.</span></span>
    
 <span data-ttu-id="94b2a-128">**ulNumCharsAllowed**</span><span class="sxs-lookup"><span data-stu-id="94b2a-128">**ulNumCharsAllowed**</span></span>
  
> <span data-ttu-id="94b2a-129">最大用户可以在文本框中键入的字符数。</span><span class="sxs-lookup"><span data-stu-id="94b2a-129">Maximum number of characters that the user can type into the text box.</span></span>
    
 <span data-ttu-id="94b2a-130">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="94b2a-130">**ulPropTag**</span></span>
  
> <span data-ttu-id="94b2a-131">属性标记类型 PT_TSTRING 的属性。</span><span class="sxs-lookup"><span data-stu-id="94b2a-131">Property tag for a property of type PT_TSTRING.</span></span> <span data-ttu-id="94b2a-132">**UlPropTag**成员标识显示和编辑控件中编辑其数据的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="94b2a-132">The **ulPropTag** member identifies the string property whose data is displayed and edited in the edit control.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="94b2a-133">说明</span><span class="sxs-lookup"><span data-stu-id="94b2a-133">Remarks</span></span>

<span data-ttu-id="94b2a-134">**DTBLEDIT**结构介绍编辑控件上一个对话框，包含字母数字信息的区域。</span><span class="sxs-lookup"><span data-stu-id="94b2a-134">A **DTBLEDIT** structure describes an edit control an area on a dialog box that contains alphanumeric information.</span></span> <span data-ttu-id="94b2a-135">几乎在所有对话框都有至少一个编辑控件。</span><span class="sxs-lookup"><span data-stu-id="94b2a-135">Almost all dialog boxes have at least one edit control.</span></span> <span data-ttu-id="94b2a-136">编辑控件可以由用户可修改或只读的。</span><span class="sxs-lookup"><span data-stu-id="94b2a-136">Edit controls can be modifiable by a user or read-only.</span></span> 
  
<span data-ttu-id="94b2a-137">编辑控件也可以是单个行或多行。</span><span class="sxs-lookup"><span data-stu-id="94b2a-137">Edit controls can also be single line or multiline.</span></span> <span data-ttu-id="94b2a-138">多行编辑控件通常具有与其关联的滚动条。</span><span class="sxs-lookup"><span data-stu-id="94b2a-138">Multiline edit controls typically have a scroll bar associated with them.</span></span> 
  
<span data-ttu-id="94b2a-139">显示表的概述，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="94b2a-139">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="94b2a-140">有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="94b2a-140">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="94b2a-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94b2a-141">See also</span></span>



[<span data-ttu-id="94b2a-142">DTCTL</span><span class="sxs-lookup"><span data-stu-id="94b2a-142">DTCTL</span></span>](dtctl.md)
  
[<span data-ttu-id="94b2a-143">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="94b2a-143">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="94b2a-144">PidTagControlType 规范属性</span><span class="sxs-lookup"><span data-stu-id="94b2a-144">PidTagControlType Canonical Property</span></span>](pidtagcontroltype-canonical-property.md)


[<span data-ttu-id="94b2a-145">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="94b2a-145">MAPI Structures</span></span>](mapi-structures.md)

