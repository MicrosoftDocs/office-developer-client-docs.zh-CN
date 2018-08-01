---
title: ADRENTRY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ADRENTRY
api_type:
- COM
ms.assetid: 5fa091a4-3a84-4881-91b3-e34fd9ca6f38
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4b6f850c8f88088863b37bd94de6b1f3d4c48d4f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19774538"
---
# <a name="adrentry"></a><span data-ttu-id="9d70f-103">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="9d70f-103">ADRENTRY</span></span>

  
  
<span data-ttu-id="9d70f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9d70f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9d70f-105">介绍属于收件人的零个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="9d70f-105">Describes zero or more properties that belong to a recipient.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9d70f-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="9d70f-106">Header file:</span></span>  <br/> |<span data-ttu-id="9d70f-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9d70f-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _ADRENTRY
{
  ULONG ulReserved1;
  ULONG cValues;
  LPSPropValue rgPropVals;
} ADRENTRY, FAR *LPADRENTRY;

```

## <a name="members"></a><span data-ttu-id="9d70f-108">Members</span><span class="sxs-lookup"><span data-stu-id="9d70f-108">Members</span></span>

 <span data-ttu-id="9d70f-109">**ulReserved1**</span><span class="sxs-lookup"><span data-stu-id="9d70f-109">**ulReserved1**</span></span>
  
> <span data-ttu-id="9d70f-110">保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="9d70f-110">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="9d70f-111">**cValues**</span><span class="sxs-lookup"><span data-stu-id="9d70f-111">**cValues**</span></span>
  
> <span data-ttu-id="9d70f-112">属性值数组中的属性数目所指的**rgPropVals**成员。</span><span class="sxs-lookup"><span data-stu-id="9d70f-112">Count of properties in the property value array pointed to by the **rgPropVals** member.</span></span> <span data-ttu-id="9d70f-113">**CValues**成员可以为零。</span><span class="sxs-lookup"><span data-stu-id="9d70f-113">The **cValues** member can be zero.</span></span> 
    
 <span data-ttu-id="9d70f-114">**rgPropVals**</span><span class="sxs-lookup"><span data-stu-id="9d70f-114">**rgPropVals**</span></span>
  
> <span data-ttu-id="9d70f-115">指向收件人描述属性的属性值数组。</span><span class="sxs-lookup"><span data-stu-id="9d70f-115">Pointer to a property value array describing the properties for the recipient.</span></span> <span data-ttu-id="9d70f-116">**RgPropVals**成员可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="9d70f-116">The **rgPropVals** member can be NULL.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="9d70f-117">说明</span><span class="sxs-lookup"><span data-stu-id="9d70f-117">Remarks</span></span>

<span data-ttu-id="9d70f-118">**ADRENTRY**结构介绍属于单个收件人的属性。</span><span class="sxs-lookup"><span data-stu-id="9d70f-118">An **ADRENTRY** structure describes properties that belong to a single recipient.</span></span> <span data-ttu-id="9d70f-119">通常用来描述收件人的属性包括：</span><span class="sxs-lookup"><span data-stu-id="9d70f-119">The properties that are typically used to describe a recipient include the following:</span></span> 
  
 <span data-ttu-id="9d70f-120">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9d70f-120">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
  
 <span data-ttu-id="9d70f-121">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9d70f-121">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>
  
 <span data-ttu-id="9d70f-122">**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9d70f-122">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span>
  
 <span data-ttu-id="9d70f-123">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9d70f-123">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>
  
<span data-ttu-id="9d70f-124">当条目标识符或**PR_ENTRYID**属性显示收件人[SPropValue](spropvalue.md)数组中时，这表示收件人已解决。</span><span class="sxs-lookup"><span data-stu-id="9d70f-124">When an entry identifier or **PR_ENTRYID** property appears in the [SPropValue](spropvalue.md) array for a recipient, this indicates that the recipient has been resolved.</span></span> <span data-ttu-id="9d70f-125">客户端调用[IAddrBook::ResolveName](iaddrbook-resolvename.md)方法，以确保已解决的传出邮件的收件人列表中的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="9d70f-125">Clients call the [IAddrBook::ResolveName](iaddrbook-resolvename.md) method to make sure that all recipients in the recipient list of an outgoing message have been resolved.</span></span> <span data-ttu-id="9d70f-126">只有解析的收件人可以发送消息。</span><span class="sxs-lookup"><span data-stu-id="9d70f-126">Only resolved recipients can be sent with messages.</span></span> 
  
 <span data-ttu-id="9d70f-127">**ADRENTRY**结构通常被组合为**aEntries** [ADRLIST](adrlist.md)结构的成员的数组。</span><span class="sxs-lookup"><span data-stu-id="9d70f-127">**ADRENTRY** structures are typically combined to form an array for the **aEntries** member of an [ADRLIST](adrlist.md) structure.</span></span> 
  
 <span data-ttu-id="9d70f-128">**ADRENTRY**结构和[SRow](srow.md)结构是相同的因为都包含保留的成员，属性值的数组和值数组中的计数。</span><span class="sxs-lookup"><span data-stu-id="9d70f-128">**ADRENTRY** structures and [SRow](srow.md) structures are identical because they both contain a reserved member, an array of property values, and a count of values in the array.</span></span> <span data-ttu-id="9d70f-129">组合**ADRENTRY**结构以形成**ADRLIST**结构的**aEntries**成员，而组合**SRow**结构以形成[SRowSet](srowset.md)结构的**aRow**成员。</span><span class="sxs-lookup"><span data-stu-id="9d70f-129">Whereas **ADRENTRY** structures are combined to form the **aEntries** member of an **ADRLIST** structure, **SRow** structures are combined to form the **aRow** member of an [SRowSet](srowset.md) structure.</span></span> <span data-ttu-id="9d70f-130">两种类型的结构遵循相同的分配规则，这意味着可以强制转换为**ADRLIST**结构和原样使用从通讯簿容器内容表中检索**SRowSet**结构。</span><span class="sxs-lookup"><span data-stu-id="9d70f-130">Both types of structures follow the same allocation rules, implying that an **SRowSet** structure that is retrieved from the contents table of an address book container can be cast to an **ADRLIST** structure and used as is.</span></span> 
  
<span data-ttu-id="9d70f-131">**ADRENTRY**结构可以为空。</span><span class="sxs-lookup"><span data-stu-id="9d70f-131">An **ADRENTRY** structure can be empty.</span></span> <span data-ttu-id="9d70f-132">例如，收件人被删除时，包含在**ADRLIST**结构**IAddrBook::Address**将调用_lppAdrList_参数指向**ADRENTRY**结构可以为空。</span><span class="sxs-lookup"><span data-stu-id="9d70f-132">For example, an **ADRENTRY** structure that is contained in the **ADRLIST** structure pointed to by the  _lppAdrList_ parameter in a call to **IAddrBook::Address** can be empty when a recipient is being removed.</span></span> 
  
<span data-ttu-id="9d70f-133">有关如何为**ADRENTRY**结构分配内存的详细信息，请参阅[管理内存 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="9d70f-133">For more information about how to allocate memory for **ADRENTRY** structures, see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9d70f-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d70f-134">See also</span></span>



[<span data-ttu-id="9d70f-135">IAddrBook::Address</span><span class="sxs-lookup"><span data-stu-id="9d70f-135">IAddrBook::Address</span></span>](iaddrbook-address.md)
  
[<span data-ttu-id="9d70f-136">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="9d70f-136">IMessage::ModifyRecipients</span></span>](imessage-modifyrecipients.md)
  
[<span data-ttu-id="9d70f-137">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="9d70f-137">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="9d70f-138">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="9d70f-138">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="9d70f-139">SRow</span><span class="sxs-lookup"><span data-stu-id="9d70f-139">SRow</span></span>](srow.md)
  
[<span data-ttu-id="9d70f-140">SRowSet</span><span class="sxs-lookup"><span data-stu-id="9d70f-140">SRowSet</span></span>](srowset.md)


[<span data-ttu-id="9d70f-141">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="9d70f-141">MAPI Structures</span></span>](mapi-structures.md)

