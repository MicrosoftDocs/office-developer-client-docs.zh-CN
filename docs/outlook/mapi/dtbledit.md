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
ms.openlocfilehash: b07ea265b5dcc6b9a9abb15c6be7ac9e0f94e8ed
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33404678"
---
# <a name="dtbledit"></a><span data-ttu-id="97050-103">DTBLEDIT</span><span class="sxs-lookup"><span data-stu-id="97050-103">DTBLEDIT</span></span>

  
  
<span data-ttu-id="97050-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="97050-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="97050-105">描述将在从显示表构建的对话框中使用的编辑控件。</span><span class="sxs-lookup"><span data-stu-id="97050-105">Describes an edit control that will be used in a dialog box built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="97050-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="97050-106">Header file:</span></span>  <br/> |<span data-ttu-id="97050-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="97050-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="97050-108">相关宏：</span><span class="sxs-lookup"><span data-stu-id="97050-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="97050-109">SizedDtblEdit</span><span class="sxs-lookup"><span data-stu-id="97050-109">SizedDtblEdit</span></span>](sizeddtbledit.md) <br/> |
   
```cpp
typedef struct _DTBLEDIT
{
  ULONG ulbLpszCharsAllowed;
  ULONG ulFlags;
  ULONG ulNumCharsAllowed;
  ULONG ulPropTag;
} DTBLEDIT, FAR *LPDTBLEDIT;

```

## <a name="members"></a><span data-ttu-id="97050-110">Members</span><span class="sxs-lookup"><span data-stu-id="97050-110">Members</span></span>

 <span data-ttu-id="97050-111">**ulbLpszCharsAllowed**</span><span class="sxs-lookup"><span data-stu-id="97050-111">**ulbLpszCharsAllowed**</span></span>
  
> <span data-ttu-id="97050-112">从 **DTBLEDIT** 结构开始到描述可在编辑控件中输入的字符的限制（如果有）的字符串筛选器的偏移量。</span><span class="sxs-lookup"><span data-stu-id="97050-112">An offset from the start of the **DTBLEDIT** structure to a character string filter that describes restrictions, if any, to the characters that can be entered into the edit control.</span></span> <span data-ttu-id="97050-113">筛选器不会解释为正则表达式，并且相同的筛选器将应用于输入的每一个字符。</span><span class="sxs-lookup"><span data-stu-id="97050-113">The filter is not interpreted as a regular expression and the same filter is applied to every character entered.</span></span> <span data-ttu-id="97050-114">筛选器的格式如下：</span><span class="sxs-lookup"><span data-stu-id="97050-114">The format of the filter is as follows:</span></span> 
    
|<span data-ttu-id="97050-115">**字符**</span><span class="sxs-lookup"><span data-stu-id="97050-115">**Character**</span></span>|<span data-ttu-id="97050-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="97050-116">**Description**</span></span>|
|:-----|:-----|
| `*` <br/> |<span data-ttu-id="97050-117">允许任何字符 (例如  `"*"` ，) 。</span><span class="sxs-lookup"><span data-stu-id="97050-117">Any character is allowed (for example,  `"*"`).</span></span>  <br/> |
| `[ ]` <br/> |<span data-ttu-id="97050-118">定义一组字符 ( `"[0123456789]".` 例如，) </span><span class="sxs-lookup"><span data-stu-id="97050-118">Defines a set of characters (for example,  `"[0123456789]".`)</span></span>  <br/> |
| `-` <br/> |<span data-ttu-id="97050-119">指示一系列字符 (例如  `"[a-z]"` ，) 。</span><span class="sxs-lookup"><span data-stu-id="97050-119">Indicates a range of characters (for example,  `"[a-z]"`).</span></span>  <br/> |
| `~` <br/> |<span data-ttu-id="97050-120">指示不允许使用这些字符 (例如  `"[~0-9]"` ，) 。</span><span class="sxs-lookup"><span data-stu-id="97050-120">Indicates that these characters are not allowed (for example,  `"[~0-9]"`).</span></span>  <br/> |
| `\` <br/> |<span data-ttu-id="97050-121">用于引用前面的任何符号 (例如，允许使用  `"[\-\\\[\]]"` -、[和 \, ] 字符) 。</span><span class="sxs-lookup"><span data-stu-id="97050-121">Used to quote any of the previous symbols (for example,  `"[\-\\\[\]]"` means -, \, [, and ] characters are allowed).</span></span>  <br/> |
   
 <span data-ttu-id="97050-122">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="97050-122">**ulFlags**</span></span>
  
> <span data-ttu-id="97050-123">用于指定字符筛选器格式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="97050-123">Bitmask of flags used to designate the format of the character filter.</span></span> <span data-ttu-id="97050-124">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="97050-124">The following flag can be set:</span></span>
    
<span data-ttu-id="97050-125">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="97050-125">MAPI_UNICODE</span></span>
  
> <span data-ttu-id="97050-126">筛选器采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="97050-126">The filter is in Unicode format.</span></span> <span data-ttu-id="97050-127">如果未MAPI_UNICODE，筛选器采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="97050-127">If the MAPI_UNICODE flag is not set, the filter is in ANSI format.</span></span>
    
 <span data-ttu-id="97050-128">**ulNumCharsAllowed**</span><span class="sxs-lookup"><span data-stu-id="97050-128">**ulNumCharsAllowed**</span></span>
  
> <span data-ttu-id="97050-129">用户可在文本框中键入的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="97050-129">Maximum number of characters that the user can type into the text box.</span></span>
    
 <span data-ttu-id="97050-130">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="97050-130">**ulPropTag**</span></span>
  
> <span data-ttu-id="97050-131">类型为 PT_TSTRING 的属性PT_TSTRING。</span><span class="sxs-lookup"><span data-stu-id="97050-131">Property tag for a property of type PT_TSTRING.</span></span> <span data-ttu-id="97050-132">**ulPropTag** 成员标识在编辑控件中显示和编辑其数据的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="97050-132">The **ulPropTag** member identifies the string property whose data is displayed and edited in the edit control.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="97050-133">备注</span><span class="sxs-lookup"><span data-stu-id="97050-133">Remarks</span></span>

<span data-ttu-id="97050-134">**DTBLEDIT** 结构描述对话框中包含字母数字信息的编辑控件区域。</span><span class="sxs-lookup"><span data-stu-id="97050-134">A **DTBLEDIT** structure describes an edit control an area on a dialog box that contains alphanumeric information.</span></span> <span data-ttu-id="97050-135">几乎所有对话框都至少有一个编辑控件。</span><span class="sxs-lookup"><span data-stu-id="97050-135">Almost all dialog boxes have at least one edit control.</span></span> <span data-ttu-id="97050-136">用户可以修改编辑控件或只读控件。</span><span class="sxs-lookup"><span data-stu-id="97050-136">Edit controls can be modifiable by a user or read-only.</span></span> 
  
<span data-ttu-id="97050-137">编辑控件还可以是单行或多行。</span><span class="sxs-lookup"><span data-stu-id="97050-137">Edit controls can also be single line or multiline.</span></span> <span data-ttu-id="97050-138">多行编辑控件通常具有与其关联的滚动条。</span><span class="sxs-lookup"><span data-stu-id="97050-138">Multiline edit controls typically have a scroll bar associated with them.</span></span> 
  
<span data-ttu-id="97050-139">有关显示表的概述，请参阅显示 [表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="97050-139">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="97050-140">若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="97050-140">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="97050-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97050-141">See also</span></span>



[<span data-ttu-id="97050-142">DTCTL</span><span class="sxs-lookup"><span data-stu-id="97050-142">DTCTL</span></span>](dtctl.md)
  
[<span data-ttu-id="97050-143">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="97050-143">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="97050-144">PidTagControlType 规范属性</span><span class="sxs-lookup"><span data-stu-id="97050-144">PidTagControlType Canonical Property</span></span>](pidtagcontroltype-canonical-property.md)


[<span data-ttu-id="97050-145">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="97050-145">MAPI Structures</span></span>](mapi-structures.md)

