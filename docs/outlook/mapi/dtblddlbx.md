---
title: DTBLDDLBX
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLDDLBX
api_type:
- COM
ms.assetid: cf60584c-4357-44c7-9d51-f30f7e510c0c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 244aaea4902d6be8eda4cdca176436af9b002ba7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438846"
---
# <a name="dtblddlbx"></a><span data-ttu-id="17734-103">DTBLDDLBX</span><span class="sxs-lookup"><span data-stu-id="17734-103">DTBLDDLBX</span></span>

  
  
<span data-ttu-id="17734-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="17734-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="17734-105">描述将在从显示表构建的对话框中使用的下拉列表控件。</span><span class="sxs-lookup"><span data-stu-id="17734-105">Describes a drop-down list control that will be used in a dialog box built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="17734-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="17734-106">Header file:</span></span>  <br/> |<span data-ttu-id="17734-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="17734-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _DTBLDDLBX
{
  ULONG ulFlags;
  ULONG ulPRDisplayProperty;
  ULONG ulPRSetProperty;
  ULONG ulPRTableName;
} DTBLDDLBX, FAR *LPDTBLDDLBX;

```

## <a name="members"></a><span data-ttu-id="17734-108">成员</span><span class="sxs-lookup"><span data-stu-id="17734-108">Members</span></span>

 <span data-ttu-id="17734-109">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="17734-109">**ulFlags**</span></span>
  
> <span data-ttu-id="17734-110">保留，必须为零。</span><span class="sxs-lookup"><span data-stu-id="17734-110">Reserved, must be zero.</span></span> 
    
 <span data-ttu-id="17734-111">**ulPRDisplayProperty**</span><span class="sxs-lookup"><span data-stu-id="17734-111">**ulPRDisplayProperty**</span></span>
  
> <span data-ttu-id="17734-112">类型为 PT_TSTRING 的属性PT_TSTRING。</span><span class="sxs-lookup"><span data-stu-id="17734-112">Property tag for a property of type PT_TSTRING.</span></span> <span data-ttu-id="17734-113">此属性是由 **ulPRTableName** 成员标识的表中的列之一。</span><span class="sxs-lookup"><span data-stu-id="17734-113">This property is one of the columns in the table identified by the **ulPRTableName** member.</span></span> <span data-ttu-id="17734-114">此属性的值显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="17734-114">The values for this property are displayed in the list.</span></span> 
    
 <span data-ttu-id="17734-115">**ulPRSetProperty**</span><span class="sxs-lookup"><span data-stu-id="17734-115">**ulPRSetProperty**</span></span>
  
> <span data-ttu-id="17734-116">任何类型的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="17734-116">Property tag for a property of any type.</span></span> <span data-ttu-id="17734-117">此属性是由 **ulPRTableName** 成员标识的表中的列之一。</span><span class="sxs-lookup"><span data-stu-id="17734-117">This property is one of the columns in the table identified by the **ulPRTableName** member.</span></span> <span data-ttu-id="17734-118">当列表的用户从 **ulPRTableName** 成员标识的表中选择 **ulPRDisplayProperty** 成员属性值时，将设置相应的 **ulPRSetProperty** 成员。</span><span class="sxs-lookup"><span data-stu-id="17734-118">When the user of the list selects a property value for the **ulPRDisplayProperty** member from the rows of the table identified by the **ulPRTableName** member, the corresponding **ulPRSetProperty** member is set.</span></span> 
    
 <span data-ttu-id="17734-119">**ulPRTableName**</span><span class="sxs-lookup"><span data-stu-id="17734-119">**ulPRTableName**</span></span>
  
> <span data-ttu-id="17734-120">表类型属性的属性标记PT_OBJECT **OpenProperty** 调用打开的表属性。</span><span class="sxs-lookup"><span data-stu-id="17734-120">Property tag for a table property of type PT_OBJECT that can be opened by using an **OpenProperty** call.</span></span> <span data-ttu-id="17734-121">该表应包含两列 **：ulPRDisplayProperty 和** **ulPRSetProperty**。</span><span class="sxs-lookup"><span data-stu-id="17734-121">The table should have two columns: **ulPRDisplayProperty** and **ulPRSetProperty**.</span></span> <span data-ttu-id="17734-122">表格的行应与列表中的项相对应。</span><span class="sxs-lookup"><span data-stu-id="17734-122">The rows of the table should correspond to items in the list.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="17734-123">备注</span><span class="sxs-lookup"><span data-stu-id="17734-123">Remarks</span></span>

<span data-ttu-id="17734-124">**DTBLDDLBX** 结构描述作为单个项目显示的下拉列表控件，直到用户选择展开它。</span><span class="sxs-lookup"><span data-stu-id="17734-124">A **DTBLDDLBX** structure describes a drop-down list control that is displayed as a single item until the user elects to expand it.</span></span> 
  
<span data-ttu-id="17734-125">属性标记标识的三个属性协同工作，以显示列表中的信息并设置相关属性。</span><span class="sxs-lookup"><span data-stu-id="17734-125">The three properties identified by the property tags work together to display the information in the list and set a related property.</span></span> <span data-ttu-id="17734-126">**ulPRTableName** 成员是通过调用 [IMAPIProp：：OpenProperty 来访问的表对象](imapiprop-openproperty.md)。</span><span class="sxs-lookup"><span data-stu-id="17734-126">The **ulPRTableName** member is a table object that is accessed through a call to [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span> <span data-ttu-id="17734-127">该表包含两列：一列用于 **ulPRDisplayProperty** 成员标识的属性，另一列用于 **ulPRSetProperty** 成员标识的属性。</span><span class="sxs-lookup"><span data-stu-id="17734-127">The table has two columns: one column for the property identified by the **ulPRDisplayProperty** member and the other for the property identified by the **ulPRSetProperty** member.</span></span> 
  
<span data-ttu-id="17734-128">**ulPRDisplayProperty** 属性驱动列表显示。</span><span class="sxs-lookup"><span data-stu-id="17734-128">The **ulPRDisplayProperty** property drives the list display.</span></span> <span data-ttu-id="17734-129">当用户从显示器中选择一个值时，MAPI 将调用 [IMAPIProp：：SetProps](imapiprop-setprops.md) 以设置 **由 ulPRSetProperty** 成员标识的相应属性。</span><span class="sxs-lookup"><span data-stu-id="17734-129">When a user selects one of the values from the display, MAPI calls [IMAPIProp::SetProps](imapiprop-setprops.md) to set the corresponding property as identified by the **ulPRSetProperty** member.</span></span> <span data-ttu-id="17734-130">这意味着属性与所选显示属性在同一行中。</span><span class="sxs-lookup"><span data-stu-id="17734-130">This means that the property in the same row as the selected display property.</span></span> <span data-ttu-id="17734-131">不能 **将 ulPRSetProperty** 成员设置为PR_NULL ([PidTagNull](pidtagnull-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="17734-131">The **ulPRSetProperty** member cannot be set to **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)).</span></span>
  
<span data-ttu-id="17734-132">如果 MAPI 已通过调用 [IMAPIProp：：GetProps](imapiprop-getprops.md)检索 **了 ulPRSetProperty** 成员所代表的属性，并且找到表中具有 **ulPRSetProperty** 成员值的行，则列表中将显示初始值。</span><span class="sxs-lookup"><span data-stu-id="17734-132">An initial value is displayed in the list if MAPI has retrieved the property represented by the **ulPRSetProperty** member through a call to [IMAPIProp::GetProps](imapiprop-getprops.md) and located a row in the table with the value for the **ulPRSetProperty** member.</span></span> <span data-ttu-id="17734-133">初始显示的值是该行中 **ulPRDisplayProperty** 列的内容，该列与结构的 **ulPRDisplayProperty** 成员中的属性匹配。</span><span class="sxs-lookup"><span data-stu-id="17734-133">The initial displayed value is the contents of the **ulPRDisplayProperty** column from that row that matches the property in the **ulPRDisplayProperty** member of the structure.</span></span> <span data-ttu-id="17734-134">**GetProps** 为 **ulPRDisplayProperty** 成员标识的属性返回的值将成为首次显示列表时显示的初始值。</span><span class="sxs-lookup"><span data-stu-id="17734-134">The value returned by **GetProps** for the property identified by the **ulPRDisplayProperty** member becomes the initial value that is shown when the list is first displayed.</span></span> 
  
<span data-ttu-id="17734-135">有关显示表的概述，请参阅显示 [表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="17734-135">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="17734-136">若要了解如何实现显示表，请参阅 [实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="17734-136">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span> <span data-ttu-id="17734-137">有关属性类型的信息，请参阅 [MAPI 属性类型概述](mapi-property-type-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="17734-137">For information about property types, see [MAPI Property Type Overview](mapi-property-type-overview.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="17734-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17734-138">See also</span></span>



[<span data-ttu-id="17734-139">DTCTL</span><span class="sxs-lookup"><span data-stu-id="17734-139">DTCTL</span></span>](dtctl.md)
  
[<span data-ttu-id="17734-140">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="17734-140">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="17734-141">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="17734-141">IMAPIProp::SetProps</span></span>](imapiprop-setprops.md)
  
[<span data-ttu-id="17734-142">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="17734-142">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)


[<span data-ttu-id="17734-143">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="17734-143">MAPI Structures</span></span>](mapi-structures.md)
  
[<span data-ttu-id="17734-144">显示表实现</span><span class="sxs-lookup"><span data-stu-id="17734-144">Display Table Implementation</span></span>](display-table-implementation.md)
  
[<span data-ttu-id="17734-145">显示表</span><span class="sxs-lookup"><span data-stu-id="17734-145">Display Tables</span></span>](display-tables.md)
  
[<span data-ttu-id="17734-146">MAPI 属性类型概述</span><span class="sxs-lookup"><span data-stu-id="17734-146">MAPI Property Type Overview</span></span>](mapi-property-type-overview.md)

