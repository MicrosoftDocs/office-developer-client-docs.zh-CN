---
title: 支持格式化的文本网关职责
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: de737118-5f3b-464f-b036-f4a3489d411a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6d2c85aa76a372ba79e55dbf5b22024288214df6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778909"
---
# <a name="supporting-formatted-text-gateway-responsibilities"></a><span data-ttu-id="b2ee6-103">支持的格式文本： 网关职责</span><span class="sxs-lookup"><span data-stu-id="b2ee6-103">Supporting Formatted Text: Gateway Responsibilities</span></span>

  
  
<span data-ttu-id="b2ee6-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b2ee6-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="b2ee6-105">**若要处理的传出邮件，网关的富文本格式**</span><span class="sxs-lookup"><span data-stu-id="b2ee6-105">**To handle Rich Text Format for outgoing messages, gateways**</span></span>
  
1. <span data-ttu-id="b2ee6-106">从邮件存储检索仅消息的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="b2ee6-106">Retrieve only a message's **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) property from the message store.</span></span> <span data-ttu-id="b2ee6-107">检索仅**PR_RTF_COMPRESSED**属性中的主要优点是消息文本不需要发送计算机之间，如果不同的计算机上存在的网关和消息存储库。</span><span class="sxs-lookup"><span data-stu-id="b2ee6-107">The main advantage in retrieving only the **PR_RTF_COMPRESSED** property is that the message text does not need to be sent between machines if the gateway and the message store exist on different machines.</span></span> 
    
2. <span data-ttu-id="b2ee6-108">可通过调用 RTF 库函数**HrTextFromCompressedRTFStream**格式化文本从生成的消息文本或，如果邮件存储在本地， **RTFSync**。</span><span class="sxs-lookup"><span data-stu-id="b2ee6-108">Generate the message text from the formatted text either by calling the RTF library function **HrTextFromCompressedRTFStream** or, if the message is stored locally, **RTFSync**.</span></span> <span data-ttu-id="b2ee6-109">应将 RTF_SYNC_RTF_CHANGED 标志设置对**RTFSync**的调用中。</span><span class="sxs-lookup"><span data-stu-id="b2ee6-109">The RTF_SYNC_RTF_CHANGED flag should be set in the call to **RTFSync**.</span></span> <span data-ttu-id="b2ee6-110">有关详细信息，请参阅[RTFSync](rtfsync.md)。</span><span class="sxs-lookup"><span data-stu-id="b2ee6-110">For more information, see [RTFSync](rtfsync.md).</span></span>
    
3. <span data-ttu-id="b2ee6-111">任何不可逆转地对进行修改的消息文本，如删除不支持的字符。</span><span class="sxs-lookup"><span data-stu-id="b2ee6-111">Make any irreversible modifications to the message text, such as dropping unsupported characters.</span></span> 
    
4. <span data-ttu-id="b2ee6-112">确保**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 和所有 RTF 辅助属性进行设置，或不存在。</span><span class="sxs-lookup"><span data-stu-id="b2ee6-112">Ensure that both **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) and all of the RTF auxilliary properties are either set or absent.</span></span>
    
5. <span data-ttu-id="b2ee6-113">如果做任何修改，调用**RTFSync**的 RTF_SYNC_RTF_CHANGED 和 RTF_SYNC_BODY_CHANGED 标志设置。</span><span class="sxs-lookup"><span data-stu-id="b2ee6-113">If any modifications were made, call **RTFSync** with both the RTF_SYNC_RTF_CHANGED and RTF_SYNC_BODY_CHANGED flags set.</span></span> <span data-ttu-id="b2ee6-114">**RTFSync**将重新计算的已修改的文本中的 RTF 辅助属性。</span><span class="sxs-lookup"><span data-stu-id="b2ee6-114">**RTFSync** will recalculate the RTF auxilliary properties from the modified text.</span></span> 
    
6. <span data-ttu-id="b2ee6-115">任何可撤销对进行修改的消息文本，如插入附件占位符和执行破坏性的代码页转换。</span><span class="sxs-lookup"><span data-stu-id="b2ee6-115">Make any reversable modifications to the message text, such as inserting attachment placeholders and performing nondestructive code page conversions.</span></span>
    
7. <span data-ttu-id="b2ee6-116">发送消息。</span><span class="sxs-lookup"><span data-stu-id="b2ee6-116">Send the message.</span></span>
    
 <span data-ttu-id="b2ee6-117">**若要处理的传入邮件，网关的富文本格式**</span><span class="sxs-lookup"><span data-stu-id="b2ee6-117">**To handle Rich Text Format for incoming messages, gateways**</span></span>
  
1. <span data-ttu-id="b2ee6-118">还原之前已发送邮件直接进行任何消息文本进行修改。</span><span class="sxs-lookup"><span data-stu-id="b2ee6-118">Reverse any message text modifications that were made directly before the message was sent.</span></span> 
    
2. <span data-ttu-id="b2ee6-119">如果邮件包含的**PR_RTF_COMPRESSED**和**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性，请调用**RTFSync** 。</span><span class="sxs-lookup"><span data-stu-id="b2ee6-119">Call **RTFSync** if the message contains both the **PR_RTF_COMPRESSED** and **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) properties.</span></span> 
    
3. <span data-ttu-id="b2ee6-120">如果邮件包含; 使用**PR_RTF_COMPRESSED**属性更新消息存储库中的消息更新**PR_BODY**属性才**PR_RTF_COMPRESSED**不存在。</span><span class="sxs-lookup"><span data-stu-id="b2ee6-120">Update the message in the message store with the **PR_RTF_COMPRESSED** property if the message contains it; update with the **PR_BODY** property only if **PR_RTF_COMPRESSED** is absent.</span></span> 
    
4. <span data-ttu-id="b2ee6-121">如果邮件包含此属性和**PR_RTF_COMPRESSED**，放弃**PR_BODY** 。</span><span class="sxs-lookup"><span data-stu-id="b2ee6-121">Discard **PR_BODY** if the message contains both this property and **PR_RTF_COMPRESSED**.</span></span>
    
<span data-ttu-id="b2ee6-122">网关呼叫**RTFSync**来避免传输的消息文本和格式化的文本，如果消息存储是不同的计算机上。</span><span class="sxs-lookup"><span data-stu-id="b2ee6-122">Gateways call **RTFSync** to avoid transmitting both the message text and formatted text if the message store is on a different machine.</span></span> <span data-ttu-id="b2ee6-123">如果本地网关，它可以设置这两个属性，并允许的邮件存储来执行同步。</span><span class="sxs-lookup"><span data-stu-id="b2ee6-123">If the gateway is local, it can set both properties and allow the message store to perform the synchronization.</span></span> 
  

