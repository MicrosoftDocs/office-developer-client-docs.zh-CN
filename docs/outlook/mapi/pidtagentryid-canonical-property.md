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
ms.openlocfilehash: feb34cdbf8ba917936c3272bcaaf6eff040ddc3a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328586"
---
# <a name="pidtagentryid-canonical-property"></a><span data-ttu-id="5f94c-103">PidTagEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="5f94c-103">PidTagEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="5f94c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5f94c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5f94c-105">包含用于打开和编辑特定 MAPI 对象的属性的 MAPI 条目标识符。</span><span class="sxs-lookup"><span data-stu-id="5f94c-105">Contains a MAPI entry identifier used to open and edit properties of a particular MAPI object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5f94c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5f94c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5f94c-107">PR_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="5f94c-107">PR_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="5f94c-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="5f94c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5f94c-109">0x0FFF</span><span class="sxs-lookup"><span data-stu-id="5f94c-109">0x0FFF</span></span>  <br/> |
|<span data-ttu-id="5f94c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5f94c-110">Data type:</span></span>  <br/> |<span data-ttu-id="5f94c-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="5f94c-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="5f94c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5f94c-112">Area:</span></span>  <br/> |<span data-ttu-id="5f94c-113">ID 属性</span><span class="sxs-lookup"><span data-stu-id="5f94c-113">ID properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5f94c-114">注解</span><span class="sxs-lookup"><span data-stu-id="5f94c-114">Remarks</span></span>

<span data-ttu-id="5f94c-115">此属性标识要实例化的**OpenEntry**对象, 并通过相应的**IMAPIProp**派生接口提供对其所有属性的访问权限。</span><span class="sxs-lookup"><span data-stu-id="5f94c-115">This property identifies an object for **OpenEntry** to instantiate and provides access to all of its properties through the appropriate derived interface of **IMAPIProp**.</span></span> 
  
<span data-ttu-id="5f94c-116">此属性是所有邮件用户的基本地址属性之一。</span><span class="sxs-lookup"><span data-stu-id="5f94c-116">This property is one of the base address properties for all messaging users.</span></span> 
  
<span data-ttu-id="5f94c-117">此属性可以包含长期标识符或短期标识符。</span><span class="sxs-lookup"><span data-stu-id="5f94c-117">This property can contain either a long-term or a short-term identifier.</span></span> <span data-ttu-id="5f94c-118">短期标识符的构造更简单且速度更快, 但在其范围和持续时间方面受到限制, 通常是当前会话和工作站。</span><span class="sxs-lookup"><span data-stu-id="5f94c-118">Short-term identifiers are easier and faster to construct, but are limited in their scope and duration, typically to the current session and workstation.</span></span> <span data-ttu-id="5f94c-119">它们通常用于临时性质的对象, 如表行或对话框条目, 然后被放弃。</span><span class="sxs-lookup"><span data-stu-id="5f94c-119">They are commonly used for objects of a temporary nature, such as table rows or dialog box entries, and then abandoned.</span></span> <span data-ttu-id="5f94c-120">长期标识符用于具有更宽范围和长期性质的对象。</span><span class="sxs-lookup"><span data-stu-id="5f94c-120">Long-term identifiers are used for objects of a more wide-ranging and long-lasting nature.</span></span> 
  
<span data-ttu-id="5f94c-121">在第一次调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法后, 此属性始终可通过[IMAPIProp:: GetProps](imapiprop-getprops.md)方法使用。</span><span class="sxs-lookup"><span data-stu-id="5f94c-121">This property is always available through the [IMAPIProp::GetProps](imapiprop-getprops.md) method following the first call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method.</span></span> <span data-ttu-id="5f94c-122">某些服务提供程序可使其在实例化后立即可用。</span><span class="sxs-lookup"><span data-stu-id="5f94c-122">Some service providers can make it available immediately after instantiation.</span></span> <span data-ttu-id="5f94c-123">提供程序必须始终从**GetProps**返回长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="5f94c-123">The provider must always return a long-term entry identifier from **GetProps**.</span></span> <span data-ttu-id="5f94c-124">因此, 若要将短期标识符转换为长期, 只需打开对象并通过**GetProps**获取其此属性即可。</span><span class="sxs-lookup"><span data-stu-id="5f94c-124">Therefore, to convert a short-term identifier to long-term, simply open the object and get its this property through **GetProps**.</span></span> 
  
<span data-ttu-id="5f94c-125">下表汇总了此属性、 **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) 和**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 之间的重要区别。</span><span class="sxs-lookup"><span data-stu-id="5f94c-125">The following table summarizes important differences among this property, **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)), and **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)).</span></span> 
  
|<span data-ttu-id="5f94c-126">**特征**</span><span class="sxs-lookup"><span data-stu-id="5f94c-126">**Characteristic**</span></span>|<span data-ttu-id="5f94c-127">**PR_ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="5f94c-127">**PR_ENTRYID**</span></span>|<span data-ttu-id="5f94c-128">**PR_RECORD_KEY**</span><span class="sxs-lookup"><span data-stu-id="5f94c-128">**PR_RECORD_KEY**</span></span>|<span data-ttu-id="5f94c-129">**PR_SEARCH_KEY**</span><span class="sxs-lookup"><span data-stu-id="5f94c-129">**PR_SEARCH_KEY**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5f94c-130">对附件对象是必需的</span><span class="sxs-lookup"><span data-stu-id="5f94c-130">Required on attachment objects</span></span>  <br/> |<span data-ttu-id="5f94c-131">否</span><span class="sxs-lookup"><span data-stu-id="5f94c-131">No</span></span>  <br/> |<span data-ttu-id="5f94c-132">是</span><span class="sxs-lookup"><span data-stu-id="5f94c-132">Yes</span></span>  <br/> |<span data-ttu-id="5f94c-133">否</span><span class="sxs-lookup"><span data-stu-id="5f94c-133">No</span></span>  <br/> |
|<span data-ttu-id="5f94c-134">对 folder 对象是必需的</span><span class="sxs-lookup"><span data-stu-id="5f94c-134">Required on folder objects</span></span>  <br/> |<span data-ttu-id="5f94c-135">是</span><span class="sxs-lookup"><span data-stu-id="5f94c-135">Yes</span></span>  <br/> |<span data-ttu-id="5f94c-136">是</span><span class="sxs-lookup"><span data-stu-id="5f94c-136">Yes</span></span>  <br/> |<span data-ttu-id="5f94c-137">否</span><span class="sxs-lookup"><span data-stu-id="5f94c-137">No</span></span>  <br/> |
|<span data-ttu-id="5f94c-138">对邮件存储对象是必需的</span><span class="sxs-lookup"><span data-stu-id="5f94c-138">Required on message store objects</span></span>  <br/> |<span data-ttu-id="5f94c-139">是</span><span class="sxs-lookup"><span data-stu-id="5f94c-139">Yes</span></span>  <br/> |<span data-ttu-id="5f94c-140">是</span><span class="sxs-lookup"><span data-stu-id="5f94c-140">Yes</span></span>  <br/> |<span data-ttu-id="5f94c-141">否</span><span class="sxs-lookup"><span data-stu-id="5f94c-141">No</span></span>  <br/> |
|<span data-ttu-id="5f94c-142">对状态对象是必需的</span><span class="sxs-lookup"><span data-stu-id="5f94c-142">Required on status objects</span></span>  <br/> |<span data-ttu-id="5f94c-143">是</span><span class="sxs-lookup"><span data-stu-id="5f94c-143">Yes</span></span>  <br/> |<span data-ttu-id="5f94c-144">否</span><span class="sxs-lookup"><span data-stu-id="5f94c-144">No</span></span>  <br/> |<span data-ttu-id="5f94c-145">否</span><span class="sxs-lookup"><span data-stu-id="5f94c-145">No</span></span>  <br/> |
|<span data-ttu-id="5f94c-146">由客户端创建</span><span class="sxs-lookup"><span data-stu-id="5f94c-146">Created by client</span></span>  <br/> |<span data-ttu-id="5f94c-147">否</span><span class="sxs-lookup"><span data-stu-id="5f94c-147">No</span></span>  <br/> |<span data-ttu-id="5f94c-148">否</span><span class="sxs-lookup"><span data-stu-id="5f94c-148">No</span></span>  <br/> |<span data-ttu-id="5f94c-149">是</span><span class="sxs-lookup"><span data-stu-id="5f94c-149">Yes</span></span>  <br/> |
|<span data-ttu-id="5f94c-150">在调用**SaveChanges**之前可用</span><span class="sxs-lookup"><span data-stu-id="5f94c-150">Available before call to **SaveChanges**</span></span> <br/> |<span data-ttu-id="5f94c-151">取决于提供程序的实现</span><span class="sxs-lookup"><span data-stu-id="5f94c-151">Depends on provider implementation</span></span>  <br/> |<span data-ttu-id="5f94c-152">取决于提供程序的实现</span><span class="sxs-lookup"><span data-stu-id="5f94c-152">Depends on provider implementation</span></span>  <br/> |<span data-ttu-id="5f94c-153">对于 "邮件", 是。</span><span class="sxs-lookup"><span data-stu-id="5f94c-153">For messages, Yes.</span></span> <span data-ttu-id="5f94c-154">对于其他人, 取决于提供程序实现。</span><span class="sxs-lookup"><span data-stu-id="5f94c-154">For others, depends on provider implementation.</span></span>  <br/> |
|<span data-ttu-id="5f94c-155">在复制操作中更改</span><span class="sxs-lookup"><span data-stu-id="5f94c-155">Changed in a copy operation</span></span>  <br/> |<span data-ttu-id="5f94c-156">是</span><span class="sxs-lookup"><span data-stu-id="5f94c-156">Yes</span></span>  <br/> |<span data-ttu-id="5f94c-157">是</span><span class="sxs-lookup"><span data-stu-id="5f94c-157">Yes</span></span>  <br/> |<span data-ttu-id="5f94c-158">否</span><span class="sxs-lookup"><span data-stu-id="5f94c-158">No</span></span>  <br/> |
|<span data-ttu-id="5f94c-159">在复制后, 客户端可对其进行更改</span><span class="sxs-lookup"><span data-stu-id="5f94c-159">Changeable by client after a copy</span></span>  <br/> |<span data-ttu-id="5f94c-160">否</span><span class="sxs-lookup"><span data-stu-id="5f94c-160">No</span></span>  <br/> |<span data-ttu-id="5f94c-161">否</span><span class="sxs-lookup"><span data-stu-id="5f94c-161">No</span></span>  <br/> |<span data-ttu-id="5f94c-162">是</span><span class="sxs-lookup"><span data-stu-id="5f94c-162">Yes</span></span>  <br/> |
|<span data-ttu-id="5f94c-163">中的唯一</span><span class="sxs-lookup"><span data-stu-id="5f94c-163">Unique within</span></span>  <br/> |<span data-ttu-id="5f94c-164">整个世界</span><span class="sxs-lookup"><span data-stu-id="5f94c-164">Entire world</span></span>  <br/> |<span data-ttu-id="5f94c-165">提供程序实例</span><span class="sxs-lookup"><span data-stu-id="5f94c-165">Provider instance</span></span>  <br/> |<span data-ttu-id="5f94c-166">整个世界</span><span class="sxs-lookup"><span data-stu-id="5f94c-166">Entire world</span></span>  <br/> |
|<span data-ttu-id="5f94c-167">二进制可比较 (与 memcmp 一样)</span><span class="sxs-lookup"><span data-stu-id="5f94c-167">Binary comparable (as with memcmp)</span></span>  <br/> |<span data-ttu-id="5f94c-168">不使用[IMAPISupport:: CompareEntryIDs](imapisupport-compareentryids.md)</span><span class="sxs-lookup"><span data-stu-id="5f94c-168">No use [IMAPISupport:: CompareEntryIDs](imapisupport-compareentryids.md)</span></span> <br/> |<span data-ttu-id="5f94c-169">是</span><span class="sxs-lookup"><span data-stu-id="5f94c-169">Yes</span></span>  <br/> |<span data-ttu-id="5f94c-170">是</span><span class="sxs-lookup"><span data-stu-id="5f94c-170">Yes</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="5f94c-171">相关资源</span><span class="sxs-lookup"><span data-stu-id="5f94c-171">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5f94c-172">协议规范</span><span class="sxs-lookup"><span data-stu-id="5f94c-172">Protocol specifications</span></span>

<span data-ttu-id="5f94c-173">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5f94c-173">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5f94c-174">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="5f94c-174">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5f94c-175">[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5f94c-175">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5f94c-176">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="5f94c-176">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="5f94c-177">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5f94c-177">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5f94c-178">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="5f94c-178">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="5f94c-179">[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5f94c-179">[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5f94c-180">从 Internet 标准电子邮件约定转换为邮件对象。</span><span class="sxs-lookup"><span data-stu-id="5f94c-180">Converts from Internet standard email conventions to message objects.</span></span>
    
<span data-ttu-id="5f94c-181">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5f94c-181">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5f94c-182">处理客户端与服务器之间的数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="5f94c-182">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="5f94c-183">[[毫秒-OXCPERM]](https://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5f94c-183">[[MS-OXCPERM]](https://msdn.microsoft.com/library/944ddb65-6249-4c34-a46e-363fcd37195e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5f94c-184">处理存储在服务器上的文件夹权限列表的检索。</span><span class="sxs-lookup"><span data-stu-id="5f94c-184">Handles the retrieval of folder permission lists that are stored on the server.</span></span>
    
<span data-ttu-id="5f94c-185">[[毫秒-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5f94c-185">[[MS-OXODLGT]](https://msdn.microsoft.com/library/01a89b11-9c43-4c40-b147-8f6a1ef5a44f%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5f94c-186">指定用于连接邮箱和将邮箱配置为代理的方法, 以及当邮件和日历对象代表其他用户操作时与这些对象的交互。</span><span class="sxs-lookup"><span data-stu-id="5f94c-186">Specifies methods for connecting to and configuring mailboxes as delegates, and interactions with message and calendar objects when they act on behalf of another user.</span></span>
    
<span data-ttu-id="5f94c-187">[[毫秒-OXWAVLS]](https://msdn.microsoft.com/library/69a276d8-5fc3-40ba-acd0-31cf42e6af58%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5f94c-187">[[MS-OXWAVLS]](https://msdn.microsoft.com/library/69a276d8-5fc3-40ba-acd0-31cf42e6af58%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5f94c-188">指定用于请求用户和资源的可用性信息的架构和方法。</span><span class="sxs-lookup"><span data-stu-id="5f94c-188">Specifies the schema and methods that are used to request availability information for users and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5f94c-189">头文件</span><span class="sxs-lookup"><span data-stu-id="5f94c-189">Header files</span></span>

<span data-ttu-id="5f94c-190">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="5f94c-190">Mapidefs.h</span></span>
  
> <span data-ttu-id="5f94c-191">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5f94c-191">Provides data type definitions.</span></span>
    
<span data-ttu-id="5f94c-192">Mapitags</span><span class="sxs-lookup"><span data-stu-id="5f94c-192">Mapitags.h</span></span>
  
> <span data-ttu-id="5f94c-193">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5f94c-193">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5f94c-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f94c-194">See also</span></span>



[<span data-ttu-id="5f94c-195">PidTagStoreEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="5f94c-195">PidTagStoreEntryId Canonical Property</span></span>](pidtagstoreentryid-canonical-property.md)


[<span data-ttu-id="5f94c-196">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5f94c-196">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5f94c-197">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5f94c-197">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5f94c-198">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5f94c-198">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5f94c-199">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5f94c-199">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

