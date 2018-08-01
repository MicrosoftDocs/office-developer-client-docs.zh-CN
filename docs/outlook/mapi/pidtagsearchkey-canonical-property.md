---
title: PidTagSearchKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: fcab369a-a1f4-4425-a272-e35046914a4d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 169afc3b8cf982c4767802542b900ae80822cd01
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778370"
---
# <a name="pidtagsearchkey-canonical-property"></a><span data-ttu-id="96e60-103">PidTagSearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="96e60-103">PidTagSearchKey Canonical Property</span></span>

  
  
<span data-ttu-id="96e60-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="96e60-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="96e60-105">包含一个标识用于搜索的相关的对象的二进制相当关键字。</span><span class="sxs-lookup"><span data-stu-id="96e60-105">Contains a binary-comparable key that identifies correlated objects for a search.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="96e60-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="96e60-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="96e60-107">PR_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="96e60-107">PR_SEARCH_KEY</span></span>  <br/> |
|<span data-ttu-id="96e60-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="96e60-108">Identifier:</span></span>  <br/> |<span data-ttu-id="96e60-109">0x300B</span><span class="sxs-lookup"><span data-stu-id="96e60-109">0x300B</span></span>  <br/> |
|<span data-ttu-id="96e60-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="96e60-110">Data type:</span></span>  <br/> |<span data-ttu-id="96e60-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="96e60-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="96e60-112">区域：</span><span class="sxs-lookup"><span data-stu-id="96e60-112">Area:</span></span>  <br/> |<span data-ttu-id="96e60-113">ID 属性</span><span class="sxs-lookup"><span data-stu-id="96e60-113">ID properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="96e60-114">说明</span><span class="sxs-lookup"><span data-stu-id="96e60-114">Remarks</span></span>

<span data-ttu-id="96e60-115">此属性的相关对象，如邮件副本提供跟踪，从而便于查找不需要匹配项，如重复的收件人。</span><span class="sxs-lookup"><span data-stu-id="96e60-115">This property provides a trace for related objects, such as message copies, and facilitates finding unwanted occurrences, such as duplicate recipients.</span></span>
  
<span data-ttu-id="96e60-116">MAPI 的邮件的收件人，用于构建搜索关键字使用的特定规则。</span><span class="sxs-lookup"><span data-stu-id="96e60-116">MAPI uses specific rules for constructing search keys for message recipients.</span></span> <span data-ttu-id="96e60-117">搜索关键字通过将的地址类型 （在大写字符），而形成冒号 ':'，规范窗体和终止空字符中的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="96e60-117">The search key is formed by concatenating the address type (in uppercase characters), the colon character ':', the email address in canonical form, and the terminating null character.</span></span> <span data-ttu-id="96e60-118">此处规范形式意味着区分大小写地址出现在正确的大小写，并且不区分大小写的地址转换为大写。</span><span class="sxs-lookup"><span data-stu-id="96e60-118">Canonical form here means that case-sensitive addresses appear in the correct case, and addresses that are not case-sensitive are converted to uppercase.</span></span> <span data-ttu-id="96e60-119">这是重要中保留邮件之间的关联。</span><span class="sxs-lookup"><span data-stu-id="96e60-119">This is important in preserving correlations among messages.</span></span>
  
<span data-ttu-id="96e60-120">对于邮件对象，该属性是可通过紧跟创建消息[IMAPIProp::GetProps](imapiprop-getprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="96e60-120">For message objects, this property is available through the [IMAPIProp::GetProps](imapiprop-getprops.md) method immediately following message creation.</span></span> <span data-ttu-id="96e60-121">对于其他对象，它位于关注[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法第一个呼叫。</span><span class="sxs-lookup"><span data-stu-id="96e60-121">For other objects, it is available following the first call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="96e60-122">此属性为可更改，因为它不可靠获取通过**GetProps**直到**SaveChanges**呼叫提交设置或更改[IMAPIProp::SetProps](imapiprop-setprops.md)方法的任何值。</span><span class="sxs-lookup"><span data-stu-id="96e60-122">Because this property is changeable, it is unreliable to obtain it through **GetProps** until a **SaveChanges** call has committed any values set or changed by the [IMAPIProp::SetProps](imapiprop-setprops.md) method.</span></span> 
  
<span data-ttu-id="96e60-123">对于配置文件，MAPI 还提供此属性作为其单个属性名为**MUID_PROFILE_INSTANCE**，硬编码的配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="96e60-123">For profiles, MAPI also furnishes a hard-coded profile section named **MUID_PROFILE_INSTANCE**, with this property as its single property.</span></span> <span data-ttu-id="96e60-124">此项保证创建过的所有配置文件中是唯一的并且可以比**PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md)) 属性，其中，例如，删除，并且具有相同名称重新创建更可靠。</span><span class="sxs-lookup"><span data-stu-id="96e60-124">This key is guaranteed to be unique among all profiles ever created, and can be more reliable than the **PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md)) property, which can be, for example, deleted and recreated with the same name.</span></span>
  
<span data-ttu-id="96e60-125">下表总结了**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))、 **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 和此属性之间的重要不同之处。</span><span class="sxs-lookup"><span data-stu-id="96e60-125">The following table summarizes important differences among the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)), **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)), and this property.</span></span>
  
|<span data-ttu-id="96e60-126">**特征**</span><span class="sxs-lookup"><span data-stu-id="96e60-126">**Characteristic**</span></span>|<span data-ttu-id="96e60-127">PR_ENTRYID \*\*\*</span><span class="sxs-lookup"><span data-stu-id="96e60-127">****PR_ENTRYID****</span></span>|<span data-ttu-id="96e60-128">PR_RECORD_KEY \*\*\*</span><span class="sxs-lookup"><span data-stu-id="96e60-128">****PR_RECORD_KEY****</span></span>|<span data-ttu-id="96e60-129">PR_SEARCH_KEY \*\*\*</span><span class="sxs-lookup"><span data-stu-id="96e60-129">****PR_SEARCH_KEY****</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="96e60-130">Attachment 对象上所需</span><span class="sxs-lookup"><span data-stu-id="96e60-130">Required on attachment objects</span></span>  <br/> |<span data-ttu-id="96e60-131">否</span><span class="sxs-lookup"><span data-stu-id="96e60-131">No</span></span>  <br/> |<span data-ttu-id="96e60-132">可访问</span><span class="sxs-lookup"><span data-stu-id="96e60-132">Yes</span></span>  <br/> |<span data-ttu-id="96e60-133">否</span><span class="sxs-lookup"><span data-stu-id="96e60-133">No</span></span>  <br/> |
|<span data-ttu-id="96e60-134">需要对文件夹对象</span><span class="sxs-lookup"><span data-stu-id="96e60-134">Required on folder objects</span></span>  <br/> |<span data-ttu-id="96e60-135">可访问</span><span class="sxs-lookup"><span data-stu-id="96e60-135">Yes</span></span>  <br/> |<span data-ttu-id="96e60-136">可访问</span><span class="sxs-lookup"><span data-stu-id="96e60-136">Yes</span></span>  <br/> |<span data-ttu-id="96e60-137">否</span><span class="sxs-lookup"><span data-stu-id="96e60-137">No</span></span>  <br/> |
|<span data-ttu-id="96e60-138">消息存储对象上所需</span><span class="sxs-lookup"><span data-stu-id="96e60-138">Required on message store objects</span></span>  <br/> |<span data-ttu-id="96e60-139">可访问</span><span class="sxs-lookup"><span data-stu-id="96e60-139">Yes</span></span>  <br/> |<span data-ttu-id="96e60-140">可访问</span><span class="sxs-lookup"><span data-stu-id="96e60-140">Yes</span></span>  <br/> |<span data-ttu-id="96e60-141">否</span><span class="sxs-lookup"><span data-stu-id="96e60-141">No</span></span>  <br/> |
|<span data-ttu-id="96e60-142">状态对象上所需</span><span class="sxs-lookup"><span data-stu-id="96e60-142">Required on status objects</span></span>  <br/> |<span data-ttu-id="96e60-143">可访问</span><span class="sxs-lookup"><span data-stu-id="96e60-143">Yes</span></span>  <br/> |<span data-ttu-id="96e60-144">否</span><span class="sxs-lookup"><span data-stu-id="96e60-144">No</span></span>  <br/> |<span data-ttu-id="96e60-145">否</span><span class="sxs-lookup"><span data-stu-id="96e60-145">No</span></span>  <br/> |
|<span data-ttu-id="96e60-146">可创建由客户端</span><span class="sxs-lookup"><span data-stu-id="96e60-146">Creatable by client</span></span>  <br/> |<span data-ttu-id="96e60-147">否</span><span class="sxs-lookup"><span data-stu-id="96e60-147">No</span></span>  <br/> |<span data-ttu-id="96e60-148">否</span><span class="sxs-lookup"><span data-stu-id="96e60-148">No</span></span>  <br/> |<span data-ttu-id="96e60-149">可访问</span><span class="sxs-lookup"><span data-stu-id="96e60-149">Yes</span></span>  <br/> |
|<span data-ttu-id="96e60-150">**SaveChanges**前可用</span><span class="sxs-lookup"><span data-stu-id="96e60-150">Available before **SaveChanges**</span></span> <br/> |<span data-ttu-id="96e60-151">取决于提供程序实现</span><span class="sxs-lookup"><span data-stu-id="96e60-151">Depends on the provider implementation</span></span>  <br/> |<span data-ttu-id="96e60-152">取决于提供程序实现</span><span class="sxs-lookup"><span data-stu-id="96e60-152">Depends on the provider implementation</span></span>  <br/> |<span data-ttu-id="96e60-153">用于消息，是。</span><span class="sxs-lookup"><span data-stu-id="96e60-153">For messages, Yes.</span></span> <span data-ttu-id="96e60-154">其他人，这取决于提供程序实现。</span><span class="sxs-lookup"><span data-stu-id="96e60-154">For others, It depends on the provider implementation.</span></span>  <br/> |
|<span data-ttu-id="96e60-155">复制操作中发生的更改</span><span class="sxs-lookup"><span data-stu-id="96e60-155">Changed in a copy operation</span></span>  <br/> |<span data-ttu-id="96e60-156">可访问</span><span class="sxs-lookup"><span data-stu-id="96e60-156">Yes</span></span>  <br/> |<span data-ttu-id="96e60-157">可访问</span><span class="sxs-lookup"><span data-stu-id="96e60-157">Yes</span></span>  <br/> |<span data-ttu-id="96e60-158">否</span><span class="sxs-lookup"><span data-stu-id="96e60-158">No</span></span>  <br/> |
|<span data-ttu-id="96e60-159">可更改后副本的客户端</span><span class="sxs-lookup"><span data-stu-id="96e60-159">Changeable by client after a copy</span></span>  <br/> |<span data-ttu-id="96e60-160">否</span><span class="sxs-lookup"><span data-stu-id="96e60-160">No</span></span>  <br/> |<span data-ttu-id="96e60-161">否</span><span class="sxs-lookup"><span data-stu-id="96e60-161">No</span></span>  <br/> |<span data-ttu-id="96e60-162">可访问</span><span class="sxs-lookup"><span data-stu-id="96e60-162">Yes</span></span>  <br/> |
|<span data-ttu-id="96e60-163">中的唯一...</span><span class="sxs-lookup"><span data-stu-id="96e60-163">Unique within ...</span></span>  <br/> |<span data-ttu-id="96e60-164">整个 world</span><span class="sxs-lookup"><span data-stu-id="96e60-164">Entire world</span></span>  <br/> |<span data-ttu-id="96e60-165">提供程序实例</span><span class="sxs-lookup"><span data-stu-id="96e60-165">Provider instance</span></span>  <br/> |<span data-ttu-id="96e60-166">整个 world</span><span class="sxs-lookup"><span data-stu-id="96e60-166">Entire world</span></span>  <br/> |
|<span data-ttu-id="96e60-167">二进制 （与 memcmp) 相当</span><span class="sxs-lookup"><span data-stu-id="96e60-167">Binary comparable (as with memcmp)</span></span>  <br/> |<span data-ttu-id="96e60-168">否 — 使用[IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md)</span><span class="sxs-lookup"><span data-stu-id="96e60-168">No -- use [IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md)</span></span> <br/> |<span data-ttu-id="96e60-169">可访问</span><span class="sxs-lookup"><span data-stu-id="96e60-169">Yes</span></span>  <br/> |<span data-ttu-id="96e60-170">可访问</span><span class="sxs-lookup"><span data-stu-id="96e60-170">Yes</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="96e60-171">相关资源</span><span class="sxs-lookup"><span data-stu-id="96e60-171">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="96e60-172">协议规范</span><span class="sxs-lookup"><span data-stu-id="96e60-172">Protocol specifications</span></span>

<span data-ttu-id="96e60-173">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="96e60-173">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="96e60-174">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="96e60-174">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="96e60-175">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="96e60-175">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="96e60-176">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="96e60-176">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="96e60-177">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="96e60-177">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="96e60-178">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="96e60-178">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="96e60-179">头文件</span><span class="sxs-lookup"><span data-stu-id="96e60-179">Header files</span></span>

<span data-ttu-id="96e60-180">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="96e60-180">Mapidefs.h</span></span>
  
> <span data-ttu-id="96e60-181">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="96e60-181">Provides data type definitions.</span></span>
    
<span data-ttu-id="96e60-182">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="96e60-182">Mapitags.h</span></span>
  
> <span data-ttu-id="96e60-183">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="96e60-183">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="96e60-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="96e60-184">See also</span></span>



[<span data-ttu-id="96e60-185">PidTagResponsibility 规范属性</span><span class="sxs-lookup"><span data-stu-id="96e60-185">PidTagResponsibility Canonical Property</span></span>](pidtagresponsibility-canonical-property.md)
  
[<span data-ttu-id="96e60-186">PidTagStoreRecordKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="96e60-186">PidTagStoreRecordKey Canonical Property</span></span>](pidtagstorerecordkey-canonical-property.md)


[<span data-ttu-id="96e60-187">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="96e60-187">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="96e60-188">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="96e60-188">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="96e60-189">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="96e60-189">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="96e60-190">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="96e60-190">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

