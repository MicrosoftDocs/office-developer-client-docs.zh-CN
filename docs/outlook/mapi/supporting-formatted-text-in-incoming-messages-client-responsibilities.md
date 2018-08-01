---
title: 支持带格式的传入邮件客户端职责中的文本
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 79727700-5ef1-4a29-9ed0-fd46c7de3202
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 863c95856f3198c74bb9d72881154676386f6a9f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19778915"
---
# <a name="supporting-formatted-text-in-incoming-messages-client-responsibilities"></a><span data-ttu-id="eb784-103">支持传入邮件中的格式化文本：客户端责任</span><span class="sxs-lookup"><span data-stu-id="eb784-103">Supporting Formatted Text in Incoming Messages: Client Responsibilities</span></span>

  
  
<span data-ttu-id="eb784-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="eb784-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="eb784-105">邮件系统之间传输邮件，如 MAPI 后台处理程序可确保的富文本格式保持同步的消息文本。</span><span class="sxs-lookup"><span data-stu-id="eb784-105">As messages are transferred between messaging systems, the MAPI spooler makes sure that the rich text formatting remains synchronized with the message text.</span></span> <span data-ttu-id="eb784-106">MAPI 后台处理程序调用[RTFSync](rtfsync.md)函数从中将其传递到传输提供程序的消息的换行版本。</span><span class="sxs-lookup"><span data-stu-id="eb784-106">The MAPI spooler calls the [RTFSync](rtfsync.md) function from within a wrapped version of the message that it passes to the transport provider.</span></span> <span data-ttu-id="eb784-107">传输提供程序保存到邮件通过调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法所做的更改，然后将其路由至新的收件人。</span><span class="sxs-lookup"><span data-stu-id="eb784-107">The transport provider saves the changes made to the message by calling the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method and then routes it to the new recipient.</span></span> 
  
<span data-ttu-id="eb784-108">当收件人的 RTF 感知客户端应用程序打开显示文本的消息时，它必须同步带格式文本，并打开**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 或**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md))具体取决于该属性是否可用。</span><span class="sxs-lookup"><span data-stu-id="eb784-108">When the recipient's RTF-aware client application opens the message to display the text, it must synchronize the text with the formatting and open either **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) or **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), depending on which property is available.</span></span>
  
 <span data-ttu-id="eb784-109">**打开一条消息，RTF 感知客户端**</span><span class="sxs-lookup"><span data-stu-id="eb784-109">**To open a message, RTF-aware clients**</span></span>
  
1. <span data-ttu-id="eb784-110">调用**RTFSync**用的格式，如果消息存储不是 RTF 感知同步消息文本。</span><span class="sxs-lookup"><span data-stu-id="eb784-110">Call **RTFSync** to synchronize the message text with the formatting if the message store is not RTF-aware.</span></span> <span data-ttu-id="eb784-111">应在_ulFlags_参数中传递 RTF_SYNC_BODY_CHANGED 标志，如果**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 属性缺失或设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="eb784-111">The RTF_SYNC_BODY_CHANGED flag should be passed in the  _ulFlags_ parameter if the **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) property is missing or set to FALSE.</span></span> <span data-ttu-id="eb784-112">使用 RTF 感知消息存储的客户端不需要做**RTFSync**呼叫，因为它的负责消息存储库。</span><span class="sxs-lookup"><span data-stu-id="eb784-112">Clients working with RTF-aware message stores need not make the **RTFSync** call because the message store takes care of it.</span></span> 
    
2. <span data-ttu-id="eb784-113">如果已更新的消息文本，请调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md) 。</span><span class="sxs-lookup"><span data-stu-id="eb784-113">Call [IMAPIProp::SaveChanges](imapiprop-savechanges.md) if the message text has been updated.</span></span> 
    
3. <span data-ttu-id="eb784-114">调用[IMAPIProp::OpenProperty](imapiprop-openproperty.md)打开**PR_RTF_COMPRESSED**属性。</span><span class="sxs-lookup"><span data-stu-id="eb784-114">Call [IMAPIProp::OpenProperty](imapiprop-openproperty.md) to open the **PR_RTF_COMPRESSED** property.</span></span> <span data-ttu-id="eb784-115">如果**PR_RTF_COMPRESSED**不可用，则应打开**PR_BODY**属性改为要显示的消息内容。</span><span class="sxs-lookup"><span data-stu-id="eb784-115">If **PR_RTF_COMPRESSED** is not available, you should open the **PR_BODY** property instead to display the message content.</span></span> 
    
4. <span data-ttu-id="eb784-116">如果可用，请调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md)函数创建的压缩文件的 RTF 数据，未压缩的版本。</span><span class="sxs-lookup"><span data-stu-id="eb784-116">Call the [WrapCompressedRTFStream](wrapcompressedrtfstream.md) function to create an uncompressed version of the compressed RTF data, if available.</span></span> 
    
5. <span data-ttu-id="eb784-117">向用户显示的未压缩的 RTF 数据或纯文本数据。</span><span class="sxs-lookup"><span data-stu-id="eb784-117">Display the uncompressed RTF data or the plain text data to the user.</span></span>
    
 <span data-ttu-id="eb784-118">**RTFSync**返回一个布尔值，指示已更新消息。</span><span class="sxs-lookup"><span data-stu-id="eb784-118">**RTFSync** returns a Boolean value that indicates whether or not the message has been updated.</span></span> <span data-ttu-id="eb784-119">如果此值，则返回 TRUE，一些时间点进行更新永久调用**SaveChanges** 。</span><span class="sxs-lookup"><span data-stu-id="eb784-119">If this value returns TRUE, call **SaveChanges** at some point to make the update permanent.</span></span> <span data-ttu-id="eb784-120">不必**RTFSync**返回后立即进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="eb784-120">The call does not have to be made immediately after **RTFSync** returns.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="eb784-121">有许多组件处理的格式化的文本之前收到，因为没有损坏的可能性。</span><span class="sxs-lookup"><span data-stu-id="eb784-121">Because so many components handle the formatted text before you receive it, there is the possibility of corruption.</span></span> <span data-ttu-id="eb784-122">此损坏可能是来自消息存储提供程序、 的第三方应用程序、 网关或传输错误。</span><span class="sxs-lookup"><span data-stu-id="eb784-122">This corruption could come from the message store provider, a third party application, a gateway, or a transmission error.</span></span> 
  

