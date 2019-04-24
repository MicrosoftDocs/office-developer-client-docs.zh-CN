---
title: PidTagStoreUnicodeMask 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStoreUnicodeMask
api_type:
- COM
ms.assetid: a6082162-2a74-4850-a0df-4bdbc67b41d8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e15c259003ed2cb425eb181f4383f3054967b993
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339317"
---
# <a name="pidtagstoreunicodemask-canonical-property"></a><span data-ttu-id="aaa8e-103">PidTagStoreUnicodeMask 规范属性</span><span class="sxs-lookup"><span data-stu-id="aaa8e-103">PidTagStoreUnicodeMask Canonical Property</span></span>

  
  
<span data-ttu-id="aaa8e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="aaa8e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="aaa8e-105">包含一个位掩码, 客户端应用程序应通过查询这些标志来确定邮件存储区的特征。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-105">Contains a bitmask of flags that client applications should query to determine the characteristics of a message store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="aaa8e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="aaa8e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="aaa8e-107">PR_STORE_UNICODE_MASK</span><span class="sxs-lookup"><span data-stu-id="aaa8e-107">PR_STORE_UNICODE_MASK</span></span>  <br/> |
|<span data-ttu-id="aaa8e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="aaa8e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="aaa8e-109">0x340F</span><span class="sxs-lookup"><span data-stu-id="aaa8e-109">0x340F</span></span>  <br/> |
|<span data-ttu-id="aaa8e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="aaa8e-110">Data type:</span></span>  <br/> |<span data-ttu-id="aaa8e-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="aaa8e-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="aaa8e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="aaa8e-112">Area:</span></span>  <br/> |<span data-ttu-id="aaa8e-113">MAPI 邮件存储</span><span class="sxs-lookup"><span data-stu-id="aaa8e-113">MAPI message store</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="aaa8e-114">注解</span><span class="sxs-lookup"><span data-stu-id="aaa8e-114">Remarks</span></span>

<span data-ttu-id="aaa8e-115">此属性会将邮件存储区的功能泄露给客户端应用程序, 以向其发送邮件。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-115">This property discloses the capabilities of a message store to client applications planning to send it a message.</span></span> <span data-ttu-id="aaa8e-116">这些标志可促进客户端或其他存储的决策, 例如是否发送**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 或仅发送**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-116">The flags can facilitate decisions by a client or another store, such as whether to send **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) or only **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)).</span></span> <span data-ttu-id="aaa8e-117">客户端永远不应设置此属性。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-117">A client should never set this property.</span></span> <span data-ttu-id="aaa8e-118">尝试返回**MAPI_E_COMPUTED**。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-118">An attempt returns **MAPI_E_COMPUTED**.</span></span> 
  
<span data-ttu-id="aaa8e-119">可以为此属性设置以下一个或多个标志:</span><span class="sxs-lookup"><span data-stu-id="aaa8e-119">One or more of the following flags can be set for this property:</span></span> 
  
<span data-ttu-id="aaa8e-120">STORE_ANSI_OK</span><span class="sxs-lookup"><span data-stu-id="aaa8e-120">STORE_ANSI_OK</span></span>
  
> <span data-ttu-id="aaa8e-121">(131072、0x00020000)邮件存储区支持包含美国国家标准协会 (ANSI) (8 位) 字符的属性。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-121">(131072, 0x00020000) The message store supports properties that contain American National Standards Institute (ANSI) (8-bit) characters.</span></span>
    
<span data-ttu-id="aaa8e-122">STORE_ATTACH_OK</span><span class="sxs-lookup"><span data-stu-id="aaa8e-122">STORE_ATTACH_OK</span></span> 
  
> <span data-ttu-id="aaa8e-123">(32, 0x00000020)邮件存储区支持对象链接和嵌入 (OLE) 或非 OLE 的邮件附件。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-123">(32, 0x00000020) The message store supports Object Linking and Embedding (OLE) or non-OLE attachments to messages.</span></span> 
    
<span data-ttu-id="aaa8e-124">STORE_CATEGORIZE_OK</span><span class="sxs-lookup"><span data-stu-id="aaa8e-124">STORE_CATEGORIZE_OK</span></span> 
  
> <span data-ttu-id="aaa8e-125">(1024、0x00000400)邮件存储区支持表格的分类视图。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-125">(1024, 0x00000400) The message store supports categorized views of tables.</span></span> 
    
<span data-ttu-id="aaa8e-126">STORE_CREATE_OK</span><span class="sxs-lookup"><span data-stu-id="aaa8e-126">STORE_CREATE_OK</span></span> 
  
> <span data-ttu-id="aaa8e-127">(16, 0x00000010)邮件存储库支持创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-127">(16, 0x00000010) The message store supports creation of new messages.</span></span> 
    
<span data-ttu-id="aaa8e-128">STORE_ENTRYID_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="aaa8e-128">STORE_ENTRYID_UNIQUE</span></span> 
  
> <span data-ttu-id="aaa8e-129">(1, 0x00000001)邮件存储区中的对象的条目标识符是唯一的, 即从不在存储的生命周期中重用。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-129">(1, 0x00000001) Entry identifiers for the objects in the message store are unique, that is, never reused during the life of the store.</span></span> 
    
<span data-ttu-id="aaa8e-130">STORE_HTML_OK</span><span class="sxs-lookup"><span data-stu-id="aaa8e-130">STORE_HTML_OK</span></span> 
  
> <span data-ttu-id="aaa8e-131">(65536、0x00010000)邮件存储区支持 HTML 邮件 (存储在**PR_BODY_HTML** ([PidTagBodyHtml](pidtagbodyhtml-canonical-property.md)) 属性中)。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-131">(65536, 0x00010000) The message store supports HTML messages, stored in the **PR_BODY_HTML** ([PidTagBodyHtml](pidtagbodyhtml-canonical-property.md)) property.</span></span> <span data-ttu-id="aaa8e-132">请注意, **STORE_HTML_OK**不是在 mapidefs.h 的版本中定义的。H 包含在 Microsoft Exchange 2000 Server 及更早版本中。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-132">Note that **STORE_HTML_OK** is not defined in versions of MAPIDEFS.H that are included with Microsoft Exchange 2000 Server and earlier.</span></span> <span data-ttu-id="aaa8e-133">如果您的开发环境使用的是 mapidefs.h。H 文件不包含**STORE_HTML_OK**, 请改用值 "0x00010000"。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-133">If your development environment uses a MAPIDEFS.H file that does not include **STORE_HTML_OK**, use the value "0x00010000" instead.</span></span> 
    
<span data-ttu-id="aaa8e-134">STORE_ITEMPROC</span><span class="sxs-lookup"><span data-stu-id="aaa8e-134">STORE_ITEMPROC</span></span>
  
> <span data-ttu-id="aaa8e-135">(2097152、0x00200000)在包装的 PST 存储区中, 指示当新邮件到达存储时, 存储将对邮件单独执行规则和垃圾邮件筛选处理。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-135">(2097152, 0x00200000) In a wrapped PST store, indicates that when a new message arrives at the store, the store does rules and spam filter processing on the message separately.</span></span> <span data-ttu-id="aaa8e-136">存储调用[IMAPISupport:: Notify](imapisupport-notify.md), 在以参数形式传递的[通知](notification.md)结构中设置**fnevNewMail** , 然后将新邮件的详细信息传递给侦听客户端。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-136">The store calls [IMAPISupport::Notify](imapisupport-notify.md), setting **fnevNewMail** in the [NOTIFICATION](notification.md) structure that is passed as a parameter, and then passes the details of the new message to the listening client.</span></span> <span data-ttu-id="aaa8e-137">随后，当侦听客户端收到通知，它不会处理邮件上的规则。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-137">Subsequently, when the listening client receives the notification, it does not process rules on the message.</span></span> 
    
<span data-ttu-id="aaa8e-138">STORE_LOCALSTORE</span><span class="sxs-lookup"><span data-stu-id="aaa8e-138">STORE_LOCALSTORE</span></span>
  
> <span data-ttu-id="aaa8e-139">(524288、0x00080000)此标志是保留的, 不应使用。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-139">(524288, 0x00080000) This flag is reserved and should not be used.</span></span>
    
<span data-ttu-id="aaa8e-140">STORE_MODIFY_OK</span><span class="sxs-lookup"><span data-stu-id="aaa8e-140">STORE_MODIFY_OK</span></span> 
  
> <span data-ttu-id="aaa8e-141">(8、0x00000008)邮件存储区支持修改现有邮件。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-141">(8, 0x00000008) The message store supports modification of its existing messages.</span></span> 
    
<span data-ttu-id="aaa8e-142">STORE_MV_PROPS_OK</span><span class="sxs-lookup"><span data-stu-id="aaa8e-142">STORE_MV_PROPS_OK</span></span> 
  
> <span data-ttu-id="aaa8e-143">(512、0x00000200)邮件存储区支持多值属性, 确保在整个 save 操作中的多值属性中的值顺序的稳定性, 并支持对表中的多值属性进行实例化。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-143">(512, 0x00000200) The message store supports multivalued properties, guarantees the stability of value order in a multivalued property throughout a save operation, and supports instantiation of multivalued properties in tables.</span></span> 
    
<span data-ttu-id="aaa8e-144">STORE_NOTIFY_OK</span><span class="sxs-lookup"><span data-stu-id="aaa8e-144">STORE_NOTIFY_OK</span></span> 
  
> <span data-ttu-id="aaa8e-145">(256、0x00000100)邮件存储区支持通知。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-145">(256, 0x00000100) The message store supports notifications.</span></span> 
    
<span data-ttu-id="aaa8e-146">STORE_OLE_OK</span><span class="sxs-lookup"><span data-stu-id="aaa8e-146">STORE_OLE_OK</span></span> 
  
> <span data-ttu-id="aaa8e-147">(64、0x00000040)邮件存储区支持 OLE 附件。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-147">(64, 0x00000040) The message store supports OLE attachments.</span></span> <span data-ttu-id="aaa8e-148">可以通过**IStorage**接口 (如通过**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 属性提供的) 访问 OLE 数据。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-148">The OLE data is accessible through an **IStorage** interface, such as that available through the **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) property.</span></span> 
    
<span data-ttu-id="aaa8e-149">STORE_PUBLIC_FOLDERS</span><span class="sxs-lookup"><span data-stu-id="aaa8e-149">STORE_PUBLIC_FOLDERS</span></span> 
  
> <span data-ttu-id="aaa8e-150">(16384、0x00004000)此存储区中的文件夹是公共的 (多用户), 而不是私有 (可能是多实例, 而不是多用户)。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-150">(16384, 0x00004000) The folders in this store are public (multi-user), not private (possibly multi-instance but not multi-user).</span></span> 
    
<span data-ttu-id="aaa8e-151">STORE_PUSHER_OK</span><span class="sxs-lookup"><span data-stu-id="aaa8e-151">STORE_PUSHER_OK</span></span>
  
> <span data-ttu-id="aaa8e-152">(8388608、0x00800000)MAPI 协议处理程序不会对存储进行爬网, 并且存储负责通过通知将任何更改推送到索引器, 以便对消息编制索引。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-152">(8388608, 0x00800000) The MAPI Protocol Handler will not crawl the store, and the store is responsible to push any changes through notifications to the indexer to have messages indexed.</span></span>
    
<span data-ttu-id="aaa8e-153">STORE_READONLY</span><span class="sxs-lookup"><span data-stu-id="aaa8e-153">STORE_READONLY</span></span> 
  
> <span data-ttu-id="aaa8e-154">(2, 0x00000002)邮件存储区的所有接口都具有只读访问级别。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-154">(2, 0x00000002) All interfaces for the message store have a read-only access level.</span></span> 
    
<span data-ttu-id="aaa8e-155">STORE_RESTRICTION_OK</span><span class="sxs-lookup"><span data-stu-id="aaa8e-155">STORE_RESTRICTION_OK</span></span> 
  
> <span data-ttu-id="aaa8e-156">(4096、0x00001000)邮件存储区支持限制。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-156">(4096, 0x00001000) The message store supports restrictions.</span></span> 
    
<span data-ttu-id="aaa8e-157">STORE_RTF_OK</span><span class="sxs-lookup"><span data-stu-id="aaa8e-157">STORE_RTF_OK</span></span> 
  
> <span data-ttu-id="aaa8e-158">(2048、0x00000800)邮件存储区支持 rtf 格式 (rtf) 邮件, 通常是压缩的, 并且存储本身会保持**PR_BODY**和**PR_RTF_COMPRESSED**同步。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-158">(2048, 0x00000800) The message store supports Rich Text Format (RTF) messages, usually compressed, and the store itself keeps **PR_BODY** and **PR_RTF_COMPRESSED** synchronized.</span></span> 
    
<span data-ttu-id="aaa8e-159">STORE_SEARCH_OK</span><span class="sxs-lookup"><span data-stu-id="aaa8e-159">STORE_SEARCH_OK</span></span> 
  
> <span data-ttu-id="aaa8e-160">(4, 0x00000004)邮件存储区支持搜索结果文件夹。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-160">(4, 0x00000004) The message store supports search-results folders.</span></span> 
    
<span data-ttu-id="aaa8e-161">STORE_SORT_OK</span><span class="sxs-lookup"><span data-stu-id="aaa8e-161">STORE_SORT_OK</span></span> 
  
> <span data-ttu-id="aaa8e-162">(8192、0x00002000)邮件存储区支持对表的视图进行排序。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-162">(8192, 0x00002000) The message store supports sorting views of tables.</span></span> 
    
<span data-ttu-id="aaa8e-163">STORE_SUBMIT_OK</span><span class="sxs-lookup"><span data-stu-id="aaa8e-163">STORE_SUBMIT_OK</span></span> 
  
> <span data-ttu-id="aaa8e-164">(128、0x00000080)邮件存储区支持标记要提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-164">(128, 0x00000080) The message store supports marking a message for submission.</span></span> 
    
<span data-ttu-id="aaa8e-165">STORE_UNCOMPRESSED_RTF</span><span class="sxs-lookup"><span data-stu-id="aaa8e-165">STORE_UNCOMPRESSED_RTF</span></span> 
  
> <span data-ttu-id="aaa8e-166">(32768、0x00008000)邮件存储区支持以非压缩形式存储 revisable 表单文本 (RTF) 邮件。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-166">(32768, 0x00008000) The message store supports storage of revisable form text (RTF) messages in uncompressed form.</span></span> <span data-ttu-id="aaa8e-167">未压缩的 RTF 流由流头中的值**dwMagicUncompressedRTF**标识。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-167">An uncompressed RTF stream is identified by the value **dwMagicUncompressedRTF** in the stream header.</span></span> <span data-ttu-id="aaa8e-168">**dwMagicUncompressedRTF**值是在 RTFLIB 中定义的。H 文件。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-168">The **dwMagicUncompressedRTF** value is defined in the RTFLIB.H file.</span></span> 
    
<span data-ttu-id="aaa8e-169">STORE_UNICODE_OK</span><span class="sxs-lookup"><span data-stu-id="aaa8e-169">STORE_UNICODE_OK</span></span>
  
> <span data-ttu-id="aaa8e-170">(262144, 0x00040000)邮件存储区支持包含 Unicode 字符的属性。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-170">(262144, 0x00040000) The message store supports properties containing Unicode characters.</span></span>
    
<span data-ttu-id="aaa8e-171">即使邮件存储区不支持 rtf, 也可以始终存储邮件的 RTF 版本。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-171">An RTF version of a message can always be stored, even if the message store is non-RTF-aware.</span></span> <span data-ttu-id="aaa8e-172">如果没有为特定存储区设置 STORE_RTF_OK 位, 则维护 RTF 版本的客户端必须自己调用[RTFSync](rtfsync.md)函数, 以使**PR_BODY**和**PR_RTF_COMPRESSED**版本与文本内容同步。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-172">If the STORE_RTF_OK bit is not set for a particular store, a client maintaining RTF versions must itself call the [RTFSync](rtfsync.md) function to keep the **PR_BODY** and **PR_RTF_COMPRESSED** versions synchronized for text content.</span></span> <span data-ttu-id="aaa8e-173">RTF 始终存储在**PR_RTF_COMPRESSED**中, 无论它是否实际压缩。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-173">RTF is always stored in **PR_RTF_COMPRESSED**, whether it is actually compressed or not.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="aaa8e-174">相关资源</span><span class="sxs-lookup"><span data-stu-id="aaa8e-174">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="aaa8e-175">头文件</span><span class="sxs-lookup"><span data-stu-id="aaa8e-175">Header files</span></span>

<span data-ttu-id="aaa8e-176">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="aaa8e-176">Mapidefs.h</span></span>
  
> <span data-ttu-id="aaa8e-177">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-177">Provides data type definitions.</span></span>
    
<span data-ttu-id="aaa8e-178">Mapitags</span><span class="sxs-lookup"><span data-stu-id="aaa8e-178">Mapitags.h</span></span>
  
> <span data-ttu-id="aaa8e-179">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="aaa8e-179">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="aaa8e-180">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aaa8e-180">See also</span></span>



[<span data-ttu-id="aaa8e-181">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="aaa8e-181">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="aaa8e-182">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="aaa8e-182">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="aaa8e-183">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="aaa8e-183">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="aaa8e-184">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="aaa8e-184">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

