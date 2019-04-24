---
title: ADRLIST
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ADRLIST
api_type:
- COM
ms.assetid: 85f0d8a5-6dd3-4f33-b31a-246d286d6286
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 319c932862615e063a02ffac07e5541b1b20ac7e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32330240"
---
# <a name="adrlist"></a><span data-ttu-id="fdb59-103">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="fdb59-103">ADRLIST</span></span>

<span data-ttu-id="fdb59-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fdb59-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fdb59-105">描述属于一个或多个收件人的零个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="fdb59-105">Describes zero or more properties that belong to one or more recipients.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fdb59-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="fdb59-106">Header file:</span></span>  <br/> |<span data-ttu-id="fdb59-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="fdb59-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="fdb59-108">相关宏:</span><span class="sxs-lookup"><span data-stu-id="fdb59-108">Related macros:</span></span>  <br/> |<span data-ttu-id="fdb59-109">[CbADRLIST](cbadrlist.md)、 [CbNewADRLIST](cbnewadrlist.md)、 [CbNewADRLIST](cbnewadrlist.md)</span><span class="sxs-lookup"><span data-stu-id="fdb59-109">[CbADRLIST](cbadrlist.md), [CbNewADRLIST](cbnewadrlist.md), [CbNewADRLIST](cbnewadrlist.md)</span></span> <br/> |
   
```cpp
typedef struct _ADRLIST
{
  ULONG cEntries;
  ADRENTRY aEntries[MAPI_DIM];
} ADRLIST, FAR *LPADRLIST;

```

## <a name="members"></a><span data-ttu-id="fdb59-110">Members</span><span class="sxs-lookup"><span data-stu-id="fdb59-110">Members</span></span>

<span data-ttu-id="fdb59-111">**cEntries**</span><span class="sxs-lookup"><span data-stu-id="fdb59-111">**cEntries**</span></span>
  
> <span data-ttu-id="fdb59-112">由**aEntries**成员指定的数组中的条目数。</span><span class="sxs-lookup"><span data-stu-id="fdb59-112">Count of entries in the array specified by the **aEntries** member.</span></span> 
    
<span data-ttu-id="fdb59-113">**aEntries**</span><span class="sxs-lookup"><span data-stu-id="fdb59-113">**aEntries**</span></span>
  
> <span data-ttu-id="fdb59-114">[ADRENTRY](adrentry.md)结构的数组, 每个收件人一个结构。</span><span class="sxs-lookup"><span data-stu-id="fdb59-114">Array of [ADRENTRY](adrentry.md) structures, one structure for each recipient.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="fdb59-115">注解</span><span class="sxs-lookup"><span data-stu-id="fdb59-115">Remarks</span></span>

<span data-ttu-id="fdb59-116">**ADRLIST**结构包含一个或多个**ADRENTRY**结构, 每个结构描述收件人的属性。</span><span class="sxs-lookup"><span data-stu-id="fdb59-116">An **ADRLIST** structure contains one or more **ADRENTRY** structures, each describing the properties of a recipient.</span></span> <span data-ttu-id="fdb59-117">收件人可以解析。</span><span class="sxs-lookup"><span data-stu-id="fdb59-117">A recipient can be unresolved.</span></span> <span data-ttu-id="fdb59-118">这意味着它在其属性值的数组中缺少条目标识符。</span><span class="sxs-lookup"><span data-stu-id="fdb59-118">This means that it is lacking an entry identifier in its array of property values.</span></span> <span data-ttu-id="fdb59-119">已解析的收件人意味着将包含 " **\_PR ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))" 属性。</span><span class="sxs-lookup"><span data-stu-id="fdb59-119">A resolved recipient means that the **PR\_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) property is included.</span></span> <span data-ttu-id="fdb59-120">通常, 解析的收件人还具有电子邮件地址**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="fdb59-120">Typically, resolved recipients also have an email address the **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) property.</span></span> <span data-ttu-id="fdb59-121">但是, 电子邮件地址不是必需的。</span><span class="sxs-lookup"><span data-stu-id="fdb59-121">However, the email address is not required.</span></span> <span data-ttu-id="fdb59-122">例如, 使用**ADRLIST**结构来描述收件人列表中的传出邮件和 MAPI, 以显示通讯簿中的条目。</span><span class="sxs-lookup"><span data-stu-id="fdb59-122">**ADRLIST** structures are used, for example, to describe the recipient list for an outgoing message and by MAPI to display the entries in the address book.</span></span> 
  
<span data-ttu-id="fdb59-123">**ADRLIST**结构类似于[SRowSet](srowset.md)结构用于表示表中的行的结构。</span><span class="sxs-lookup"><span data-stu-id="fdb59-123">**ADRLIST** structures resemble [SRowSet](srowset.md) structures the structures used for representing rows in tables.</span></span> <span data-ttu-id="fdb59-124">事实上, 这两个结构设计为可互换使用。</span><span class="sxs-lookup"><span data-stu-id="fdb59-124">In fact, these two structures are designed so that they can be used interchangeably.</span></span> <span data-ttu-id="fdb59-125">两者都包含描述一组属性和数组中值的计数的结构数组。</span><span class="sxs-lookup"><span data-stu-id="fdb59-125">Both contain an array of structures describing a group of properties and a count of the values in the array.</span></span> <span data-ttu-id="fdb59-126">而在**ADRLIST**结构中, 数组包含[ADRENTRY](adrentry.md)结构, 在**SRowSet**结构中, 数组包含[SRow](srow.md)结构。</span><span class="sxs-lookup"><span data-stu-id="fdb59-126">Whereas in the **ADRLIST** structure, the array contains [ADRENTRY](adrentry.md) structures, in the **SRowSet** structure the array contains [SRow](srow.md) structures.</span></span> <span data-ttu-id="fdb59-127">**ADRENTRY**结构和**SRow**结构在布局中相同。</span><span class="sxs-lookup"><span data-stu-id="fdb59-127">**ADRENTRY** structures and **SRow** structures are identical in layout.</span></span> <span data-ttu-id="fdb59-128">由于**ADRLIST**和**SRowSet**结构遵循相同的分配规则, 从通讯簿容器的 "内容" 表中检索到的**SRowSet**结构可以强制转换为**ADRLIST**结构并按如下方式使用。</span><span class="sxs-lookup"><span data-stu-id="fdb59-128">Because **ADRLIST** and **SRowSet** structures follow the same allocation rules, an **SRowSet** structure that is retrieved from the contents table of an address book container can be cast to an **ADRLIST** structure and used as is.</span></span> 
  
<span data-ttu-id="fdb59-129">下图显示了**ADRLIST**结构的布局。</span><span class="sxs-lookup"><span data-stu-id="fdb59-129">The following illustration shows the layout of an **ADRLIST** structure.</span></span> 
  
<span data-ttu-id="fdb59-130">**ADRLIST 组件**</span><span class="sxs-lookup"><span data-stu-id="fdb59-130">**ADRLIST components**</span></span>
  
<span data-ttu-id="fdb59-131">![ADRLIST 组件](media/amapi_18.gif "ADRLIST 组件")</span><span class="sxs-lookup"><span data-stu-id="fdb59-131">![ADRLIST components](media/amapi_18.gif "ADRLIST components")</span></span>
  
<span data-ttu-id="fdb59-132">**ADRLIST**结构中的**ADRENTRY**和[SPropValue](spropvalue.md)部分必须独立于其他部件进行分配和释放。</span><span class="sxs-lookup"><span data-stu-id="fdb59-132">The **ADRENTRY** and [SPropValue](spropvalue.md) portions in an **ADRLIST** structure must be allocated and freed independently of the other parts.</span></span> <span data-ttu-id="fdb59-133">也就是说, 在**ADRENTRY**结构的内存已分配并在**ADRENTRY**结构释放之前释放之后, 必须单独分配每个**SPropValue**结构。</span><span class="sxs-lookup"><span data-stu-id="fdb59-133">That is, each **SPropValue** structure must be allocated individually after memory for the **ADRENTRY** structure has been allocated and freed before the **ADRENTRY** structure is freed.</span></span> <span data-ttu-id="fdb59-134">处理内存的独立性使得收件人和单个收件人属性可以从地址列表中随意添加或删除。</span><span class="sxs-lookup"><span data-stu-id="fdb59-134">This independence in handling memory allows recipients and individual recipient properties to be freely added or deleted from the address list.</span></span> 
  
<span data-ttu-id="fdb59-135">必须使用[MAPIAllocateBuffer](mapiallocatebuffer.md)和[MAPIFreeBuffer](mapifreebuffer.md)函数来分配和释放**ADRLIST**结构及其所有部分。</span><span class="sxs-lookup"><span data-stu-id="fdb59-135">The [MAPIAllocateBuffer](mapiallocatebuffer.md) and [MAPIFreeBuffer](mapifreebuffer.md) functions must be used to allocate and free the **ADRLIST** structure and all its parts.</span></span> 
  
<span data-ttu-id="fdb59-136">如果收件人列表太大而无法装入内存, 客户端可以调用[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)方法来处理列表的子集。</span><span class="sxs-lookup"><span data-stu-id="fdb59-136">If a recipient list is too large to fit in memory, clients can call the [IMessage::ModifyRecipients](imessage-modifyrecipients.md) method to work with a subset of the list.</span></span> <span data-ttu-id="fdb59-137">在这种情况下, 客户端不应使用通讯簿常见的对话框。</span><span class="sxs-lookup"><span data-stu-id="fdb59-137">Clients should not use the address book common dialog boxes in this situation.</span></span> 
  
<span data-ttu-id="fdb59-138">有关如何为**ADRENTRY**结构分配内存的详细信息, 请参阅[管理内存中的 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="fdb59-138">For more information about how to allocate memory for **ADRENTRY** structures, see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fdb59-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fdb59-139">See also</span></span>

- [<span data-ttu-id="fdb59-140">ADRENTRY</span><span class="sxs-lookup"><span data-stu-id="fdb59-140">ADRENTRY</span></span>](adrentry.md)  
- [<span data-ttu-id="fdb59-141">CbNewADRLIST</span><span class="sxs-lookup"><span data-stu-id="fdb59-141">CbNewADRLIST</span></span>](cbnewadrlist.md) 
- [<span data-ttu-id="fdb59-142">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="fdb59-142">IMessage::ModifyRecipients</span></span>](imessage-modifyrecipients.md) 
- [<span data-ttu-id="fdb59-143">SRowSet</span><span class="sxs-lookup"><span data-stu-id="fdb59-143">SRowSet</span></span>](srowset.md)
- [<span data-ttu-id="fdb59-144">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="fdb59-144">MAPI Structures</span></span>](mapi-structures.md)

