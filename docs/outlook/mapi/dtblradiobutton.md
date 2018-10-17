---
title: DTBLRADIOBUTTON
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLRADIOBUTTON
api_type:
- COM
ms.assetid: 64cef938-ef6f-43bb-8f6e-d4cd4d6c9888
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 493176029be3e7b154188aa164a95a8bc9c0e7d9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569741"
---
# <a name="dtblradiobutton"></a><span data-ttu-id="b5c77-103">DTBLRADIOBUTTON</span><span class="sxs-lookup"><span data-stu-id="b5c77-103">DTBLRADIOBUTTON</span></span>

  
  
<span data-ttu-id="b5c77-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b5c77-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b5c77-105">介绍将成为单选按钮组的一部分的一个单选按钮。</span><span class="sxs-lookup"><span data-stu-id="b5c77-105">Describes one radio button that will be part of a radio button group.</span></span> <span data-ttu-id="b5c77-106">将显示表中生成的对话框中使用的单选按钮组。</span><span class="sxs-lookup"><span data-stu-id="b5c77-106">The radio button group will be used in a dialog box that is built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b5c77-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="b5c77-107">Header file:</span></span>  <br/> |<span data-ttu-id="b5c77-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b5c77-108">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _DTBLRADIOBUTTON
{
  ULONG ulbLpszLabel;
  ULONG ulFlags;
  ULONG ulcButtons;
  ULONG ulPropTag;
  long lReturnValue;
} DTBLRADIOBUTTON, FAR *LPDTBLRADIOBUTTON;

```

## <a name="members"></a><span data-ttu-id="b5c77-109">Members</span><span class="sxs-lookup"><span data-stu-id="b5c77-109">Members</span></span>

 <span data-ttu-id="b5c77-110">**ulbLpszLabel**</span><span class="sxs-lookup"><span data-stu-id="b5c77-110">**ulbLpszLabel**</span></span>
  
> <span data-ttu-id="b5c77-111">在内存中的单选按钮的字符的字符串标签的位置。</span><span class="sxs-lookup"><span data-stu-id="b5c77-111">Position in memory of the character string label for the radio button.</span></span>
    
 <span data-ttu-id="b5c77-112">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="b5c77-112">**ulFlags**</span></span>
  
> <span data-ttu-id="b5c77-113">用于指定所指的**ulbLpszLabel**成员标签的格式的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="b5c77-113">Bitmask of flags used to designate the format of the label pointed to by the **ulbLpszLabel** member.</span></span> <span data-ttu-id="b5c77-114">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="b5c77-114">The following flag can be set:</span></span> 
    
<span data-ttu-id="b5c77-115">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b5c77-115">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="b5c77-116">标签为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="b5c77-116">The label is in Unicode format.</span></span> <span data-ttu-id="b5c77-117">如果未设置 MAPI_UNICODE 标志，标签为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="b5c77-117">If the MAPI_UNICODE flag is not set, the label is in ANSI format.</span></span>
    
 <span data-ttu-id="b5c77-118">**ulcButtons**</span><span class="sxs-lookup"><span data-stu-id="b5c77-118">**ulcButtons**</span></span>
  
> <span data-ttu-id="b5c77-119">单选按钮组中的按钮的计数。</span><span class="sxs-lookup"><span data-stu-id="b5c77-119">Count of buttons in the radio button group.</span></span> <span data-ttu-id="b5c77-120">显示表的连续行中都必须包含其他按钮的组中的**DTBLRADIOBUTTON**结构。</span><span class="sxs-lookup"><span data-stu-id="b5c77-120">The **DTBLRADIOBUTTON** structures for the other buttons in the group must be contained in successive rows of the display table.</span></span> <span data-ttu-id="b5c77-121">每个这些行应**ulcButtons**成员的包含相同的值。</span><span class="sxs-lookup"><span data-stu-id="b5c77-121">Each of these rows should contain the same value for the **ulcButtons** member.</span></span> 
    
 <span data-ttu-id="b5c77-122">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="b5c77-122">**ulPropTag**</span></span>
  
> <span data-ttu-id="b5c77-123">属性标记类型 PT_LONG 的属性。</span><span class="sxs-lookup"><span data-stu-id="b5c77-123">Property tag for a property of type PT_LONG.</span></span> <span data-ttu-id="b5c77-124">单选按钮组中的初始选择基于此属性的初始值。</span><span class="sxs-lookup"><span data-stu-id="b5c77-124">The initial selection in the radio button group is based on the initial value of this property.</span></span> <span data-ttu-id="b5c77-125">组中的每个按钮必须**ulPropTag**设置为相同的属性。</span><span class="sxs-lookup"><span data-stu-id="b5c77-125">Each button in the group must have **ulPropTag** set to the same property.</span></span> 
    
 <span data-ttu-id="b5c77-126">**lReturnValue**</span><span class="sxs-lookup"><span data-stu-id="b5c77-126">**lReturnValue**</span></span>
  
> <span data-ttu-id="b5c77-127">标识所选的按钮的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="b5c77-127">Unique number that identifies the selected button.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b5c77-128">注解</span><span class="sxs-lookup"><span data-stu-id="b5c77-128">Remarks</span></span>

<span data-ttu-id="b5c77-129">**DTBLRADIOBUTTON**结构介绍与一组按钮关联的一个按钮控件的单选按钮。</span><span class="sxs-lookup"><span data-stu-id="b5c77-129">A **DTBLRADIOBUTTON** structure describes a radio button a button control that is associated with a group of buttons.</span></span> <span data-ttu-id="b5c77-130">可以检查组中的只有一个按钮;设置一个按钮使未设置组中的其他按钮。</span><span class="sxs-lookup"><span data-stu-id="b5c77-130">Only one button in the group can be checked; setting one button causes the other buttons in the group to be unset.</span></span> 
  
<span data-ttu-id="b5c77-131">将按钮的数目是组中的单选按钮数。</span><span class="sxs-lookup"><span data-stu-id="b5c77-131">The button count is the number of radio buttons in the group.</span></span> <span data-ttu-id="b5c77-132">显示表中的后续行中必须是其他单选按钮组中的结构。</span><span class="sxs-lookup"><span data-stu-id="b5c77-132">The structures for the other radio buttons in the group must be in subsequent rows in the display table.</span></span> <span data-ttu-id="b5c77-133">每个这些结构应具有相同的值，它按钮的计数。</span><span class="sxs-lookup"><span data-stu-id="b5c77-133">Each of these structures should have the same value for its button count.</span></span>
  
<span data-ttu-id="b5c77-134">显示表的概述，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="b5c77-134">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="b5c77-135">有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="b5c77-135">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b5c77-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5c77-136">See also</span></span>



[<span data-ttu-id="b5c77-137">BuildDisplayTable</span><span class="sxs-lookup"><span data-stu-id="b5c77-137">BuildDisplayTable</span></span>](builddisplaytable.md)
  
[<span data-ttu-id="b5c77-138">DTCTL</span><span class="sxs-lookup"><span data-stu-id="b5c77-138">DTCTL</span></span>](dtctl.md)
  
[<span data-ttu-id="b5c77-139">SizedDtblButton</span><span class="sxs-lookup"><span data-stu-id="b5c77-139">SizedDtblButton</span></span>](sizeddtblbutton.md)


[<span data-ttu-id="b5c77-140">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="b5c77-140">MAPI Structures</span></span>](mapi-structures.md)
