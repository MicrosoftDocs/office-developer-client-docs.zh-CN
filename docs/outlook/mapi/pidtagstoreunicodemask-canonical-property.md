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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437936"
---
# <a name="pidtagstoreunicodemask-canonical-property"></a><span data-ttu-id="feb6b-103">PidTagStoreUnicodeMask 规范属性</span><span class="sxs-lookup"><span data-stu-id="feb6b-103">PidTagStoreUnicodeMask Canonical Property</span></span>

  
  
<span data-ttu-id="feb6b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="feb6b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="feb6b-105">包含客户端应用程序应查询以确定邮件存储特征的位掩码标志。</span><span class="sxs-lookup"><span data-stu-id="feb6b-105">Contains a bitmask of flags that client applications should query to determine the characteristics of a message store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="feb6b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="feb6b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="feb6b-107">PR_STORE_UNICODE_MASK</span><span class="sxs-lookup"><span data-stu-id="feb6b-107">PR_STORE_UNICODE_MASK</span></span>  <br/> |
|<span data-ttu-id="feb6b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="feb6b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="feb6b-109">0x340F</span><span class="sxs-lookup"><span data-stu-id="feb6b-109">0x340F</span></span>  <br/> |
|<span data-ttu-id="feb6b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="feb6b-110">Data type:</span></span>  <br/> |<span data-ttu-id="feb6b-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="feb6b-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="feb6b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="feb6b-112">Area:</span></span>  <br/> |<span data-ttu-id="feb6b-113">MAPI 邮件存储</span><span class="sxs-lookup"><span data-stu-id="feb6b-113">MAPI message store</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="feb6b-114">备注</span><span class="sxs-lookup"><span data-stu-id="feb6b-114">Remarks</span></span>

<span data-ttu-id="feb6b-115">此属性向计划向客户端应用程序公开邮件存储的功能。</span><span class="sxs-lookup"><span data-stu-id="feb6b-115">This property discloses the capabilities of a message store to client applications planning to send it a message.</span></span> <span data-ttu-id="feb6b-116">该标志有助于客户端或其他存储做出决策，例如是发送 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 还是仅发送 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 。</span><span class="sxs-lookup"><span data-stu-id="feb6b-116">The flags can facilitate decisions by a client or another store, such as whether to send **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) or only **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)).</span></span> <span data-ttu-id="feb6b-117">客户端永远不应设置此属性。</span><span class="sxs-lookup"><span data-stu-id="feb6b-117">A client should never set this property.</span></span> <span data-ttu-id="feb6b-118">尝试返回 **MAPI_E_COMPUTED**。</span><span class="sxs-lookup"><span data-stu-id="feb6b-118">An attempt returns **MAPI_E_COMPUTED**.</span></span> 
  
<span data-ttu-id="feb6b-119">可以为此属性设置以下一个或多个标志：</span><span class="sxs-lookup"><span data-stu-id="feb6b-119">One or more of the following flags can be set for this property:</span></span> 
  
<span data-ttu-id="feb6b-120">STORE_ANSI_OK</span><span class="sxs-lookup"><span data-stu-id="feb6b-120">STORE_ANSI_OK</span></span>
  
> <span data-ttu-id="feb6b-121"> (131072 0x00020000) 邮件存储支持包含美国国家标准协会 (ANSI)  (8 位字符) 属性。</span><span class="sxs-lookup"><span data-stu-id="feb6b-121">(131072, 0x00020000) The message store supports properties that contain American National Standards Institute (ANSI) (8-bit) characters.</span></span>
    
<span data-ttu-id="feb6b-122">STORE_ATTACH_OK</span><span class="sxs-lookup"><span data-stu-id="feb6b-122">STORE_ATTACH_OK</span></span> 
  
> <span data-ttu-id="feb6b-123"> (32 0x00000020) 邮件存储支持对象链接和嵌入 OLE (OLE) 或非 OLE 附件。</span><span class="sxs-lookup"><span data-stu-id="feb6b-123">(32, 0x00000020) The message store supports Object Linking and Embedding (OLE) or non-OLE attachments to messages.</span></span> 
    
<span data-ttu-id="feb6b-124">STORE_CATEGORIZE_OK</span><span class="sxs-lookup"><span data-stu-id="feb6b-124">STORE_CATEGORIZE_OK</span></span> 
  
> <span data-ttu-id="feb6b-125"> (1024 中，0x00000400) 邮件存储支持表的分类视图。</span><span class="sxs-lookup"><span data-stu-id="feb6b-125">(1024, 0x00000400) The message store supports categorized views of tables.</span></span> 
    
<span data-ttu-id="feb6b-126">STORE_CREATE_OK</span><span class="sxs-lookup"><span data-stu-id="feb6b-126">STORE_CREATE_OK</span></span> 
  
> <span data-ttu-id="feb6b-127"> (16 0x00000010) 邮件存储支持新建邮件。</span><span class="sxs-lookup"><span data-stu-id="feb6b-127">(16, 0x00000010) The message store supports creation of new messages.</span></span> 
    
<span data-ttu-id="feb6b-128">STORE_ENTRYID_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="feb6b-128">STORE_ENTRYID_UNIQUE</span></span> 
  
> <span data-ttu-id="feb6b-129"> (1 0x00000001) ，邮件存储中对象的条目标识符是唯一的，即从不在存储生命周期中重复使用。</span><span class="sxs-lookup"><span data-stu-id="feb6b-129">(1, 0x00000001) Entry identifiers for the objects in the message store are unique, that is, never reused during the life of the store.</span></span> 
    
<span data-ttu-id="feb6b-130">STORE_HTML_OK</span><span class="sxs-lookup"><span data-stu-id="feb6b-130">STORE_HTML_OK</span></span> 
  
> <span data-ttu-id="feb6b-131"> (65536 中，0x00010000) 邮件存储支持 HTML 邮件，存储在 PR_BODY_HTML ( [PidTagBodyHtml](pidtagbodyhtml-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="feb6b-131">(65536, 0x00010000) The message store supports HTML messages, stored in the **PR_BODY_HTML** ([PidTagBodyHtml](pidtagbodyhtml-canonical-property.md)) property.</span></span> <span data-ttu-id="feb6b-132">请注意 **，STORE_HTML_OK** MAPIDEFS 版本中未定义。Microsoft Exchange 2000 Server 及更早版本中包含的 H。</span><span class="sxs-lookup"><span data-stu-id="feb6b-132">Note that **STORE_HTML_OK** is not defined in versions of MAPIDEFS.H that are included with Microsoft Exchange 2000 Server and earlier.</span></span> <span data-ttu-id="feb6b-133">如果你的开发环境使用 MAPIDEFS。不包含文件的 H **文件** STORE_HTML_OK，请改为使用值"0x00010000"。</span><span class="sxs-lookup"><span data-stu-id="feb6b-133">If your development environment uses a MAPIDEFS.H file that does not include **STORE_HTML_OK**, use the value "0x00010000" instead.</span></span> 
    
<span data-ttu-id="feb6b-134">STORE_ITEMPROC</span><span class="sxs-lookup"><span data-stu-id="feb6b-134">STORE_ITEMPROC</span></span>
  
> <span data-ttu-id="feb6b-135"> (2097152 0x00200000) 包装的 PST 存储中，指示当新邮件到达存储区时，该存储会单独对邮件执行规则和垃圾邮件筛选器处理。</span><span class="sxs-lookup"><span data-stu-id="feb6b-135">(2097152, 0x00200000) In a wrapped PST store, indicates that when a new message arrives at the store, the store does rules and spam filter processing on the message separately.</span></span> <span data-ttu-id="feb6b-136">存储调用 [IMAPISupport：：Notify](imapisupport-notify.md)，在作为参数传递的 [NOTIFICATION](notification.md)结构中设置 **fnevNewMail，** 然后将新消息的详细信息传递给侦听客户端。</span><span class="sxs-lookup"><span data-stu-id="feb6b-136">The store calls [IMAPISupport::Notify](imapisupport-notify.md), setting **fnevNewMail** in the [NOTIFICATION](notification.md) structure that is passed as a parameter, and then passes the details of the new message to the listening client.</span></span> <span data-ttu-id="feb6b-137">随后，当侦听客户端收到通知，它不会处理邮件上的规则。</span><span class="sxs-lookup"><span data-stu-id="feb6b-137">Subsequently, when the listening client receives the notification, it does not process rules on the message.</span></span> 
    
<span data-ttu-id="feb6b-138">STORE_LOCALSTORE</span><span class="sxs-lookup"><span data-stu-id="feb6b-138">STORE_LOCALSTORE</span></span>
  
> <span data-ttu-id="feb6b-139"> (524288，0x00080000) 保留此标志，不应使用。</span><span class="sxs-lookup"><span data-stu-id="feb6b-139">(524288, 0x00080000) This flag is reserved and should not be used.</span></span>
    
<span data-ttu-id="feb6b-140">STORE_MODIFY_OK</span><span class="sxs-lookup"><span data-stu-id="feb6b-140">STORE_MODIFY_OK</span></span> 
  
> <span data-ttu-id="feb6b-141"> (8，0x00000008) 邮件存储支持修改其现有邮件。</span><span class="sxs-lookup"><span data-stu-id="feb6b-141">(8, 0x00000008) The message store supports modification of its existing messages.</span></span> 
    
<span data-ttu-id="feb6b-142">STORE_MV_PROPS_OK</span><span class="sxs-lookup"><span data-stu-id="feb6b-142">STORE_MV_PROPS_OK</span></span> 
  
> <span data-ttu-id="feb6b-143"> (512， 0x00000200) 邮件存储支持多值属性，在整个保存操作中保证多值属性中值顺序的稳定性，并支持表中的多值属性实例化。</span><span class="sxs-lookup"><span data-stu-id="feb6b-143">(512, 0x00000200) The message store supports multivalued properties, guarantees the stability of value order in a multivalued property throughout a save operation, and supports instantiation of multivalued properties in tables.</span></span> 
    
<span data-ttu-id="feb6b-144">STORE_NOTIFY_OK</span><span class="sxs-lookup"><span data-stu-id="feb6b-144">STORE_NOTIFY_OK</span></span> 
  
> <span data-ttu-id="feb6b-145"> (256，0x00000100) 邮件存储支持通知。</span><span class="sxs-lookup"><span data-stu-id="feb6b-145">(256, 0x00000100) The message store supports notifications.</span></span> 
    
<span data-ttu-id="feb6b-146">STORE_OLE_OK</span><span class="sxs-lookup"><span data-stu-id="feb6b-146">STORE_OLE_OK</span></span> 
  
> <span data-ttu-id="feb6b-147"> (64，0x00000040) 邮件存储支持 OLE 附件。</span><span class="sxs-lookup"><span data-stu-id="feb6b-147">(64, 0x00000040) The message store supports OLE attachments.</span></span> <span data-ttu-id="feb6b-148">OLE 数据可通过 **IStorage** 接口访问，例如可通过 **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 访问。</span><span class="sxs-lookup"><span data-stu-id="feb6b-148">The OLE data is accessible through an **IStorage** interface, such as that available through the **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) property.</span></span> 
    
<span data-ttu-id="feb6b-149">STORE_PUBLIC_FOLDERS</span><span class="sxs-lookup"><span data-stu-id="feb6b-149">STORE_PUBLIC_FOLDERS</span></span> 
  
> <span data-ttu-id="feb6b-150"> (16384 中，0x00004000) 此存储中的文件夹是公共 (多用户) ，而不是私有 (可能是多实例，但不是多用户) 。</span><span class="sxs-lookup"><span data-stu-id="feb6b-150">(16384, 0x00004000) The folders in this store are public (multi-user), not private (possibly multi-instance but not multi-user).</span></span> 
    
<span data-ttu-id="feb6b-151">STORE_PUSHER_OK</span><span class="sxs-lookup"><span data-stu-id="feb6b-151">STORE_PUSHER_OK</span></span>
  
> <span data-ttu-id="feb6b-152"> (8388608 中，0x00800000) MAPI 协议处理程序将不会对存储进行爬网，并且存储负责通过通知将任何更改推送到索引器，以对消息编制索引。</span><span class="sxs-lookup"><span data-stu-id="feb6b-152">(8388608, 0x00800000) The MAPI Protocol Handler will not crawl the store, and the store is responsible to push any changes through notifications to the indexer to have messages indexed.</span></span>
    
<span data-ttu-id="feb6b-153">STORE_READONLY</span><span class="sxs-lookup"><span data-stu-id="feb6b-153">STORE_READONLY</span></span> 
  
> <span data-ttu-id="feb6b-154"> (2 0x00000002) ，邮件存储的所有接口具有只读访问级别。</span><span class="sxs-lookup"><span data-stu-id="feb6b-154">(2, 0x00000002) All interfaces for the message store have a read-only access level.</span></span> 
    
<span data-ttu-id="feb6b-155">STORE_RESTRICTION_OK</span><span class="sxs-lookup"><span data-stu-id="feb6b-155">STORE_RESTRICTION_OK</span></span> 
  
> <span data-ttu-id="feb6b-156"> (4096，0x00001000) 邮件存储支持限制。</span><span class="sxs-lookup"><span data-stu-id="feb6b-156">(4096, 0x00001000) The message store supports restrictions.</span></span> 
    
<span data-ttu-id="feb6b-157">STORE_RTF_OK</span><span class="sxs-lookup"><span data-stu-id="feb6b-157">STORE_RTF_OK</span></span> 
  
> <span data-ttu-id="feb6b-158"> (2048 0x00000800) 邮件存储支持 RTF 格式 (RTF) 邮件（通常已压缩）并且存储本身保持 PR_BODY 和 PR_RTF_COMPRESSED **同步。**</span><span class="sxs-lookup"><span data-stu-id="feb6b-158">(2048, 0x00000800) The message store supports Rich Text Format (RTF) messages, usually compressed, and the store itself keeps **PR_BODY** and **PR_RTF_COMPRESSED** synchronized.</span></span> 
    
<span data-ttu-id="feb6b-159">STORE_SEARCH_OK</span><span class="sxs-lookup"><span data-stu-id="feb6b-159">STORE_SEARCH_OK</span></span> 
  
> <span data-ttu-id="feb6b-160"> (4，0x00000004) 邮件存储支持搜索结果文件夹。</span><span class="sxs-lookup"><span data-stu-id="feb6b-160">(4, 0x00000004) The message store supports search-results folders.</span></span> 
    
<span data-ttu-id="feb6b-161">STORE_SORT_OK</span><span class="sxs-lookup"><span data-stu-id="feb6b-161">STORE_SORT_OK</span></span> 
  
> <span data-ttu-id="feb6b-162"> (8192，0x00002000) 邮件存储支持表的排序视图。</span><span class="sxs-lookup"><span data-stu-id="feb6b-162">(8192, 0x00002000) The message store supports sorting views of tables.</span></span> 
    
<span data-ttu-id="feb6b-163">STORE_SUBMIT_OK</span><span class="sxs-lookup"><span data-stu-id="feb6b-163">STORE_SUBMIT_OK</span></span> 
  
> <span data-ttu-id="feb6b-164"> (128 0x00000080) 邮件存储支持将邮件标记为提交。</span><span class="sxs-lookup"><span data-stu-id="feb6b-164">(128, 0x00000080) The message store supports marking a message for submission.</span></span> 
    
<span data-ttu-id="feb6b-165">STORE_UNCOMPRESSED_RTF</span><span class="sxs-lookup"><span data-stu-id="feb6b-165">STORE_UNCOMPRESSED_RTF</span></span> 
  
> <span data-ttu-id="feb6b-166"> (32768 中，0x00008000) 邮件存储支持将可修改的表单文本存储在未压缩 (RTF) 邮件中。</span><span class="sxs-lookup"><span data-stu-id="feb6b-166">(32768, 0x00008000) The message store supports storage of revisable form text (RTF) messages in uncompressed form.</span></span> <span data-ttu-id="feb6b-167">未压缩的 RTF 流由流标头中的 **值 dwMagicUncompressedRTF** 标识。</span><span class="sxs-lookup"><span data-stu-id="feb6b-167">An uncompressed RTF stream is identified by the value **dwMagicUncompressedRTF** in the stream header.</span></span> <span data-ttu-id="feb6b-168">**dwMagicUncompressedRTF** 值在 RTFLIB 中定义。H 文件。</span><span class="sxs-lookup"><span data-stu-id="feb6b-168">The **dwMagicUncompressedRTF** value is defined in the RTFLIB.H file.</span></span> 
    
<span data-ttu-id="feb6b-169">STORE_UNICODE_OK</span><span class="sxs-lookup"><span data-stu-id="feb6b-169">STORE_UNICODE_OK</span></span>
  
> <span data-ttu-id="feb6b-170"> (262144 中，0x00040000) 邮件存储支持包含 Unicode 字符的属性。</span><span class="sxs-lookup"><span data-stu-id="feb6b-170">(262144, 0x00040000) The message store supports properties containing Unicode characters.</span></span>
    
<span data-ttu-id="feb6b-171">始终可以存储邮件的 RTF 版本，即使邮件存储无法识别 RTF。</span><span class="sxs-lookup"><span data-stu-id="feb6b-171">An RTF version of a message can always be stored, even if the message store is non-RTF-aware.</span></span> <span data-ttu-id="feb6b-172">如果未为STORE_RTF_OK存储设置该位，则维护 RTF 版本的客户端必须自己调用 [RTFSync](rtfsync.md)函数，以保持文本内容的 PR_BODY 和 **PR_RTF_COMPRESSED** 版本的同步。 </span><span class="sxs-lookup"><span data-stu-id="feb6b-172">If the STORE_RTF_OK bit is not set for a particular store, a client maintaining RTF versions must itself call the [RTFSync](rtfsync.md) function to keep the **PR_BODY** and **PR_RTF_COMPRESSED** versions synchronized for text content.</span></span> <span data-ttu-id="feb6b-173">RTF 始终存储在PR_RTF_COMPRESSED，不管它是否实际压缩。</span><span class="sxs-lookup"><span data-stu-id="feb6b-173">RTF is always stored in **PR_RTF_COMPRESSED**, whether it is actually compressed or not.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="feb6b-174">相关资源</span><span class="sxs-lookup"><span data-stu-id="feb6b-174">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="feb6b-175">头文件</span><span class="sxs-lookup"><span data-stu-id="feb6b-175">Header files</span></span>

<span data-ttu-id="feb6b-176">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="feb6b-176">Mapidefs.h</span></span>
  
> <span data-ttu-id="feb6b-177">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="feb6b-177">Provides data type definitions.</span></span>
    
<span data-ttu-id="feb6b-178">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="feb6b-178">Mapitags.h</span></span>
  
> <span data-ttu-id="feb6b-179">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="feb6b-179">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="feb6b-180">另请参阅</span><span class="sxs-lookup"><span data-stu-id="feb6b-180">See also</span></span>



[<span data-ttu-id="feb6b-181">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="feb6b-181">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="feb6b-182">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="feb6b-182">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="feb6b-183">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="feb6b-183">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="feb6b-184">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="feb6b-184">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

