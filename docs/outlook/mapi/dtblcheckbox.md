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
ms.openlocfilehash: fa7f6ac116bf5255d2598465085bab2695ae2c25
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564512"
---
# <a name="dtblcheckbox"></a><span data-ttu-id="16cd3-103">DTBLCHECKBOX</span><span class="sxs-lookup"><span data-stu-id="16cd3-103">DTBLCHECKBOX</span></span>

  
  
<span data-ttu-id="16cd3-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="16cd3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="16cd3-105">包含有关复选框将显示表中生成的对话框中使用的信息。</span><span class="sxs-lookup"><span data-stu-id="16cd3-105">Contains information about a check box that will be used in a dialog box built from a display table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="16cd3-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="16cd3-106">Header file:</span></span>  <br/> |<span data-ttu-id="16cd3-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="16cd3-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="16cd3-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="16cd3-108">Related macro:</span></span>  <br/> |[<span data-ttu-id="16cd3-109">SizedDtblCheckBox</span><span class="sxs-lookup"><span data-stu-id="16cd3-109">SizedDtblCheckBox</span></span>](sizeddtblcheckbox.md) <br/> |
   
```cpp
typedef struct _DTBLCHECKBOX
{
  ULONG ulbLpszLabel;
  ULONG ulFlags;
  ULONG ulPRPropertyName;
} DTBLCHECKBOX, FAR *LPDTBLCHECKBOX;

```

## <a name="members"></a><span data-ttu-id="16cd3-110">Members</span><span class="sxs-lookup"><span data-stu-id="16cd3-110">Members</span></span>

 <span data-ttu-id="16cd3-111">**ulbLpszLabel**</span><span class="sxs-lookup"><span data-stu-id="16cd3-111">**ulbLpszLabel**</span></span>
  
> <span data-ttu-id="16cd3-112">在复选框中显示的字符字符串的内存中的位置。</span><span class="sxs-lookup"><span data-stu-id="16cd3-112">Position in memory of the character string that is displayed with the check box.</span></span> 
    
 <span data-ttu-id="16cd3-113">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="16cd3-113">**ulFlags**</span></span>
  
> <span data-ttu-id="16cd3-114">用于指定的复选框标签格式的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="16cd3-114">Bitmask of flags used to designate the format of the check box label.</span></span> <span data-ttu-id="16cd3-115">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="16cd3-115">The following flag can be set:</span></span>
    
<span data-ttu-id="16cd3-116">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="16cd3-116">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="16cd3-117">标签为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="16cd3-117">The label is in Unicode format.</span></span> <span data-ttu-id="16cd3-118">如果未设置 MAPI_UNICODE 标志，标签为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="16cd3-118">If the MAPI_UNICODE flag is not set, the label is in ANSI format.</span></span>
    
 <span data-ttu-id="16cd3-119">**ulPRPropertyName**</span><span class="sxs-lookup"><span data-stu-id="16cd3-119">**ulPRPropertyName**</span></span>
  
> <span data-ttu-id="16cd3-120">属性标记类型 PT_BOOLEAN 的属性。</span><span class="sxs-lookup"><span data-stu-id="16cd3-120">Property tag for a property of type PT_BOOLEAN.</span></span> <span data-ttu-id="16cd3-121">此属性的值会影响状态的复选框。</span><span class="sxs-lookup"><span data-stu-id="16cd3-121">The value of this property is affected by the state of the check box.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="16cd3-122">注解</span><span class="sxs-lookup"><span data-stu-id="16cd3-122">Remarks</span></span>

<span data-ttu-id="16cd3-123">**DTBLCHECKBOX**结构介绍复选框控件，反映了两种状态之一： 启用 （复选的框） 或禁用 （空框）。</span><span class="sxs-lookup"><span data-stu-id="16cd3-123">A **DTBLCHECKBOX** structure describes a check box a control that reflects one of two states: enabled (a checked box) or disabled (an empty box).</span></span> 
  
<span data-ttu-id="16cd3-124">**UlPRPropertyName**成员描述其值操作通过更改复选框的状态的布尔属性。</span><span class="sxs-lookup"><span data-stu-id="16cd3-124">The **ulPRPropertyName** member describes a Boolean property whose value is manipulated by changing the state of the check box.</span></span> <span data-ttu-id="16cd3-125">当第一次显示复选框时，MAPI 调用与要检索的一组默认属性的显示表相关联的**IMAPIProp**实现的**GetProps**方法。</span><span class="sxs-lookup"><span data-stu-id="16cd3-125">When the check box is first displayed, MAPI calls the **GetProps** method of the **IMAPIProp** implementation that is associated with the display table to retrieve a set of default properties.</span></span> <span data-ttu-id="16cd3-126">如果属性之一映射到**DTBLCHECKBOX**结构中的属性标记，该属性的值显示为复选框的初始值。</span><span class="sxs-lookup"><span data-stu-id="16cd3-126">If one of the properties maps to the property tag in the **DTBLCHECKBOX** structure, the value for that property is displayed as the check box's initial value.</span></span> 
  
<span data-ttu-id="16cd3-127">复选框控件可以进行修改。</span><span class="sxs-lookup"><span data-stu-id="16cd3-127">Check box controls can be modifiable.</span></span> <span data-ttu-id="16cd3-128">这允许用户更改其状态。</span><span class="sxs-lookup"><span data-stu-id="16cd3-128">This allows a user to change their states.</span></span> <span data-ttu-id="16cd3-129">在其[DTCTL](dtctl.md)结构的**ulCtlFlags**成员和中其**PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) 属性，可修改复选框设置 DT_EDITABLE 标志。</span><span class="sxs-lookup"><span data-stu-id="16cd3-129">Modifiable check boxes set the DT_EDITABLE flag in the **ulCtlFlags** member of their [DTCTL](dtctl.md) structure and in their **PR_CONTROL_FLAGS** ([PidTagControlFlags](pidtagcontrolflags-canonical-property.md)) property.</span></span> <span data-ttu-id="16cd3-130">当一个复选框更改其状态时，MAPI 调用[IMAPIProp::SetProps](imapiprop-setprops.md)设置为新状态的**DTBLCHECKBOX**结构属性标记成员中标识的属性。</span><span class="sxs-lookup"><span data-stu-id="16cd3-130">When a check box changes its state, MAPI calls [IMAPIProp::SetProps](imapiprop-setprops.md) to set the property identified in the property tag member of the **DTBLCHECKBOX** structure to the new state.</span></span> 
  
<span data-ttu-id="16cd3-131">例如，通讯簿提供程序可能会在其配置对话框中，若要调整收件人的**PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) 属性的设置包括可修改复选框控件。</span><span class="sxs-lookup"><span data-stu-id="16cd3-131">For example, an address book provider might include a modifiable check box control in its configuration dialog box to adjust the setting of a recipient's **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)) property.</span></span> <span data-ttu-id="16cd3-132">当用户选择复选框时，MAPI 将此属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="16cd3-132">When the user selects the check box, MAPI sets this property to TRUE.</span></span> <span data-ttu-id="16cd3-133">时未选中该复选框，则将该属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="16cd3-133">When the check box is unselected, the property is set to FALSE.</span></span>
  
<span data-ttu-id="16cd3-134">显示表的概述，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="16cd3-134">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="16cd3-135">有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="16cd3-135">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span> <span data-ttu-id="16cd3-136">属性类型有关的信息，请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="16cd3-136">For information about property types, see [MAPI Property Type Overview](mapi-property-type-overview.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="16cd3-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16cd3-137">See also</span></span>



[<span data-ttu-id="16cd3-138">DTCTL</span><span class="sxs-lookup"><span data-stu-id="16cd3-138">DTCTL</span></span>](dtctl.md)
  
[<span data-ttu-id="16cd3-139">PidTagControlType 规范属性</span><span class="sxs-lookup"><span data-stu-id="16cd3-139">PidTagControlType Canonical Property</span></span>](pidtagcontroltype-canonical-property.md)


[<span data-ttu-id="16cd3-140">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="16cd3-140">MAPI Structures</span></span>](mapi-structures.md)

