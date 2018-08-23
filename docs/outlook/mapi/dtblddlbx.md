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
ms.openlocfilehash: 3307bb252ca4436999a541f85657fed9878c798a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579394"
---
# <a name="dtblddlbx"></a><span data-ttu-id="cc46b-103">DTBLDDLBX</span><span class="sxs-lookup"><span data-stu-id="cc46b-103">DTBLDDLBX</span></span>

  
  
<span data-ttu-id="cc46b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cc46b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cc46b-105">描述将显示表中生成的对话框中使用的下拉列表控件。</span><span class="sxs-lookup"><span data-stu-id="cc46b-105">Describes a drop-down list control that will be used in a dialog box built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cc46b-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="cc46b-106">Header file:</span></span>  <br/> |<span data-ttu-id="cc46b-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cc46b-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _DTBLDDLBX
{
  ULONG ulFlags;
  ULONG ulPRDisplayProperty;
  ULONG ulPRSetProperty;
  ULONG ulPRTableName;
} DTBLDDLBX, FAR *LPDTBLDDLBX;

```

## <a name="members"></a><span data-ttu-id="cc46b-108">Members</span><span class="sxs-lookup"><span data-stu-id="cc46b-108">Members</span></span>

 <span data-ttu-id="cc46b-109">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="cc46b-109">**ulFlags**</span></span>
  
> <span data-ttu-id="cc46b-110">保留，必须为零。</span><span class="sxs-lookup"><span data-stu-id="cc46b-110">Reserved, must be zero.</span></span> 
    
 <span data-ttu-id="cc46b-111">**ulPRDisplayProperty**</span><span class="sxs-lookup"><span data-stu-id="cc46b-111">**ulPRDisplayProperty**</span></span>
  
> <span data-ttu-id="cc46b-112">属性标记类型 PT_TSTRING 的属性。</span><span class="sxs-lookup"><span data-stu-id="cc46b-112">Property tag for a property of type PT_TSTRING.</span></span> <span data-ttu-id="cc46b-113">此属性是一个由**ulPRTableName**成员标识表中的列。</span><span class="sxs-lookup"><span data-stu-id="cc46b-113">This property is one of the columns in the table identified by the **ulPRTableName** member.</span></span> <span data-ttu-id="cc46b-114">此属性的值显示在列表中。</span><span class="sxs-lookup"><span data-stu-id="cc46b-114">The values for this property are displayed in the list.</span></span> 
    
 <span data-ttu-id="cc46b-115">**ulPRSetProperty**</span><span class="sxs-lookup"><span data-stu-id="cc46b-115">**ulPRSetProperty**</span></span>
  
> <span data-ttu-id="cc46b-116">属性标记任何类型的属性。</span><span class="sxs-lookup"><span data-stu-id="cc46b-116">Property tag for a property of any type.</span></span> <span data-ttu-id="cc46b-117">此属性是一个由**ulPRTableName**成员标识表中的列。</span><span class="sxs-lookup"><span data-stu-id="cc46b-117">This property is one of the columns in the table identified by the **ulPRTableName** member.</span></span> <span data-ttu-id="cc46b-118">当列表的用户从由**ulPRTableName**成员标识表的行**ulPRDisplayProperty**成员的选择的属性值时，设置相应的**ulPRSetProperty**成员。</span><span class="sxs-lookup"><span data-stu-id="cc46b-118">When the user of the list selects a property value for the **ulPRDisplayProperty** member from the rows of the table identified by the **ulPRTableName** member, the corresponding **ulPRSetProperty** member is set.</span></span> 
    
 <span data-ttu-id="cc46b-119">**ulPRTableName**</span><span class="sxs-lookup"><span data-stu-id="cc46b-119">**ulPRTableName**</span></span>
  
> <span data-ttu-id="cc46b-120">调用属性表属性类型可以打开使用**OpenProperty** PT_OBJECT 的标记。</span><span class="sxs-lookup"><span data-stu-id="cc46b-120">Property tag for a table property of type PT_OBJECT that can be opened by using an **OpenProperty** call.</span></span> <span data-ttu-id="cc46b-121">表应具有两个列： **ulPRDisplayProperty**和**ulPRSetProperty**。</span><span class="sxs-lookup"><span data-stu-id="cc46b-121">The table should have two columns: **ulPRDisplayProperty** and **ulPRSetProperty**.</span></span> <span data-ttu-id="cc46b-122">Table 的行应对应于列表中的项。</span><span class="sxs-lookup"><span data-stu-id="cc46b-122">The rows of the table should correspond to items in the list.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="cc46b-123">注解</span><span class="sxs-lookup"><span data-stu-id="cc46b-123">Remarks</span></span>

<span data-ttu-id="cc46b-124">**DTBLDDLBX**结构描述用户选择将其展开之前将显示为单个项目的下拉列表控件。</span><span class="sxs-lookup"><span data-stu-id="cc46b-124">A **DTBLDDLBX** structure describes a drop-down list control that is displayed as a single item until the user elects to expand it.</span></span> 
  
<span data-ttu-id="cc46b-125">由属性标记标识的三个属性一起在列表中显示的信息和设置相关的属性。</span><span class="sxs-lookup"><span data-stu-id="cc46b-125">The three properties identified by the property tags work together to display the information in the list and set a related property.</span></span> <span data-ttu-id="cc46b-126">**UlPRTableName**成员是 table 对象，通过调用[IMAPIProp::OpenProperty](imapiprop-openproperty.md)访问。</span><span class="sxs-lookup"><span data-stu-id="cc46b-126">The **ulPRTableName** member is a table object that is accessed through a call to [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span> <span data-ttu-id="cc46b-127">表中的两个列： 属性由**ulPRDisplayProperty**成员和另一个用于标识由**ulPRSetProperty**成员属性标识的一列。</span><span class="sxs-lookup"><span data-stu-id="cc46b-127">The table has two columns: one column for the property identified by the **ulPRDisplayProperty** member and the other for the property identified by the **ulPRSetProperty** member.</span></span> 
  
<span data-ttu-id="cc46b-128">**UlPRDisplayProperty**属性驱动器的列表显示。</span><span class="sxs-lookup"><span data-stu-id="cc46b-128">The **ulPRDisplayProperty** property drives the list display.</span></span> <span data-ttu-id="cc46b-129">当用户从显示中选择一个值时，MAPI 调用[IMAPIProp::SetProps](imapiprop-setprops.md)由**ulPRSetProperty**成员标识设置的相应属性。</span><span class="sxs-lookup"><span data-stu-id="cc46b-129">When a user selects one of the values from the display, MAPI calls [IMAPIProp::SetProps](imapiprop-setprops.md) to set the corresponding property as identified by the **ulPRSetProperty** member.</span></span> <span data-ttu-id="cc46b-130">这意味着，选定的显示属性与位于同一行中的属性。</span><span class="sxs-lookup"><span data-stu-id="cc46b-130">This means that the property in the same row as the selected display property.</span></span> <span data-ttu-id="cc46b-131">**UlPRSetProperty**成员不能设置为**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="cc46b-131">The **ulPRSetProperty** member cannot be set to **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)).</span></span>
  
<span data-ttu-id="cc46b-132">如果 MAPI 已检索**ulPRSetProperty**成员[IMAPIProp::GetProps](imapiprop-getprops.md)呼叫通过所表示的属性和值表中的行位于**ulPRSetProperty**成员的列表中显示初始值。</span><span class="sxs-lookup"><span data-stu-id="cc46b-132">An initial value is displayed in the list if MAPI has retrieved the property represented by the **ulPRSetProperty** member through a call to [IMAPIProp::GetProps](imapiprop-getprops.md) and located a row in the table with the value for the **ulPRSetProperty** member.</span></span> <span data-ttu-id="cc46b-133">显示的初始值是结构的**ulPRDisplayProperty**列中**ulPRDisplayProperty**成员属性相匹配的行中的内容。</span><span class="sxs-lookup"><span data-stu-id="cc46b-133">The initial displayed value is the contents of the **ulPRDisplayProperty** column from that row that matches the property in the **ulPRDisplayProperty** member of the structure.</span></span> <span data-ttu-id="cc46b-134">返回**GetProps**标识**ulPRDisplayProperty**成员属性的值将成为首次显示列表时显示的初始值。</span><span class="sxs-lookup"><span data-stu-id="cc46b-134">The value returned by **GetProps** for the property identified by the **ulPRDisplayProperty** member becomes the initial value that is shown when the list is first displayed.</span></span> 
  
<span data-ttu-id="cc46b-135">显示表的概述，请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="cc46b-135">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="cc46b-136">有关如何实施显示表的信息，请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="cc46b-136">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span> <span data-ttu-id="cc46b-137">属性类型有关的信息，请参阅[MAPI 属性类型概述](mapi-property-type-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="cc46b-137">For information about property types, see [MAPI Property Type Overview](mapi-property-type-overview.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cc46b-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc46b-138">See also</span></span>



[<span data-ttu-id="cc46b-139">DTCTL</span><span class="sxs-lookup"><span data-stu-id="cc46b-139">DTCTL</span></span>](dtctl.md)
  
[<span data-ttu-id="cc46b-140">IMAPIProp::OpenProperty</span><span class="sxs-lookup"><span data-stu-id="cc46b-140">IMAPIProp::OpenProperty</span></span>](imapiprop-openproperty.md)
  
[<span data-ttu-id="cc46b-141">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="cc46b-141">IMAPIProp::SetProps</span></span>](imapiprop-setprops.md)
  
[<span data-ttu-id="cc46b-142">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="cc46b-142">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)


[<span data-ttu-id="cc46b-143">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="cc46b-143">MAPI Structures</span></span>](mapi-structures.md)
  
[<span data-ttu-id="cc46b-144">显示表实现</span><span class="sxs-lookup"><span data-stu-id="cc46b-144">Display Table Implementation</span></span>](display-table-implementation.md)
  
[<span data-ttu-id="cc46b-145">显示表</span><span class="sxs-lookup"><span data-stu-id="cc46b-145">Display Tables</span></span>](display-tables.md)
  
[<span data-ttu-id="cc46b-146">MAPI 属性类型概述</span><span class="sxs-lookup"><span data-stu-id="cc46b-146">MAPI Property Type Overview</span></span>](mapi-property-type-overview.md)

