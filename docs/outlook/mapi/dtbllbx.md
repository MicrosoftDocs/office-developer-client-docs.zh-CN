---
title: DTBLLBX
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLLBX
api_type:
- COM
ms.assetid: 971b4837-6823-4f28-9803-3c22b2ec091f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 04fbfb2e6938c1ae5971e90b30f5ef749e7963e1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774850"
---
# <a name="dtbllbx"></a><span data-ttu-id="8a58a-103">DTBLLBX</span><span class="sxs-lookup"><span data-stu-id="8a58a-103">DTBLLBX</span></span>

  
  
<span data-ttu-id="8a58a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8a58a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8a58a-105">描述将显示表中生成的对话框中使用的列表。</span><span class="sxs-lookup"><span data-stu-id="8a58a-105">Describes a list that will be used in a dialog box that is built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8a58a-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="8a58a-106">Header file:</span></span>  <br/> |<span data-ttu-id="8a58a-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8a58a-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _DTBLLBX
{
  ULONG ulFlags;
  ULONG ulPRSetProperty;
  ULONG ulPRTableName;
} DTBLLBX, FAR *LPDTBLLBX

```

## <a name="members"></a><span data-ttu-id="8a58a-108">Members</span><span class="sxs-lookup"><span data-stu-id="8a58a-108">Members</span></span>

 <span data-ttu-id="8a58a-109">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="8a58a-109">**ulFlags**</span></span>
  
> <span data-ttu-id="8a58a-110">用于消除从列表中的水平或垂直滚动条的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="8a58a-110">Bitmask of flags used to eliminate a horizontal or vertical scroll bar from the list.</span></span> <span data-ttu-id="8a58a-111">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="8a58a-111">The following flags can be set:</span></span>
    
<span data-ttu-id="8a58a-112">MAPI_NO_HBAR</span><span class="sxs-lookup"><span data-stu-id="8a58a-112">MAPI_NO_HBAR</span></span> 
  
> <span data-ttu-id="8a58a-113">不水平滚动条应与列表所示。</span><span class="sxs-lookup"><span data-stu-id="8a58a-113">No horizontal scroll bar should be shown with the list.</span></span>
    
<span data-ttu-id="8a58a-114">MAPI_NO_VBAR</span><span class="sxs-lookup"><span data-stu-id="8a58a-114">MAPI_NO_VBAR</span></span> 
  
> <span data-ttu-id="8a58a-115">不垂直滚动条应与列表所示。</span><span class="sxs-lookup"><span data-stu-id="8a58a-115">No vertical scroll bar should be shown with the list.</span></span>
    
 <span data-ttu-id="8a58a-116">**ulPRSetProperty**</span><span class="sxs-lookup"><span data-stu-id="8a58a-116">**ulPRSetProperty**</span></span>
  
> <span data-ttu-id="8a58a-117">属性标记任何类型的属性。</span><span class="sxs-lookup"><span data-stu-id="8a58a-117">Property tag for a property of any type.</span></span> <span data-ttu-id="8a58a-118">此属性是一个由**ulPRTableTable**成员标识表中的列。</span><span class="sxs-lookup"><span data-stu-id="8a58a-118">This property is one of the columns in the table identified by the **ulPRTableTable** member.</span></span> 
    
 <span data-ttu-id="8a58a-119">**ulPRTableName**</span><span class="sxs-lookup"><span data-stu-id="8a58a-119">**ulPRTableName**</span></span>
  
> <span data-ttu-id="8a58a-120">调用属性表属性类型可以打开使用**OpenProperty** PT_OBJECT 的标记。</span><span class="sxs-lookup"><span data-stu-id="8a58a-120">Property tag for a table property of type PT_OBJECT that can be opened by using an **OpenProperty** call.</span></span> <span data-ttu-id="8a58a-121">该表应具有的列数取决于列表是否是单个或多个所选内容列表。</span><span class="sxs-lookup"><span data-stu-id="8a58a-121">The number of columns that the table should have depends on whether the list is a single or multiple selection list.</span></span> <span data-ttu-id="8a58a-122">如果**ulPRSetProperty**成员设置为**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md))，允许多重选择列表。</span><span class="sxs-lookup"><span data-stu-id="8a58a-122">If the **ulPRSetProperty** member is set to **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)), the list allows for multiple selection.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8a58a-123">说明</span><span class="sxs-lookup"><span data-stu-id="8a58a-123">Remarks</span></span>

<span data-ttu-id="8a58a-124">**DTBLLBX**结构介绍用于显示多个项目，并使用户可以选择一个或多个项目的控件的列表。</span><span class="sxs-lookup"><span data-stu-id="8a58a-124">A **DTBLLBX** structure describes a list a control that is used to show multiple items and let a user select one or more of the items.</span></span> 
  
<span data-ttu-id="8a58a-125">**UlPRSetProperty**成员和**ulPRTableName**成员协同; 工作当从表中选择一个值时，它是写回**ulPRSetProperty**时消除对话框。</span><span class="sxs-lookup"><span data-stu-id="8a58a-125">The **ulPRSetProperty** member and **ulPRTableName** member work together; when one value is chosen from the table, it is written back to **ulPRSetProperty** when the dialog box is dismissed.</span></span> 
  
<span data-ttu-id="8a58a-126">Flags 值指示是否应与列表中显示水平或垂直滚动条。</span><span class="sxs-lookup"><span data-stu-id="8a58a-126">The flags value indicates whether a horizontal or vertical scroll bar should be displayed with the list.</span></span> <span data-ttu-id="8a58a-127">默认值是不显示的滚动条如果需要的类型。</span><span class="sxs-lookup"><span data-stu-id="8a58a-127">The default is to have types of scroll bars appear if it is required.</span></span> <span data-ttu-id="8a58a-128">服务提供商可以设置 MAPI_NO_HBAR 禁止在水平滚动条和 MAPI_NO_VBAR 禁止在垂直滚动条。</span><span class="sxs-lookup"><span data-stu-id="8a58a-128">Service providers can set MAPI_NO_HBAR to suppress a horizontal scroll bar and MAPI_NO_VBAR to suppress a vertical scroll bar.</span></span> 
  
<span data-ttu-id="8a58a-129">两个属性标记成员协同工作来在列表中显示值和选择列表中的项目时设置相应的属性。</span><span class="sxs-lookup"><span data-stu-id="8a58a-129">The two property tag members work together to display values in the list and set corresponding properties when an item in the list is selected.</span></span> <span data-ttu-id="8a58a-130">当 MAPI 首次显示列表时，它会调用**IMAPIProp**实现**OpenProperty**方法来检索标识**ulPRTableName**成员中的表。</span><span class="sxs-lookup"><span data-stu-id="8a58a-130">When MAPI first displays the list, it calls the **IMAPIProp** implementation's **OpenProperty** method to retrieve the table identified in the **ulPRTableName** member.</span></span> <span data-ttu-id="8a58a-131">表中的列数取决于**ulPRSetProperty**成员的值。</span><span class="sxs-lookup"><span data-stu-id="8a58a-131">The number of columns in the table depends on the value of the **ulPRSetProperty** member.</span></span> <span data-ttu-id="8a58a-132">如果**ulPRSetProperty**设置为**PR_NULL**，列表是一个包含收件人，如通讯簿容器、 邮件收件人表或通讯组列表内容表对象所基于的多个所选内容列表。</span><span class="sxs-lookup"><span data-stu-id="8a58a-132">If **ulPRSetProperty** is set to **PR_NULL**, the list is a multiple selection list based on an object that contains recipients, such as an address book container, a recipient table for a message, or a distribution list contents table.</span></span> 
  
<span data-ttu-id="8a58a-133">多选列表表必须包括以下各列：</span><span class="sxs-lookup"><span data-stu-id="8a58a-133">A table for a multiple selection list must include the following columns:</span></span>
  
 <span data-ttu-id="8a58a-134">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="8a58a-134">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
  
 <span data-ttu-id="8a58a-135">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="8a58a-135">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>
  
 <span data-ttu-id="8a58a-136">**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="8a58a-136">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span></span>
  
 <span data-ttu-id="8a58a-137">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) 和最多五个其他多值的字符串属性也可以显示与所需的三个列。</span><span class="sxs-lookup"><span data-stu-id="8a58a-137">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) and a maximum of five other multivalued string properties can also be displayed with the three required columns.</span></span> 
  
<span data-ttu-id="8a58a-138">如果未设置为**PR_NULL** **ulPRSetProperty**成员，列表是单项选择列表。</span><span class="sxs-lookup"><span data-stu-id="8a58a-138">If the **ulPRSetProperty** member is not set to **PR_NULL**, the list is a single selection list.</span></span> <span data-ttu-id="8a58a-139">**UlPRSetProperty**的初始值确定所选的第一行。</span><span class="sxs-lookup"><span data-stu-id="8a58a-139">The initial value of **ulPRSetProperty** determines the first selected row.</span></span> <span data-ttu-id="8a58a-140">当用户选择行之一时， **ulPRSetProperty**成员设置为所选的值，该值写回[IMAPIProp::SetProps](imapiprop-setprops.md)调用与该属性接口实现。</span><span class="sxs-lookup"><span data-stu-id="8a58a-140">When a user selects one of the rows, the **ulPRSetProperty** member is set to the selected value and this value is written back to the property interface implementation with a call to [IMAPIProp::SetProps](imapiprop-setprops.md).</span></span> 
  
<span data-ttu-id="8a58a-141">显示表的概述，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="8a58a-141">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="8a58a-142">有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="8a58a-142">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8a58a-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a58a-143">See also</span></span>



[<span data-ttu-id="8a58a-144">DTCTL</span><span class="sxs-lookup"><span data-stu-id="8a58a-144">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="8a58a-145">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="8a58a-145">MAPI Structures</span></span>](mapi-structures.md)

