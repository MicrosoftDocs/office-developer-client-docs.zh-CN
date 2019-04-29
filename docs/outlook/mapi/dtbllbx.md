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
ms.openlocfilehash: 2bff20af2b3e9ea4e203e38ae38a8bc19074a727
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438566"
---
# <a name="dtbllbx"></a><span data-ttu-id="1022b-103">DTBLLBX</span><span class="sxs-lookup"><span data-stu-id="1022b-103">DTBLLBX</span></span>

  
  
<span data-ttu-id="1022b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1022b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1022b-105">介绍将在从显示表生成的对话框中使用的列表。</span><span class="sxs-lookup"><span data-stu-id="1022b-105">Describes a list that will be used in a dialog box that is built from a display table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1022b-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="1022b-106">Header file:</span></span>  <br/> |<span data-ttu-id="1022b-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="1022b-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _DTBLLBX
{
  ULONG ulFlags;
  ULONG ulPRSetProperty;
  ULONG ulPRTableName;
} DTBLLBX, FAR *LPDTBLLBX

```

## <a name="members"></a><span data-ttu-id="1022b-108">成员</span><span class="sxs-lookup"><span data-stu-id="1022b-108">Members</span></span>

 <span data-ttu-id="1022b-109">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="1022b-109">**ulFlags**</span></span>
  
> <span data-ttu-id="1022b-110">用于从列表中消除水平或垂直滚动条的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="1022b-110">Bitmask of flags used to eliminate a horizontal or vertical scroll bar from the list.</span></span> <span data-ttu-id="1022b-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="1022b-111">The following flags can be set:</span></span>
    
<span data-ttu-id="1022b-112">MAPI_NO_HBAR</span><span class="sxs-lookup"><span data-stu-id="1022b-112">MAPI_NO_HBAR</span></span> 
  
> <span data-ttu-id="1022b-113">不应在列表中显示任何水平滚动条。</span><span class="sxs-lookup"><span data-stu-id="1022b-113">No horizontal scroll bar should be shown with the list.</span></span>
    
<span data-ttu-id="1022b-114">MAPI_NO_VBAR</span><span class="sxs-lookup"><span data-stu-id="1022b-114">MAPI_NO_VBAR</span></span> 
  
> <span data-ttu-id="1022b-115">不应在列表中显示垂直滚动条。</span><span class="sxs-lookup"><span data-stu-id="1022b-115">No vertical scroll bar should be shown with the list.</span></span>
    
 <span data-ttu-id="1022b-116">**ulPRSetProperty**</span><span class="sxs-lookup"><span data-stu-id="1022b-116">**ulPRSetProperty**</span></span>
  
> <span data-ttu-id="1022b-117">任何类型的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="1022b-117">Property tag for a property of any type.</span></span> <span data-ttu-id="1022b-118">此属性是由**ulPRTableTable**成员标识的表中的一列。</span><span class="sxs-lookup"><span data-stu-id="1022b-118">This property is one of the columns in the table identified by the **ulPRTableTable** member.</span></span> 
    
 <span data-ttu-id="1022b-119">**ulPRTableName**</span><span class="sxs-lookup"><span data-stu-id="1022b-119">**ulPRTableName**</span></span>
  
> <span data-ttu-id="1022b-120">可以使用**OpenProperty**调用打开的 PT_OBJECT 类型的 table 属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="1022b-120">Property tag for a table property of type PT_OBJECT that can be opened by using an **OpenProperty** call.</span></span> <span data-ttu-id="1022b-121">表应包含的列数取决于列表是单个还是多个选择列表。</span><span class="sxs-lookup"><span data-stu-id="1022b-121">The number of columns that the table should have depends on whether the list is a single or multiple selection list.</span></span> <span data-ttu-id="1022b-122">如果将**ulPRSetProperty**成员设置为**PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)), 则此列表允许多项选择。</span><span class="sxs-lookup"><span data-stu-id="1022b-122">If the **ulPRSetProperty** member is set to **PR_NULL** ([PidTagNull](pidtagnull-canonical-property.md)), the list allows for multiple selection.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1022b-123">说明</span><span class="sxs-lookup"><span data-stu-id="1022b-123">Remarks</span></span>

<span data-ttu-id="1022b-124">**DTBLLBX**结构描述用于显示多个项目的控件的列表, 并允许用户选择一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="1022b-124">A **DTBLLBX** structure describes a list a control that is used to show multiple items and let a user select one or more of the items.</span></span> 
  
<span data-ttu-id="1022b-125">**ulPRSetProperty**成员和**ulPRTableName**成员一起工作;当从表中选择一个值时, 它会在对话框关闭时写回到**ulPRSetProperty** 。</span><span class="sxs-lookup"><span data-stu-id="1022b-125">The **ulPRSetProperty** member and **ulPRTableName** member work together; when one value is chosen from the table, it is written back to **ulPRSetProperty** when the dialog box is dismissed.</span></span> 
  
<span data-ttu-id="1022b-126">flags 值指示是否在列表中显示水平和垂直滚动条。</span><span class="sxs-lookup"><span data-stu-id="1022b-126">The flags value indicates whether a horizontal or vertical scroll bar should be displayed with the list.</span></span> <span data-ttu-id="1022b-127">默认值为如果需要, 则显示滚动条的类型。</span><span class="sxs-lookup"><span data-stu-id="1022b-127">The default is to have types of scroll bars appear if it is required.</span></span> <span data-ttu-id="1022b-128">服务提供程序可以将 MAPI_NO_HBAR 设置为禁止水平滚动条和 MAPI_NO_VBAR, 以禁止显示垂直滚动条。</span><span class="sxs-lookup"><span data-stu-id="1022b-128">Service providers can set MAPI_NO_HBAR to suppress a horizontal scroll bar and MAPI_NO_VBAR to suppress a vertical scroll bar.</span></span> 
  
<span data-ttu-id="1022b-129">当选择列表中的项目时, 这两个属性标记成员将一起显示列表中的值并设置相应的属性。</span><span class="sxs-lookup"><span data-stu-id="1022b-129">The two property tag members work together to display values in the list and set corresponding properties when an item in the list is selected.</span></span> <span data-ttu-id="1022b-130">当 MAPI 第一次显示列表时, 它会调用**IMAPIProp**实现的**OpenProperty**方法, 以检索**ulPRTableName**成员中标识的表。</span><span class="sxs-lookup"><span data-stu-id="1022b-130">When MAPI first displays the list, it calls the **IMAPIProp** implementation's **OpenProperty** method to retrieve the table identified in the **ulPRTableName** member.</span></span> <span data-ttu-id="1022b-131">表中的列数取决于**ulPRSetProperty**成员的值。</span><span class="sxs-lookup"><span data-stu-id="1022b-131">The number of columns in the table depends on the value of the **ulPRSetProperty** member.</span></span> <span data-ttu-id="1022b-132">如果将**ulPRSetProperty**设置为**PR_NULL**, 则列表是基于包含收件人的对象的多选列表, 如通讯簿容器、邮件的收件人表或通讯组列表内容表。</span><span class="sxs-lookup"><span data-stu-id="1022b-132">If **ulPRSetProperty** is set to **PR_NULL**, the list is a multiple selection list based on an object that contains recipients, such as an address book container, a recipient table for a message, or a distribution list contents table.</span></span> 
  
<span data-ttu-id="1022b-133">多选列表的表格必须包含以下列:</span><span class="sxs-lookup"><span data-stu-id="1022b-133">A table for a multiple selection list must include the following columns:</span></span>
  
 <span data-ttu-id="1022b-134">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1022b-134">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
  
 <span data-ttu-id="1022b-135">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1022b-135">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>
  
 <span data-ttu-id="1022b-136">**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1022b-136">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span></span>
  
 <span data-ttu-id="1022b-137">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)), 并且最多有五个其他多值字符串属性也可以显示三个必需的列。</span><span class="sxs-lookup"><span data-stu-id="1022b-137">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) and a maximum of five other multivalued string properties can also be displayed with the three required columns.</span></span> 
  
<span data-ttu-id="1022b-138">如果**ulPRSetProperty**成员未设置为**PR_NULL**, 则该列表为单个选择列表。</span><span class="sxs-lookup"><span data-stu-id="1022b-138">If the **ulPRSetProperty** member is not set to **PR_NULL**, the list is a single selection list.</span></span> <span data-ttu-id="1022b-139">**ulPRSetProperty**的初始值决定了第一个选定的行。</span><span class="sxs-lookup"><span data-stu-id="1022b-139">The initial value of **ulPRSetProperty** determines the first selected row.</span></span> <span data-ttu-id="1022b-140">当用户选择其中一个行时, **ulPRSetProperty**成员将设置为选定值, 并将此值写回到属性接口实现中, 调用[IMAPIProp:: SetProps](imapiprop-setprops.md)。</span><span class="sxs-lookup"><span data-stu-id="1022b-140">When a user selects one of the rows, the **ulPRSetProperty** member is set to the selected value and this value is written back to the property interface implementation with a call to [IMAPIProp::SetProps](imapiprop-setprops.md).</span></span> 
  
<span data-ttu-id="1022b-141">有关显示表的概述, 请参阅[显示表](display-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="1022b-141">For an overview of display tables, see [Display Tables](display-tables.md).</span></span> <span data-ttu-id="1022b-142">有关如何实现显示表的信息, 请参阅[实现显示表](display-table-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="1022b-142">For information about how to implement a display table, see [Implementing a Display Table](display-table-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1022b-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1022b-143">See also</span></span>



[<span data-ttu-id="1022b-144">DTCTL</span><span class="sxs-lookup"><span data-stu-id="1022b-144">DTCTL</span></span>](dtctl.md)


[<span data-ttu-id="1022b-145">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="1022b-145">MAPI Structures</span></span>](mapi-structures.md)

