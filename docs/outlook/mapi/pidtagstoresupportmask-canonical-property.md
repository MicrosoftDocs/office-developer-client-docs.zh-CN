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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 8d9f6311b19ddb489885004a9e507f780d9f1ea9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778466"
---
# <a name="pidtagstoresupportmask-canonical-property"></a><span data-ttu-id="d2be9-103">PidTagStoreSupportMask 规范属性</span><span class="sxs-lookup"><span data-stu-id="d2be9-103">PidTagStoreSupportMask Canonical Property</span></span>

  
  
<span data-ttu-id="d2be9-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d2be9-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d2be9-105">包含的标志位掩码的客户端应用程序查询，以确定的消息存储的特征。</span><span class="sxs-lookup"><span data-stu-id="d2be9-105">Contains a bitmask of flags that client applications query to determine the characteristics of a message store.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d2be9-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="d2be9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d2be9-107">PR_STORE_SUPPORT_MASK</span><span class="sxs-lookup"><span data-stu-id="d2be9-107">PR_STORE_SUPPORT_MASK</span></span>  <br/> |
|<span data-ttu-id="d2be9-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d2be9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d2be9-109">0x340D</span><span class="sxs-lookup"><span data-stu-id="d2be9-109">0x340D</span></span>  <br/> |
|<span data-ttu-id="d2be9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d2be9-110">Data type:</span></span>  <br/> |<span data-ttu-id="d2be9-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="d2be9-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="d2be9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d2be9-112">Area:</span></span>  <br/> |<span data-ttu-id="d2be9-113">其他</span><span class="sxs-lookup"><span data-stu-id="d2be9-113">Miscellaneous</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d2be9-114">备注</span><span class="sxs-lookup"><span data-stu-id="d2be9-114">Remarks</span></span>

<span data-ttu-id="d2be9-115">此属性会泄露打算将其发送一条消息的客户端应用程序的消息存储的功能。</span><span class="sxs-lookup"><span data-stu-id="d2be9-115">This property discloses the capabilities of a message store to client applications that are planning to send it a message.</span></span> <span data-ttu-id="d2be9-116">标志可支持的客户端或另一个存储，如是否发送**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 或仅**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 的决策。</span><span class="sxs-lookup"><span data-stu-id="d2be9-116">The flags can support decisions by a client or another store, such as whether to send **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) or only **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)).</span></span> <span data-ttu-id="d2be9-117">客户端应始终不将**PR_STORE_SUPPORT_MASK**;试图设置此标志返回 MAPI_E_COMPUTED。</span><span class="sxs-lookup"><span data-stu-id="d2be9-117">A client should never set **PR_STORE_SUPPORT_MASK**; an attempt to set this flag returns MAPI_E_COMPUTED.</span></span> 
  
<span data-ttu-id="d2be9-118">可以为**PR_STORE_SUPPORT_MASK**位掩码设置一个或多个以下标志：</span><span class="sxs-lookup"><span data-stu-id="d2be9-118">One or more of the following flags can be set for the **PR_STORE_SUPPORT_MASK** bitmask:</span></span> 
  
<span data-ttu-id="d2be9-119">STORE_ANSI_OK</span><span class="sxs-lookup"><span data-stu-id="d2be9-119">STORE_ANSI_OK</span></span>
  
> <span data-ttu-id="d2be9-120">（131072、 0x00020000）消息存储库支持属性包含 ANSI （8 位） 字符。</span><span class="sxs-lookup"><span data-stu-id="d2be9-120">(131072, 0x00020000) The message store supports properties that contain ANSI (8-bit) characters.</span></span>
    
<span data-ttu-id="d2be9-121">STORE_ATTACH_OK</span><span class="sxs-lookup"><span data-stu-id="d2be9-121">STORE_ATTACH_OK</span></span> 
  
> <span data-ttu-id="d2be9-122">（32、 0x00000020）消息存储库支持邮件附件 （OLE 或非 OLE）。</span><span class="sxs-lookup"><span data-stu-id="d2be9-122">(32, 0x00000020) The message store supports attachments (OLE or non-OLE) to messages.</span></span> 
    
<span data-ttu-id="d2be9-123">STORE_CATEGORIZE_OK</span><span class="sxs-lookup"><span data-stu-id="d2be9-123">STORE_CATEGORIZE_OK</span></span> 
  
> <span data-ttu-id="d2be9-124">(1024，0x00000400)消息存储支持表的分类的的视图。</span><span class="sxs-lookup"><span data-stu-id="d2be9-124">(1024, 0x00000400) The message store supports categorized views of tables.</span></span> 
    
<span data-ttu-id="d2be9-125">STORE_CREATE_OK</span><span class="sxs-lookup"><span data-stu-id="d2be9-125">STORE_CREATE_OK</span></span> 
  
> <span data-ttu-id="d2be9-126">（16、 0x00000010）消息存储库支持创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="d2be9-126">(16, 0x00000010) The message store supports creation of new messages.</span></span> 
    
<span data-ttu-id="d2be9-127">STORE_ENTRYID_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="d2be9-127">STORE_ENTRYID_UNIQUE</span></span> 
  
> <span data-ttu-id="d2be9-128">（1，0x00000001）消息存储库中的对象的项标识符是唯一的即永远不会存储的生命周期内重用。</span><span class="sxs-lookup"><span data-stu-id="d2be9-128">(1, 0x00000001) Entry identifiers for the objects in the message store are unique, that is, never reused during the life of the store.</span></span> 
    
<span data-ttu-id="d2be9-129">STORE_HTML_OK</span><span class="sxs-lookup"><span data-stu-id="d2be9-129">STORE_HTML_OK</span></span> 
  
> <span data-ttu-id="d2be9-130">（65536、 0x00010000）消息存储库支持 HTML 邮件，存储在**PR_BODY_HTML** ([PidTagBodyHtml](pidtagbodyhtml-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d2be9-130">(65536, 0x00010000) The message store supports HTML messages, stored in the **PR_BODY_HTML** ([PidTagBodyHtml](pidtagbodyhtml-canonical-property.md)) property.</span></span> <span data-ttu-id="d2be9-131">如果您的开发环境使用 MAPIDEFS。H 文件，不包括 STORE_HTML_OK，则改用 0x00010000 的值。</span><span class="sxs-lookup"><span data-stu-id="d2be9-131">If your development environment uses a MAPIDEFS.H file that does not include STORE_HTML_OK, use the value 0x00010000 instead.</span></span> 
    
<span data-ttu-id="d2be9-132">STORE_ITEMPROC</span><span class="sxs-lookup"><span data-stu-id="d2be9-132">STORE_ITEMPROC</span></span>
  
> <span data-ttu-id="d2be9-133">（2097152、 0x00200000）换行的 PST 存储区中指示当一个新的邮件到达存储，存储执行规则和单独的处理邮件的垃圾邮件筛选器。</span><span class="sxs-lookup"><span data-stu-id="d2be9-133">(2097152, 0x00200000) In a wrapped PST store, indicates that when a new message arrives at the store, the store performs rules and spam filter processing on the message separately.</span></span> <span data-ttu-id="d2be9-134">存储呼叫[IMAPISupport::Notify](imapisupport-notify.md)，设置**fnevNewMail**作为一个参数传递，然后将新消息的详细信息传递到侦听客户端的[通知](notification.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="d2be9-134">The store calls [IMAPISupport::Notify](imapisupport-notify.md), setting **fnevNewMail** in the [NOTIFICATION](notification.md) structure that is passed as a parameter, and then passes the details of the new message to the listening client.</span></span> <span data-ttu-id="d2be9-135">随后，侦听客户端接收通知时，它不处理邮件的规则。</span><span class="sxs-lookup"><span data-stu-id="d2be9-135">Subsequently, when the listening client receives the notification, it does not process rules on the message.</span></span> 
    
<span data-ttu-id="d2be9-136">STORE_LOCALSTORE</span><span class="sxs-lookup"><span data-stu-id="d2be9-136">STORE_LOCALSTORE</span></span>
  
> <span data-ttu-id="d2be9-137">（524288、 0x00080000）此标志保留，不应使用。</span><span class="sxs-lookup"><span data-stu-id="d2be9-137">(524288, 0x00080000) This flag is reserved and should not be used.</span></span>
    
<span data-ttu-id="d2be9-138">STORE_MODIFY_OK</span><span class="sxs-lookup"><span data-stu-id="d2be9-138">STORE_MODIFY_OK</span></span> 
  
> <span data-ttu-id="d2be9-139">（8，0x00000008）消息存储库支持其现有的邮件的修改。</span><span class="sxs-lookup"><span data-stu-id="d2be9-139">(8, 0x00000008) The message store supports modification of its existing messages.</span></span> 
    
<span data-ttu-id="d2be9-140">STORE_MV_PROPS_OK</span><span class="sxs-lookup"><span data-stu-id="d2be9-140">STORE_MV_PROPS_OK</span></span> 
  
> <span data-ttu-id="d2be9-141">（512、 0x00000200）消息存储库支持多值的属性，按原样的整个保存一个多值属性的值顺序稳定性操作，并且支持实例化的表中的多值属性。</span><span class="sxs-lookup"><span data-stu-id="d2be9-141">(512, 0x00000200) The message store supports multivalued properties, guarantees the stability of value order in a multivalued property throughout a save operation, and supports instantiation of multivalued properties in tables.</span></span> 
    
<span data-ttu-id="d2be9-142">STORE_NOTIFY_OK</span><span class="sxs-lookup"><span data-stu-id="d2be9-142">STORE_NOTIFY_OK</span></span> 
  
> <span data-ttu-id="d2be9-143">（256、 0x00000100）消息存储库支持通知。</span><span class="sxs-lookup"><span data-stu-id="d2be9-143">(256, 0x00000100) The message store supports notifications.</span></span> 
    
<span data-ttu-id="d2be9-144">STORE_OLE_OK</span><span class="sxs-lookup"><span data-stu-id="d2be9-144">STORE_OLE_OK</span></span> 
  
> <span data-ttu-id="d2be9-145">（64、 0x00000040）消息存储库支持 OLE 附件。</span><span class="sxs-lookup"><span data-stu-id="d2be9-145">(64, 0x00000040) The message store supports OLE attachments.</span></span> <span data-ttu-id="d2be9-146">OLE 数据可通过**IStorage**界面，例如，可通过**PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d2be9-146">The OLE data can be accessed through an **IStorage** interface, such as that available through the **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) property.</span></span> 
    
<span data-ttu-id="d2be9-147">STORE_PUBLIC_FOLDERS</span><span class="sxs-lookup"><span data-stu-id="d2be9-147">STORE_PUBLIC_FOLDERS</span></span> 
  
> <span data-ttu-id="d2be9-148">（16384、 0x00004000）此存储区中的文件夹是公共 （多用户），不专用 (可能是多实例，但不是多的用户)。</span><span class="sxs-lookup"><span data-stu-id="d2be9-148">(16384, 0x00004000) The folders in this store are public (multi-user), not private (possibly multi-instance but not multi-user).</span></span> 
    
<span data-ttu-id="d2be9-149">STORE_PUSHER_OK</span><span class="sxs-lookup"><span data-stu-id="d2be9-149">STORE_PUSHER_OK</span></span>
  
> <span data-ttu-id="d2be9-150">（8388608、 0x00800000）MAPI 协议处理程序将不存储进行爬网，并存储负责向索引器已编制索引的邮件推送通知通过任何更改。</span><span class="sxs-lookup"><span data-stu-id="d2be9-150">(8388608, 0x00800000) The MAPI Protocol Handler will not crawl the store, and the store is responsible for pushing any changes through notifications to the indexer to have messages indexed.</span></span>
    
<span data-ttu-id="d2be9-151">STORE_READONLY</span><span class="sxs-lookup"><span data-stu-id="d2be9-151">STORE_READONLY</span></span> 
  
> <span data-ttu-id="d2be9-152">（2，0x00000002:uc）消息存储的所有接口都具有只读访问权限级别。</span><span class="sxs-lookup"><span data-stu-id="d2be9-152">(2, 0x00000002) All interfaces for the message store have a read-only access level.</span></span> 
    
<span data-ttu-id="d2be9-153">STORE_RESTRICTION_OK</span><span class="sxs-lookup"><span data-stu-id="d2be9-153">STORE_RESTRICTION_OK</span></span> 
  
> <span data-ttu-id="d2be9-154">(4096，0x00001000)消息存储支持的限制。</span><span class="sxs-lookup"><span data-stu-id="d2be9-154">(4096, 0x00001000) The message store supports restrictions.</span></span> 
    
<span data-ttu-id="d2be9-155">STORE_RTF_OK</span><span class="sxs-lookup"><span data-stu-id="d2be9-155">STORE_RTF_OK</span></span> 
  
> <span data-ttu-id="d2be9-156">(2048年 0x00000800)消息存储库支持富文本格式 (RTF) 消息，通常压缩，并存储本身保持**PR_BODY**和**PR_RTF_COMPRESSED**同步。</span><span class="sxs-lookup"><span data-stu-id="d2be9-156">(2048, 0x00000800) The message store supports Rich Text Format (RTF) messages, usually compressed, and the store itself keeps **PR_BODY** and **PR_RTF_COMPRESSED** synchronized.</span></span> 
    
<span data-ttu-id="d2be9-157">STORE_RULES_OK</span><span class="sxs-lookup"><span data-stu-id="d2be9-157">STORE_RULES_OK</span></span>
  
> <span data-ttu-id="d2be9-158">（268435456、 0x10000000）指示的规则应存储在此 PST 存储区中，即使它不是默认存储。</span><span class="sxs-lookup"><span data-stu-id="d2be9-158">(268435456, 0x10000000) Indicates that rules should be stored in this PST store even if it is not the default store.</span></span> <span data-ttu-id="d2be9-159">与**NON_EMS_XP_SAVE**结合使用时**STORE_RULES_OK** ，都能够在非默认 PST 自动换行存储上运行规则。</span><span class="sxs-lookup"><span data-stu-id="d2be9-159">When **STORE_RULES_OK** is used in conjunction with **NON_EMS_XP_SAVE**, rules are able to run on non-default PST wrapped stores.</span></span>
    
<span data-ttu-id="d2be9-160">STORE_SEARCH_OK</span><span class="sxs-lookup"><span data-stu-id="d2be9-160">STORE_SEARCH_OK</span></span> 
  
> <span data-ttu-id="d2be9-161">（4，0x00000004）消息存储库支持搜索结果文件夹。</span><span class="sxs-lookup"><span data-stu-id="d2be9-161">(4, 0x00000004) The message store supports search-results folders.</span></span> 
    
<span data-ttu-id="d2be9-162">STORE_SORT_OK</span><span class="sxs-lookup"><span data-stu-id="d2be9-162">STORE_SORT_OK</span></span> 
  
> <span data-ttu-id="d2be9-163">(8192，0x00002000)消息存储支持表的排序的视图。</span><span class="sxs-lookup"><span data-stu-id="d2be9-163">(8192, 0x00002000) The message store supports sorting views of tables.</span></span> 
    
<span data-ttu-id="d2be9-164">STORE_SUBMIT_OK</span><span class="sxs-lookup"><span data-stu-id="d2be9-164">STORE_SUBMIT_OK</span></span> 
  
> <span data-ttu-id="d2be9-165">（128、 0x00000080）消息存储库支持标记提交的邮件。</span><span class="sxs-lookup"><span data-stu-id="d2be9-165">(128, 0x00000080) The message store supports marking a message for submission.</span></span> 
    
<span data-ttu-id="d2be9-166">STORE_UNCOMPRESSED_RTF</span><span class="sxs-lookup"><span data-stu-id="d2be9-166">STORE_UNCOMPRESSED_RTF</span></span> 
  
> <span data-ttu-id="d2be9-167">（32768、 0x00008000）消息存储在未压缩的窗体中支持 RTF 邮件存储。</span><span class="sxs-lookup"><span data-stu-id="d2be9-167">(32768, 0x00008000) The message store supports storage of RTF messages in uncompressed form.</span></span> <span data-ttu-id="d2be9-168">由值**dwMagicUncompressedRTF**流标头中标识未压缩的 RTF 流。</span><span class="sxs-lookup"><span data-stu-id="d2be9-168">An uncompressed RTF stream is identified by the value **dwMagicUncompressedRTF** in the stream header.</span></span> <span data-ttu-id="d2be9-169">RTFLIB 中定义的**dwMagicUncompressedRTF**值。H 文件。</span><span class="sxs-lookup"><span data-stu-id="d2be9-169">The **dwMagicUncompressedRTF** value is defined in the RTFLIB.H file.</span></span> 
    
<span data-ttu-id="d2be9-170">STORE_UNICODE_OK</span><span class="sxs-lookup"><span data-stu-id="d2be9-170">STORE_UNICODE_OK</span></span>
  
> <span data-ttu-id="d2be9-171">（262144、 0x00040000）指示消息存储库支持 Unicode 存储。</span><span class="sxs-lookup"><span data-stu-id="d2be9-171">(262144, 0x00040000) Indicates that the message store supports Unicode storage.</span></span> <span data-ttu-id="d2be9-172">客户端可以查看此标志以确定是请求还是将 Unicode 信息保存到存储的状态。</span><span class="sxs-lookup"><span data-stu-id="d2be9-172">A client can look for the presence of the flag to decide whether to request or to save Unicode information to the store.</span></span> 
    
<span data-ttu-id="d2be9-173">总是可以存储一条消息的 RTF 版本，即使不识别 RTF 的消息存储库。</span><span class="sxs-lookup"><span data-stu-id="d2be9-173">An RTF version of a message can always be stored, even if the message store is non-RTF-aware.</span></span> <span data-ttu-id="d2be9-174">如果特定存储未设置 STORE_RTF_OK 位，维护 RTF 版本的客户端必须本身调用[RTFSync](rtfsync.md)函数保留为文本内容同步的**PR_BODY**和**PR_RTF_COMPRESSED**版本。</span><span class="sxs-lookup"><span data-stu-id="d2be9-174">If the STORE_RTF_OK bit is not set for a particular store, a client maintaining RTF versions must itself call the [RTFSync](rtfsync.md) function to keep the **PR_BODY** and **PR_RTF_COMPRESSED** versions synchronized for text content.</span></span> <span data-ttu-id="d2be9-175">RTF 始终存储在**PR_RTF_COMPRESSED**，是否或不实际压缩。</span><span class="sxs-lookup"><span data-stu-id="d2be9-175">RTF is always stored in **PR_RTF_COMPRESSED**, whether it is actually compressed or not.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="d2be9-176">相关资源</span><span class="sxs-lookup"><span data-stu-id="d2be9-176">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d2be9-177">协议规范</span><span class="sxs-lookup"><span data-stu-id="d2be9-177">Protocol specifications</span></span>

<span data-ttu-id="d2be9-178">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d2be9-178">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d2be9-179">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="d2be9-179">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d2be9-180">[[MS OXMSG]](http://msdn.microsoft.com/library/b046868c-9fbf-41ae-9ffb-8de2bd4eec82%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d2be9-180">[[MS-OXMSG]](http://msdn.microsoft.com/library/b046868c-9fbf-41ae-9ffb-8de2bd4eec82%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d2be9-181">介绍用于发送到客户端上共享文件夹相关的信息的消息的格式。</span><span class="sxs-lookup"><span data-stu-id="d2be9-181">Describes the format of messages used to send information related to sharing folders on the client.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d2be9-182">头文件</span><span class="sxs-lookup"><span data-stu-id="d2be9-182">Header files</span></span>

<span data-ttu-id="d2be9-183">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d2be9-183">Mapidefs.h</span></span>
  
> <span data-ttu-id="d2be9-184">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d2be9-184">Provides data type definitions.</span></span>
    
<span data-ttu-id="d2be9-185">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d2be9-185">Mapitags.h</span></span>
  
> <span data-ttu-id="d2be9-186">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d2be9-186">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d2be9-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2be9-187">See also</span></span>



[<span data-ttu-id="d2be9-188">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d2be9-188">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d2be9-189">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d2be9-189">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d2be9-190">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d2be9-190">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d2be9-191">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d2be9-191">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

