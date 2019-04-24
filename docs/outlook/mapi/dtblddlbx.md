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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32340101"
---
# <a name="dtblddlbx"></a><span data-ttu-id="817e7-103">DTBLDDLBX</span><span class="sxs-lookup"><span data-stu-id="817e7-103">DTBLDDLBX</span></span>

  
  
<span data-ttu-id="817e7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="817e7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="817e7-105">介绍将在从显示表生成的对话框中使用的下拉列表控件。</span><span class="sxs-lookup"><span data-stu-id="817e7-105">Describes a drop-down list control that will be used in a dialog box built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="817e7-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="817e7-106">Header file:</span></span>  <br/> |<span data-ttu-id="817e7-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="817e7-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _DTBLDDLBX
{
  ULONG ulFlags;
  ULONG ulPRDisplayProperty;
  ULONG ulPRSetProperty;
  ULONG ulPRTableName;
} DTBLDDLBX, FAR *LPDTBLDDLBX;

```

## <a name="members"></a><span data-ttu-id="817e7-108">成员</span><span class="sxs-lookup"><span data-stu-id="817e7-108">Members</span></span>

 <span data-ttu-id="817e7-109">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="817e7-109">**ulFlags**</span></span>
  
> <span data-ttu-id="817e7-110">保留, 必须为零。</span><span class="sxs-lookup"><span data-stu-id="817e7-110">Reserved, must be zero.</span></span> 
    
 <span data-ttu-id="817e7-111">**ulPRDisplayProperty**</span><span class="sxs-lookup"><span data-stu-id="817e7-111">**ulPRDisplayProperty**</span></span>
  
> <span data-ttu-id="817e7-112">类型为 PT_TSTRING 的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="817e7-112">Property tag for a property of type PT_TSTRING.</span></span> <span data-ttu-id="817e7-113">此属性是由**ulPRTableName**成员标识的表中的一列。</span><span class="sxs-lookup"><span data-stu-id="817e7-113">This property is one of the columns in the table identified by the **ulPRTableName** member.</span></span> <span data-ttu-id="817e7-114">此属性的值将显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="817e7-114">The values for this property are displayed in the list.</span></span> 
    
 <span data-ttu-id="817e7-115">**ulPRSetProperty**</span><span class="sxs-lookup"><span data-stu-id="817e7-115">**ulPRSetProperty**</span></span>
  
> <span data-ttu-id="817e7-116">任何类型的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="817e7-116">Property tag for a property of any type.</span></span> <span data-ttu-id="817e7-117">此属性是由**ulPRTableName**成员标识的表中的一列。</span><span class="sxs-lookup"><span data-stu-id="817e7-117">This property is one of the columns in the table identified by the **ulPRTableName** member.</span></span> <span data-ttu-id="817e7-118">当列表的用户从**ulPRTableName**成员所标识的表的行中选择**ulPRDisplayProperty**成员的属性值时, 将设置相应的**ulPRSetProperty**成员。</span><span class="sxs-lookup"><span data-stu-id="817e7-118">When the user of the list selects a property value for the **ulPRDisplayProperty** member from the rows of the table identified by the **ulPRTableName** member, the corresponding **ulPRSetProperty** member is set.</span></span> 
    
 <span data-ttu-id="817e7-119">**ulPRTableName**</span><span class="sxs-lookup"><span data-stu-id="817e7-119">**ulPRTableName**</span></span>
  
> <span data-ttu-id="817e7-120">可以使用**OpenProperty**调用打开的 PT_OBJECT 类型的 table 属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="817e7-120">Property tag for a table property of type PT_OBJECT that can be opened by using an **OpenProperty** call.</span></span> <span data-ttu-id="817e7-121">该表应具有两列: **ulPRDisplayProperty**和**ulPRSetProperty**。</span><span class="sxs-lookup"><span data-stu-id="817e7-121">The table should have two columns: **ulPRDisplayProperty** and **ulPRSetProperty**.</span></span> <span data-ttu-id="817e7-122">表中的行应与列表中的项相对应。</span><span class="sxs-lookup"><span data-stu-id="817e7-122">The rows of the table should correspond to items in the list.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="817e7-123">注解</span><span class="sxs-lookup"><span data-stu-id="817e7-123">Remarks</span></span>

<span data-ttu-id="817e7-124">**DTBLDDLBX**结构描述了一个下拉列表控件, 该控件显示为单个项目, 直到用户将其展开。</span><span class="sxs-lookup"><span data-stu-id="817e7-124">A **DTBLDDLBX** structure describes a drop-down list control that is displayed as a single item until the user elects to expand it.</span></span> 
  
<span data-ttu-id="817e7-125">由属性标记标识的三个属性一起使用, 以显示列表中的信息并设置一个相关的属性。</span><span class="sxs-lookup"><span data-stu-id="817e7-125">The three properties identified by the property tags work together to display the information in the list and set a related property.</span></span> <span data-ttu-id="817e7-126">**ulPRTableName**成员是通过调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)访问的 table 对象。</span><span class="sxs-lookup"><span data-stu-id="817e7-126">The **ulPRTableName** member is a table object that is accessed through a call to [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span> <span data-ttu-id="817e7-127">表包含两列: 由**ulPRDisplayProperty**成员标识的属性的一个列, 另一个为**ulPRSetProperty**成员标识的属性的列。</span><span class="sxs-lookup"><span data-stu-id="817e7-127">The table has two columns: one column for the property identified by the **ulPRDisplayProperty** member and the other for the property identified by the **ulPRSetProperty** member.</span></span> 
  
<span data-ttu-id="817e7-128">**ulPRDisplayProperty**属性驱动列表显示。</span><span class="sxs-lookup"><span data-stu-id="817e7-128">The **ulPRDisplayProperty** property drives the list display.</span></span> <span data-ttu-id="817e7-129">当用户从显示中选择一个值时, MAPI 调用[IMAPIProp:: SetProps](imapiprop-setprops.md)以设置**ulPRSetProperty**成员标识的相应属性。</span><span class="sxs-lookup"><span data-stu-id="817e7-129">When a user selects one of the values from the display, MAPI calls [IMAPIProp::SetProps](imapiprop-setprops.md) to set the corresponding property as identified by the **ulPRSetProperty** member.</span></span> <span data-ttu-id="817e7-130">这意味着与选定的显示属性位于同一行中的属性。</span><span class="sxs-lookup"><span data-stu-id="817e7-130">This means that the property in the same row as the selected display property.</span></span> <span data-ttu-id="817e7-131">**ulPRSetProperty**成员不能设置为**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="817e7-131">The **ulPRSetProperty** member cannot be set to **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)).</span></span>
  
<span data-ttu-id="817e7-132">如果 MAPI 已通过调用[IMAPIProp:: GetProps](imapiprop-getprops.md)检索**ulPRSetProperty**成员代表的属性, 并在表中找到包含**ulPRSetProperty**成员值的行, 则会在列表中显示一个初始值。</span><span class="sxs-lookup"><span data-stu-id="817e7-132">An initial value is displayed in the list if MAPI has retrieved the property represented by the **ulPRSetProperty** member through a call to [IMAPIProp::GetProps](imapiprop-getprops.md) and located a row in the table with the value for the **ulPRSetProperty** member.</span></span> <span data-ttu-id="817e7-133">最初显示的值是**ulPRDisplayProperty**列中与该结构的**ulPRDisplayProperty**成员中的属性相匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="817e7-133">The initial displayed value is the contents of the **ulPRDisplayProperty** column from that row that matches the property in the **ulPRDisplayProperty** member of the structure.</span></span> <span data-ttu-id="817e7-134">由**ulPRDisplayProperty**成员标识的属性的**GetProps**返回的值成为首次显示列表时显示的初始值。</span><span class="sxs-lookup"><span data-stu-id="817e7-134">The value returned by **GetProps** for the property identified by the **ulPRDisplayProperty** member becomes the initial value that is shown when the list is first displayed.</span></span> 
  
<span data-ttu-id="817e7-135">有关显示表的概述, 请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="817e7-135">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="817e7-136">有关如何实现显示表的信息, 请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="817e7-136">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span> <span data-ttu-id="817e7-137">有关属性类型的信息, 请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="817e7-137">For information about property types, see [MAPI Property Type Overview](mapi-property-type-overview.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="817e7-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="817e7-138">See also</span></span>



[<span data-ttu-id="817e7-139">DTCTL</span><span class="sxs-lookup"><span data-stu-id="817e7-139">DTCTL</span></span>](dtctl.md)
  
[<span data-ttu-id="817e7-140">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="817e7-140">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="817e7-141">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="817e7-141">IMAPIProp::SetProps</span></span>](imapiprop-setprops.md)
  
[<span data-ttu-id="817e7-142">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="817e7-142">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)


[<span data-ttu-id="817e7-143">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="817e7-143">MAPI Structures</span></span>](mapi-structures.md)
  
[<span data-ttu-id="817e7-144">显示表实现</span><span class="sxs-lookup"><span data-stu-id="817e7-144">Display Table Implementation</span></span>](display-table-implementation.md)
  
[<span data-ttu-id="817e7-145">显示表</span><span class="sxs-lookup"><span data-stu-id="817e7-145">Display Tables</span></span>](display-tables.md)
  
[<span data-ttu-id="817e7-146">MAPI 属性类型概述</span><span class="sxs-lookup"><span data-stu-id="817e7-146">MAPI Property Type Overview</span></span>](mapi-property-type-overview.md)

