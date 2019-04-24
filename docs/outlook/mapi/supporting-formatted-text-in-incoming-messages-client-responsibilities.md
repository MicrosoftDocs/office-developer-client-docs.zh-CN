---
title: 在传入邮件中支持格式化文本客户端责任
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 79727700-5ef1-4a29-9ed0-fd46c7de3202
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7f3cf5b245bdcd2c2707f0e2028d52a15c7e0f6b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327410"
---
# <a name="supporting-formatted-text-in-incoming-messages-client-responsibilities"></a><span data-ttu-id="2dea6-103">在传入邮件中支持格式化文本: 客户端责任</span><span class="sxs-lookup"><span data-stu-id="2dea6-103">Supporting Formatted Text in Incoming Messages: Client Responsibilities</span></span>

  
  
<span data-ttu-id="2dea6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2dea6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2dea6-105">当邮件在邮件系统之间传输时, MAPI 后台处理程序会确保 rtf 格式设置与邮件文本保持同步。</span><span class="sxs-lookup"><span data-stu-id="2dea6-105">As messages are transferred between messaging systems, the MAPI spooler makes sure that the rich text formatting remains synchronized with the message text.</span></span> <span data-ttu-id="2dea6-106">MAPI 后台处理程序从传递给传输提供程序的邮件的已包装版本中调用[RTFSync](rtfsync.md)函数。</span><span class="sxs-lookup"><span data-stu-id="2dea6-106">The MAPI spooler calls the [RTFSync](rtfsync.md) function from within a wrapped version of the message that it passes to the transport provider.</span></span> <span data-ttu-id="2dea6-107">传输提供程序通过调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法来保存对邮件所做的更改, 然后将其路由到新的收件人。</span><span class="sxs-lookup"><span data-stu-id="2dea6-107">The transport provider saves the changes made to the message by calling the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method and then routes it to the new recipient.</span></span> 
  
<span data-ttu-id="2dea6-108">当收件人的 RTF 感知客户端应用程序打开邮件以显示文本时, 它必须将文本与格式设置同步并打开**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 或**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), 具体取决于可用的属性。</span><span class="sxs-lookup"><span data-stu-id="2dea6-108">When the recipient's RTF-aware client application opens the message to display the text, it must synchronize the text with the formatting and open either **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) or **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)), depending on which property is available.</span></span>
  
 <span data-ttu-id="2dea6-109">**打开邮件、支持 RTF 的客户端**</span><span class="sxs-lookup"><span data-stu-id="2dea6-109">**To open a message, RTF-aware clients**</span></span>
  
1. <span data-ttu-id="2dea6-110">如果邮件存储区不支持 RTF, 则调用**RTFSync**以将邮件文本与格式同步。</span><span class="sxs-lookup"><span data-stu-id="2dea6-110">Call **RTFSync** to synchronize the message text with the formatting if the message store is not RTF-aware.</span></span> <span data-ttu-id="2dea6-111">如果**PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) 属性缺失或设置为 FALSE, 则应在_ulFlags_参数中传递 RTF_SYNC_BODY_CHANGED 标志。</span><span class="sxs-lookup"><span data-stu-id="2dea6-111">The RTF_SYNC_BODY_CHANGED flag should be passed in the  _ulFlags_ parameter if the **PR_RTF_IN_SYNC** ([PidTagRtfInSync](pidtagrtfinsync-canonical-property.md)) property is missing or set to FALSE.</span></span> <span data-ttu-id="2dea6-112">处理 RTF 格式的邮件存储区的客户端无需进行**RTFSync**调用, 因为邮件存储负责处理它。</span><span class="sxs-lookup"><span data-stu-id="2dea6-112">Clients working with RTF-aware message stores need not make the **RTFSync** call because the message store takes care of it.</span></span> 
    
2. <span data-ttu-id="2dea6-113">如果邮件文本已更新, 则调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md) 。</span><span class="sxs-lookup"><span data-stu-id="2dea6-113">Call [IMAPIProp::SaveChanges](imapiprop-savechanges.md) if the message text has been updated.</span></span> 
    
3. <span data-ttu-id="2dea6-114">调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)以打开**PR_RTF_COMPRESSED**属性。</span><span class="sxs-lookup"><span data-stu-id="2dea6-114">Call [IMAPIProp::OpenProperty](imapiprop-openproperty.md) to open the **PR_RTF_COMPRESSED** property.</span></span> <span data-ttu-id="2dea6-115">如果**PR_RTF_COMPRESSED**不可用, 则应改为打开**PR_BODY**属性以显示邮件内容。</span><span class="sxs-lookup"><span data-stu-id="2dea6-115">If **PR_RTF_COMPRESSED** is not available, you should open the **PR_BODY** property instead to display the message content.</span></span> 
    
4. <span data-ttu-id="2dea6-116">调用[WrapCompressedRTFStream](wrapcompressedrtfstream.md)函数以创建压缩的 RTF 数据的未压缩版本 (如果可用)。</span><span class="sxs-lookup"><span data-stu-id="2dea6-116">Call the [WrapCompressedRTFStream](wrapcompressedrtfstream.md) function to create an uncompressed version of the compressed RTF data, if available.</span></span> 
    
5. <span data-ttu-id="2dea6-117">向用户显示未压缩的 RTF 数据或纯文本数据。</span><span class="sxs-lookup"><span data-stu-id="2dea6-117">Display the uncompressed RTF data or the plain text data to the user.</span></span>
    
 <span data-ttu-id="2dea6-118">**RTFSync**返回一个布尔值, 该值指示是否已更新邮件。</span><span class="sxs-lookup"><span data-stu-id="2dea6-118">**RTFSync** returns a Boolean value that indicates whether or not the message has been updated.</span></span> <span data-ttu-id="2dea6-119">如果此值返回 TRUE, 则在某个时刻调用**SaveChanges**以使更新成为永久更新。</span><span class="sxs-lookup"><span data-stu-id="2dea6-119">If this value returns TRUE, call **SaveChanges** at some point to make the update permanent.</span></span> <span data-ttu-id="2dea6-120">不需要在**RTFSync**返回后立即执行该调用。</span><span class="sxs-lookup"><span data-stu-id="2dea6-120">The call does not have to be made immediately after **RTFSync** returns.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2dea6-121">由于在您接收到格式化文本之前很多组件会对其进行处理, 因此可能会损坏。</span><span class="sxs-lookup"><span data-stu-id="2dea6-121">Because so many components handle the formatted text before you receive it, there is the possibility of corruption.</span></span> <span data-ttu-id="2dea6-122">此损坏可能来自邮件存储提供程序、第三方应用程序、网关或传输错误。</span><span class="sxs-lookup"><span data-stu-id="2dea6-122">This corruption could come from the message store provider, a third party application, a gateway, or a transmission error.</span></span> 
  

