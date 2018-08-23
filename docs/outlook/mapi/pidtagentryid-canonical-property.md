---
title: PidTagEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagEntryId
api_type:
- HeaderDef
ms.assetid: ca02e873-c2d2-4d58-8df8-c05fbcdc8fba
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f3d49faba9d1e9cc8609ee55f7fb3c329e9ae947
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593037"
---
# <a name="pidtagentryid-canonical-property"></a><span data-ttu-id="08e02-103">PidTagEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="08e02-103">PidTagEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="08e02-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="08e02-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="08e02-105">包含用于打开和编辑特定的 MAPI 对象的属性的 MAPI 条目标识符。</span><span class="sxs-lookup"><span data-stu-id="08e02-105">Contains a MAPI entry identifier used to open and edit properties of a particular MAPI object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="08e02-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="08e02-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="08e02-107">PR_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="08e02-107">PR_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="08e02-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="08e02-108">Identifier:</span></span>  <br/> |<span data-ttu-id="08e02-109">0x0FFF</span><span class="sxs-lookup"><span data-stu-id="08e02-109">0x0FFF</span></span>  <br/> |
|<span data-ttu-id="08e02-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="08e02-110">Data type:</span></span>  <br/> |<span data-ttu-id="08e02-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="08e02-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="08e02-112">区域：</span><span class="sxs-lookup"><span data-stu-id="08e02-112">Area:</span></span>  <br/> |<span data-ttu-id="08e02-113">ID 属性</span><span class="sxs-lookup"><span data-stu-id="08e02-113">ID properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="08e02-114">注解</span><span class="sxs-lookup"><span data-stu-id="08e02-114">Remarks</span></span>

<span data-ttu-id="08e02-115">此属性标识**OpenEntry**若要实例化对象，并提供对其所有属性通过**IMAPIProp**相应派生界面访问。</span><span class="sxs-lookup"><span data-stu-id="08e02-115">This property identifies an object for **OpenEntry** to instantiate and provides access to all of its properties through the appropriate derived interface of **IMAPIProp**.</span></span> 
  
<span data-ttu-id="08e02-116">此属性是所有邮件用户的基址属性之一。</span><span class="sxs-lookup"><span data-stu-id="08e02-116">This property is one of the base address properties for all messaging users.</span></span> 
  
<span data-ttu-id="08e02-117">此属性可以包含长期或短期标识符。</span><span class="sxs-lookup"><span data-stu-id="08e02-117">This property can contain either a long-term or a short-term identifier.</span></span> <span data-ttu-id="08e02-118">短期标识符是更轻松和快速构造，但不能在其范围和持续时间，通常为当前会话和工作站超出。</span><span class="sxs-lookup"><span data-stu-id="08e02-118">Short-term identifiers are easier and faster to construct, but are limited in their scope and duration, typically to the current session and workstation.</span></span> <span data-ttu-id="08e02-119">它们是通常用于临时性质，如表格行或对话框中各项，对象，然后放弃。</span><span class="sxs-lookup"><span data-stu-id="08e02-119">They are commonly used for objects of a temporary nature, such as table rows or dialog box entries, and then abandoned.</span></span> <span data-ttu-id="08e02-120">长期标识符用于更全面且长期性质的对象。</span><span class="sxs-lookup"><span data-stu-id="08e02-120">Long-term identifiers are used for objects of a more wide-ranging and long-lasting nature.</span></span> 
  
<span data-ttu-id="08e02-121">此属性始终是可通过以下方法[IMAPIProp::SaveChanges](imapiprop-savechanges.md)第一次调用[IMAPIProp::GetProps](imapiprop-getprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="08e02-121">This property is always available through the [IMAPIProp::GetProps](imapiprop-getprops.md) method following the first call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="08e02-122">某些服务提供商可以使其可实例化后立即。</span><span class="sxs-lookup"><span data-stu-id="08e02-122">Some service providers can make it available immediately after instantiation.</span></span> <span data-ttu-id="08e02-123">提供程序必须始终返回从**GetProps**长期的项标识符。</span><span class="sxs-lookup"><span data-stu-id="08e02-123">The provider must always return a long-term entry identifier from **GetProps**.</span></span> <span data-ttu-id="08e02-124">因此，将转换为长期的短期标识符，只需打开的对象并获取其 this 通过**GetProps**属性。</span><span class="sxs-lookup"><span data-stu-id="08e02-124">Therefore, to convert a short-term identifier to long-term, simply open the object and get its this property through **GetProps**.</span></span> 
  
<span data-ttu-id="08e02-125">下表总结了此属性，之间重要差异**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 和**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="08e02-125">The following table summarizes important differences among this property, **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)), and **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)).</span></span> 
  
|<span data-ttu-id="08e02-126">**特征**</span><span class="sxs-lookup"><span data-stu-id="08e02-126">**Characteristic**</span></span>|<span data-ttu-id="08e02-127">**PR_ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="08e02-127">**PR_ENTRYID**</span></span>|<span data-ttu-id="08e02-128">**PR_RECORD_KEY**</span><span class="sxs-lookup"><span data-stu-id="08e02-128">**PR_RECORD_KEY**</span></span>|<span data-ttu-id="08e02-129">**PR_SEARCH_KEY**</span><span class="sxs-lookup"><span data-stu-id="08e02-129">**PR_SEARCH_KEY**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="08e02-130">Attachment 对象上所需</span><span class="sxs-lookup"><span data-stu-id="08e02-130">Required on attachment objects</span></span>  <br/> |<span data-ttu-id="08e02-131">否</span><span class="sxs-lookup"><span data-stu-id="08e02-131">No</span></span>  <br/> |<span data-ttu-id="08e02-132">是</span><span class="sxs-lookup"><span data-stu-id="08e02-132">Yes</span></span>  <br/> |<span data-ttu-id="08e02-133">否</span><span class="sxs-lookup"><span data-stu-id="08e02-133">No</span></span>  <br/> |
|<span data-ttu-id="08e02-134">需要对文件夹对象</span><span class="sxs-lookup"><span data-stu-id="08e02-134">Required on folder objects</span></span>  <br/> |<span data-ttu-id="08e02-135">是</span><span class="sxs-lookup"><span data-stu-id="08e02-135">Yes</span></span>  <br/> |<span data-ttu-id="08e02-136">是</span><span class="sxs-lookup"><span data-stu-id="08e02-136">Yes</span></span>  <br/> |<span data-ttu-id="08e02-137">否</span><span class="sxs-lookup"><span data-stu-id="08e02-137">No</span></span>  <br/> |
|<span data-ttu-id="08e02-138">消息存储对象上所需</span><span class="sxs-lookup"><span data-stu-id="08e02-138">Required on message store objects</span></span>  <br/> |<span data-ttu-id="08e02-139">是</span><span class="sxs-lookup"><span data-stu-id="08e02-139">Yes</span></span>  <br/> |<span data-ttu-id="08e02-140">是</span><span class="sxs-lookup"><span data-stu-id="08e02-140">Yes</span></span>  <br/> |<span data-ttu-id="08e02-141">否</span><span class="sxs-lookup"><span data-stu-id="08e02-141">No</span></span>  <br/> |
|<span data-ttu-id="08e02-142">状态对象上所需</span><span class="sxs-lookup"><span data-stu-id="08e02-142">Required on status objects</span></span>  <br/> |<span data-ttu-id="08e02-143">是</span><span class="sxs-lookup"><span data-stu-id="08e02-143">Yes</span></span>  <br/> |<span data-ttu-id="08e02-144">否</span><span class="sxs-lookup"><span data-stu-id="08e02-144">No</span></span>  <br/> |<span data-ttu-id="08e02-145">否</span><span class="sxs-lookup"><span data-stu-id="08e02-145">No</span></span>  <br/> |
|<span data-ttu-id="08e02-146">创建客户端</span><span class="sxs-lookup"><span data-stu-id="08e02-146">Created by client</span></span>  <br/> |<span data-ttu-id="08e02-147">否</span><span class="sxs-lookup"><span data-stu-id="08e02-147">No</span></span>  <br/> |<span data-ttu-id="08e02-148">否</span><span class="sxs-lookup"><span data-stu-id="08e02-148">No</span></span>  <br/> |<span data-ttu-id="08e02-149">是</span><span class="sxs-lookup"><span data-stu-id="08e02-149">Yes</span></span>  <br/> |
|<span data-ttu-id="08e02-150">调用**SaveChanges**前可用</span><span class="sxs-lookup"><span data-stu-id="08e02-150">Available before call to **SaveChanges**</span></span> <br/> |<span data-ttu-id="08e02-151">取决于提供程序实现</span><span class="sxs-lookup"><span data-stu-id="08e02-151">Depends on provider implementation</span></span>  <br/> |<span data-ttu-id="08e02-152">取决于提供程序实现</span><span class="sxs-lookup"><span data-stu-id="08e02-152">Depends on provider implementation</span></span>  <br/> |<span data-ttu-id="08e02-153">用于消息，是。</span><span class="sxs-lookup"><span data-stu-id="08e02-153">For messages, Yes.</span></span> <span data-ttu-id="08e02-154">其他人，取决于提供程序实现。</span><span class="sxs-lookup"><span data-stu-id="08e02-154">For others, depends on provider implementation.</span></span>  <br/> |
|<span data-ttu-id="08e02-155">复制操作中发生的更改</span><span class="sxs-lookup"><span data-stu-id="08e02-155">Changed in a copy operation</span></span>  <br/> |<span data-ttu-id="08e02-156">是</span><span class="sxs-lookup"><span data-stu-id="08e02-156">Yes</span></span>  <br/> |<span data-ttu-id="08e02-157">是</span><span class="sxs-lookup"><span data-stu-id="08e02-157">Yes</span></span>  <br/> |<span data-ttu-id="08e02-158">否</span><span class="sxs-lookup"><span data-stu-id="08e02-158">No</span></span>  <br/> |
|<span data-ttu-id="08e02-159">可更改后副本的客户端</span><span class="sxs-lookup"><span data-stu-id="08e02-159">Changeable by client after a copy</span></span>  <br/> |<span data-ttu-id="08e02-160">否</span><span class="sxs-lookup"><span data-stu-id="08e02-160">No</span></span>  <br/> |<span data-ttu-id="08e02-161">否</span><span class="sxs-lookup"><span data-stu-id="08e02-161">No</span></span>  <br/> |<span data-ttu-id="08e02-162">是</span><span class="sxs-lookup"><span data-stu-id="08e02-162">Yes</span></span>  <br/> |
|<span data-ttu-id="08e02-163">唯一</span><span class="sxs-lookup"><span data-stu-id="08e02-163">Unique within</span></span>  <br/> |<span data-ttu-id="08e02-164">整个 world</span><span class="sxs-lookup"><span data-stu-id="08e02-164">Entire world</span></span>  <br/> |<span data-ttu-id="08e02-165">提供程序实例</span><span class="sxs-lookup"><span data-stu-id="08e02-165">Provider instance</span></span>  <br/> |<span data-ttu-id="08e02-166">整个 world</span><span class="sxs-lookup"><span data-stu-id="08e02-166">Entire world</span></span>  <br/> |
|<span data-ttu-id="08e02-167">二进制 （与 memcmp) 相当</span><span class="sxs-lookup"><span data-stu-id="08e02-167">Binary comparable (as with memcmp)</span></span>  <br/> |<span data-ttu-id="08e02-168">无需使用[IMAPISupport:: CompareEntryIDs](imapisupport-compareentryids.md)</span><span class="sxs-lookup"><span data-stu-id="08e02-168">No use [IMAPISupport:: CompareEntryIDs](imapisupport-compareentryids.md)</span></span> <br/> |<span data-ttu-id="08e02-169">是</span><span class="sxs-lookup"><span data-stu-id="08e02-169">Yes</span></span>  <br/> |<span data-ttu-id="08e02-170">是</span><span class="sxs-lookup"><span data-stu-id="08e02-170">Yes</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="08e02-171">相关资源</span><span class="sxs-lookup"><span data-stu-id="08e02-171">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="08e02-172">协议规范</span><span class="sxs-lookup"><span data-stu-id="08e02-172">Protocol specifications</span></span>

<span data-ttu-id="08e02-173">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="08e02-173">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="08e02-174">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="08e02-174">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="08e02-175">[[MS OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="08e02-175">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="08e02-176">处理邮件和附件的对象。</span><span class="sxs-lookup"><span data-stu-id="08e02-176">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="08e02-177">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="08e02-177">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="08e02-178">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="08e02-178">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="08e02-179">[[MS OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="08e02-179">[[MS-OXCMAIL]](http://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="08e02-180">从 Internet 标准电子邮件约定转换为消息对象。</span><span class="sxs-lookup"><span data-stu-id="08e02-180">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="08e02-181">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="08e02-181">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="08e02-182">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="08e02-182">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="08e02-183">[[MS OXCPERM]](http://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="08e02-183">[[MS-OXCPERM]](http://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="08e02-184">处理检索存储在服务器的文件夹的权限列表。</span><span class="sxs-lookup"><span data-stu-id="08e02-184">Handles the retrieval of folder permission lists that are stored on the server.</span></span>
    
<span data-ttu-id="08e02-185">[[MS OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="08e02-185">[[MS-OXODLGT]](http://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="08e02-186">指定用于连接到和它们代表另一个用户操作时，作为代理人，以及与邮件和日历的对象交互配置邮箱的方法。</span><span class="sxs-lookup"><span data-stu-id="08e02-186">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
<span data-ttu-id="08e02-187">[[MS OXWAVLS]](http://msdn.microsoft.com/library/69a276d8-5fc3-40ba-acd0-31cf42e6af58%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="08e02-187">[[MS-OXWAVLS]](http://msdn.microsoft.com/library/69a276d8-5fc3-40ba-acd0-31cf42e6af58%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="08e02-188">指定架构和用于请求用户和资源的可用性信息的方法。</span><span class="sxs-lookup"><span data-stu-id="08e02-188">Specifies the schema and methods that are used to request availability information for users and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="08e02-189">头文件</span><span class="sxs-lookup"><span data-stu-id="08e02-189">Header files</span></span>

<span data-ttu-id="08e02-190">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="08e02-190">Mapidefs.h</span></span>
  
> <span data-ttu-id="08e02-191">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="08e02-191">Provides data type definitions.</span></span>
    
<span data-ttu-id="08e02-192">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="08e02-192">Mapitags.h</span></span>
  
> <span data-ttu-id="08e02-193">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="08e02-193">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="08e02-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08e02-194">See also</span></span>



[<span data-ttu-id="08e02-195">PidTagStoreEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="08e02-195">PidTagStoreEntryId Canonical Property</span></span>](pidtagstoreentryid-canonical-property.md)


[<span data-ttu-id="08e02-196">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="08e02-196">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="08e02-197">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="08e02-197">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="08e02-198">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="08e02-198">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="08e02-199">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="08e02-199">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

