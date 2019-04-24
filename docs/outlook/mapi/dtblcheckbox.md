---
title: DTBLCHECKBOX
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLCHECKBOX
api_type:
- COM
ms.assetid: 0dd12990-5431-4768-9d64-27d4ef6b7b20
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ed0bbe986f374648e2ee85f3a0d2dfe7bc392e0f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287267"
---
# <a name="dtblcheckbox"></a><span data-ttu-id="f5e1b-103">DTBLCHECKBOX</span><span class="sxs-lookup"><span data-stu-id="f5e1b-103">DTBLCHECKBOX</span></span>

  
  
<span data-ttu-id="f5e1b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f5e1b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f5e1b-105">包含有关将在从显示表生成的对话框中使用的复选框的信息。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-105">Contains information about a check box that will be used in a dialog box built from a display table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f5e1b-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="f5e1b-106">Header file:</span></span>  <br/> |<span data-ttu-id="f5e1b-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="f5e1b-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="f5e1b-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="f5e1b-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="f5e1b-109">SizedDtblCheckBox</span><span class="sxs-lookup"><span data-stu-id="f5e1b-109">SizedDtblCheckBox</span></span>](sizeddtblcheckbox.md) <br/> |
   
```cpp
typedef struct _DTBLCHECKBOX
{
  ULONG ulbLpszLabel;
  ULONG ulFlags;
  ULONG ulPRPropertyName;
} DTBLCHECKBOX, FAR *LPDTBLCHECKBOX;

```

## <a name="members"></a><span data-ttu-id="f5e1b-110">Members</span><span class="sxs-lookup"><span data-stu-id="f5e1b-110">Members</span></span>

 <span data-ttu-id="f5e1b-111">**ulbLpszLabel**</span><span class="sxs-lookup"><span data-stu-id="f5e1b-111">**ulbLpszLabel**</span></span>
  
> <span data-ttu-id="f5e1b-112">使用复选框显示的字符字符串在内存中的位置。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-112">Position in memory of the character string that is displayed with the check box.</span></span> 
    
 <span data-ttu-id="f5e1b-113">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="f5e1b-113">**ulFlags**</span></span>
  
> <span data-ttu-id="f5e1b-114">用于指定复选框标签格式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-114">Bitmask of flags used to designate the format of the check box label.</span></span> <span data-ttu-id="f5e1b-115">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="f5e1b-115">The following flag can be set:</span></span>
    
<span data-ttu-id="f5e1b-116">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="f5e1b-116">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="f5e1b-117">标签采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-117">The label is in Unicode format.</span></span> <span data-ttu-id="f5e1b-118">如果未设置 MAPI_UNICODE 标志, 则标签将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-118">If the MAPI_UNICODE flag is not set, the label is in ANSI format.</span></span>
    
 <span data-ttu-id="f5e1b-119">**ulPRPropertyName**</span><span class="sxs-lookup"><span data-stu-id="f5e1b-119">**ulPRPropertyName**</span></span>
  
> <span data-ttu-id="f5e1b-120">类型为 PT_BOOLEAN 的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-120">Property tag for a property of type PT_BOOLEAN.</span></span> <span data-ttu-id="f5e1b-121">此属性的值受复选框状态的影响。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-121">The value of this property is affected by the state of the check box.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f5e1b-122">注解</span><span class="sxs-lookup"><span data-stu-id="f5e1b-122">Remarks</span></span>

<span data-ttu-id="f5e1b-123">**DTBLCHECKBOX**结构描述了一个复选框, 该控件反映两个状态之一: 已启用 (复选框) 或已禁用 (空框)。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-123">A **DTBLCHECKBOX** structure describes a check box a control that reflects one of two states: enabled (a checked box) or disabled (an empty box).</span></span> 
  
<span data-ttu-id="f5e1b-124">**ulPRPropertyName**成员描述了一个布尔属性, 该属性的值通过更改复选框的状态进行操作。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-124">The **ulPRPropertyName** member describes a Boolean property whose value is manipulated by changing the state of the check box.</span></span> <span data-ttu-id="f5e1b-125">当该复选框第一次显示时, MAPI 将调用与显示表相关联的**IMAPIProp**实现的**GetProps**方法, 以检索一组默认属性。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-125">When the check box is first displayed, MAPI calls the **GetProps** method of the **IMAPIProp** implementation that is associated with the display table to retrieve a set of default properties.</span></span> <span data-ttu-id="f5e1b-126">如果其中一个属性映射到**DTBLCHECKBOX**结构中的属性标记, 则该属性的值将显示为复选框的初始值。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-126">If one of the properties maps to the property tag in the **DTBLCHECKBOX** structure, the value for that property is displayed as the check box's initial value.</span></span> 
  
<span data-ttu-id="f5e1b-127">可以修改复选框控件。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-127">Check box controls can be modifiable.</span></span> <span data-ttu-id="f5e1b-128">这样一来, 用户可以更改其状态。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-128">This allows a user to change their states.</span></span> <span data-ttu-id="f5e1b-129">可修改的复选框在其[DTCTL](dtctl.md)结构的**ulCtlFlags**成员及其**PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 属性中设置 DT_EDITABLE 标志。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-129">Modifiable check boxes set the DT_EDITABLE flag in the **ulCtlFlags** member of their [DTCTL](dtctl.md) structure and in their **PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) property.</span></span> <span data-ttu-id="f5e1b-130">复选框更改其状态时, MAPI 调用[IMAPIProp:: SetProps](imapiprop-setprops.md)将在**DTBLCHECKBOX**结构的 property 标记成员中标识的属性设置为新状态。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-130">When a check box changes its state, MAPI calls [IMAPIProp::SetProps](imapiprop-setprops.md) to set the property identified in the property tag member of the **DTBLCHECKBOX** structure to the new state.</span></span> 
  
<span data-ttu-id="f5e1b-131">例如, 通讯簿提供程序可能在其配置对话框中包含一个可修改的复选框控件, 以调整收件人的**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性的设置。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-131">For example, an address book provider might include a modifiable check box control in its configuration dialog box to adjust the setting of a recipient's **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) property.</span></span> <span data-ttu-id="f5e1b-132">当用户选中此复选框时, MAPI 会将此属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-132">When the user selects the check box, MAPI sets this property to TRUE.</span></span> <span data-ttu-id="f5e1b-133">如果未选中此复选框, 则会将该属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-133">When the check box is unselected, the property is set to FALSE.</span></span>
  
<span data-ttu-id="f5e1b-134">有关显示表的概述, 请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-134">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="f5e1b-135">有关如何实现显示表的信息, 请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-135">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span> <span data-ttu-id="f5e1b-136">有关属性类型的信息, 请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-136">For information about property types, see [MAPI Property Type Overview](mapi-property-type-overview.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f5e1b-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5e1b-137">See also</span></span>



[<span data-ttu-id="f5e1b-138">DTCTL</span><span class="sxs-lookup"><span data-stu-id="f5e1b-138">DTCTL</span></span>](dtctl.md)
  
[<span data-ttu-id="f5e1b-139">PidTagControlType 规范属性</span><span class="sxs-lookup"><span data-stu-id="f5e1b-139">PidTagControlType Canonical Property</span></span>](pidtagcontroltype-canonical-property.md)


[<span data-ttu-id="f5e1b-140">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="f5e1b-140">MAPI Structures</span></span>](mapi-structures.md)

