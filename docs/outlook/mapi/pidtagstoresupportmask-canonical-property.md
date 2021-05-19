---
title: PidTagStoreSupportMask 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStoreSupportMask
api_type:
- COM
ms.assetid: ada5694a-b5b1-471f-be33-906fc052681a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 143e7f0d2cd89cd4e7956cdda05d1bd512db4027
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32340969"
---
# <a name="pidtagstoresupportmask-canonical-property"></a><span data-ttu-id="558bb-103">PidTagStoreSupportMask 规范属性</span><span class="sxs-lookup"><span data-stu-id="558bb-103">PidTagStoreSupportMask Canonical Property</span></span>

  
  
<span data-ttu-id="558bb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="558bb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="558bb-105">包含客户端应用程序查询以确定邮件存储特征的位掩码标志。</span><span class="sxs-lookup"><span data-stu-id="558bb-105">Contains a bitmask of flags that client applications query to determine the characteristics of a message store.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="558bb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="558bb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="558bb-107">PR_STORE_SUPPORT_MASK</span><span class="sxs-lookup"><span data-stu-id="558bb-107">PR_STORE_SUPPORT_MASK</span></span>  <br/> |
|<span data-ttu-id="558bb-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="558bb-108">Identifier:</span></span>  <br/> |<span data-ttu-id="558bb-109">0x340D</span><span class="sxs-lookup"><span data-stu-id="558bb-109">0x340D</span></span>  <br/> |
|<span data-ttu-id="558bb-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="558bb-110">Data type:</span></span>  <br/> |<span data-ttu-id="558bb-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="558bb-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="558bb-112">区域：</span><span class="sxs-lookup"><span data-stu-id="558bb-112">Area:</span></span>  <br/> |<span data-ttu-id="558bb-113">其他</span><span class="sxs-lookup"><span data-stu-id="558bb-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="558bb-114">备注</span><span class="sxs-lookup"><span data-stu-id="558bb-114">Remarks</span></span>

<span data-ttu-id="558bb-115">此属性向计划向邮件发送的客户端应用程序公开邮件存储的功能。</span><span class="sxs-lookup"><span data-stu-id="558bb-115">This property discloses the capabilities of a message store to client applications that are planning to send it a message.</span></span> <span data-ttu-id="558bb-116">该标志可以支持客户端或其他存储的决策，例如是发送 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 还是仅PR_RTF_COMPRESSED ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 。 </span><span class="sxs-lookup"><span data-stu-id="558bb-116">The flags can support decisions by a client or another store, such as whether to send **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) or only **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)).</span></span> <span data-ttu-id="558bb-117">客户端永远不应设置 **PR_STORE_SUPPORT_MASK;** 尝试设置此标志将返回MAPI_E_COMPUTED。</span><span class="sxs-lookup"><span data-stu-id="558bb-117">A client should never set **PR_STORE_SUPPORT_MASK**; an attempt to set this flag returns MAPI_E_COMPUTED.</span></span> 
  
<span data-ttu-id="558bb-118">可以针对该位掩码设置以下一个或多个PR_STORE_SUPPORT_MASK标记： </span><span class="sxs-lookup"><span data-stu-id="558bb-118">One or more of the following flags can be set for the **PR_STORE_SUPPORT_MASK** bitmask:</span></span> 
  
<span data-ttu-id="558bb-119">STORE_ANSI_OK</span><span class="sxs-lookup"><span data-stu-id="558bb-119">STORE_ANSI_OK</span></span>
  
> <span data-ttu-id="558bb-120"> (131072 中，0x00020000) 邮件存储支持包含 ANSI (8 位字符) 属性。</span><span class="sxs-lookup"><span data-stu-id="558bb-120">(131072, 0x00020000) The message store supports properties that contain ANSI (8-bit) characters.</span></span>
    
<span data-ttu-id="558bb-121">STORE_ATTACH_OK</span><span class="sxs-lookup"><span data-stu-id="558bb-121">STORE_ATTACH_OK</span></span> 
  
> <span data-ttu-id="558bb-122"> (32 0x00000020) 邮件存储支持对邮件 (OLE 或非 OLE) 附件。</span><span class="sxs-lookup"><span data-stu-id="558bb-122">(32, 0x00000020) The message store supports attachments (OLE or non-OLE) to messages.</span></span> 
    
<span data-ttu-id="558bb-123">STORE_CATEGORIZE_OK</span><span class="sxs-lookup"><span data-stu-id="558bb-123">STORE_CATEGORIZE_OK</span></span> 
  
> <span data-ttu-id="558bb-124"> (1024 中，0x00000400) 邮件存储支持表的分类视图。</span><span class="sxs-lookup"><span data-stu-id="558bb-124">(1024, 0x00000400) The message store supports categorized views of tables.</span></span> 
    
<span data-ttu-id="558bb-125">STORE_CREATE_OK</span><span class="sxs-lookup"><span data-stu-id="558bb-125">STORE_CREATE_OK</span></span> 
  
> <span data-ttu-id="558bb-126"> (16 0x00000010) 邮件存储支持新建邮件。</span><span class="sxs-lookup"><span data-stu-id="558bb-126">(16, 0x00000010) The message store supports creation of new messages.</span></span> 
    
<span data-ttu-id="558bb-127">STORE_ENTRYID_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="558bb-127">STORE_ENTRYID_UNIQUE</span></span> 
  
> <span data-ttu-id="558bb-128"> (1 0x00000001) ，邮件存储中对象的条目标识符是唯一的，即从不在存储生命周期中重复使用。</span><span class="sxs-lookup"><span data-stu-id="558bb-128">(1, 0x00000001) Entry identifiers for the objects in the message store are unique, that is, never reused during the life of the store.</span></span> 
    
<span data-ttu-id="558bb-129">STORE_HTML_OK</span><span class="sxs-lookup"><span data-stu-id="558bb-129">STORE_HTML_OK</span></span> 
  
> <span data-ttu-id="558bb-130"> (65536 中，0x00010000) 邮件存储支持 HTML 邮件，存储在 PR_BODY_HTML ( [PidTagBodyHtml](pidtagbodyhtml-canonical-property.md)) 属性中。</span><span class="sxs-lookup"><span data-stu-id="558bb-130">(65536, 0x00010000) The message store supports HTML messages, stored in the **PR_BODY_HTML** ([PidTagBodyHtml](pidtagbodyhtml-canonical-property.md)) property.</span></span> <span data-ttu-id="558bb-131">如果你的开发环境使用 MAPIDEFS。不包含值的 H STORE_HTML_OK，请改为使用 0x00010000 值。</span><span class="sxs-lookup"><span data-stu-id="558bb-131">If your development environment uses a MAPIDEFS.H file that does not include STORE_HTML_OK, use the value 0x00010000 instead.</span></span> 
    
<span data-ttu-id="558bb-132">STORE_ITEMPROC</span><span class="sxs-lookup"><span data-stu-id="558bb-132">STORE_ITEMPROC</span></span>
  
> <span data-ttu-id="558bb-133"> (2097152 0x00200000) 包装的 PST 存储中，指示当新邮件到达存储区时，该存储将单独对邮件执行规则和垃圾邮件筛选器处理。</span><span class="sxs-lookup"><span data-stu-id="558bb-133">(2097152, 0x00200000) In a wrapped PST store, indicates that when a new message arrives at the store, the store performs rules and spam filter processing on the message separately.</span></span> <span data-ttu-id="558bb-134">存储调用 [IMAPISupport：：Notify](imapisupport-notify.md)，在作为参数传递的 [NOTIFICATION](notification.md)结构中设置 **fnevNewMail，** 然后将新消息的详细信息传递给侦听客户端。</span><span class="sxs-lookup"><span data-stu-id="558bb-134">The store calls [IMAPISupport::Notify](imapisupport-notify.md), setting **fnevNewMail** in the [NOTIFICATION](notification.md) structure that is passed as a parameter, and then passes the details of the new message to the listening client.</span></span> <span data-ttu-id="558bb-135">随后，当侦听客户端收到通知，它不会处理邮件上的规则。</span><span class="sxs-lookup"><span data-stu-id="558bb-135">Subsequently, when the listening client receives the notification, it does not process rules on the message.</span></span> 
    
<span data-ttu-id="558bb-136">STORE_LOCALSTORE</span><span class="sxs-lookup"><span data-stu-id="558bb-136">STORE_LOCALSTORE</span></span>
  
> <span data-ttu-id="558bb-137"> (524288，0x00080000) 保留此标志，不应使用。</span><span class="sxs-lookup"><span data-stu-id="558bb-137">(524288, 0x00080000) This flag is reserved and should not be used.</span></span>
    
<span data-ttu-id="558bb-138">STORE_MODIFY_OK</span><span class="sxs-lookup"><span data-stu-id="558bb-138">STORE_MODIFY_OK</span></span> 
  
> <span data-ttu-id="558bb-139"> (8，0x00000008) 邮件存储支持修改其现有邮件。</span><span class="sxs-lookup"><span data-stu-id="558bb-139">(8, 0x00000008) The message store supports modification of its existing messages.</span></span> 
    
<span data-ttu-id="558bb-140">STORE_MV_PROPS_OK</span><span class="sxs-lookup"><span data-stu-id="558bb-140">STORE_MV_PROPS_OK</span></span> 
  
> <span data-ttu-id="558bb-141"> (512， 0x00000200) 邮件存储支持多值属性，在整个保存操作中保证多值属性中值顺序的稳定性，并支持表中的多值属性实例化。</span><span class="sxs-lookup"><span data-stu-id="558bb-141">(512, 0x00000200) The message store supports multivalued properties, guarantees the stability of value order in a multivalued property throughout a save operation, and supports instantiation of multivalued properties in tables.</span></span> 
    
<span data-ttu-id="558bb-142">STORE_NOTIFY_OK</span><span class="sxs-lookup"><span data-stu-id="558bb-142">STORE_NOTIFY_OK</span></span> 
  
> <span data-ttu-id="558bb-143"> (256，0x00000100) 邮件存储支持通知。</span><span class="sxs-lookup"><span data-stu-id="558bb-143">(256, 0x00000100) The message store supports notifications.</span></span> 
    
<span data-ttu-id="558bb-144">STORE_OLE_OK</span><span class="sxs-lookup"><span data-stu-id="558bb-144">STORE_OLE_OK</span></span> 
  
> <span data-ttu-id="558bb-145"> (64，0x00000040) 邮件存储支持 OLE 附件。</span><span class="sxs-lookup"><span data-stu-id="558bb-145">(64, 0x00000040) The message store supports OLE attachments.</span></span> <span data-ttu-id="558bb-146">OLE 数据可通过 **IStorage** 接口访问，例如可通过 **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 访问。</span><span class="sxs-lookup"><span data-stu-id="558bb-146">The OLE data can be accessed through an **IStorage** interface, such as that available through the **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) property.</span></span> 
    
<span data-ttu-id="558bb-147">STORE_PUBLIC_FOLDERS</span><span class="sxs-lookup"><span data-stu-id="558bb-147">STORE_PUBLIC_FOLDERS</span></span> 
  
> <span data-ttu-id="558bb-148"> (16384 中，0x00004000) 此存储中的文件夹是公共 (多用户) ，而不是私有 (可能是多实例，但不是多用户) 。</span><span class="sxs-lookup"><span data-stu-id="558bb-148">(16384, 0x00004000) The folders in this store are public (multi-user), not private (possibly multi-instance but not multi-user).</span></span> 
    
<span data-ttu-id="558bb-149">STORE_PUSHER_OK</span><span class="sxs-lookup"><span data-stu-id="558bb-149">STORE_PUSHER_OK</span></span>
  
> <span data-ttu-id="558bb-150"> (8388608 中，0x00800000) MAPI 协议处理程序将不会对存储进行爬网，存储负责通过通知将任何更改推送到索引器，以对邮件编制索引。</span><span class="sxs-lookup"><span data-stu-id="558bb-150">(8388608, 0x00800000) The MAPI Protocol Handler will not crawl the store, and the store is responsible for pushing any changes through notifications to the indexer to have messages indexed.</span></span>
    
<span data-ttu-id="558bb-151">STORE_READONLY</span><span class="sxs-lookup"><span data-stu-id="558bb-151">STORE_READONLY</span></span> 
  
> <span data-ttu-id="558bb-152"> (2 0x00000002) ，邮件存储的所有接口具有只读访问级别。</span><span class="sxs-lookup"><span data-stu-id="558bb-152">(2, 0x00000002) All interfaces for the message store have a read-only access level.</span></span> 
    
<span data-ttu-id="558bb-153">STORE_RESTRICTION_OK</span><span class="sxs-lookup"><span data-stu-id="558bb-153">STORE_RESTRICTION_OK</span></span> 
  
> <span data-ttu-id="558bb-154"> (4096，0x00001000) 邮件存储支持限制。</span><span class="sxs-lookup"><span data-stu-id="558bb-154">(4096, 0x00001000) The message store supports restrictions.</span></span> 
    
<span data-ttu-id="558bb-155">STORE_RTF_OK</span><span class="sxs-lookup"><span data-stu-id="558bb-155">STORE_RTF_OK</span></span> 
  
> <span data-ttu-id="558bb-156"> (2048 0x00000800) 邮件存储支持 RTF 格式 (RTF) 邮件（通常已压缩）并且存储本身保持 PR_BODY 和 PR_RTF_COMPRESSED **同步。**</span><span class="sxs-lookup"><span data-stu-id="558bb-156">(2048, 0x00000800) The message store supports Rich Text Format (RTF) messages, usually compressed, and the store itself keeps **PR_BODY** and **PR_RTF_COMPRESSED** synchronized.</span></span> 
    
<span data-ttu-id="558bb-157">STORE_RULES_OK</span><span class="sxs-lookup"><span data-stu-id="558bb-157">STORE_RULES_OK</span></span>
  
> <span data-ttu-id="558bb-158"> (268435456，0x10000000) 指示即使规则不是默认存储，也应存储在此 PST 存储中。</span><span class="sxs-lookup"><span data-stu-id="558bb-158">(268435456, 0x10000000) Indicates that rules should be stored in this PST store even if it is not the default store.</span></span> <span data-ttu-id="558bb-159">当 **STORE_RULES_OK** PST 包装存储区 **NON_EMS_XP_SAVE时，** 规则可以在非默认 PST 包装存储区中运行。</span><span class="sxs-lookup"><span data-stu-id="558bb-159">When **STORE_RULES_OK** is used in conjunction with **NON_EMS_XP_SAVE**, rules are able to run on non-default PST wrapped stores.</span></span>
    
<span data-ttu-id="558bb-160">STORE_SEARCH_OK</span><span class="sxs-lookup"><span data-stu-id="558bb-160">STORE_SEARCH_OK</span></span> 
  
> <span data-ttu-id="558bb-161"> (4，0x00000004) 邮件存储支持搜索结果文件夹。</span><span class="sxs-lookup"><span data-stu-id="558bb-161">(4, 0x00000004) The message store supports search-results folders.</span></span> 
    
<span data-ttu-id="558bb-162">STORE_SORT_OK</span><span class="sxs-lookup"><span data-stu-id="558bb-162">STORE_SORT_OK</span></span> 
  
> <span data-ttu-id="558bb-163"> (8192，0x00002000) 邮件存储支持表的排序视图。</span><span class="sxs-lookup"><span data-stu-id="558bb-163">(8192, 0x00002000) The message store supports sorting views of tables.</span></span> 
    
<span data-ttu-id="558bb-164">STORE_SUBMIT_OK</span><span class="sxs-lookup"><span data-stu-id="558bb-164">STORE_SUBMIT_OK</span></span> 
  
> <span data-ttu-id="558bb-165"> (128 0x00000080) 邮件存储支持将邮件标记为提交。</span><span class="sxs-lookup"><span data-stu-id="558bb-165">(128, 0x00000080) The message store supports marking a message for submission.</span></span> 
    
<span data-ttu-id="558bb-166">STORE_UNCOMPRESSED_RTF</span><span class="sxs-lookup"><span data-stu-id="558bb-166">STORE_UNCOMPRESSED_RTF</span></span> 
  
> <span data-ttu-id="558bb-167"> (32768 中，0x00008000) 邮件存储支持以未压缩的形式存储 RTF 邮件。</span><span class="sxs-lookup"><span data-stu-id="558bb-167">(32768, 0x00008000) The message store supports storage of RTF messages in uncompressed form.</span></span> <span data-ttu-id="558bb-168">未压缩的 RTF 流由流标头中的 **值 dwMagicUncompressedRTF** 标识。</span><span class="sxs-lookup"><span data-stu-id="558bb-168">An uncompressed RTF stream is identified by the value **dwMagicUncompressedRTF** in the stream header.</span></span> <span data-ttu-id="558bb-169">**dwMagicUncompressedRTF** 值在 RTFLIB 中定义。H 文件。</span><span class="sxs-lookup"><span data-stu-id="558bb-169">The **dwMagicUncompressedRTF** value is defined in the RTFLIB.H file.</span></span> 
    
<span data-ttu-id="558bb-170">STORE_UNICODE_OK</span><span class="sxs-lookup"><span data-stu-id="558bb-170">STORE_UNICODE_OK</span></span>
  
> <span data-ttu-id="558bb-171"> (262144 中，0x00040000) 指示邮件存储支持 Unicode 存储。</span><span class="sxs-lookup"><span data-stu-id="558bb-171">(262144, 0x00040000) Indicates that the message store supports Unicode storage.</span></span> <span data-ttu-id="558bb-172">客户端可以查找标记以决定是否请求或将 Unicode 信息保存到存储区。</span><span class="sxs-lookup"><span data-stu-id="558bb-172">A client can look for the presence of the flag to decide whether to request or to save Unicode information to the store.</span></span> 
    
<span data-ttu-id="558bb-173">始终可以存储邮件的 RTF 版本，即使邮件存储无法识别 RTF。</span><span class="sxs-lookup"><span data-stu-id="558bb-173">An RTF version of a message can always be stored, even if the message store is non-RTF-aware.</span></span> <span data-ttu-id="558bb-174">如果未为STORE_RTF_OK存储设置该位，则维护 RTF 版本的客户端必须自己调用 [RTFSync](rtfsync.md)函数，以保持文本内容的 PR_BODY 和 **PR_RTF_COMPRESSED** 版本的同步。 </span><span class="sxs-lookup"><span data-stu-id="558bb-174">If the STORE_RTF_OK bit is not set for a particular store, a client maintaining RTF versions must itself call the [RTFSync](rtfsync.md) function to keep the **PR_BODY** and **PR_RTF_COMPRESSED** versions synchronized for text content.</span></span> <span data-ttu-id="558bb-175">RTF 始终存储在PR_RTF_COMPRESSED，不管它是否实际压缩。</span><span class="sxs-lookup"><span data-stu-id="558bb-175">RTF is always stored in **PR_RTF_COMPRESSED**, whether it is actually compressed or not.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="558bb-176">相关资源</span><span class="sxs-lookup"><span data-stu-id="558bb-176">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="558bb-177">协议规范</span><span class="sxs-lookup"><span data-stu-id="558bb-177">Protocol specifications</span></span>

<span data-ttu-id="558bb-178">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="558bb-178">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="558bb-179">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="558bb-179">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="558bb-180">[[MS-OXMSG]](https://msdn.microsoft.com/library/b046868c-9fbf-41ae-9ffb-8de2bd4eec82%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="558bb-180">[[MS-OXMSG]](https://msdn.microsoft.com/library/b046868c-9fbf-41ae-9ffb-8de2bd4eec82%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="558bb-181">描述用于发送与客户端上的共享文件夹有关的信息的邮件的格式。</span><span class="sxs-lookup"><span data-stu-id="558bb-181">Describes the format of messages used to send information related to sharing folders on the client.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="558bb-182">头文件</span><span class="sxs-lookup"><span data-stu-id="558bb-182">Header files</span></span>

<span data-ttu-id="558bb-183">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="558bb-183">Mapidefs.h</span></span>
  
> <span data-ttu-id="558bb-184">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="558bb-184">Provides data type definitions.</span></span>
    
<span data-ttu-id="558bb-185">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="558bb-185">Mapitags.h</span></span>
  
> <span data-ttu-id="558bb-186">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="558bb-186">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="558bb-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="558bb-187">See also</span></span>



[<span data-ttu-id="558bb-188">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="558bb-188">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="558bb-189">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="558bb-189">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="558bb-190">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="558bb-190">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="558bb-191">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="558bb-191">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

