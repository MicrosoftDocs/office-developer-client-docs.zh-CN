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
ms.openlocfilehash: eefd0c62314a35c4c6c956b8d4a4d92d5746d1c1
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22590461"
---
# <a name="dtbledit"></a><span data-ttu-id="b927d-103">DTBLEDIT</span><span class="sxs-lookup"><span data-stu-id="b927d-103">DTBLEDIT</span></span>

  
  
<span data-ttu-id="b927d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b927d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b927d-105">描述将显示表中生成的对话框中使用编辑控件。</span><span class="sxs-lookup"><span data-stu-id="b927d-105">Describes an edit control that will be used in a dialog box built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b927d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="b927d-106">Header file:</span></span>  <br/> |<span data-ttu-id="b927d-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b927d-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="b927d-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="b927d-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="b927d-109">SizedDtblEdit</span><span class="sxs-lookup"><span data-stu-id="b927d-109">SizedDtblEdit</span></span>](sizeddtbledit.md) <br/> |
   
```cpp
typedef struct _DTBLEDIT
{
  ULONG ulbLpszCharsAllowed;
  ULONG ulFlags;
  ULONG ulNumCharsAllowed;
  ULONG ulPropTag;
} DTBLEDIT, FAR *LPDTBLEDIT;

```

## <a name="members"></a><span data-ttu-id="b927d-110">Members</span><span class="sxs-lookup"><span data-stu-id="b927d-110">Members</span></span>

 <span data-ttu-id="b927d-111">**ulbLpszCharsAllowed**</span><span class="sxs-lookup"><span data-stu-id="b927d-111">**ulbLpszCharsAllowed**</span></span>
  
> <span data-ttu-id="b927d-112">从**DTBLEDIT**结构开始到描述的限制，如果有，可以编辑控件中输入的字符的字符的字符串筛选器偏移量。</span><span class="sxs-lookup"><span data-stu-id="b927d-112">An offset from the start of the **DTBLEDIT** structure to a character string filter that describes restrictions, if any, to the characters that can be entered into the edit control.</span></span> <span data-ttu-id="b927d-113">筛选器将不被解释为一个正则表达式和相同的筛选器应用于输入每个字符。</span><span class="sxs-lookup"><span data-stu-id="b927d-113">The filter is not interpreted as a regular expression and the same filter is applied to every character entered.</span></span> <span data-ttu-id="b927d-114">筛选器的格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="b927d-114">The format of the filter is as follows:</span></span> 
    
|<span data-ttu-id="b927d-115">**字符**</span><span class="sxs-lookup"><span data-stu-id="b927d-115">**Character**</span></span>|<span data-ttu-id="b927d-116">**说明**</span><span class="sxs-lookup"><span data-stu-id="b927d-116">**Description**</span></span>|
|:-----|:-----|
| `*` <br/> |<span data-ttu-id="b927d-117">允许任何字符 (例如， `"*"`)。</span><span class="sxs-lookup"><span data-stu-id="b927d-117">Any character is allowed (for example,  `"*"`).</span></span>  <br/> |
| `[ ]` <br/> |<span data-ttu-id="b927d-118">定义一组字符 (例如， `"[0123456789]".`)</span><span class="sxs-lookup"><span data-stu-id="b927d-118">Defines a set of characters (for example,  `"[0123456789]".`)</span></span>  <br/> |
| `-` <br/> |<span data-ttu-id="b927d-119">指示某个范围的字符 (例如， `"[a-z]"`)。</span><span class="sxs-lookup"><span data-stu-id="b927d-119">Indicates a range of characters (for example,  `"[a-z]"`).</span></span>  <br/> |
| `~` <br/> |<span data-ttu-id="b927d-120">指示不允许这些字符 (例如， `"[~0-9]"`)。</span><span class="sxs-lookup"><span data-stu-id="b927d-120">Indicates that these characters are not allowed (for example,  `"[~0-9]"`).</span></span>  <br/> |
| `\` <br/> |<span data-ttu-id="b927d-121">用于 quote 任何以前符号 (例如，`"[\-\\\[\]]"`是指-， \, [，和] 允许字符)。</span><span class="sxs-lookup"><span data-stu-id="b927d-121">Used to quote any of the previous symbols (for example,  `"[\-\\\[\]]"` means -, \, [, and ] characters are allowed).</span></span>  <br/> |
   
 <span data-ttu-id="b927d-122">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="b927d-122">**ulFlags**</span></span>
  
> <span data-ttu-id="b927d-123">用于指定格式的字符筛选器的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="b927d-123">Bitmask of flags used to designate the format of the character filter.</span></span> <span data-ttu-id="b927d-124">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="b927d-124">The following flag can be set:</span></span>
    
<span data-ttu-id="b927d-125">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b927d-125">MAPI_UNICODE</span></span>
  
> <span data-ttu-id="b927d-126">筛选器在 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="b927d-126">The filter is in Unicode format.</span></span> <span data-ttu-id="b927d-127">如果未设置 MAPI_UNICODE 标志，筛选器为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="b927d-127">If the MAPI_UNICODE flag is not set, the filter is in ANSI format.</span></span>
    
 <span data-ttu-id="b927d-128">**ulNumCharsAllowed**</span><span class="sxs-lookup"><span data-stu-id="b927d-128">**ulNumCharsAllowed**</span></span>
  
> <span data-ttu-id="b927d-129">最大用户可以在文本框中键入的字符数。</span><span class="sxs-lookup"><span data-stu-id="b927d-129">Maximum number of characters that the user can type into the text box.</span></span>
    
 <span data-ttu-id="b927d-130">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="b927d-130">**ulPropTag**</span></span>
  
> <span data-ttu-id="b927d-131">属性标记类型 PT_TSTRING 的属性。</span><span class="sxs-lookup"><span data-stu-id="b927d-131">Property tag for a property of type PT_TSTRING.</span></span> <span data-ttu-id="b927d-132">**UlPropTag**成员标识显示和编辑控件中编辑其数据的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="b927d-132">The **ulPropTag** member identifies the string property whose data is displayed and edited in the edit control.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="b927d-133">注解</span><span class="sxs-lookup"><span data-stu-id="b927d-133">Remarks</span></span>

<span data-ttu-id="b927d-134">**DTBLEDIT**结构介绍编辑控件上一个对话框，包含字母数字信息的区域。</span><span class="sxs-lookup"><span data-stu-id="b927d-134">A **DTBLEDIT** structure describes an edit control an area on a dialog box that contains alphanumeric information.</span></span> <span data-ttu-id="b927d-135">几乎在所有对话框都有至少一个编辑控件。</span><span class="sxs-lookup"><span data-stu-id="b927d-135">Almost all dialog boxes have at least one edit control.</span></span> <span data-ttu-id="b927d-136">编辑控件可以由用户可修改或只读的。</span><span class="sxs-lookup"><span data-stu-id="b927d-136">Edit controls can be modifiable by a user or read-only.</span></span> 
  
<span data-ttu-id="b927d-137">编辑控件也可以是单个行或多行。</span><span class="sxs-lookup"><span data-stu-id="b927d-137">Edit controls can also be single line or multiline.</span></span> <span data-ttu-id="b927d-138">多行编辑控件通常具有与其关联的滚动条。</span><span class="sxs-lookup"><span data-stu-id="b927d-138">Multiline edit controls typically have a scroll bar associated with them.</span></span> 
  
<span data-ttu-id="b927d-139">显示表的概述，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="b927d-139">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="b927d-140">有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="b927d-140">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b927d-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b927d-141">See also</span></span>



[<span data-ttu-id="b927d-142">DTCTL</span><span class="sxs-lookup"><span data-stu-id="b927d-142">DTCTL</span></span>](dtctl.md)
  
[<span data-ttu-id="b927d-143">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="b927d-143">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="b927d-144">PidTagControlType 规范属性</span><span class="sxs-lookup"><span data-stu-id="b927d-144">PidTagControlType Canonical Property</span></span>](pidtagcontroltype-canonical-property.md)


[<span data-ttu-id="b927d-145">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="b927d-145">MAPI Structures</span></span>](mapi-structures.md)

