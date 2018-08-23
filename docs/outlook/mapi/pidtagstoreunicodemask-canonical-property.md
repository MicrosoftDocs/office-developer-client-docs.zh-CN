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
ms.openlocfilehash: 4bfbaada3ced58a689ca4d4745e6e4c798755d4a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574305"
---
# <a name="pidtagstoreunicodemask-canonical-property"></a><span data-ttu-id="f8701-103">PidTagStoreUnicodeMask 规范属性</span><span class="sxs-lookup"><span data-stu-id="f8701-103">PidTagStoreUnicodeMask Canonical Property</span></span>

  
  
<span data-ttu-id="f8701-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f8701-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f8701-105">包含客户端应用程序应查询以确定的消息存储的特征的标志位的掩码。</span><span class="sxs-lookup"><span data-stu-id="f8701-105">Contains a bitmask of flags that client applications should query to determine the characteristics of a message store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f8701-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f8701-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f8701-107">PR_STORE_UNICODE_MASK</span><span class="sxs-lookup"><span data-stu-id="f8701-107">PR_STORE_UNICODE_MASK</span></span>  <br/> |
|<span data-ttu-id="f8701-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="f8701-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f8701-109">0x340F</span><span class="sxs-lookup"><span data-stu-id="f8701-109">0x340F</span></span>  <br/> |
|<span data-ttu-id="f8701-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f8701-110">Data type:</span></span>  <br/> |<span data-ttu-id="f8701-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="f8701-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="f8701-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f8701-112">Area:</span></span>  <br/> |<span data-ttu-id="f8701-113">MAPI 邮件存储</span><span class="sxs-lookup"><span data-stu-id="f8701-113">MAPI message store</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f8701-114">注解</span><span class="sxs-lookup"><span data-stu-id="f8701-114">Remarks</span></span>

<span data-ttu-id="f8701-115">此属性会泄露打算将其发送一条消息的客户端应用程序的消息存储的功能。</span><span class="sxs-lookup"><span data-stu-id="f8701-115">This property discloses the capabilities of a message store to client applications planning to send it a message.</span></span> <span data-ttu-id="f8701-116">Flags 可以方便地通过客户端或另一个存储，如是否发送**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 或仅**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 的决策。</span><span class="sxs-lookup"><span data-stu-id="f8701-116">The flags can facilitate decisions by a client or another store, such as whether to send **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) or only **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)).</span></span> <span data-ttu-id="f8701-117">客户端应永远不会将该属性。</span><span class="sxs-lookup"><span data-stu-id="f8701-117">A client should never set this property.</span></span> <span data-ttu-id="f8701-118">尝试返回**MAPI_E_COMPUTED**。</span><span class="sxs-lookup"><span data-stu-id="f8701-118">An attempt returns **MAPI_E_COMPUTED**.</span></span> 
  
<span data-ttu-id="f8701-119">此属性，可以设置一个或多个以下标志：</span><span class="sxs-lookup"><span data-stu-id="f8701-119">One or more of the following flags can be set for this property:</span></span> 
  
<span data-ttu-id="f8701-120">STORE_ANSI_OK</span><span class="sxs-lookup"><span data-stu-id="f8701-120">STORE_ANSI_OK</span></span>
  
> <span data-ttu-id="f8701-121">（131072、 0x00020000）消息存储库支持属性包含协会 (ANSI) （8 位） 字符。</span><span class="sxs-lookup"><span data-stu-id="f8701-121">(131072, 0x00020000) The message store supports properties that contain American National Standards Institute (ANSI) (8-bit) characters.</span></span>
    
<span data-ttu-id="f8701-122">STORE_ATTACH_OK</span><span class="sxs-lookup"><span data-stu-id="f8701-122">STORE_ATTACH_OK</span></span> 
  
> <span data-ttu-id="f8701-123">（32、 0x00000020）消息存储库支持对象链接和嵌入 (OLE) 或非 OLE 邮件附件。</span><span class="sxs-lookup"><span data-stu-id="f8701-123">(32, 0x00000020) The message store supports Object Linking and Embedding (OLE) or non-OLE attachments to messages.</span></span> 
    
<span data-ttu-id="f8701-124">STORE_CATEGORIZE_OK</span><span class="sxs-lookup"><span data-stu-id="f8701-124">STORE_CATEGORIZE_OK</span></span> 
  
> <span data-ttu-id="f8701-125">(1024，0x00000400)消息存储支持表的分类的的视图。</span><span class="sxs-lookup"><span data-stu-id="f8701-125">(1024, 0x00000400) The message store supports categorized views of tables.</span></span> 
    
<span data-ttu-id="f8701-126">STORE_CREATE_OK</span><span class="sxs-lookup"><span data-stu-id="f8701-126">STORE_CREATE_OK</span></span> 
  
> <span data-ttu-id="f8701-127">（16、 0x00000010）消息存储库支持创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="f8701-127">(16, 0x00000010) The message store supports creation of new messages.</span></span> 
    
<span data-ttu-id="f8701-128">STORE_ENTRYID_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="f8701-128">STORE_ENTRYID_UNIQUE</span></span> 
  
> <span data-ttu-id="f8701-129">（1，0x00000001）消息存储库中的对象的项标识符是唯一的即永远不会存储的生命周期内重用。</span><span class="sxs-lookup"><span data-stu-id="f8701-129">(1, 0x00000001) Entry identifiers for the objects in the message store are unique, that is, never reused during the life of the store.</span></span> 
    
<span data-ttu-id="f8701-130">STORE_HTML_OK</span><span class="sxs-lookup"><span data-stu-id="f8701-130">STORE_HTML_OK</span></span> 
  
> <span data-ttu-id="f8701-131">（65536、 0x00010000）消息存储库支持 HTML 邮件，存储在**PR_BODY_HTML** ([PidTagBodyHtml](pidtagbodyhtml-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="f8701-131">(65536, 0x00010000) The message store supports HTML messages, stored in the **PR_BODY_HTML** ([PidTagBodyHtml](pidtagbodyhtml-canonical-property.md)) property.</span></span> <span data-ttu-id="f8701-132">请注意， **STORE_HTML_OK** MAPIDEFS 的版本中未定义。是包含与 Microsoft Exchange 2000 Server 及更早版本的 H。</span><span class="sxs-lookup"><span data-stu-id="f8701-132">Note that **STORE_HTML_OK** is not defined in versions of MAPIDEFS.H that are included with Microsoft Exchange 2000 Server and earlier.</span></span> <span data-ttu-id="f8701-133">如果您的开发环境使用 MAPIDEFS。H 文件，不包括**STORE_HTML_OK**，则改用"0x00010000"的值。</span><span class="sxs-lookup"><span data-stu-id="f8701-133">If your development environment uses a MAPIDEFS.H file that does not include **STORE_HTML_OK**, use the value "0x00010000" instead.</span></span> 
    
<span data-ttu-id="f8701-134">STORE_ITEMPROC</span><span class="sxs-lookup"><span data-stu-id="f8701-134">STORE_ITEMPROC</span></span>
  
> <span data-ttu-id="f8701-135">（2097152、 0x00200000）在换行 PST 存储中，指示在新邮件到达存储，存储的规则和垃圾邮件筛选单独对邮件处理。</span><span class="sxs-lookup"><span data-stu-id="f8701-135">(2097152, 0x00200000) In a wrapped PST store, indicates that when a new message arrives at the store, the store does rules and spam filter processing on the message separately.</span></span> <span data-ttu-id="f8701-136">存储呼叫[IMAPISupport::Notify](imapisupport-notify.md)，设置**fnevNewMail**作为一个参数传递，然后将新消息的详细信息传递到侦听客户端的[通知](notification.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="f8701-136">The store calls [IMAPISupport::Notify](imapisupport-notify.md), setting **fnevNewMail** in the [NOTIFICATION](notification.md) structure that is passed as a parameter, and then passes the details of the new message to the listening client.</span></span> <span data-ttu-id="f8701-137">随后，侦听客户端接收通知时，它不处理邮件的规则。</span><span class="sxs-lookup"><span data-stu-id="f8701-137">Subsequently, when the listening client receives the notification, it does not process rules on the message.</span></span> 
    
<span data-ttu-id="f8701-138">STORE_LOCALSTORE</span><span class="sxs-lookup"><span data-stu-id="f8701-138">STORE_LOCALSTORE</span></span>
  
> <span data-ttu-id="f8701-139">（524288、 0x00080000）此标志保留，不应使用。</span><span class="sxs-lookup"><span data-stu-id="f8701-139">(524288, 0x00080000) This flag is reserved and should not be used.</span></span>
    
<span data-ttu-id="f8701-140">STORE_MODIFY_OK</span><span class="sxs-lookup"><span data-stu-id="f8701-140">STORE_MODIFY_OK</span></span> 
  
> <span data-ttu-id="f8701-141">（8，0x00000008）消息存储库支持其现有的邮件的修改。</span><span class="sxs-lookup"><span data-stu-id="f8701-141">(8, 0x00000008) The message store supports modification of its existing messages.</span></span> 
    
<span data-ttu-id="f8701-142">STORE_MV_PROPS_OK</span><span class="sxs-lookup"><span data-stu-id="f8701-142">STORE_MV_PROPS_OK</span></span> 
  
> <span data-ttu-id="f8701-143">（512、 0x00000200）消息存储库支持多值的属性，按原样的整个保存一个多值属性的值顺序稳定性操作，并且支持实例化的表中的多值属性。</span><span class="sxs-lookup"><span data-stu-id="f8701-143">(512, 0x00000200) The message store supports multivalued properties, guarantees the stability of value order in a multivalued property throughout a save operation, and supports instantiation of multivalued properties in tables.</span></span> 
    
<span data-ttu-id="f8701-144">STORE_NOTIFY_OK</span><span class="sxs-lookup"><span data-stu-id="f8701-144">STORE_NOTIFY_OK</span></span> 
  
> <span data-ttu-id="f8701-145">（256、 0x00000100）消息存储库支持通知。</span><span class="sxs-lookup"><span data-stu-id="f8701-145">(256, 0x00000100) The message store supports notifications.</span></span> 
    
<span data-ttu-id="f8701-146">STORE_OLE_OK</span><span class="sxs-lookup"><span data-stu-id="f8701-146">STORE_OLE_OK</span></span> 
  
> <span data-ttu-id="f8701-147">（64、 0x00000040）消息存储库支持 OLE 附件。</span><span class="sxs-lookup"><span data-stu-id="f8701-147">(64, 0x00000040) The message store supports OLE attachments.</span></span> <span data-ttu-id="f8701-148">OLE 数据是可通过**IStorage**接口，例如，可通过**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="f8701-148">The OLE data is accessible through an **IStorage** interface, such as that available through the **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) property.</span></span> 
    
<span data-ttu-id="f8701-149">STORE_PUBLIC_FOLDERS</span><span class="sxs-lookup"><span data-stu-id="f8701-149">STORE_PUBLIC_FOLDERS</span></span> 
  
> <span data-ttu-id="f8701-150">（16384、 0x00004000）此存储区中的文件夹是公共 （多用户），不专用 (可能是多实例，但不是多的用户)。</span><span class="sxs-lookup"><span data-stu-id="f8701-150">(16384, 0x00004000) The folders in this store are public (multi-user), not private (possibly multi-instance but not multi-user).</span></span> 
    
<span data-ttu-id="f8701-151">STORE_PUSHER_OK</span><span class="sxs-lookup"><span data-stu-id="f8701-151">STORE_PUSHER_OK</span></span>
  
> <span data-ttu-id="f8701-152">（8388608、 0x00800000）MAPI 协议处理程序将不存储进行爬网，并存储负责将任何更改通过通知推送到索引器已编制索引的邮件。</span><span class="sxs-lookup"><span data-stu-id="f8701-152">(8388608, 0x00800000) The MAPI Protocol Handler will not crawl the store, and the store is responsible to push any changes through notifications to the indexer to have messages indexed.</span></span>
    
<span data-ttu-id="f8701-153">STORE_READONLY</span><span class="sxs-lookup"><span data-stu-id="f8701-153">STORE_READONLY</span></span> 
  
> <span data-ttu-id="f8701-154">（2，0x00000002:uc）消息存储的所有接口都具有只读访问权限级别。</span><span class="sxs-lookup"><span data-stu-id="f8701-154">(2, 0x00000002) All interfaces for the message store have a read-only access level.</span></span> 
    
<span data-ttu-id="f8701-155">STORE_RESTRICTION_OK</span><span class="sxs-lookup"><span data-stu-id="f8701-155">STORE_RESTRICTION_OK</span></span> 
  
> <span data-ttu-id="f8701-156">(4096，0x00001000)消息存储支持的限制。</span><span class="sxs-lookup"><span data-stu-id="f8701-156">(4096, 0x00001000) The message store supports restrictions.</span></span> 
    
<span data-ttu-id="f8701-157">STORE_RTF_OK</span><span class="sxs-lookup"><span data-stu-id="f8701-157">STORE_RTF_OK</span></span> 
  
> <span data-ttu-id="f8701-158">(2048年 0x00000800)消息存储库支持富文本格式 (RTF) 消息，通常压缩，并存储本身保持**PR_BODY**和**PR_RTF_COMPRESSED**同步。</span><span class="sxs-lookup"><span data-stu-id="f8701-158">(2048, 0x00000800) The message store supports Rich Text Format (RTF) messages, usually compressed, and the store itself keeps **PR_BODY** and **PR_RTF_COMPRESSED** synchronized.</span></span> 
    
<span data-ttu-id="f8701-159">STORE_SEARCH_OK</span><span class="sxs-lookup"><span data-stu-id="f8701-159">STORE_SEARCH_OK</span></span> 
  
> <span data-ttu-id="f8701-160">（4，0x00000004）消息存储库支持搜索结果文件夹。</span><span class="sxs-lookup"><span data-stu-id="f8701-160">(4, 0x00000004) The message store supports search-results folders.</span></span> 
    
<span data-ttu-id="f8701-161">STORE_SORT_OK</span><span class="sxs-lookup"><span data-stu-id="f8701-161">STORE_SORT_OK</span></span> 
  
> <span data-ttu-id="f8701-162">(8192，0x00002000)消息存储支持表的排序的视图。</span><span class="sxs-lookup"><span data-stu-id="f8701-162">(8192, 0x00002000) The message store supports sorting views of tables.</span></span> 
    
<span data-ttu-id="f8701-163">STORE_SUBMIT_OK</span><span class="sxs-lookup"><span data-stu-id="f8701-163">STORE_SUBMIT_OK</span></span> 
  
> <span data-ttu-id="f8701-164">（128、 0x00000080）消息存储库支持标记提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="f8701-164">(128, 0x00000080) The message store supports marking a message for submission.</span></span> 
    
<span data-ttu-id="f8701-165">STORE_UNCOMPRESSED_RTF</span><span class="sxs-lookup"><span data-stu-id="f8701-165">STORE_UNCOMPRESSED_RTF</span></span> 
  
> <span data-ttu-id="f8701-166">（32768、 0x00008000）消息存储在未压缩的窗体中支持可修改格式 (RTF) 文本消息存储。</span><span class="sxs-lookup"><span data-stu-id="f8701-166">(32768, 0x00008000) The message store supports storage of revisable form text (RTF) messages in uncompressed form.</span></span> <span data-ttu-id="f8701-167">由值**dwMagicUncompressedRTF**流标头中标识未压缩的 RTF 流。</span><span class="sxs-lookup"><span data-stu-id="f8701-167">An uncompressed RTF stream is identified by the value **dwMagicUncompressedRTF** in the stream header.</span></span> <span data-ttu-id="f8701-168">RTFLIB 中定义的**dwMagicUncompressedRTF**值。H 文件。</span><span class="sxs-lookup"><span data-stu-id="f8701-168">The **dwMagicUncompressedRTF** value is defined in the RTFLIB.H file.</span></span> 
    
<span data-ttu-id="f8701-169">STORE_UNICODE_OK</span><span class="sxs-lookup"><span data-stu-id="f8701-169">STORE_UNICODE_OK</span></span>
  
> <span data-ttu-id="f8701-170">（262144、 0x00040000）消息存储库支持属性包含 Unicode 字符。</span><span class="sxs-lookup"><span data-stu-id="f8701-170">(262144, 0x00040000) The message store supports properties containing Unicode characters.</span></span>
    
<span data-ttu-id="f8701-171">总是可以存储一条消息的 RTF 版本，即使不识别 RTF 的消息存储库。</span><span class="sxs-lookup"><span data-stu-id="f8701-171">An RTF version of a message can always be stored, even if the message store is non-RTF-aware.</span></span> <span data-ttu-id="f8701-172">如果特定存储未设置 STORE_RTF_OK 位，维护 RTF 版本的客户端必须本身调用[RTFSync](rtfsync.md)函数保留为文本内容同步的**PR_BODY**和**PR_RTF_COMPRESSED**版本。</span><span class="sxs-lookup"><span data-stu-id="f8701-172">If the STORE_RTF_OK bit is not set for a particular store, a client maintaining RTF versions must itself call the [RTFSync](rtfsync.md) function to keep the **PR_BODY** and **PR_RTF_COMPRESSED** versions synchronized for text content.</span></span> <span data-ttu-id="f8701-173">RTF 始终存储在**PR_RTF_COMPRESSED**，是否或不实际压缩。</span><span class="sxs-lookup"><span data-stu-id="f8701-173">RTF is always stored in **PR_RTF_COMPRESSED**, whether it is actually compressed or not.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="f8701-174">相关资源</span><span class="sxs-lookup"><span data-stu-id="f8701-174">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="f8701-175">头文件</span><span class="sxs-lookup"><span data-stu-id="f8701-175">Header files</span></span>

<span data-ttu-id="f8701-176">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f8701-176">Mapidefs.h</span></span>
  
> <span data-ttu-id="f8701-177">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f8701-177">Provides data type definitions.</span></span>
    
<span data-ttu-id="f8701-178">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f8701-178">Mapitags.h</span></span>
  
> <span data-ttu-id="f8701-179">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f8701-179">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f8701-180">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8701-180">See also</span></span>



[<span data-ttu-id="f8701-181">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f8701-181">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f8701-182">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f8701-182">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f8701-183">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f8701-183">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f8701-184">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f8701-184">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

