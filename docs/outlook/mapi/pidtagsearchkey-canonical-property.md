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
# <a name="pidtagsearchkey-canonical-property"></a><span data-ttu-id="725c9-103">PidTagSearchKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="725c9-103">PidTagSearchKey Canonical Property</span></span>

  
  
<span data-ttu-id="725c9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="725c9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="725c9-105">包含二进制可比较的键, 用于标识搜索的相关对象。</span><span class="sxs-lookup"><span data-stu-id="725c9-105">Contains a binary-comparable key that identifies correlated objects for a search.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="725c9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="725c9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="725c9-107">PR_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="725c9-107">PR_SEARCH_KEY</span></span>  <br/> |
|<span data-ttu-id="725c9-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="725c9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="725c9-109">0x300B</span><span class="sxs-lookup"><span data-stu-id="725c9-109">0x300B</span></span>  <br/> |
|<span data-ttu-id="725c9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="725c9-110">Data type:</span></span>  <br/> |<span data-ttu-id="725c9-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="725c9-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="725c9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="725c9-112">Area:</span></span>  <br/> |<span data-ttu-id="725c9-113">ID 属性</span><span class="sxs-lookup"><span data-stu-id="725c9-113">ID properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="725c9-114">注解</span><span class="sxs-lookup"><span data-stu-id="725c9-114">Remarks</span></span>

<span data-ttu-id="725c9-115">此属性为相关对象 (如邮件副本) 提供跟踪, 便于查找不需要的事件, 如重复的收件人。</span><span class="sxs-lookup"><span data-stu-id="725c9-115">This property provides a trace for related objects, such as message copies, and facilitates finding unwanted occurrences, such as duplicate recipients.</span></span>
  
<span data-ttu-id="725c9-116">MAPI 使用特定的规则来构建邮件收件人的搜索键。</span><span class="sxs-lookup"><span data-stu-id="725c9-116">MAPI uses specific rules for constructing search keys for message recipients.</span></span> <span data-ttu-id="725c9-117">通过串联地址类型 (大写字符)、冒号字符 ":"、电子邮件地址规范格式以及终止 null 字符形成搜索关键字。</span><span class="sxs-lookup"><span data-stu-id="725c9-117">The search key is formed by concatenating the address type (in uppercase characters), the colon character ':', the email address in canonical form, and the terminating null character.</span></span> <span data-ttu-id="725c9-118">此处的规范表单表示区分大小写的地址以正确的大小写显示, 并且不区分大小写的地址将转换为大写。</span><span class="sxs-lookup"><span data-stu-id="725c9-118">Canonical form here means that case-sensitive addresses appear in the correct case, and addresses that are not case-sensitive are converted to uppercase.</span></span> <span data-ttu-id="725c9-119">这在保留邮件之间的相关性时非常重要。</span><span class="sxs-lookup"><span data-stu-id="725c9-119">This is important in preserving correlations among messages.</span></span>
  
<span data-ttu-id="725c9-120">对于 message 对象, 此属性通过[IMAPIProp:: GetProps](imapiprop-getprops.md)方法在邮件创建后立即可用。</span><span class="sxs-lookup"><span data-stu-id="725c9-120">For message objects, this property is available through the [IMAPIProp::GetProps](imapiprop-getprops.md) method immediately following message creation.</span></span> <span data-ttu-id="725c9-121">对于其他对象, 在首次调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法时, 将提供该对象。</span><span class="sxs-lookup"><span data-stu-id="725c9-121">For other objects, it is available following the first call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="725c9-122">由于此属性是可更改的, 在**SaveChanges**调用提交了由[IMAPIProp:: SetProps](imapiprop-setprops.md)方法设置或更改的任何值之前, 不能通过**GetProps**获取该属性。</span><span class="sxs-lookup"><span data-stu-id="725c9-122">Because this property is changeable, it is unreliable to obtain it through **GetProps** until a **SaveChanges** call has committed any values set or changed by the [IMAPIProp::SetProps](imapiprop-setprops.md) method.</span></span> 
  
<span data-ttu-id="725c9-123">对于配置文件, MAPI 也提供名为**MUID_PROFILE_INSTANCE**的硬编码配置文件部分, 并将该属性作为其单个属性。</span><span class="sxs-lookup"><span data-stu-id="725c9-123">For profiles, MAPI also furnishes a hard-coded profile section named **MUID_PROFILE_INSTANCE**, with this property as its single property.</span></span> <span data-ttu-id="725c9-124">在创建的所有配置文件中, 此键都是唯一的, 并且可以比**PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md)) 属性更可靠, 例如, 可以使用相同的名称删除和重新创建该属性。</span><span class="sxs-lookup"><span data-stu-id="725c9-124">This key is guaranteed to be unique among all profiles ever created, and can be more reliable than the **PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md)) property, which can be, for example, deleted and recreated with the same name.</span></span>
  
<span data-ttu-id="725c9-125">下表汇总了**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))、 **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 和此属性之间的重要区别。</span><span class="sxs-lookup"><span data-stu-id="725c9-125">The following table summarizes important differences among the **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)), **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)), and this property.</span></span>
  
|<span data-ttu-id="725c9-126">**特征**</span><span class="sxs-lookup"><span data-stu-id="725c9-126">**Characteristic**</span></span>|<span data-ttu-id="725c9-127">PR_ENTRYID \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="725c9-127">\*\*\*\*PR_ENTRYID\*\*\*\*</span></span>|<span data-ttu-id="725c9-128">PR_RECORD_KEY \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="725c9-128">\*\*\*\*PR_RECORD_KEY\*\*\*\*</span></span>|<span data-ttu-id="725c9-129">PR_SEARCH_KEY \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="725c9-129">\*\*\*\*PR_SEARCH_KEY\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="725c9-130">对附件对象是必需的</span><span class="sxs-lookup"><span data-stu-id="725c9-130">Required on attachment objects</span></span>  <br/> |<span data-ttu-id="725c9-131">否</span><span class="sxs-lookup"><span data-stu-id="725c9-131">No</span></span>  <br/> |<span data-ttu-id="725c9-132">是</span><span class="sxs-lookup"><span data-stu-id="725c9-132">Yes</span></span>  <br/> |<span data-ttu-id="725c9-133">否</span><span class="sxs-lookup"><span data-stu-id="725c9-133">No</span></span>  <br/> |
|<span data-ttu-id="725c9-134">对 folder 对象是必需的</span><span class="sxs-lookup"><span data-stu-id="725c9-134">Required on folder objects</span></span>  <br/> |<span data-ttu-id="725c9-135">是</span><span class="sxs-lookup"><span data-stu-id="725c9-135">Yes</span></span>  <br/> |<span data-ttu-id="725c9-136">是</span><span class="sxs-lookup"><span data-stu-id="725c9-136">Yes</span></span>  <br/> |<span data-ttu-id="725c9-137">否</span><span class="sxs-lookup"><span data-stu-id="725c9-137">No</span></span>  <br/> |
|<span data-ttu-id="725c9-138">对邮件存储对象是必需的</span><span class="sxs-lookup"><span data-stu-id="725c9-138">Required on message store objects</span></span>  <br/> |<span data-ttu-id="725c9-139">是</span><span class="sxs-lookup"><span data-stu-id="725c9-139">Yes</span></span>  <br/> |<span data-ttu-id="725c9-140">是</span><span class="sxs-lookup"><span data-stu-id="725c9-140">Yes</span></span>  <br/> |<span data-ttu-id="725c9-141">否</span><span class="sxs-lookup"><span data-stu-id="725c9-141">No</span></span>  <br/> |
|<span data-ttu-id="725c9-142">对状态对象是必需的</span><span class="sxs-lookup"><span data-stu-id="725c9-142">Required on status objects</span></span>  <br/> |<span data-ttu-id="725c9-143">是</span><span class="sxs-lookup"><span data-stu-id="725c9-143">Yes</span></span>  <br/> |<span data-ttu-id="725c9-144">否</span><span class="sxs-lookup"><span data-stu-id="725c9-144">No</span></span>  <br/> |<span data-ttu-id="725c9-145">否</span><span class="sxs-lookup"><span data-stu-id="725c9-145">No</span></span>  <br/> |
|<span data-ttu-id="725c9-146">可由客户端创建</span><span class="sxs-lookup"><span data-stu-id="725c9-146">Creatable by client</span></span>  <br/> |<span data-ttu-id="725c9-147">否</span><span class="sxs-lookup"><span data-stu-id="725c9-147">No</span></span>  <br/> |<span data-ttu-id="725c9-148">否</span><span class="sxs-lookup"><span data-stu-id="725c9-148">No</span></span>  <br/> |<span data-ttu-id="725c9-149">是</span><span class="sxs-lookup"><span data-stu-id="725c9-149">Yes</span></span>  <br/> |
|<span data-ttu-id="725c9-150">在**SaveChanges**之前可用</span><span class="sxs-lookup"><span data-stu-id="725c9-150">Available before **SaveChanges**</span></span> <br/> |<span data-ttu-id="725c9-151">取决于提供程序实现</span><span class="sxs-lookup"><span data-stu-id="725c9-151">Depends on the provider implementation</span></span>  <br/> |<span data-ttu-id="725c9-152">取决于提供程序实现</span><span class="sxs-lookup"><span data-stu-id="725c9-152">Depends on the provider implementation</span></span>  <br/> |<span data-ttu-id="725c9-153">对于 "邮件", 是。</span><span class="sxs-lookup"><span data-stu-id="725c9-153">For messages, Yes.</span></span> <span data-ttu-id="725c9-154">对于其他用户, 它取决于提供程序实现。</span><span class="sxs-lookup"><span data-stu-id="725c9-154">For others, It depends on the provider implementation.</span></span>  <br/> |
|<span data-ttu-id="725c9-155">在复制操作中更改</span><span class="sxs-lookup"><span data-stu-id="725c9-155">Changed in a copy operation</span></span>  <br/> |<span data-ttu-id="725c9-156">是</span><span class="sxs-lookup"><span data-stu-id="725c9-156">Yes</span></span>  <br/> |<span data-ttu-id="725c9-157">是</span><span class="sxs-lookup"><span data-stu-id="725c9-157">Yes</span></span>  <br/> |<span data-ttu-id="725c9-158">否</span><span class="sxs-lookup"><span data-stu-id="725c9-158">No</span></span>  <br/> |
|<span data-ttu-id="725c9-159">在复制后, 客户端可对其进行更改</span><span class="sxs-lookup"><span data-stu-id="725c9-159">Changeable by client after a copy</span></span>  <br/> |<span data-ttu-id="725c9-160">否</span><span class="sxs-lookup"><span data-stu-id="725c9-160">No</span></span>  <br/> |<span data-ttu-id="725c9-161">否</span><span class="sxs-lookup"><span data-stu-id="725c9-161">No</span></span>  <br/> |<span data-ttu-id="725c9-162">是</span><span class="sxs-lookup"><span data-stu-id="725c9-162">Yes</span></span>  <br/> |
|<span data-ttu-id="725c9-163">中的唯一 .。。</span><span class="sxs-lookup"><span data-stu-id="725c9-163">Unique within ...</span></span>  <br/> |<span data-ttu-id="725c9-164">整个世界</span><span class="sxs-lookup"><span data-stu-id="725c9-164">Entire world</span></span>  <br/> |<span data-ttu-id="725c9-165">提供程序实例</span><span class="sxs-lookup"><span data-stu-id="725c9-165">Provider instance</span></span>  <br/> |<span data-ttu-id="725c9-166">整个世界</span><span class="sxs-lookup"><span data-stu-id="725c9-166">Entire world</span></span>  <br/> |
|<span data-ttu-id="725c9-167">二进制可比较 (与 memcmp 一样)</span><span class="sxs-lookup"><span data-stu-id="725c9-167">Binary comparable (as with memcmp)</span></span>  <br/> |<span data-ttu-id="725c9-168">No--use [IMAPISupport:: CompareEntryIDs](imapisupport-compareentryids.md)</span><span class="sxs-lookup"><span data-stu-id="725c9-168">No -- use [IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md)</span></span> <br/> |<span data-ttu-id="725c9-169">是</span><span class="sxs-lookup"><span data-stu-id="725c9-169">Yes</span></span>  <br/> |<span data-ttu-id="725c9-170">是</span><span class="sxs-lookup"><span data-stu-id="725c9-170">Yes</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="725c9-171">相关资源</span><span class="sxs-lookup"><span data-stu-id="725c9-171">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="725c9-172">协议规范</span><span class="sxs-lookup"><span data-stu-id="725c9-172">Protocol specifications</span></span>

<span data-ttu-id="725c9-173">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="725c9-173">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="725c9-174">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="725c9-174">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="725c9-175">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="725c9-175">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="725c9-176">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="725c9-176">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="725c9-177">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="725c9-177">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="725c9-178">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="725c9-178">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="725c9-179">头文件</span><span class="sxs-lookup"><span data-stu-id="725c9-179">Header files</span></span>

<span data-ttu-id="725c9-180">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="725c9-180">Mapidefs.h</span></span>
  
> <span data-ttu-id="725c9-181">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="725c9-181">Provides data type definitions.</span></span>
    
<span data-ttu-id="725c9-182">Mapitags</span><span class="sxs-lookup"><span data-stu-id="725c9-182">Mapitags.h</span></span>
  
> <span data-ttu-id="725c9-183">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="725c9-183">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="725c9-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="725c9-184">See also</span></span>



[<span data-ttu-id="725c9-185">PidTagResponsibility 规范属性</span><span class="sxs-lookup"><span data-stu-id="725c9-185">PidTagResponsibility Canonical Property</span></span>](pidtagresponsibility-canonical-property.md)
  
[<span data-ttu-id="725c9-186">PidTagStoreRecordKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="725c9-186">PidTagStoreRecordKey Canonical Property</span></span>](pidtagstorerecordkey-canonical-property.md)


[<span data-ttu-id="725c9-187">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="725c9-187">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="725c9-188">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="725c9-188">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="725c9-189">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="725c9-189">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="725c9-190">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="725c9-190">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

