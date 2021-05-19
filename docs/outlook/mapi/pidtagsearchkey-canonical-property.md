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
ms.openlocfilehash: 9e6b9ddf37c1db8ea28ae2f82caed2a487e551e5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345463"
---
# <a name="pidtagsearchkey-canonical-property"></a><span data-ttu-id="ac723-103">PidTagSearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="ac723-103">PidTagSearchKey Canonical Property</span></span>

  
  
<span data-ttu-id="ac723-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ac723-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ac723-105">包含标识搜索的相关对象的二进制比较键。</span><span class="sxs-lookup"><span data-stu-id="ac723-105">Contains a binary-comparable key that identifies correlated objects for a search.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ac723-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ac723-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ac723-107">PR_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="ac723-107">PR_SEARCH_KEY</span></span>  <br/> |
|<span data-ttu-id="ac723-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ac723-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ac723-109">0x300B</span><span class="sxs-lookup"><span data-stu-id="ac723-109">0x300B</span></span>  <br/> |
|<span data-ttu-id="ac723-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ac723-110">Data type:</span></span>  <br/> |<span data-ttu-id="ac723-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="ac723-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="ac723-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ac723-112">Area:</span></span>  <br/> |<span data-ttu-id="ac723-113">ID 属性</span><span class="sxs-lookup"><span data-stu-id="ac723-113">ID properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ac723-114">备注</span><span class="sxs-lookup"><span data-stu-id="ac723-114">Remarks</span></span>

<span data-ttu-id="ac723-115">此属性提供相关对象（如邮件副本）的跟踪，并便于查找不需要的事件，如重复的收件人。</span><span class="sxs-lookup"><span data-stu-id="ac723-115">This property provides a trace for related objects, such as message copies, and facilitates finding unwanted occurrences, such as duplicate recipients.</span></span>
  
<span data-ttu-id="ac723-116">MAPI 使用特定规则来构造邮件收件人的搜索键。</span><span class="sxs-lookup"><span data-stu-id="ac723-116">MAPI uses specific rules for constructing search keys for message recipients.</span></span> <span data-ttu-id="ac723-117">搜索键通过连接地址类型 (（大写字符) 、冒号字符"："、规范形式的电子邮件地址和终止 null 字符）来形成。</span><span class="sxs-lookup"><span data-stu-id="ac723-117">The search key is formed by concatenating the address type (in uppercase characters), the colon character ':', the email address in canonical form, and the terminating null character.</span></span> <span data-ttu-id="ac723-118">此处的规范形式意味着正确大小写显示区分大小写的地址，不区分大小写的地址将转换为大写。</span><span class="sxs-lookup"><span data-stu-id="ac723-118">Canonical form here means that case-sensitive addresses appear in the correct case, and addresses that are not case-sensitive are converted to uppercase.</span></span> <span data-ttu-id="ac723-119">这一点对于保留邮件之间的关联很重要。</span><span class="sxs-lookup"><span data-stu-id="ac723-119">This is important in preserving correlations among messages.</span></span>
  
<span data-ttu-id="ac723-120">对于 message 对象，此属性可在创建邮件后立即通过 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法使用。</span><span class="sxs-lookup"><span data-stu-id="ac723-120">For message objects, this property is available through the [IMAPIProp::GetProps](imapiprop-getprops.md) method immediately following message creation.</span></span> <span data-ttu-id="ac723-121">对于其他对象，在首次调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法后可用。</span><span class="sxs-lookup"><span data-stu-id="ac723-121">For other objects, it is available following the first call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="ac723-122">由于此属性是可更改的，因此在 **SaveChanges** 调用提交 [IMAPIProp：：SetProps](imapiprop-setprops.md)方法设置或更改的任何值之前，通过 **GetProps** 获取此属性是不可靠的。</span><span class="sxs-lookup"><span data-stu-id="ac723-122">Because this property is changeable, it is unreliable to obtain it through **GetProps** until a **SaveChanges** call has committed any values set or changed by the [IMAPIProp::SetProps](imapiprop-setprops.md) method.</span></span> 
  
<span data-ttu-id="ac723-123">对于配置文件，MAPI 还提供名为 **MUID_PROFILE_INSTANCE** 的硬编码配置文件节，此属性用作其单个属性。</span><span class="sxs-lookup"><span data-stu-id="ac723-123">For profiles, MAPI also furnishes a hard-coded profile section named **MUID_PROFILE_INSTANCE**, with this property as its single property.</span></span> <span data-ttu-id="ac723-124">该密钥保证在以前创建的所有配置文件中是唯一的，并且比 **PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md)) 属性更可靠，例如，可以使用相同的名称删除和重新创建该属性。</span><span class="sxs-lookup"><span data-stu-id="ac723-124">This key is guaranteed to be unique among all profiles ever created, and can be more reliable than the **PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md)) property, which can be, for example, deleted and recreated with the same name.</span></span>
  
<span data-ttu-id="ac723-125">下表总结了 PR_ENTRYID ([PidTagEntryId](pidtagentryid-canonical-property.md)) 、PR_RECORD_KEY ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 和此属性之间的重要差异。  </span><span class="sxs-lookup"><span data-stu-id="ac723-125">The following table summarizes important differences among the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)), **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)), and this property.</span></span>
  
|<span data-ttu-id="ac723-126">**特征**</span><span class="sxs-lookup"><span data-stu-id="ac723-126">**Characteristic**</span></span>|<span data-ttu-id="ac723-127">PR_ENTRYID\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ac723-127">\*\*\*\*PR_ENTRYID\*\*\*\*</span></span>|<span data-ttu-id="ac723-128">PR_RECORD_KEY\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ac723-128">\*\*\*\*PR_RECORD_KEY\*\*\*\*</span></span>|<span data-ttu-id="ac723-129">PR_SEARCH_KEY\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ac723-129">\*\*\*\*PR_SEARCH_KEY\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ac723-130">附件对象上必需</span><span class="sxs-lookup"><span data-stu-id="ac723-130">Required on attachment objects</span></span>  <br/> |<span data-ttu-id="ac723-131">否</span><span class="sxs-lookup"><span data-stu-id="ac723-131">No</span></span>  <br/> |<span data-ttu-id="ac723-132">是</span><span class="sxs-lookup"><span data-stu-id="ac723-132">Yes</span></span>  <br/> |<span data-ttu-id="ac723-133">否</span><span class="sxs-lookup"><span data-stu-id="ac723-133">No</span></span>  <br/> |
|<span data-ttu-id="ac723-134">文件夹对象上必需</span><span class="sxs-lookup"><span data-stu-id="ac723-134">Required on folder objects</span></span>  <br/> |<span data-ttu-id="ac723-135">是</span><span class="sxs-lookup"><span data-stu-id="ac723-135">Yes</span></span>  <br/> |<span data-ttu-id="ac723-136">是</span><span class="sxs-lookup"><span data-stu-id="ac723-136">Yes</span></span>  <br/> |<span data-ttu-id="ac723-137">否</span><span class="sxs-lookup"><span data-stu-id="ac723-137">No</span></span>  <br/> |
|<span data-ttu-id="ac723-138">在邮件存储对象上是必需的</span><span class="sxs-lookup"><span data-stu-id="ac723-138">Required on message store objects</span></span>  <br/> |<span data-ttu-id="ac723-139">是</span><span class="sxs-lookup"><span data-stu-id="ac723-139">Yes</span></span>  <br/> |<span data-ttu-id="ac723-140">是</span><span class="sxs-lookup"><span data-stu-id="ac723-140">Yes</span></span>  <br/> |<span data-ttu-id="ac723-141">否</span><span class="sxs-lookup"><span data-stu-id="ac723-141">No</span></span>  <br/> |
|<span data-ttu-id="ac723-142">状态对象上必需</span><span class="sxs-lookup"><span data-stu-id="ac723-142">Required on status objects</span></span>  <br/> |<span data-ttu-id="ac723-143">是</span><span class="sxs-lookup"><span data-stu-id="ac723-143">Yes</span></span>  <br/> |<span data-ttu-id="ac723-144">否</span><span class="sxs-lookup"><span data-stu-id="ac723-144">No</span></span>  <br/> |<span data-ttu-id="ac723-145">否</span><span class="sxs-lookup"><span data-stu-id="ac723-145">No</span></span>  <br/> |
|<span data-ttu-id="ac723-146">按客户端创建</span><span class="sxs-lookup"><span data-stu-id="ac723-146">Creatable by client</span></span>  <br/> |<span data-ttu-id="ac723-147">否</span><span class="sxs-lookup"><span data-stu-id="ac723-147">No</span></span>  <br/> |<span data-ttu-id="ac723-148">否</span><span class="sxs-lookup"><span data-stu-id="ac723-148">No</span></span>  <br/> |<span data-ttu-id="ac723-149">是</span><span class="sxs-lookup"><span data-stu-id="ac723-149">Yes</span></span>  <br/> |
|<span data-ttu-id="ac723-150">在 **SaveChanges 之前可用**</span><span class="sxs-lookup"><span data-stu-id="ac723-150">Available before **SaveChanges**</span></span> <br/> |<span data-ttu-id="ac723-151">取决于提供程序实现</span><span class="sxs-lookup"><span data-stu-id="ac723-151">Depends on the provider implementation</span></span>  <br/> |<span data-ttu-id="ac723-152">取决于提供程序实现</span><span class="sxs-lookup"><span data-stu-id="ac723-152">Depends on the provider implementation</span></span>  <br/> |<span data-ttu-id="ac723-153">对于邮件，是。</span><span class="sxs-lookup"><span data-stu-id="ac723-153">For messages, Yes.</span></span> <span data-ttu-id="ac723-154">对于其他人，它依赖于提供程序实现。</span><span class="sxs-lookup"><span data-stu-id="ac723-154">For others, It depends on the provider implementation.</span></span>  <br/> |
|<span data-ttu-id="ac723-155">复制操作中已更改</span><span class="sxs-lookup"><span data-stu-id="ac723-155">Changed in a copy operation</span></span>  <br/> |<span data-ttu-id="ac723-156">是</span><span class="sxs-lookup"><span data-stu-id="ac723-156">Yes</span></span>  <br/> |<span data-ttu-id="ac723-157">是</span><span class="sxs-lookup"><span data-stu-id="ac723-157">Yes</span></span>  <br/> |<span data-ttu-id="ac723-158">否</span><span class="sxs-lookup"><span data-stu-id="ac723-158">No</span></span>  <br/> |
|<span data-ttu-id="ac723-159">复制后客户端可更改</span><span class="sxs-lookup"><span data-stu-id="ac723-159">Changeable by client after a copy</span></span>  <br/> |<span data-ttu-id="ac723-160">否</span><span class="sxs-lookup"><span data-stu-id="ac723-160">No</span></span>  <br/> |<span data-ttu-id="ac723-161">否</span><span class="sxs-lookup"><span data-stu-id="ac723-161">No</span></span>  <br/> |<span data-ttu-id="ac723-162">是</span><span class="sxs-lookup"><span data-stu-id="ac723-162">Yes</span></span>  <br/> |
|<span data-ttu-id="ac723-163">在 ... 中是唯一的</span><span class="sxs-lookup"><span data-stu-id="ac723-163">Unique within ...</span></span>  <br/> |<span data-ttu-id="ac723-164">整个世界</span><span class="sxs-lookup"><span data-stu-id="ac723-164">Entire world</span></span>  <br/> |<span data-ttu-id="ac723-165">提供程序实例</span><span class="sxs-lookup"><span data-stu-id="ac723-165">Provider instance</span></span>  <br/> |<span data-ttu-id="ac723-166">整个世界</span><span class="sxs-lookup"><span data-stu-id="ac723-166">Entire world</span></span>  <br/> |
|<span data-ttu-id="ac723-167">二进制 (与 memcmp) </span><span class="sxs-lookup"><span data-stu-id="ac723-167">Binary comparable (as with memcmp)</span></span>  <br/> |<span data-ttu-id="ac723-168">否 -- 使用 [IMAPISupport：：CompareEntryIDs](imapisupport-compareentryids.md)</span><span class="sxs-lookup"><span data-stu-id="ac723-168">No -- use [IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md)</span></span> <br/> |<span data-ttu-id="ac723-169">是</span><span class="sxs-lookup"><span data-stu-id="ac723-169">Yes</span></span>  <br/> |<span data-ttu-id="ac723-170">是</span><span class="sxs-lookup"><span data-stu-id="ac723-170">Yes</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="ac723-171">相关资源</span><span class="sxs-lookup"><span data-stu-id="ac723-171">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ac723-172">协议规范</span><span class="sxs-lookup"><span data-stu-id="ac723-172">Protocol specifications</span></span>

<span data-ttu-id="ac723-173">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ac723-173">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ac723-174">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="ac723-174">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ac723-175">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ac723-175">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ac723-176">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="ac723-176">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="ac723-177">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ac723-177">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ac723-178">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="ac723-178">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ac723-179">头文件</span><span class="sxs-lookup"><span data-stu-id="ac723-179">Header files</span></span>

<span data-ttu-id="ac723-180">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ac723-180">Mapidefs.h</span></span>
  
> <span data-ttu-id="ac723-181">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ac723-181">Provides data type definitions.</span></span>
    
<span data-ttu-id="ac723-182">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ac723-182">Mapitags.h</span></span>
  
> <span data-ttu-id="ac723-183">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ac723-183">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ac723-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac723-184">See also</span></span>



[<span data-ttu-id="ac723-185">PidTagResponsibility 规范属性</span><span class="sxs-lookup"><span data-stu-id="ac723-185">PidTagResponsibility Canonical Property</span></span>](pidtagresponsibility-canonical-property.md)
  
[<span data-ttu-id="ac723-186">PidTagStoreRecordKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="ac723-186">PidTagStoreRecordKey Canonical Property</span></span>](pidtagstorerecordkey-canonical-property.md)


[<span data-ttu-id="ac723-187">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ac723-187">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ac723-188">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ac723-188">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ac723-189">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ac723-189">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ac723-190">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ac723-190">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

