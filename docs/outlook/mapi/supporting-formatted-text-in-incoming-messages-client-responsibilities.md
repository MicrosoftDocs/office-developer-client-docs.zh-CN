---
title: 支持传入邮件客户端责任中的格式化文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 79727700-5ef1-4a29-9ed0-fd46c7de3202
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7f3cf5b245bdcd2c2707f0e2028d52a15c7e0f6b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434499"
---
# <a name="supporting-formatted-text-in-incoming-messages-client-responsibilities"></a><span data-ttu-id="9ff83-103">支持传入邮件中的格式化文本：客户端责任</span><span class="sxs-lookup"><span data-stu-id="9ff83-103">Supporting Formatted Text in Incoming Messages: Client Responsibilities</span></span>

  
  
<span data-ttu-id="9ff83-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9ff83-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9ff83-105">在邮件系统之间传输邮件时，MAPI 后台处理程序确保格式文本格式与邮件文本保持同步。</span><span class="sxs-lookup"><span data-stu-id="9ff83-105">As messages are transferred between messaging systems, the MAPI spooler makes sure that the rich text formatting remains synchronized with the message text.</span></span> <span data-ttu-id="9ff83-106">MAPI 后台处理程序从传递给传输提供程序的邮件的封装版本中调用 [RTFSync](rtfsync.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="9ff83-106">The MAPI spooler calls the [RTFSync](rtfsync.md) function from within a wrapped version of the message that it passes to the transport provider.</span></span> <span data-ttu-id="9ff83-107">传输提供程序通过调用 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法保存对邮件所做的更改，然后将它路由到新收件人。</span><span class="sxs-lookup"><span data-stu-id="9ff83-107">The transport provider saves the changes made to the message by calling the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method and then routes it to the new recipient.</span></span> 
  
<span data-ttu-id="9ff83-108">当收件人的 RTF 感知客户端应用程序打开邮件以显示文本时，它必须将文本与格式同步，并打开 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 或 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) ，具体取决于可用的属性。</span><span class="sxs-lookup"><span data-stu-id="9ff83-108">When the recipient's RTF-aware client application opens the message to display the text, it must synchronize the text with the formatting and open either **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) or **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), depending on which property is available.</span></span>
  
 <span data-ttu-id="9ff83-109">**若要打开消息，请识别 RTF 的客户端**</span><span class="sxs-lookup"><span data-stu-id="9ff83-109">**To open a message, RTF-aware clients**</span></span>
  
1. <span data-ttu-id="9ff83-110">如果邮件存储无法识别 RTF，则调用 **RTFSync** 将邮件文本与格式同步。</span><span class="sxs-lookup"><span data-stu-id="9ff83-110">Call **RTFSync** to synchronize the message text with the formatting if the message store is not RTF-aware.</span></span> <span data-ttu-id="9ff83-111">如果 PR_RTF_IN_SYNC ([PidTagRtfIn) Sync](pidtagrtfinsync-canonical-property.md)属性缺失或设置为 FALSE，则 RTF_SYNC_BODY_CHANGED 标记应在 _ulFlags_ 参数中传递。</span><span class="sxs-lookup"><span data-stu-id="9ff83-111">The RTF_SYNC_BODY_CHANGED flag should be passed in the  _ulFlags_ parameter if the **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) property is missing or set to FALSE.</span></span> <span data-ttu-id="9ff83-112">使用 RTF 感知邮件存储的客户端不需要进行 **RTFSync** 调用，因为邮件存储会处理它。</span><span class="sxs-lookup"><span data-stu-id="9ff83-112">Clients working with RTF-aware message stores need not make the **RTFSync** call because the message store takes care of it.</span></span> 
    
2. <span data-ttu-id="9ff83-113">如果消息文本已更新，则调用[IMAPIProp：：SaveChanges。](imapiprop-savechanges.md)</span><span class="sxs-lookup"><span data-stu-id="9ff83-113">Call [IMAPIProp::SaveChanges](imapiprop-savechanges.md) if the message text has been updated.</span></span> 
    
3. <span data-ttu-id="9ff83-114">调用 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 以打开 **PR_RTF_COMPRESSED** 属性。</span><span class="sxs-lookup"><span data-stu-id="9ff83-114">Call [IMAPIProp::OpenProperty](imapiprop-openproperty.md) to open the **PR_RTF_COMPRESSED** property.</span></span> <span data-ttu-id="9ff83-115">如果 **PR_RTF_COMPRESSED** 不可用，应打开 **PR_BODY** 属性以显示邮件内容。</span><span class="sxs-lookup"><span data-stu-id="9ff83-115">If **PR_RTF_COMPRESSED** is not available, you should open the **PR_BODY** property instead to display the message content.</span></span> 
    
4. <span data-ttu-id="9ff83-116">调用 [WrapCompressedRTFStream](wrapcompressedrtfstream.md) 函数以创建压缩 RTF 数据的未压缩版本（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="9ff83-116">Call the [WrapCompressedRTFStream](wrapcompressedrtfstream.md) function to create an uncompressed version of the compressed RTF data, if available.</span></span> 
    
5. <span data-ttu-id="9ff83-117">向用户显示未压缩的 RTF 数据或纯文本数据。</span><span class="sxs-lookup"><span data-stu-id="9ff83-117">Display the uncompressed RTF data or the plain text data to the user.</span></span>
    
 <span data-ttu-id="9ff83-118">**RTFSync** 返回一个布尔 值，该值指示消息是否已更新。</span><span class="sxs-lookup"><span data-stu-id="9ff83-118">**RTFSync** returns a Boolean value that indicates whether or not the message has been updated.</span></span> <span data-ttu-id="9ff83-119">如果此值返回 TRUE，则 **有时调用 SaveChanges** 以永久更新。</span><span class="sxs-lookup"><span data-stu-id="9ff83-119">If this value returns TRUE, call **SaveChanges** at some point to make the update permanent.</span></span> <span data-ttu-id="9ff83-120">在 **RTFSync** 返回后，无需立即进行调用。</span><span class="sxs-lookup"><span data-stu-id="9ff83-120">The call does not have to be made immediately after **RTFSync** returns.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9ff83-121">由于许多组件在接收格式化文本之前会处理该文本，因此存在损坏的可能性。</span><span class="sxs-lookup"><span data-stu-id="9ff83-121">Because so many components handle the formatted text before you receive it, there is the possibility of corruption.</span></span> <span data-ttu-id="9ff83-122">此损坏可能来自邮件存储提供程序、第三方应用程序、网关或传输错误。</span><span class="sxs-lookup"><span data-stu-id="9ff83-122">This corruption could come from the message store provider, a third party application, a gateway, or a transmission error.</span></span> 
  

