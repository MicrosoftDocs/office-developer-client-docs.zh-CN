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
ms.openlocfilehash: 94e412f2f542298adcedf4414c19b5303330cf2f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339415"
---
# <a name="dtblradiobutton"></a><span data-ttu-id="36305-103">DTBLRADIOBUTTON</span><span class="sxs-lookup"><span data-stu-id="36305-103">DTBLRADIOBUTTON</span></span>

  
  
<span data-ttu-id="36305-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="36305-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="36305-105">介绍一个单选按钮组, 该按钮将成为单选按钮组的一部分。</span><span class="sxs-lookup"><span data-stu-id="36305-105">Describes one radio button that will be part of a radio button group.</span></span> <span data-ttu-id="36305-106">单选按钮组将在根据显示表生成的对话框中使用。</span><span class="sxs-lookup"><span data-stu-id="36305-106">The radio button group will be used in a dialog box that is built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="36305-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="36305-107">Header file:</span></span>  <br/> |<span data-ttu-id="36305-108">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="36305-108">Mapidefs.h</span></span>  <br/> |
   
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

## <a name="members"></a><span data-ttu-id="36305-109">Members</span><span class="sxs-lookup"><span data-stu-id="36305-109">Members</span></span>

 <span data-ttu-id="36305-110">**ulbLpszLabel**</span><span class="sxs-lookup"><span data-stu-id="36305-110">**ulbLpszLabel**</span></span>
  
> <span data-ttu-id="36305-111">单选按钮的字符字符串标签在内存中的位置。</span><span class="sxs-lookup"><span data-stu-id="36305-111">Position in memory of the character string label for the radio button.</span></span>
    
 <span data-ttu-id="36305-112">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="36305-112">**ulFlags**</span></span>
  
> <span data-ttu-id="36305-113">标志的位掩码, 用于指定**ulbLpszLabel**成员指向的标签的格式。</span><span class="sxs-lookup"><span data-stu-id="36305-113">Bitmask of flags used to designate the format of the label pointed to by the **ulbLpszLabel** member.</span></span> <span data-ttu-id="36305-114">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="36305-114">The following flag can be set:</span></span> 
    
<span data-ttu-id="36305-115">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="36305-115">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="36305-116">标签采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="36305-116">The label is in Unicode format.</span></span> <span data-ttu-id="36305-117">如果未设置 MAPI_UNICODE 标志, 则标签将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="36305-117">If the MAPI_UNICODE flag is not set, the label is in ANSI format.</span></span>
    
 <span data-ttu-id="36305-118">**ulcButtons**</span><span class="sxs-lookup"><span data-stu-id="36305-118">**ulcButtons**</span></span>
  
> <span data-ttu-id="36305-119">单选按钮组中的按钮数。</span><span class="sxs-lookup"><span data-stu-id="36305-119">Count of buttons in the radio button group.</span></span> <span data-ttu-id="36305-120">组中其他按钮的**DTBLRADIOBUTTON**结构必须包含在显示表的连续行中。</span><span class="sxs-lookup"><span data-stu-id="36305-120">The **DTBLRADIOBUTTON** structures for the other buttons in the group must be contained in successive rows of the display table.</span></span> <span data-ttu-id="36305-121">这些行中的每一行应包含**ulcButtons**成员的相同值。</span><span class="sxs-lookup"><span data-stu-id="36305-121">Each of these rows should contain the same value for the **ulcButtons** member.</span></span> 
    
 <span data-ttu-id="36305-122">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="36305-122">**ulPropTag**</span></span>
  
> <span data-ttu-id="36305-123">类型为 PT_LONG 的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="36305-123">Property tag for a property of type PT_LONG.</span></span> <span data-ttu-id="36305-124">单选按钮组中的初始选择基于此属性的初始值。</span><span class="sxs-lookup"><span data-stu-id="36305-124">The initial selection in the radio button group is based on the initial value of this property.</span></span> <span data-ttu-id="36305-125">该组中的每个按钮都必须将**ulPropTag**设置为同一属性。</span><span class="sxs-lookup"><span data-stu-id="36305-125">Each button in the group must have **ulPropTag** set to the same property.</span></span> 
    
 <span data-ttu-id="36305-126">**lReturnValue**</span><span class="sxs-lookup"><span data-stu-id="36305-126">**lReturnValue**</span></span>
  
> <span data-ttu-id="36305-127">标识所选按钮的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="36305-127">Unique number that identifies the selected button.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="36305-128">注解</span><span class="sxs-lookup"><span data-stu-id="36305-128">Remarks</span></span>

<span data-ttu-id="36305-129">**DTBLRADIOBUTTON**结构描述了一个单选按钮与一组按钮相关联的按钮控件。</span><span class="sxs-lookup"><span data-stu-id="36305-129">A **DTBLRADIOBUTTON** structure describes a radio button a button control that is associated with a group of buttons.</span></span> <span data-ttu-id="36305-130">只能选中组中的一个按钮;设置一个按钮将导致取消设置组中的其他按钮。</span><span class="sxs-lookup"><span data-stu-id="36305-130">Only one button in the group can be checked; setting one button causes the other buttons in the group to be unset.</span></span> 
  
<span data-ttu-id="36305-131">按钮计数是组中的单选按钮的数目。</span><span class="sxs-lookup"><span data-stu-id="36305-131">The button count is the number of radio buttons in the group.</span></span> <span data-ttu-id="36305-132">组中其他单选按钮的结构必须位于显示表的后续行中。</span><span class="sxs-lookup"><span data-stu-id="36305-132">The structures for the other radio buttons in the group must be in subsequent rows in the display table.</span></span> <span data-ttu-id="36305-133">这些结构中的每一个都应具有相同的按钮计数值。</span><span class="sxs-lookup"><span data-stu-id="36305-133">Each of these structures should have the same value for its button count.</span></span>
  
<span data-ttu-id="36305-134">有关显示表的概述, 请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="36305-134">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="36305-135">有关如何实现显示表的信息, 请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="36305-135">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="36305-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36305-136">See also</span></span>



[<span data-ttu-id="36305-137">BuildDisplayTable</span><span class="sxs-lookup"><span data-stu-id="36305-137">BuildDisplayTable</span></span>](builddisplaytable.md)
  
[<span data-ttu-id="36305-138">DTCTL</span><span class="sxs-lookup"><span data-stu-id="36305-138">DTCTL</span></span>](dtctl.md)
  
[<span data-ttu-id="36305-139">SizedDtblButton</span><span class="sxs-lookup"><span data-stu-id="36305-139">SizedDtblButton</span></span>](sizeddtblbutton.md)


[<span data-ttu-id="36305-140">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="36305-140">MAPI Structures</span></span>](mapi-structures.md)

