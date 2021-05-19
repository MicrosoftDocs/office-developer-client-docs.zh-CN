---
title: 支持格式化文本网关责任
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: de737118-5f3b-464f-b036-f4a3489d411a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d5c3480018be399a85ee0bfda7ce1ff9b701cecc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419427"
---
# <a name="supporting-formatted-text-gateway-responsibilities"></a><span data-ttu-id="d6158-103">支持格式化文本：网关责任</span><span class="sxs-lookup"><span data-stu-id="d6158-103">Supporting Formatted Text: Gateway Responsibilities</span></span>

  
  
<span data-ttu-id="d6158-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d6158-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="d6158-105">**处理传出邮件的富文本格式，网关**</span><span class="sxs-lookup"><span data-stu-id="d6158-105">**To handle Rich Text Format for outgoing messages, gateways**</span></span>
  
1. <span data-ttu-id="d6158-106">从邮件存储中仅检索 **PR_RTF_COMPRESSED (** [PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d6158-106">Retrieve only a message's **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property from the message store.</span></span> <span data-ttu-id="d6158-107">仅检索 PR_RTF_COMPRESSED 属性的主要优点是，如果网关和邮件存储存在于不同的计算机上，则无需在计算机之间发送消息文本。</span><span class="sxs-lookup"><span data-stu-id="d6158-107">The main advantage in retrieving only the **PR_RTF_COMPRESSED** property is that the message text does not need to be sent between machines if the gateway and the message store exist on different machines.</span></span> 
    
2. <span data-ttu-id="d6158-108">通过调用 RTF 库函数 **HrTextFromCompressedRTFStream** 或 **RTFSync（** 如果邮件存储在本地）从格式化文本生成消息文本。</span><span class="sxs-lookup"><span data-stu-id="d6158-108">Generate the message text from the formatted text either by calling the RTF library function **HrTextFromCompressedRTFStream** or, if the message is stored locally, **RTFSync**.</span></span> <span data-ttu-id="d6158-109">应在RTF_SYNC_RTF_CHANGED **RTFSync** 中设置该标记。</span><span class="sxs-lookup"><span data-stu-id="d6158-109">The RTF_SYNC_RTF_CHANGED flag should be set in the call to **RTFSync**.</span></span> <span data-ttu-id="d6158-110">有关详细信息，请参阅 [RTFSync](rtfsync.md)。</span><span class="sxs-lookup"><span data-stu-id="d6158-110">For more information, see [RTFSync](rtfsync.md).</span></span>
    
3. <span data-ttu-id="d6158-111">对邮件文本进行任何不可恢复的修改，例如删除不受支持的字符。</span><span class="sxs-lookup"><span data-stu-id="d6158-111">Make any irreversible modifications to the message text, such as dropping unsupported characters.</span></span> 
    
4. <span data-ttu-id="d6158-112">确保[PidTagRtfInSync PR_RTF_IN_SYNC (PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 所有 RTF 辅助属性已设置或不存在。 </span><span class="sxs-lookup"><span data-stu-id="d6158-112">Ensure that both **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) and all of the RTF auxilliary properties are either set or absent.</span></span>
    
5. <span data-ttu-id="d6158-113">如果进行了任何修改，请调用同时设置了 RTF_SYNC_RTF_CHANGED 和 RTF_SYNC_BODY_CHANGED **RTFSync。**</span><span class="sxs-lookup"><span data-stu-id="d6158-113">If any modifications were made, call **RTFSync** with both the RTF_SYNC_RTF_CHANGED and RTF_SYNC_BODY_CHANGED flags set.</span></span> <span data-ttu-id="d6158-114">**RTFSync** 将重新计算修改文本中的 RTF 辅助属性。</span><span class="sxs-lookup"><span data-stu-id="d6158-114">**RTFSync** will recalculate the RTF auxilliary properties from the modified text.</span></span> 
    
6. <span data-ttu-id="d6158-115">对邮件文本进行任何可还原的修改，例如插入附件占位符和执行无损坏的代码页转换。</span><span class="sxs-lookup"><span data-stu-id="d6158-115">Make any reversable modifications to the message text, such as inserting attachment placeholders and performing nondestructive code page conversions.</span></span>
    
7. <span data-ttu-id="d6158-116">发送邮件。</span><span class="sxs-lookup"><span data-stu-id="d6158-116">Send the message.</span></span>
    
 <span data-ttu-id="d6158-117">**处理传入邮件、网关的富文本格式**</span><span class="sxs-lookup"><span data-stu-id="d6158-117">**To handle Rich Text Format for incoming messages, gateways**</span></span>
  
1. <span data-ttu-id="d6158-118">取消直接在邮件发送前所做的任何邮件文本修改。</span><span class="sxs-lookup"><span data-stu-id="d6158-118">Reverse any message text modifications that were made directly before the message was sent.</span></span> 
    
2. <span data-ttu-id="d6158-119">如果邮件包含 [PidTagBody](pidtagbody-canonical-property.md)属性中的 PR_RTF_COMPRESSED **和** PR_BODY **(，)** **RTFSync。**</span><span class="sxs-lookup"><span data-stu-id="d6158-119">Call **RTFSync** if the message contains both the **PR_RTF_COMPRESSED** and **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) properties.</span></span> 
    
3. <span data-ttu-id="d6158-120">使用 PR_RTF_COMPRESSED **属性更新** 邮件存储中的邮件;仅在缺少 **PR_BODY** **时PR_RTF_COMPRESSED更新** 。</span><span class="sxs-lookup"><span data-stu-id="d6158-120">Update the message in the message store with the **PR_RTF_COMPRESSED** property if the message contains it; update with the **PR_BODY** property only if **PR_RTF_COMPRESSED** is absent.</span></span> 
    
4. <span data-ttu-id="d6158-121">如果 **PR_BODY** 包含此属性和属性，则放弃 **PR_RTF_COMPRESSED。**</span><span class="sxs-lookup"><span data-stu-id="d6158-121">Discard **PR_BODY** if the message contains both this property and **PR_RTF_COMPRESSED**.</span></span>
    
<span data-ttu-id="d6158-122">网关调用 **RTFSync** 以避免在邮件存储位于其他计算机上时同时传输消息文本和格式化文本。</span><span class="sxs-lookup"><span data-stu-id="d6158-122">Gateways call **RTFSync** to avoid transmitting both the message text and formatted text if the message store is on a different machine.</span></span> <span data-ttu-id="d6158-123">如果网关是本地网关，它可以同时设置这两个属性并允许邮件存储执行同步。</span><span class="sxs-lookup"><span data-stu-id="d6158-123">If the gateway is local, it can set both properties and allow the message store to perform the synchronization.</span></span> 
  

