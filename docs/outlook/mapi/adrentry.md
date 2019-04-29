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
ms.openlocfilehash: 36e0218c9e4e312a138bef7517242f74079212c4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421436"
---
# <a name="adrentry"></a><span data-ttu-id="af2d5-103">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="af2d5-103">ADRENTRY</span></span>

  
  
<span data-ttu-id="af2d5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="af2d5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="af2d5-105">描述属于收件人的零个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="af2d5-105">Describes zero or more properties that belong to a recipient.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="af2d5-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="af2d5-106">Header file:</span></span>  <br/> |<span data-ttu-id="af2d5-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="af2d5-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _ADRENTRY
{
  ULONG ulReserved1;
  ULONG cValues;
  LPSPropValue rgPropVals;
} ADRENTRY, FAR *LPADRENTRY;

```

## <a name="members"></a><span data-ttu-id="af2d5-108">Members</span><span class="sxs-lookup"><span data-stu-id="af2d5-108">Members</span></span>

 <span data-ttu-id="af2d5-109">**ulReserved1**</span><span class="sxs-lookup"><span data-stu-id="af2d5-109">**ulReserved1**</span></span>
  
> <span data-ttu-id="af2d5-110">保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="af2d5-110">Reserved; must be zero.</span></span>
    
 <span data-ttu-id="af2d5-111">**cValues**</span><span class="sxs-lookup"><span data-stu-id="af2d5-111">**cValues**</span></span>
  
> <span data-ttu-id="af2d5-112">属性值数组中由**rgPropVals**成员指向的属性的计数。</span><span class="sxs-lookup"><span data-stu-id="af2d5-112">Count of properties in the property value array pointed to by the **rgPropVals** member.</span></span> <span data-ttu-id="af2d5-113">**cValues**成员可以为零。</span><span class="sxs-lookup"><span data-stu-id="af2d5-113">The **cValues** member can be zero.</span></span> 
    
 <span data-ttu-id="af2d5-114">**rgPropVals**</span><span class="sxs-lookup"><span data-stu-id="af2d5-114">**rgPropVals**</span></span>
  
> <span data-ttu-id="af2d5-115">指向描述收件人属性的属性值数组的指针。</span><span class="sxs-lookup"><span data-stu-id="af2d5-115">Pointer to a property value array describing the properties for the recipient.</span></span> <span data-ttu-id="af2d5-116">**rgPropVals**成员可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="af2d5-116">The **rgPropVals** member can be NULL.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="af2d5-117">说明</span><span class="sxs-lookup"><span data-stu-id="af2d5-117">Remarks</span></span>

<span data-ttu-id="af2d5-118">**ADRENTRY**结构描述属于单个收件人的属性。</span><span class="sxs-lookup"><span data-stu-id="af2d5-118">An **ADRENTRY** structure describes properties that belong to a single recipient.</span></span> <span data-ttu-id="af2d5-119">通常用于描述收件人的属性包括以下各项:</span><span class="sxs-lookup"><span data-stu-id="af2d5-119">The properties that are typically used to describe a recipient include the following:</span></span> 
  
 <span data-ttu-id="af2d5-120">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="af2d5-120">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
  
 <span data-ttu-id="af2d5-121">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="af2d5-121">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>
  
 <span data-ttu-id="af2d5-122">**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="af2d5-122">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span>
  
 <span data-ttu-id="af2d5-123">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="af2d5-123">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>
  
<span data-ttu-id="af2d5-124">当收件人的[SPropValue](spropvalue.md)数组中出现条目标识符或**PR_ENTRYID**属性时, 表示收件人已解决。</span><span class="sxs-lookup"><span data-stu-id="af2d5-124">When an entry identifier or **PR_ENTRYID** property appears in the [SPropValue](spropvalue.md) array for a recipient, this indicates that the recipient has been resolved.</span></span> <span data-ttu-id="af2d5-125">客户端调用[IAddrBook:: ResolveName](iaddrbook-resolvename.md)方法, 以确保已解决传出邮件的收件人列表中的所有收件人。</span><span class="sxs-lookup"><span data-stu-id="af2d5-125">Clients call the [IAddrBook::ResolveName](iaddrbook-resolvename.md) method to make sure that all recipients in the recipient list of an outgoing message have been resolved.</span></span> <span data-ttu-id="af2d5-126">只有解析的收件人可以与邮件一起发送。</span><span class="sxs-lookup"><span data-stu-id="af2d5-126">Only resolved recipients can be sent with messages.</span></span> 
  
 <span data-ttu-id="af2d5-127">**ADRENTRY**结构通常组合在一起构成[ADRLIST](adrlist.md)结构的**aEntries**成员的数组。</span><span class="sxs-lookup"><span data-stu-id="af2d5-127">**ADRENTRY** structures are typically combined to form an array for the **aEntries** member of an [ADRLIST](adrlist.md) structure.</span></span> 
  
 <span data-ttu-id="af2d5-128">**ADRENTRY**结构和[SRow](srow.md)结构相同, 因为它们都包含一个保留成员、属性值的数组和数组中的值的计数。</span><span class="sxs-lookup"><span data-stu-id="af2d5-128">**ADRENTRY** structures and [SRow](srow.md) structures are identical because they both contain a reserved member, an array of property values, and a count of values in the array.</span></span> <span data-ttu-id="af2d5-129">虽然**ADRENTRY**结构组合起来构成了**ADRLIST**结构的**aEntries**成员, 但**SRow**结构组合在一起构成了[aRow](srowset.md)结构的**SRowSet**成员。</span><span class="sxs-lookup"><span data-stu-id="af2d5-129">Whereas **ADRENTRY** structures are combined to form the **aEntries** member of an **ADRLIST** structure, **SRow** structures are combined to form the **aRow** member of an [SRowSet](srowset.md) structure.</span></span> <span data-ttu-id="af2d5-130">这两种类型的结构都遵循相同的分配规则, 暗指从通讯簿容器的 "内容" 表中检索到的**SRowSet**结构可以转换为**ADRLIST**结构并按如下方式使用。</span><span class="sxs-lookup"><span data-stu-id="af2d5-130">Both types of structures follow the same allocation rules, implying that an **SRowSet** structure that is retrieved from the contents table of an address book container can be cast to an **ADRLIST** structure and used as is.</span></span> 
  
<span data-ttu-id="af2d5-131">**ADRENTRY**结构可以为空。</span><span class="sxs-lookup"><span data-stu-id="af2d5-131">An **ADRENTRY** structure can be empty.</span></span> <span data-ttu-id="af2d5-132">例如, 在删除收件人时, **ADRLIST**结构中包含的结构中包含的**ADRENTRY**结构, 在对**IAddrBook:: Address**的调用中, 该结构指向的_lppAdrList_参数可能为空。</span><span class="sxs-lookup"><span data-stu-id="af2d5-132">For example, an **ADRENTRY** structure that is contained in the **ADRLIST** structure pointed to by the  _lppAdrList_ parameter in a call to **IAddrBook::Address** can be empty when a recipient is being removed.</span></span> 
  
<span data-ttu-id="af2d5-133">有关如何为**ADRENTRY**结构分配内存的详细信息, 请参阅[管理内存中的 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="af2d5-133">For more information about how to allocate memory for **ADRENTRY** structures, see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="af2d5-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af2d5-134">See also</span></span>



[<span data-ttu-id="af2d5-135">IAddrBook::Address</span><span class="sxs-lookup"><span data-stu-id="af2d5-135">IAddrBook::Address</span></span>](iaddrbook-address.md)
  
[<span data-ttu-id="af2d5-136">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="af2d5-136">IMessage::ModifyRecipients</span></span>](imessage-modifyrecipients.md)
  
[<span data-ttu-id="af2d5-137">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="af2d5-137">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="af2d5-138">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="af2d5-138">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="af2d5-139">SRow</span><span class="sxs-lookup"><span data-stu-id="af2d5-139">SRow</span></span>](srow.md)
  
[<span data-ttu-id="af2d5-140">SRowSet</span><span class="sxs-lookup"><span data-stu-id="af2d5-140">SRowSet</span></span>](srowset.md)


[<span data-ttu-id="af2d5-141">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="af2d5-141">MAPI Structures</span></span>](mapi-structures.md)

